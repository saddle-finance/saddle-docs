Contracts relying on this library must initialize SwapUtils.Swap struct then use this library
for SwapUtils.Swap struct. Note that this library contains both functions called by users and admins.
Admin functions should be protected within contracts using this library.

# Functions:

- [`getA(struct SwapUtils.Swap self)`](#SwapUtils-getA-struct-SwapUtils-Swap-)
- [`getAPrecise(struct SwapUtils.Swap self)`](#SwapUtils-getAPrecise-struct-SwapUtils-Swap-)
- [`getDepositTimestamp(struct SwapUtils.Swap self, address user)`](#SwapUtils-getDepositTimestamp-struct-SwapUtils-Swap-address-)
- [`calculateWithdrawOneToken(struct SwapUtils.Swap self, address account, uint256 tokenAmount, uint8 tokenIndex)`](#SwapUtils-calculateWithdrawOneToken-struct-SwapUtils-Swap-address-uint256-uint8-)
- [`getVirtualPrice(struct SwapUtils.Swap self)`](#SwapUtils-getVirtualPrice-struct-SwapUtils-Swap-)
- [`calculateSwap(struct SwapUtils.Swap self, uint8 tokenIndexFrom, uint8 tokenIndexTo, uint256 dx)`](#SwapUtils-calculateSwap-struct-SwapUtils-Swap-uint8-uint8-uint256-)
- [`calculateRemoveLiquidity(struct SwapUtils.Swap self, address account, uint256 amount)`](#SwapUtils-calculateRemoveLiquidity-struct-SwapUtils-Swap-address-uint256-)
- [`calculateCurrentWithdrawFee(struct SwapUtils.Swap self, address user)`](#SwapUtils-calculateCurrentWithdrawFee-struct-SwapUtils-Swap-address-)
- [`calculateTokenAmount(struct SwapUtils.Swap self, address account, uint256[] amounts, bool deposit)`](#SwapUtils-calculateTokenAmount-struct-SwapUtils-Swap-address-uint256---bool-)
- [`getAdminBalance(struct SwapUtils.Swap self, uint256 index)`](#SwapUtils-getAdminBalance-struct-SwapUtils-Swap-uint256-)
- [`swap(struct SwapUtils.Swap self, uint8 tokenIndexFrom, uint8 tokenIndexTo, uint256 dx, uint256 minDy)`](#SwapUtils-swap-struct-SwapUtils-Swap-uint8-uint8-uint256-uint256-)
- [`addLiquidity(struct SwapUtils.Swap self, uint256[] amounts, uint256 minToMint, bytes32[] merkleProof)`](#SwapUtils-addLiquidity-struct-SwapUtils-Swap-uint256---uint256-bytes32---)
- [`updateUserWithdrawFee(struct SwapUtils.Swap self, address user, uint256 toMint)`](#SwapUtils-updateUserWithdrawFee-struct-SwapUtils-Swap-address-uint256-)
- [`removeLiquidity(struct SwapUtils.Swap self, uint256 amount, uint256[] minAmounts)`](#SwapUtils-removeLiquidity-struct-SwapUtils-Swap-uint256-uint256---)
- [`removeLiquidityOneToken(struct SwapUtils.Swap self, uint256 tokenAmount, uint8 tokenIndex, uint256 minAmount)`](#SwapUtils-removeLiquidityOneToken-struct-SwapUtils-Swap-uint256-uint8-uint256-)
- [`removeLiquidityImbalance(struct SwapUtils.Swap self, uint256[] amounts, uint256 maxBurnAmount)`](#SwapUtils-removeLiquidityImbalance-struct-SwapUtils-Swap-uint256---uint256-)
- [`withdrawAdminFees(struct SwapUtils.Swap self, address to)`](#SwapUtils-withdrawAdminFees-struct-SwapUtils-Swap-address-)
- [`setAdminFee(struct SwapUtils.Swap self, uint256 newAdminFee)`](#SwapUtils-setAdminFee-struct-SwapUtils-Swap-uint256-)
- [`setSwapFee(struct SwapUtils.Swap self, uint256 newSwapFee)`](#SwapUtils-setSwapFee-struct-SwapUtils-Swap-uint256-)
- [`setDefaultWithdrawFee(struct SwapUtils.Swap self, uint256 newWithdrawFee)`](#SwapUtils-setDefaultWithdrawFee-struct-SwapUtils-Swap-uint256-)
- [`rampA(struct SwapUtils.Swap self, uint256 futureA_, uint256 futureTime_)`](#SwapUtils-rampA-struct-SwapUtils-Swap-uint256-uint256-)
- [`stopRampA(struct SwapUtils.Swap self)`](#SwapUtils-stopRampA-struct-SwapUtils-Swap-)

# Events:

- [`TokenSwap(address buyer, uint256 tokensSold, uint256 tokensBought, uint128 soldId, uint128 boughtId)`](#SwapUtils-TokenSwap-address-uint256-uint256-uint128-uint128-)
- [`AddLiquidity(address provider, uint256[] tokenAmounts, uint256[] fees, uint256 invariant, uint256 lpTokenSupply)`](#SwapUtils-AddLiquidity-address-uint256---uint256---uint256-uint256-)
- [`RemoveLiquidity(address provider, uint256[] tokenAmounts, uint256 lpTokenSupply)`](#SwapUtils-RemoveLiquidity-address-uint256---uint256-)
- [`RemoveLiquidityOne(address provider, uint256 lpTokenAmount, uint256 lpTokenSupply, uint256 boughtId, uint256 tokensBought)`](#SwapUtils-RemoveLiquidityOne-address-uint256-uint256-uint256-uint256-)
- [`RemoveLiquidityImbalance(address provider, uint256[] tokenAmounts, uint256[] fees, uint256 invariant, uint256 lpTokenSupply)`](#SwapUtils-RemoveLiquidityImbalance-address-uint256---uint256---uint256-uint256-)
- [`NewAdminFee(uint256 newAdminFee)`](#SwapUtils-NewAdminFee-uint256-)
- [`NewSwapFee(uint256 newSwapFee)`](#SwapUtils-NewSwapFee-uint256-)
- [`NewWithdrawFee(uint256 newWithdrawFee)`](#SwapUtils-NewWithdrawFee-uint256-)
- [`RampA(uint256 oldA, uint256 newA, uint256 initialTime, uint256 futureTime)`](#SwapUtils-RampA-uint256-uint256-uint256-uint256-)
- [`StopRampA(uint256 currentA, uint256 time)`](#SwapUtils-StopRampA-uint256-uint256-)

# Function `getA(struct SwapUtils.Swap self) → uint256` {#SwapUtils-getA-struct-SwapUtils-Swap-}

See the StableSwap paper for details

## Parameters:

- `self`: Swap struct to read from

## Return Values:

- A parameter

# Function `getAPrecise(struct SwapUtils.Swap self) → uint256` {#SwapUtils-getAPrecise-struct-SwapUtils-Swap-}

See the StableSwap paper for details

## Parameters:

- `self`: Swap struct to read from

## Return Values:

- A parameter in its raw precision form

# Function `getDepositTimestamp(struct SwapUtils.Swap self, address user) → uint256` {#SwapUtils-getDepositTimestamp-struct-SwapUtils-Swap-address-}

No description

## Parameters:

- `self`: Swap struct to read from

## Return Values:

- timestamp of last deposit

# Function `calculateWithdrawOneToken(struct SwapUtils.Swap self, address account, uint256 tokenAmount, uint8 tokenIndex) → uint256, uint256` {#SwapUtils-calculateWithdrawOneToken-struct-SwapUtils-Swap-address-uint256-uint8-}

No description

## Parameters:

- `account`: the address that is withdrawing

- `tokenAmount`: the amount to withdraw in the pool's precision

- `tokenIndex`: which token will be withdrawn

- `self`: Swap struct to read from

## Return Values:

- the amount of token user will receive and the associated swap fee

# Function `getVirtualPrice(struct SwapUtils.Swap self) → uint256` {#SwapUtils-getVirtualPrice-struct-SwapUtils-Swap-}

No description

## Parameters:

- `self`: Swap struct to read from

## Return Values:

- the virtual price, scaled to precision of POOL_PRECISION_DECIMALS

# Function `calculateSwap(struct SwapUtils.Swap self, uint8 tokenIndexFrom, uint8 tokenIndexTo, uint256 dx) → uint256 dy` {#SwapUtils-calculateSwap-struct-SwapUtils-Swap-uint8-uint8-uint256-}

No description

## Parameters:

- `self`: Swap struct to read from

- `tokenIndexFrom`: the token to sell

- `tokenIndexTo`: the token to buy

- `dx`: the number of tokens to sell. If the token charges a fee on transfers,
  use the amount that gets transferred after the fee.

## Return Values:

- dy the number of tokens the user will get

# Function `calculateRemoveLiquidity(struct SwapUtils.Swap self, address account, uint256 amount) → uint256[]` {#SwapUtils-calculateRemoveLiquidity-struct-SwapUtils-Swap-address-uint256-}

No description

## Parameters:

- `account`: the address that is removing liquidity. required for withdraw fee calculation

- `amount`: the amount of LP tokens that would to be burned on
  withdrawal

## Return Values:

- array of amounts of tokens user will receive

# Function `calculateCurrentWithdrawFee(struct SwapUtils.Swap self, address user) → uint256` {#SwapUtils-calculateCurrentWithdrawFee-struct-SwapUtils-Swap-address-}

No description

## Parameters:

- `user`: address you want to calculate withdraw fee of

## Return Values:

- current withdraw fee of the user

# Function `calculateTokenAmount(struct SwapUtils.Swap self, address account, uint256[] amounts, bool deposit) → uint256` {#SwapUtils-calculateTokenAmount-struct-SwapUtils-Swap-address-uint256---bool-}

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

# Function `getAdminBalance(struct SwapUtils.Swap self, uint256 index) → uint256` {#SwapUtils-getAdminBalance-struct-SwapUtils-Swap-uint256-}

No description

## Parameters:

- `self`: Swap struct to read from

- `index`: Index of the pooled token

## Return Values:

- admin balance in the token's precision

# Function `swap(struct SwapUtils.Swap self, uint8 tokenIndexFrom, uint8 tokenIndexTo, uint256 dx, uint256 minDy) → uint256` {#SwapUtils-swap-struct-SwapUtils-Swap-uint8-uint8-uint256-uint256-}

No description

## Parameters:

- `self`: Swap struct to read from and write to

- `tokenIndexFrom`: the token the user wants to sell

- `tokenIndexTo`: the token the user wants to buy

- `dx`: the amount of tokens the user wants to sell

- `minDy`: the min amount the user would like to receive, or revert.

## Return Values:

- amount of token user received on swap

# Function `addLiquidity(struct SwapUtils.Swap self, uint256[] amounts, uint256 minToMint, bytes32[] merkleProof) → uint256` {#SwapUtils-addLiquidity-struct-SwapUtils-Swap-uint256---uint256-bytes32---}

No description

## Parameters:

- `self`: Swap struct to read from and write to

- `amounts`: the amounts of each token to add, in their native precision

- `minToMint`: the minimum LP tokens adding this amount of liquidity
  should mint, otherwise revert. Handy for front-running mitigation

- `merkleProof`: bytes32 array that will be used to prove the existence of the caller's address in the list of
  allowed addresses. If the pool is not in the guarded launch phase, this parameter will be ignored.

## Return Values:

- amount of LP token user received

# Function `updateUserWithdrawFee(struct SwapUtils.Swap self, address user, uint256 toMint)` {#SwapUtils-updateUserWithdrawFee-struct-SwapUtils-Swap-address-uint256-}

No description

## Parameters:

- `self`: Swap struct to read from and write to

- `user`: address of the user depositing tokens

- `toMint`: amount of pool tokens to be minted

# Function `removeLiquidity(struct SwapUtils.Swap self, uint256 amount, uint256[] minAmounts) → uint256[]` {#SwapUtils-removeLiquidity-struct-SwapUtils-Swap-uint256-uint256---}

Liquidity can always be removed, even when the pool is paused.

## Parameters:

- `self`: Swap struct to read from and write to

- `amount`: the amount of LP tokens to burn

- `minAmounts`: the minimum amounts of each token in the pool
  acceptable for this burn. Useful as a front-running mitigation

## Return Values:

- amounts of tokens the user received

# Function `removeLiquidityOneToken(struct SwapUtils.Swap self, uint256 tokenAmount, uint8 tokenIndex, uint256 minAmount) → uint256` {#SwapUtils-removeLiquidityOneToken-struct-SwapUtils-Swap-uint256-uint8-uint256-}

No description

## Parameters:

- `self`: Swap struct to read from and write to

- `tokenAmount`: the amount of the lp tokens to burn

- `tokenIndex`: the index of the token you want to receive

- `minAmount`: the minimum amount to withdraw, otherwise revert

## Return Values:

- amount chosen token that user received

# Function `removeLiquidityImbalance(struct SwapUtils.Swap self, uint256[] amounts, uint256 maxBurnAmount) → uint256` {#SwapUtils-removeLiquidityImbalance-struct-SwapUtils-Swap-uint256---uint256-}

No description

## Parameters:

- `self`: Swap struct to read from and write to

- `amounts`: how much of each token to withdraw

- `maxBurnAmount`: the max LP token provider is willing to pay to
  remove liquidity. Useful as a front-running mitigation.

## Return Values:

- actual amount of LP tokens burned in the withdrawal

# Function `withdrawAdminFees(struct SwapUtils.Swap self, address to)` {#SwapUtils-withdrawAdminFees-struct-SwapUtils-Swap-address-}

No description

## Parameters:

- `self`: Swap struct to withdraw fees from

- `to`: Address to send the fees to

# Function `setAdminFee(struct SwapUtils.Swap self, uint256 newAdminFee)` {#SwapUtils-setAdminFee-struct-SwapUtils-Swap-uint256-}

adminFee cannot be higher than 100% of the swap fee

## Parameters:

- `self`: Swap struct to update

- `newAdminFee`: new admin fee to be applied on future transactions

# Function `setSwapFee(struct SwapUtils.Swap self, uint256 newSwapFee)` {#SwapUtils-setSwapFee-struct-SwapUtils-Swap-uint256-}

fee cannot be higher than 1% of each swap

## Parameters:

- `self`: Swap struct to update

- `newSwapFee`: new swap fee to be applied on future transactions

# Function `setDefaultWithdrawFee(struct SwapUtils.Swap self, uint256 newWithdrawFee)` {#SwapUtils-setDefaultWithdrawFee-struct-SwapUtils-Swap-uint256-}

No description

## Parameters:

- `self`: Swap struct to update

- `newWithdrawFee`: new withdraw fee to be applied

# Function `rampA(struct SwapUtils.Swap self, uint256 futureA_, uint256 futureTime_)` {#SwapUtils-rampA-struct-SwapUtils-Swap-uint256-uint256-}

No description

## Parameters:

- `self`: Swap struct to update

- `futureA_`: the new A to ramp towards

- `futureTime_`: timestamp when the new A should be reached

# Function `stopRampA(struct SwapUtils.Swap self)` {#SwapUtils-stopRampA-struct-SwapUtils-Swap-}

No description

## Parameters:

- `self`: Swap struct to update

# Event `TokenSwap(address buyer, uint256 tokensSold, uint256 tokensBought, uint128 soldId, uint128 boughtId)` {#SwapUtils-TokenSwap-address-uint256-uint256-uint128-uint128-}

No description

# Event `AddLiquidity(address provider, uint256[] tokenAmounts, uint256[] fees, uint256 invariant, uint256 lpTokenSupply)` {#SwapUtils-AddLiquidity-address-uint256---uint256---uint256-uint256-}

No description

# Event `RemoveLiquidity(address provider, uint256[] tokenAmounts, uint256 lpTokenSupply)` {#SwapUtils-RemoveLiquidity-address-uint256---uint256-}

No description

# Event `RemoveLiquidityOne(address provider, uint256 lpTokenAmount, uint256 lpTokenSupply, uint256 boughtId, uint256 tokensBought)` {#SwapUtils-RemoveLiquidityOne-address-uint256-uint256-uint256-uint256-}

No description

# Event `RemoveLiquidityImbalance(address provider, uint256[] tokenAmounts, uint256[] fees, uint256 invariant, uint256 lpTokenSupply)` {#SwapUtils-RemoveLiquidityImbalance-address-uint256---uint256---uint256-uint256-}

No description

# Event `NewAdminFee(uint256 newAdminFee)` {#SwapUtils-NewAdminFee-uint256-}

No description

# Event `NewSwapFee(uint256 newSwapFee)` {#SwapUtils-NewSwapFee-uint256-}

No description

# Event `NewWithdrawFee(uint256 newWithdrawFee)` {#SwapUtils-NewWithdrawFee-uint256-}

No description

# Event `RampA(uint256 oldA, uint256 newA, uint256 initialTime, uint256 futureTime)` {#SwapUtils-RampA-uint256-uint256-uint256-uint256-}

No description

# Event `StopRampA(uint256 currentA, uint256 time)` {#SwapUtils-StopRampA-uint256-uint256-}

No description
