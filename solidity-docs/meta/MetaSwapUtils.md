A library to be used within MetaSwap.sol. Contains functions responsible for custody and AMM functionalities.

MetaSwap is a modified version of Swap that allows Swap's LP token to be utilized in pooling with other tokens.
As an example, if there is a Swap pool consisting of [DAI, USDC, USDT]. Then a MetaSwap pool can be created
with [sUSD, BaseSwapLPToken] to allow trades between either the LP token or the underlying tokens and sUSD.

Contracts relying on this library must initialize SwapUtils.Swap struct then use this library
for SwapUtils.Swap struct. Note that this library contains both functions called by users and admins.
Admin functions should be protected within contracts using this library.

# Functions:

- [`calculateWithdrawOneToken(struct SwapUtils.Swap self, struct MetaSwapUtils.MetaSwap metaSwapStorage, uint256 tokenAmount, uint8 tokenIndex)`](#MetaSwapUtils-calculateWithdrawOneToken-struct-SwapUtils-Swap-struct-MetaSwapUtils-MetaSwap-uint256-uint8-)
- [`getVirtualPrice(struct SwapUtils.Swap self, struct MetaSwapUtils.MetaSwap metaSwapStorage)`](#MetaSwapUtils-getVirtualPrice-struct-SwapUtils-Swap-struct-MetaSwapUtils-MetaSwap-)
- [`calculateSwap(struct SwapUtils.Swap self, struct MetaSwapUtils.MetaSwap metaSwapStorage, uint8 tokenIndexFrom, uint8 tokenIndexTo, uint256 dx)`](#MetaSwapUtils-calculateSwap-struct-SwapUtils-Swap-struct-MetaSwapUtils-MetaSwap-uint8-uint8-uint256-)
- [`calculateSwapUnderlying(struct SwapUtils.Swap self, struct MetaSwapUtils.MetaSwap metaSwapStorage, uint8 tokenIndexFrom, uint8 tokenIndexTo, uint256 dx)`](#MetaSwapUtils-calculateSwapUnderlying-struct-SwapUtils-Swap-struct-MetaSwapUtils-MetaSwap-uint8-uint8-uint256-)
- [`calculateTokenAmount(struct SwapUtils.Swap self, struct MetaSwapUtils.MetaSwap metaSwapStorage, uint256[] amounts, bool deposit)`](#MetaSwapUtils-calculateTokenAmount-struct-SwapUtils-Swap-struct-MetaSwapUtils-MetaSwap-uint256---bool-)
- [`swap(struct SwapUtils.Swap self, struct MetaSwapUtils.MetaSwap metaSwapStorage, uint8 tokenIndexFrom, uint8 tokenIndexTo, uint256 dx, uint256 minDy)`](#MetaSwapUtils-swap-struct-SwapUtils-Swap-struct-MetaSwapUtils-MetaSwap-uint8-uint8-uint256-uint256-)
- [`swapUnderlying(struct SwapUtils.Swap self, struct MetaSwapUtils.MetaSwap metaSwapStorage, uint8 tokenIndexFrom, uint8 tokenIndexTo, uint256 dx, uint256 minDy)`](#MetaSwapUtils-swapUnderlying-struct-SwapUtils-Swap-struct-MetaSwapUtils-MetaSwap-uint8-uint8-uint256-uint256-)
- [`addLiquidity(struct SwapUtils.Swap self, struct MetaSwapUtils.MetaSwap metaSwapStorage, uint256[] amounts, uint256 minToMint)`](#MetaSwapUtils-addLiquidity-struct-SwapUtils-Swap-struct-MetaSwapUtils-MetaSwap-uint256---uint256-)
- [`removeLiquidityOneToken(struct SwapUtils.Swap self, struct MetaSwapUtils.MetaSwap metaSwapStorage, uint256 tokenAmount, uint8 tokenIndex, uint256 minAmount)`](#MetaSwapUtils-removeLiquidityOneToken-struct-SwapUtils-Swap-struct-MetaSwapUtils-MetaSwap-uint256-uint8-uint256-)
- [`removeLiquidityImbalance(struct SwapUtils.Swap self, struct MetaSwapUtils.MetaSwap metaSwapStorage, uint256[] amounts, uint256 maxBurnAmount)`](#MetaSwapUtils-removeLiquidityImbalance-struct-SwapUtils-Swap-struct-MetaSwapUtils-MetaSwap-uint256---uint256-)

# Events:

- [`TokenSwap(address buyer, uint256 tokensSold, uint256 tokensBought, uint128 soldId, uint128 boughtId)`](#MetaSwapUtils-TokenSwap-address-uint256-uint256-uint128-uint128-)
- [`TokenSwapUnderlying(address buyer, uint256 tokensSold, uint256 tokensBought, uint128 soldId, uint128 boughtId)`](#MetaSwapUtils-TokenSwapUnderlying-address-uint256-uint256-uint128-uint128-)
- [`AddLiquidity(address provider, uint256[] tokenAmounts, uint256[] fees, uint256 invariant, uint256 lpTokenSupply)`](#MetaSwapUtils-AddLiquidity-address-uint256---uint256---uint256-uint256-)
- [`RemoveLiquidityOne(address provider, uint256 lpTokenAmount, uint256 lpTokenSupply, uint256 boughtId, uint256 tokensBought)`](#MetaSwapUtils-RemoveLiquidityOne-address-uint256-uint256-uint256-uint256-)
- [`RemoveLiquidityImbalance(address provider, uint256[] tokenAmounts, uint256[] fees, uint256 invariant, uint256 lpTokenSupply)`](#MetaSwapUtils-RemoveLiquidityImbalance-address-uint256---uint256---uint256-uint256-)
- [`NewAdminFee(uint256 newAdminFee)`](#MetaSwapUtils-NewAdminFee-uint256-)
- [`NewSwapFee(uint256 newSwapFee)`](#MetaSwapUtils-NewSwapFee-uint256-)
- [`NewWithdrawFee(uint256 newWithdrawFee)`](#MetaSwapUtils-NewWithdrawFee-uint256-)

# Function `calculateWithdrawOneToken(struct SwapUtils.Swap self, struct MetaSwapUtils.MetaSwap metaSwapStorage, uint256 tokenAmount, uint8 tokenIndex) → uint256 dy` {#MetaSwapUtils-calculateWithdrawOneToken-struct-SwapUtils-Swap-struct-MetaSwapUtils-MetaSwap-uint256-uint8-}

Calculate how much the user would receive when withdrawing via single token

## Parameters:

- `self`: Swap struct to read from

- `metaSwapStorage`: MetaSwap struct to read from

- `tokenAmount`: the amount to withdraw in the pool's precision

- `tokenIndex`: which token will be withdrawn

## Return Values:

- dy the amount of token user will receive

# Function `getVirtualPrice(struct SwapUtils.Swap self, struct MetaSwapUtils.MetaSwap metaSwapStorage) → uint256` {#MetaSwapUtils-getVirtualPrice-struct-SwapUtils-Swap-struct-MetaSwapUtils-MetaSwap-}

Get the virtual price, to help calculate profit

## Parameters:

- `self`: Swap struct to read from

- `metaSwapStorage`: MetaSwap struct to read from

## Return Values:

- the virtual price, scaled to precision of BASE_VIRTUAL_PRICE_PRECISION

# Function `calculateSwap(struct SwapUtils.Swap self, struct MetaSwapUtils.MetaSwap metaSwapStorage, uint8 tokenIndexFrom, uint8 tokenIndexTo, uint256 dx) → uint256 dy` {#MetaSwapUtils-calculateSwap-struct-SwapUtils-Swap-struct-MetaSwapUtils-MetaSwap-uint8-uint8-uint256-}

Externally calculates a swap between two tokens. The SwapUtils.Swap storage and
MetaSwap storage should be from the same MetaSwap contract.

## Parameters:

- `self`: Swap struct to read from

- `metaSwapStorage`: MetaSwap struct from the same contract

- `tokenIndexFrom`: the token to sell

- `tokenIndexTo`: the token to buy

- `dx`: the number of tokens to sell. If the token charges a fee on transfers,
  use the amount that gets transferred after the fee.

## Return Values:

- dy the number of tokens the user will get

# Function `calculateSwapUnderlying(struct SwapUtils.Swap self, struct MetaSwapUtils.MetaSwap metaSwapStorage, uint8 tokenIndexFrom, uint8 tokenIndexTo, uint256 dx) → uint256` {#MetaSwapUtils-calculateSwapUnderlying-struct-SwapUtils-Swap-struct-MetaSwapUtils-MetaSwap-uint8-uint8-uint256-}

Calculates the expected return amount from swapping between
the pooled tokens and the underlying tokens of the base Swap pool.

## Parameters:

- `self`: Swap struct to read from

- `metaSwapStorage`: MetaSwap struct from the same contract

- `tokenIndexFrom`: the token to sell

- `tokenIndexTo`: the token to buy

- `dx`: the number of tokens to sell. If the token charges a fee on transfers,
  use the amount that gets transferred after the fee.

## Return Values:

- dy the number of tokens the user will get

# Function `calculateTokenAmount(struct SwapUtils.Swap self, struct MetaSwapUtils.MetaSwap metaSwapStorage, uint256[] amounts, bool deposit) → uint256` {#MetaSwapUtils-calculateTokenAmount-struct-SwapUtils-Swap-struct-MetaSwapUtils-MetaSwap-uint256---bool-}

A simple method to calculate prices from deposits or
withdrawals, excluding fees but including slippage. This is
helpful as an input into the various "min" parameters on calls
to fight front-running

This shouldn't be used outside frontends for user estimates.

## Parameters:

- `self`: Swap struct to read from

- `metaSwapStorage`: MetaSwap struct to read from

- `amounts`: an array of token amounts to deposit or withdrawal,
  corresponding to pooledTokens. The amount should be in each
  pooled token's native precision. If a token charges a fee on transfers,
  use the amount that gets transferred after the fee.

- `deposit`: whether this is a deposit or a withdrawal

## Return Values:

- if deposit was true, total amount of lp token that will be minted and if
  deposit was false, total amount of lp token that will be burned

# Function `swap(struct SwapUtils.Swap self, struct MetaSwapUtils.MetaSwap metaSwapStorage, uint8 tokenIndexFrom, uint8 tokenIndexTo, uint256 dx, uint256 minDy) → uint256` {#MetaSwapUtils-swap-struct-SwapUtils-Swap-struct-MetaSwapUtils-MetaSwap-uint8-uint8-uint256-uint256-}

swap two tokens in the pool

## Parameters:

- `self`: Swap struct to read from and write to

- `metaSwapStorage`: MetaSwap struct to read from and write to

- `tokenIndexFrom`: the token the user wants to sell

- `tokenIndexTo`: the token the user wants to buy

- `dx`: the amount of tokens the user wants to sell

- `minDy`: the min amount the user would like to receive, or revert.

## Return Values:

- amount of token user received on swap

# Function `swapUnderlying(struct SwapUtils.Swap self, struct MetaSwapUtils.MetaSwap metaSwapStorage, uint8 tokenIndexFrom, uint8 tokenIndexTo, uint256 dx, uint256 minDy) → uint256` {#MetaSwapUtils-swapUnderlying-struct-SwapUtils-Swap-struct-MetaSwapUtils-MetaSwap-uint8-uint8-uint256-uint256-}

Swaps with the underlying tokens of the base Swap pool. For this function,
the token indices are flattened out so that underlying tokens are represented
in the indices.

Since this calls multiple external functions during the execution,
it is recommended to protect any function that depends on this with reentrancy guards.

## Parameters:

- `self`: Swap struct to read from and write to

- `metaSwapStorage`: MetaSwap struct to read from and write to

- `tokenIndexFrom`: the token the user wants to sell

- `tokenIndexTo`: the token the user wants to buy

- `dx`: the amount of tokens the user wants to sell

- `minDy`: the min amount the user would like to receive, or revert.

## Return Values:

- amount of token user received on swap

# Function `addLiquidity(struct SwapUtils.Swap self, struct MetaSwapUtils.MetaSwap metaSwapStorage, uint256[] amounts, uint256 minToMint) → uint256` {#MetaSwapUtils-addLiquidity-struct-SwapUtils-Swap-struct-MetaSwapUtils-MetaSwap-uint256---uint256-}

Add liquidity to the pool

## Parameters:

- `self`: Swap struct to read from and write to

- `metaSwapStorage`: MetaSwap struct to read from and write to

- `amounts`: the amounts of each token to add, in their native precision

- `minToMint`: the minimum LP tokens adding this amount of liquidity
  should mint, otherwise revert. Handy for front-running mitigation
  allowed addresses. If the pool is not in the guarded launch phase, this parameter will be ignored.

## Return Values:

- amount of LP token user received

# Function `removeLiquidityOneToken(struct SwapUtils.Swap self, struct MetaSwapUtils.MetaSwap metaSwapStorage, uint256 tokenAmount, uint8 tokenIndex, uint256 minAmount) → uint256` {#MetaSwapUtils-removeLiquidityOneToken-struct-SwapUtils-Swap-struct-MetaSwapUtils-MetaSwap-uint256-uint8-uint256-}

Remove liquidity from the pool all in one token.

## Parameters:

- `self`: Swap struct to read from and write to

- `metaSwapStorage`: MetaSwap struct to read from and write to

- `tokenAmount`: the amount of the lp tokens to burn

- `tokenIndex`: the index of the token you want to receive

- `minAmount`: the minimum amount to withdraw, otherwise revert

## Return Values:

- amount chosen token that user received

# Function `removeLiquidityImbalance(struct SwapUtils.Swap self, struct MetaSwapUtils.MetaSwap metaSwapStorage, uint256[] amounts, uint256 maxBurnAmount) → uint256` {#MetaSwapUtils-removeLiquidityImbalance-struct-SwapUtils-Swap-struct-MetaSwapUtils-MetaSwap-uint256---uint256-}

Remove liquidity from the pool, weighted differently than the
pool's current balances.

## Parameters:

- `self`: Swap struct to read from and write to

- `metaSwapStorage`: MetaSwap struct to read from and write to

- `amounts`: how much of each token to withdraw

- `maxBurnAmount`: the max LP token provider is willing to pay to
  remove liquidity. Useful as a front-running mitigation.

## Return Values:

- actual amount of LP tokens burned in the withdrawal

# Event `TokenSwap(address buyer, uint256 tokensSold, uint256 tokensBought, uint128 soldId, uint128 boughtId)` {#MetaSwapUtils-TokenSwap-address-uint256-uint256-uint128-uint128-}

No description

# Event `TokenSwapUnderlying(address buyer, uint256 tokensSold, uint256 tokensBought, uint128 soldId, uint128 boughtId)` {#MetaSwapUtils-TokenSwapUnderlying-address-uint256-uint256-uint128-uint128-}

No description

# Event `AddLiquidity(address provider, uint256[] tokenAmounts, uint256[] fees, uint256 invariant, uint256 lpTokenSupply)` {#MetaSwapUtils-AddLiquidity-address-uint256---uint256---uint256-uint256-}

No description

# Event `RemoveLiquidityOne(address provider, uint256 lpTokenAmount, uint256 lpTokenSupply, uint256 boughtId, uint256 tokensBought)` {#MetaSwapUtils-RemoveLiquidityOne-address-uint256-uint256-uint256-uint256-}

No description

# Event `RemoveLiquidityImbalance(address provider, uint256[] tokenAmounts, uint256[] fees, uint256 invariant, uint256 lpTokenSupply)` {#MetaSwapUtils-RemoveLiquidityImbalance-address-uint256---uint256---uint256-uint256-}

No description

# Event `NewAdminFee(uint256 newAdminFee)` {#MetaSwapUtils-NewAdminFee-uint256-}

No description

# Event `NewSwapFee(uint256 newSwapFee)` {#MetaSwapUtils-NewSwapFee-uint256-}

No description

# Event `NewWithdrawFee(uint256 newWithdrawFee)` {#MetaSwapUtils-NewWithdrawFee-uint256-}

No description
