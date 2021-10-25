This contract is responsible for custody of closely pegged assets (eg. group of stablecoins)
and automatic market making system. Users become an LP (Liquidity Provider) by depositing their tokens
in desired ratios for an exchange of the pool token that represents their share of the pool.
Users can burn pool tokens and withdraw their share of token(s).

Each time a swap between the pooled tokens happens, a set fee incurs which effectively gets
distributed to the LPs.

In case of emergencies, admin can pause additional deposits, swaps, or single-asset withdraws - which
stops the ratio of the tokens in the pool from changing.
Users can always withdraw their tokens via multi-asset withdraws.

Most of the logic is stored as a library `SwapUtils` for the sake of reducing contract's
deployment size.

# Functions:

- [`initialize(contract IERC20[] _pooledTokens, uint8[] decimals, string lpTokenName, string lpTokenSymbol, uint256 _a, uint256 _fee, uint256 _adminFee, address lpTokenTargetAddress)`](#Swap-initialize-contract-IERC20---uint8---string-string-uint256-uint256-uint256-address-)
- [`getA()`](#Swap-getA--)
- [`getAPrecise()`](#Swap-getAPrecise--)
- [`getToken(uint8 index)`](#Swap-getToken-uint8-)
- [`getTokenIndex(address tokenAddress)`](#Swap-getTokenIndex-address-)
- [`getTokenBalance(uint8 index)`](#Swap-getTokenBalance-uint8-)
- [`getVirtualPrice()`](#Swap-getVirtualPrice--)
- [`calculateSwap(uint8 tokenIndexFrom, uint8 tokenIndexTo, uint256 dx)`](#Swap-calculateSwap-uint8-uint8-uint256-)
- [`calculateTokenAmount(uint256[] amounts, bool deposit)`](#Swap-calculateTokenAmount-uint256---bool-)
- [`calculateRemoveLiquidity(uint256 amount)`](#Swap-calculateRemoveLiquidity-uint256-)
- [`calculateRemoveLiquidityOneToken(uint256 tokenAmount, uint8 tokenIndex)`](#Swap-calculateRemoveLiquidityOneToken-uint256-uint8-)
- [`getAdminBalance(uint256 index)`](#Swap-getAdminBalance-uint256-)
- [`swap(uint8 tokenIndexFrom, uint8 tokenIndexTo, uint256 dx, uint256 minDy, uint256 deadline)`](#Swap-swap-uint8-uint8-uint256-uint256-uint256-)
- [`addLiquidity(uint256[] amounts, uint256 minToMint, uint256 deadline)`](#Swap-addLiquidity-uint256---uint256-uint256-)
- [`removeLiquidity(uint256 amount, uint256[] minAmounts, uint256 deadline)`](#Swap-removeLiquidity-uint256-uint256---uint256-)
- [`removeLiquidityOneToken(uint256 tokenAmount, uint8 tokenIndex, uint256 minAmount, uint256 deadline)`](#Swap-removeLiquidityOneToken-uint256-uint8-uint256-uint256-)
- [`removeLiquidityImbalance(uint256[] amounts, uint256 maxBurnAmount, uint256 deadline)`](#Swap-removeLiquidityImbalance-uint256---uint256-uint256-)
- [`withdrawAdminFees()`](#Swap-withdrawAdminFees--)
- [`setAdminFee(uint256 newAdminFee)`](#Swap-setAdminFee-uint256-)
- [`setSwapFee(uint256 newSwapFee)`](#Swap-setSwapFee-uint256-)
- [`rampA(uint256 futureA, uint256 futureTime)`](#Swap-rampA-uint256-uint256-)
- [`stopRampA()`](#Swap-stopRampA--)

# Events:

- [`TokenSwap(address buyer, uint256 tokensSold, uint256 tokensBought, uint128 soldId, uint128 boughtId)`](#Swap-TokenSwap-address-uint256-uint256-uint128-uint128-)
- [`AddLiquidity(address provider, uint256[] tokenAmounts, uint256[] fees, uint256 invariant, uint256 lpTokenSupply)`](#Swap-AddLiquidity-address-uint256---uint256---uint256-uint256-)
- [`RemoveLiquidity(address provider, uint256[] tokenAmounts, uint256 lpTokenSupply)`](#Swap-RemoveLiquidity-address-uint256---uint256-)
- [`RemoveLiquidityOne(address provider, uint256 lpTokenAmount, uint256 lpTokenSupply, uint256 boughtId, uint256 tokensBought)`](#Swap-RemoveLiquidityOne-address-uint256-uint256-uint256-uint256-)
- [`RemoveLiquidityImbalance(address provider, uint256[] tokenAmounts, uint256[] fees, uint256 invariant, uint256 lpTokenSupply)`](#Swap-RemoveLiquidityImbalance-address-uint256---uint256---uint256-uint256-)
- [`NewAdminFee(uint256 newAdminFee)`](#Swap-NewAdminFee-uint256-)
- [`NewSwapFee(uint256 newSwapFee)`](#Swap-NewSwapFee-uint256-)
- [`NewWithdrawFee(uint256 newWithdrawFee)`](#Swap-NewWithdrawFee-uint256-)
- [`RampA(uint256 oldA, uint256 newA, uint256 initialTime, uint256 futureTime)`](#Swap-RampA-uint256-uint256-uint256-uint256-)
- [`StopRampA(uint256 currentA, uint256 time)`](#Swap-StopRampA-uint256-uint256-)

# Function `initialize(contract IERC20[] _pooledTokens, uint8[] decimals, string lpTokenName, string lpTokenSymbol, uint256 _a, uint256 _fee, uint256 _adminFee, address lpTokenTargetAddress)` {#Swap-initialize-contract-IERC20---uint8---string-string-uint256-uint256-uint256-address-}

Initializes this Swap contract with the given parameters.
This will also clone a LPToken contract that represents users'
LP positions. The owner of LPToken will be this contract - which means
only this contract is allowed to mint/burn tokens.

## Parameters:

- `_pooledTokens`: an array of ERC20s this pool will accept

- `decimals`: the decimals to use for each pooled token,
  eg 8 for WBTC. Cannot be larger than POOL_PRECISION_DECIMALS

- `lpTokenName`: the long-form name of the token to be deployed

- `lpTokenSymbol`: the short symbol for the token to be deployed

- `_a`: the amplification coefficient _ n _ (n - 1). See the
  StableSwap paper for details

- `_fee`: default swap fee to be initialized with

- `_adminFee`: default adminFee to be initialized with

- `lpTokenTargetAddress`: the address of an existing LPToken contract to use as a target

# Function `getA() → uint256` {#Swap-getA--}

Return A, the amplification coefficient _ n _ (n - 1)

See the StableSwap paper for details

## Return Values:

- A parameter

# Function `getAPrecise() → uint256` {#Swap-getAPrecise--}

Return A in its raw precision form

See the StableSwap paper for details

## Return Values:

- A parameter in its raw precision form

# Function `getToken(uint8 index) → contract IERC20` {#Swap-getToken-uint8-}

Return address of the pooled token at given index. Reverts if tokenIndex is out of range.

## Parameters:

- `index`: the index of the token

## Return Values:

- address of the token at given index

# Function `getTokenIndex(address tokenAddress) → uint8` {#Swap-getTokenIndex-address-}

Return the index of the given token address. Reverts if no matching
token is found.

## Parameters:

- `tokenAddress`: address of the token

## Return Values:

- the index of the given token address

# Function `getTokenBalance(uint8 index) → uint256` {#Swap-getTokenBalance-uint8-}

Return current balance of the pooled token at given index

## Parameters:

- `index`: the index of the token

## Return Values:

- current balance of the pooled token at given index with token's native precision

# Function `getVirtualPrice() → uint256` {#Swap-getVirtualPrice--}

Get the virtual price, to help calculate profit

## Return Values:

- the virtual price, scaled to the POOL_PRECISION_DECIMALS

# Function `calculateSwap(uint8 tokenIndexFrom, uint8 tokenIndexTo, uint256 dx) → uint256` {#Swap-calculateSwap-uint8-uint8-uint256-}

Calculate amount of tokens you receive on swap

## Parameters:

- `tokenIndexFrom`: the token the user wants to sell

- `tokenIndexTo`: the token the user wants to buy

- `dx`: the amount of tokens the user wants to sell. If the token charges
  a fee on transfers, use the amount that gets transferred after the fee.

## Return Values:

- amount of tokens the user will receive

# Function `calculateTokenAmount(uint256[] amounts, bool deposit) → uint256` {#Swap-calculateTokenAmount-uint256---bool-}

A simple method to calculate prices from deposits or
withdrawals, excluding fees but including slippage. This is
helpful as an input into the various "min" parameters on calls
to fight front-running

This shouldn't be used outside frontends for user estimates.

## Parameters:

- `amounts`: an array of token amounts to deposit or withdrawal,
  corresponding to pooledTokens. The amount should be in each
  pooled token's native precision. If a token charges a fee on transfers,
  use the amount that gets transferred after the fee.

- `deposit`: whether this is a deposit or a withdrawal

## Return Values:

- token amount the user will receive

# Function `calculateRemoveLiquidity(uint256 amount) → uint256[]` {#Swap-calculateRemoveLiquidity-uint256-}

A simple method to calculate amount of each underlying
tokens that is returned upon burning given amount of LP tokens

## Parameters:

- `amount`: the amount of LP tokens that would be burned on withdrawal

## Return Values:

- array of token balances that the user will receive

# Function `calculateRemoveLiquidityOneToken(uint256 tokenAmount, uint8 tokenIndex) → uint256 availableTokenAmount` {#Swap-calculateRemoveLiquidityOneToken-uint256-uint8-}

Calculate the amount of underlying token available to withdraw
when withdrawing via only single token

## Parameters:

- `tokenAmount`: the amount of LP token to burn

- `tokenIndex`: index of which token will be withdrawn

## Return Values:

- availableTokenAmount calculated amount of underlying token
  available to withdraw

# Function `getAdminBalance(uint256 index) → uint256` {#Swap-getAdminBalance-uint256-}

This function reads the accumulated amount of admin fees of the token with given index

## Parameters:

- `index`: Index of the pooled token

## Return Values:

- s token balance in the token's precision

# Function `swap(uint8 tokenIndexFrom, uint8 tokenIndexTo, uint256 dx, uint256 minDy, uint256 deadline) → uint256` {#Swap-swap-uint8-uint8-uint256-uint256-uint256-}

Swap two tokens using this pool

## Parameters:

- `tokenIndexFrom`: the token the user wants to swap from

- `tokenIndexTo`: the token the user wants to swap to

- `dx`: the amount of tokens the user wants to swap from

- `minDy`: the min amount the user would like to receive, or revert.

- `deadline`: latest timestamp to accept this transaction

# Function `addLiquidity(uint256[] amounts, uint256 minToMint, uint256 deadline) → uint256` {#Swap-addLiquidity-uint256---uint256-uint256-}

Add liquidity to the pool with the given amounts of tokens

## Parameters:

- `amounts`: the amounts of each token to add, in their native precision

- `minToMint`: the minimum LP tokens adding this amount of liquidity
  should mint, otherwise revert. Handy for front-running mitigation

- `deadline`: latest timestamp to accept this transaction

## Return Values:

- amount of LP token user minted and received

# Function `removeLiquidity(uint256 amount, uint256[] minAmounts, uint256 deadline) → uint256[]` {#Swap-removeLiquidity-uint256-uint256---uint256-}

Burn LP tokens to remove liquidity from the pool. Withdraw fee that decays linearly
over period of 4 weeks since last deposit will apply.

Liquidity can always be removed, even when the pool is paused.

## Parameters:

- `amount`: the amount of LP tokens to burn

- `minAmounts`: the minimum amounts of each token in the pool
  acceptable for this burn. Useful as a front-running mitigation

- `deadline`: latest timestamp to accept this transaction

## Return Values:

- amounts of tokens user received

# Function `removeLiquidityOneToken(uint256 tokenAmount, uint8 tokenIndex, uint256 minAmount, uint256 deadline) → uint256` {#Swap-removeLiquidityOneToken-uint256-uint8-uint256-uint256-}

Remove liquidity from the pool all in one token. Withdraw fee that decays linearly
over period of 4 weeks since last deposit will apply.

## Parameters:

- `tokenAmount`: the amount of the token you want to receive

- `tokenIndex`: the index of the token you want to receive

- `minAmount`: the minimum amount to withdraw, otherwise revert

- `deadline`: latest timestamp to accept this transaction

## Return Values:

- amount of chosen token user received

# Function `removeLiquidityImbalance(uint256[] amounts, uint256 maxBurnAmount, uint256 deadline) → uint256` {#Swap-removeLiquidityImbalance-uint256---uint256-uint256-}

Remove liquidity from the pool, weighted differently than the
pool's current balances. Withdraw fee that decays linearly
over period of 4 weeks since last deposit will apply.

## Parameters:

- `amounts`: how much of each token to withdraw

- `maxBurnAmount`: the max LP token provider is willing to pay to
  remove liquidity. Useful as a front-running mitigation.

- `deadline`: latest timestamp to accept this transaction

## Return Values:

- amount of LP tokens burned

# Function `withdrawAdminFees()` {#Swap-withdrawAdminFees--}

Withdraw all admin fees to the contract owner

# Function `setAdminFee(uint256 newAdminFee)` {#Swap-setAdminFee-uint256-}

Update the admin fee. Admin fee takes portion of the swap fee.

## Parameters:

- `newAdminFee`: new admin fee to be applied on future transactions

# Function `setSwapFee(uint256 newSwapFee)` {#Swap-setSwapFee-uint256-}

Update the swap fee to be applied on swaps

## Parameters:

- `newSwapFee`: new swap fee to be applied on future transactions

# Function `rampA(uint256 futureA, uint256 futureTime)` {#Swap-rampA-uint256-uint256-}

Start ramping up or down A parameter towards given futureA and futureTime
Checks if the change is too rapid, and commits the new A value only when it falls under
the limit range.

## Parameters:

- `futureA`: the new A to ramp towards

- `futureTime`: timestamp when the new A should be reached

# Function `stopRampA()` {#Swap-stopRampA--}

Stop ramping A immediately. Reverts if ramp A is already stopped.

# Event `TokenSwap(address buyer, uint256 tokensSold, uint256 tokensBought, uint128 soldId, uint128 boughtId)` {#Swap-TokenSwap-address-uint256-uint256-uint128-uint128-}

No description

# Event `AddLiquidity(address provider, uint256[] tokenAmounts, uint256[] fees, uint256 invariant, uint256 lpTokenSupply)` {#Swap-AddLiquidity-address-uint256---uint256---uint256-uint256-}

No description

# Event `RemoveLiquidity(address provider, uint256[] tokenAmounts, uint256 lpTokenSupply)` {#Swap-RemoveLiquidity-address-uint256---uint256-}

No description

# Event `RemoveLiquidityOne(address provider, uint256 lpTokenAmount, uint256 lpTokenSupply, uint256 boughtId, uint256 tokensBought)` {#Swap-RemoveLiquidityOne-address-uint256-uint256-uint256-uint256-}

No description

# Event `RemoveLiquidityImbalance(address provider, uint256[] tokenAmounts, uint256[] fees, uint256 invariant, uint256 lpTokenSupply)` {#Swap-RemoveLiquidityImbalance-address-uint256---uint256---uint256-uint256-}

No description

# Event `NewAdminFee(uint256 newAdminFee)` {#Swap-NewAdminFee-uint256-}

No description

# Event `NewSwapFee(uint256 newSwapFee)` {#Swap-NewSwapFee-uint256-}

No description

# Event `NewWithdrawFee(uint256 newWithdrawFee)` {#Swap-NewWithdrawFee-uint256-}

No description

# Event `RampA(uint256 oldA, uint256 newA, uint256 initialTime, uint256 futureTime)` {#Swap-RampA-uint256-uint256-uint256-uint256-}

No description

# Event `StopRampA(uint256 currentA, uint256 time)` {#Swap-StopRampA-uint256-uint256-}

No description
