A library to be used within Swap.sol. Contains functions responsible for custody and AMM functionalities.

Contracts relying on this library must initialize SwapUtils.Swap struct then use this library
for SwapUtils.Swap struct. Note that this library contains both functions called by users and admins.
Admin functions should be protected within contracts using this library.

# Functions:

- [`getDepositTimestamp(struct SwapUtilsV1.Swap self, address user)`](#SwapUtilsV1-getDepositTimestamp-struct-SwapUtilsV1-Swap-address-)
- [`calculateWithdrawOneToken(struct SwapUtilsV1.Swap self, address account, uint256 tokenAmount, uint8 tokenIndex)`](#SwapUtilsV1-calculateWithdrawOneToken-struct-SwapUtilsV1-Swap-address-uint256-uint8-)
- [`getVirtualPrice(struct SwapUtilsV1.Swap self)`](#SwapUtilsV1-getVirtualPrice-struct-SwapUtilsV1-Swap-)
- [`calculateSwap(struct SwapUtilsV1.Swap self, uint8 tokenIndexFrom, uint8 tokenIndexTo, uint256 dx)`](#SwapUtilsV1-calculateSwap-struct-SwapUtilsV1-Swap-uint8-uint8-uint256-)
- [`calculateRemoveLiquidity(struct SwapUtilsV1.Swap self, address account, uint256 amount)`](#SwapUtilsV1-calculateRemoveLiquidity-struct-SwapUtilsV1-Swap-address-uint256-)
- [`calculateCurrentWithdrawFee(struct SwapUtilsV1.Swap self, address user)`](#SwapUtilsV1-calculateCurrentWithdrawFee-struct-SwapUtilsV1-Swap-address-)
- [`calculateTokenAmount(struct SwapUtilsV1.Swap self, address account, uint256[] amounts, bool deposit)`](#SwapUtilsV1-calculateTokenAmount-struct-SwapUtilsV1-Swap-address-uint256---bool-)
- [`getAdminBalance(struct SwapUtilsV1.Swap self, uint256 index)`](#SwapUtilsV1-getAdminBalance-struct-SwapUtilsV1-Swap-uint256-)
- [`swap(struct SwapUtilsV1.Swap self, uint8 tokenIndexFrom, uint8 tokenIndexTo, uint256 dx, uint256 minDy)`](#SwapUtilsV1-swap-struct-SwapUtilsV1-Swap-uint8-uint8-uint256-uint256-)
- [`addLiquidity(struct SwapUtilsV1.Swap self, uint256[] amounts, uint256 minToMint)`](#SwapUtilsV1-addLiquidity-struct-SwapUtilsV1-Swap-uint256---uint256-)
- [`updateUserWithdrawFee(struct SwapUtilsV1.Swap self, address user, uint256 toMint)`](#SwapUtilsV1-updateUserWithdrawFee-struct-SwapUtilsV1-Swap-address-uint256-)
- [`removeLiquidity(struct SwapUtilsV1.Swap self, uint256 amount, uint256[] minAmounts)`](#SwapUtilsV1-removeLiquidity-struct-SwapUtilsV1-Swap-uint256-uint256---)
- [`removeLiquidityOneToken(struct SwapUtilsV1.Swap self, uint256 tokenAmount, uint8 tokenIndex, uint256 minAmount)`](#SwapUtilsV1-removeLiquidityOneToken-struct-SwapUtilsV1-Swap-uint256-uint8-uint256-)
- [`removeLiquidityImbalance(struct SwapUtilsV1.Swap self, uint256[] amounts, uint256 maxBurnAmount)`](#SwapUtilsV1-removeLiquidityImbalance-struct-SwapUtilsV1-Swap-uint256---uint256-)
- [`withdrawAdminFees(struct SwapUtilsV1.Swap self, address to)`](#SwapUtilsV1-withdrawAdminFees-struct-SwapUtilsV1-Swap-address-)
- [`setAdminFee(struct SwapUtilsV1.Swap self, uint256 newAdminFee)`](#SwapUtilsV1-setAdminFee-struct-SwapUtilsV1-Swap-uint256-)
- [`setSwapFee(struct SwapUtilsV1.Swap self, uint256 newSwapFee)`](#SwapUtilsV1-setSwapFee-struct-SwapUtilsV1-Swap-uint256-)
- [`setDefaultWithdrawFee(struct SwapUtilsV1.Swap self, uint256 newWithdrawFee)`](#SwapUtilsV1-setDefaultWithdrawFee-struct-SwapUtilsV1-Swap-uint256-)

# Events:

- [`TokenSwap(address buyer, uint256 tokensSold, uint256 tokensBought, uint128 soldId, uint128 boughtId)`](#SwapUtilsV1-TokenSwap-address-uint256-uint256-uint128-uint128-)
- [`AddLiquidity(address provider, uint256[] tokenAmounts, uint256[] fees, uint256 invariant, uint256 lpTokenSupply)`](#SwapUtilsV1-AddLiquidity-address-uint256---uint256---uint256-uint256-)
- [`RemoveLiquidity(address provider, uint256[] tokenAmounts, uint256 lpTokenSupply)`](#SwapUtilsV1-RemoveLiquidity-address-uint256---uint256-)
- [`RemoveLiquidityOne(address provider, uint256 lpTokenAmount, uint256 lpTokenSupply, uint256 boughtId, uint256 tokensBought)`](#SwapUtilsV1-RemoveLiquidityOne-address-uint256-uint256-uint256-uint256-)
- [`RemoveLiquidityImbalance(address provider, uint256[] tokenAmounts, uint256[] fees, uint256 invariant, uint256 lpTokenSupply)`](#SwapUtilsV1-RemoveLiquidityImbalance-address-uint256---uint256---uint256-uint256-)
- [`NewAdminFee(uint256 newAdminFee)`](#SwapUtilsV1-NewAdminFee-uint256-)
- [`NewSwapFee(uint256 newSwapFee)`](#SwapUtilsV1-NewSwapFee-uint256-)
- [`NewWithdrawFee(uint256 newWithdrawFee)`](#SwapUtilsV1-NewWithdrawFee-uint256-)

# Function `getDepositTimestamp(struct SwapUtilsV1.Swap self, address user) → uint256` {#SwapUtilsV1-getDepositTimestamp-struct-SwapUtilsV1-Swap-address-}

Retrieves the timestamp of last deposit made by the given address

## Parameters:

- `self`: Swap struct to read from

## Return Values:

- timestamp of last deposit

# Function `calculateWithdrawOneToken(struct SwapUtilsV1.Swap self, address account, uint256 tokenAmount, uint8 tokenIndex) → uint256` {#SwapUtilsV1-calculateWithdrawOneToken-struct-SwapUtilsV1-Swap-address-uint256-uint8-}

Calculate the dy, the amount of selected token that user receives and
the fee of withdrawing in one token

## Parameters:

- `account`: the address that is withdrawing

- `tokenAmount`: the amount to withdraw in the pool's precision

- `tokenIndex`: which token will be withdrawn

- `self`: Swap struct to read from

## Return Values:

- the amount of token user will receive

# Function `getVirtualPrice(struct SwapUtilsV1.Swap self) → uint256` {#SwapUtilsV1-getVirtualPrice-struct-SwapUtilsV1-Swap-}

Get the virtual price, to help calculate profit

## Parameters:

- `self`: Swap struct to read from

## Return Values:

- the virtual price, scaled to precision of POOL_PRECISION_DECIMALS

# Function `calculateSwap(struct SwapUtilsV1.Swap self, uint8 tokenIndexFrom, uint8 tokenIndexTo, uint256 dx) → uint256 dy` {#SwapUtilsV1-calculateSwap-struct-SwapUtilsV1-Swap-uint8-uint8-uint256-}

Externally calculates a swap between two tokens.

## Parameters:

- `self`: Swap struct to read from

- `tokenIndexFrom`: the token to sell

- `tokenIndexTo`: the token to buy

- `dx`: the number of tokens to sell. If the token charges a fee on transfers,
  use the amount that gets transferred after the fee.

## Return Values:

- dy the number of tokens the user will get

# Function `calculateRemoveLiquidity(struct SwapUtilsV1.Swap self, address account, uint256 amount) → uint256[]` {#SwapUtilsV1-calculateRemoveLiquidity-struct-SwapUtilsV1-Swap-address-uint256-}

A simple method to calculate amount of each underlying
tokens that is returned upon burning given amount of
LP tokens

## Parameters:

- `account`: the address that is removing liquidity. required for withdraw fee calculation

- `amount`: the amount of LP tokens that would to be burned on
  withdrawal

## Return Values:

- array of amounts of tokens user will receive

# Function `calculateCurrentWithdrawFee(struct SwapUtilsV1.Swap self, address user) → uint256` {#SwapUtilsV1-calculateCurrentWithdrawFee-struct-SwapUtilsV1-Swap-address-}

Calculate the fee that is applied when the given user withdraws.
Withdraw fee decays linearly over WITHDRAW_FEE_DECAY_TIME.

## Parameters:

- `user`: address you want to calculate withdraw fee of

## Return Values:

- current withdraw fee of the user

# Function `calculateTokenAmount(struct SwapUtilsV1.Swap self, address account, uint256[] amounts, bool deposit) → uint256` {#SwapUtilsV1-calculateTokenAmount-struct-SwapUtilsV1-Swap-address-uint256---bool-}

A simple method to calculate prices from deposits or
withdrawals, excluding fees but including slippage. This is
helpful as an input into the various "min" parameters on calls
to fight front-running

This shouldn't be used outside frontends for user estimates.

## Parameters:

- `self`: Swap struct to read from

- `account`: address of the account depositing or withdrawing tokens

- `amounts`: an array of token amounts to deposit or withdrawal,
  corresponding to pooledTokens. The amount should be in each
  pooled token's native precision. If a token charges a fee on transfers,
  use the amount that gets transferred after the fee.

- `deposit`: whether this is a deposit or a withdrawal

## Return Values:

- if deposit was true, total amount of lp token that will be minted and if
  deposit was false, total amount of lp token that will be burned

# Function `getAdminBalance(struct SwapUtilsV1.Swap self, uint256 index) → uint256` {#SwapUtilsV1-getAdminBalance-struct-SwapUtilsV1-Swap-uint256-}

return accumulated amount of admin fees of the token with given index

## Parameters:

- `self`: Swap struct to read from

- `index`: Index of the pooled token

## Return Values:

- admin balance in the token's precision

# Function `swap(struct SwapUtilsV1.Swap self, uint8 tokenIndexFrom, uint8 tokenIndexTo, uint256 dx, uint256 minDy) → uint256` {#SwapUtilsV1-swap-struct-SwapUtilsV1-Swap-uint8-uint8-uint256-uint256-}

swap two tokens in the pool

## Parameters:

- `self`: Swap struct to read from and write to

- `tokenIndexFrom`: the token the user wants to sell

- `tokenIndexTo`: the token the user wants to buy

- `dx`: the amount of tokens the user wants to sell

- `minDy`: the min amount the user would like to receive, or revert.

## Return Values:

- amount of token user received on swap

# Function `addLiquidity(struct SwapUtilsV1.Swap self, uint256[] amounts, uint256 minToMint) → uint256` {#SwapUtilsV1-addLiquidity-struct-SwapUtilsV1-Swap-uint256---uint256-}

Add liquidity to the pool

## Parameters:

- `self`: Swap struct to read from and write to

- `amounts`: the amounts of each token to add, in their native precision

- `minToMint`: the minimum LP tokens adding this amount of liquidity
  should mint, otherwise revert. Handy for front-running mitigation
  allowed addresses. If the pool is not in the guarded launch phase, this parameter will be ignored.

## Return Values:

- amount of LP token user received

# Function `updateUserWithdrawFee(struct SwapUtilsV1.Swap self, address user, uint256 toMint)` {#SwapUtilsV1-updateUserWithdrawFee-struct-SwapUtilsV1-Swap-address-uint256-}

Update the withdraw fee for `user`. If the user is currently
not providing liquidity in the pool, sets to default value. If not, recalculate
the starting withdraw fee based on the last deposit's time & amount relative
to the new deposit.

## Parameters:

- `self`: Swap struct to read from and write to

- `user`: address of the user depositing tokens

- `toMint`: amount of pool tokens to be minted

# Function `removeLiquidity(struct SwapUtilsV1.Swap self, uint256 amount, uint256[] minAmounts) → uint256[]` {#SwapUtilsV1-removeLiquidity-struct-SwapUtilsV1-Swap-uint256-uint256---}

Burn LP tokens to remove liquidity from the pool.

Liquidity can always be removed, even when the pool is paused.

## Parameters:

- `self`: Swap struct to read from and write to

- `amount`: the amount of LP tokens to burn

- `minAmounts`: the minimum amounts of each token in the pool
  acceptable for this burn. Useful as a front-running mitigation

## Return Values:

- amounts of tokens the user received

# Function `removeLiquidityOneToken(struct SwapUtilsV1.Swap self, uint256 tokenAmount, uint8 tokenIndex, uint256 minAmount) → uint256` {#SwapUtilsV1-removeLiquidityOneToken-struct-SwapUtilsV1-Swap-uint256-uint8-uint256-}

Remove liquidity from the pool all in one token.

## Parameters:

- `self`: Swap struct to read from and write to

- `tokenAmount`: the amount of the lp tokens to burn

- `tokenIndex`: the index of the token you want to receive

- `minAmount`: the minimum amount to withdraw, otherwise revert

## Return Values:

- amount chosen token that user received

# Function `removeLiquidityImbalance(struct SwapUtilsV1.Swap self, uint256[] amounts, uint256 maxBurnAmount) → uint256` {#SwapUtilsV1-removeLiquidityImbalance-struct-SwapUtilsV1-Swap-uint256---uint256-}

Remove liquidity from the pool, weighted differently than the
pool's current balances.

## Parameters:

- `self`: Swap struct to read from and write to

- `amounts`: how much of each token to withdraw

- `maxBurnAmount`: the max LP token provider is willing to pay to
  remove liquidity. Useful as a front-running mitigation.

## Return Values:

- actual amount of LP tokens burned in the withdrawal

# Function `withdrawAdminFees(struct SwapUtilsV1.Swap self, address to)` {#SwapUtilsV1-withdrawAdminFees-struct-SwapUtilsV1-Swap-address-}

withdraw all admin fees to a given address

## Parameters:

- `self`: Swap struct to withdraw fees from

- `to`: Address to send the fees to

# Function `setAdminFee(struct SwapUtilsV1.Swap self, uint256 newAdminFee)` {#SwapUtilsV1-setAdminFee-struct-SwapUtilsV1-Swap-uint256-}

Sets the admin fee

adminFee cannot be higher than 100% of the swap fee

## Parameters:

- `self`: Swap struct to update

- `newAdminFee`: new admin fee to be applied on future transactions

# Function `setSwapFee(struct SwapUtilsV1.Swap self, uint256 newSwapFee)` {#SwapUtilsV1-setSwapFee-struct-SwapUtilsV1-Swap-uint256-}

update the swap fee

fee cannot be higher than 1% of each swap

## Parameters:

- `self`: Swap struct to update

- `newSwapFee`: new swap fee to be applied on future transactions

# Function `setDefaultWithdrawFee(struct SwapUtilsV1.Swap self, uint256 newWithdrawFee)` {#SwapUtilsV1-setDefaultWithdrawFee-struct-SwapUtilsV1-Swap-uint256-}

update the default withdraw fee. This also affects deposits made in the past as well.

## Parameters:

- `self`: Swap struct to update

- `newWithdrawFee`: new withdraw fee to be applied

# Event `TokenSwap(address buyer, uint256 tokensSold, uint256 tokensBought, uint128 soldId, uint128 boughtId)` {#SwapUtilsV1-TokenSwap-address-uint256-uint256-uint128-uint128-}

No description

# Event `AddLiquidity(address provider, uint256[] tokenAmounts, uint256[] fees, uint256 invariant, uint256 lpTokenSupply)` {#SwapUtilsV1-AddLiquidity-address-uint256---uint256---uint256-uint256-}

No description

# Event `RemoveLiquidity(address provider, uint256[] tokenAmounts, uint256 lpTokenSupply)` {#SwapUtilsV1-RemoveLiquidity-address-uint256---uint256-}

No description

# Event `RemoveLiquidityOne(address provider, uint256 lpTokenAmount, uint256 lpTokenSupply, uint256 boughtId, uint256 tokensBought)` {#SwapUtilsV1-RemoveLiquidityOne-address-uint256-uint256-uint256-uint256-}

No description

# Event `RemoveLiquidityImbalance(address provider, uint256[] tokenAmounts, uint256[] fees, uint256 invariant, uint256 lpTokenSupply)` {#SwapUtilsV1-RemoveLiquidityImbalance-address-uint256---uint256---uint256-uint256-}

No description

# Event `NewAdminFee(uint256 newAdminFee)` {#SwapUtilsV1-NewAdminFee-uint256-}

No description

# Event `NewSwapFee(uint256 newSwapFee)` {#SwapUtilsV1-NewSwapFee-uint256-}

No description

# Event `NewWithdrawFee(uint256 newWithdrawFee)` {#SwapUtilsV1-NewWithdrawFee-uint256-}

No description
