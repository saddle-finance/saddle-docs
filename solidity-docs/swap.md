# Swap

Most of the logic is stored as a library `SwapUtils` for the sake of reducing contract's deployment size.

## Functions:

* [`constructor(contract IERC20[] _pooledTokens, uint8[] decimals, string lpTokenName, string lpTokenSymbol, uint256 _a, uint256 _fee, uint256 _adminFee, uint256 _withdrawFee, contract IAllowlist _allowlist)`](swap.md#Swap-constructor-contract-IERC20---uint8---string-string-uint256-uint256-uint256-uint256-contract-IAllowlist-)
* [`getA()`](swap.md#Swap-getA--)
* [`getAPrecise()`](swap.md#Swap-getAPrecise--)
* [`getToken(uint8 index)`](swap.md#Swap-getToken-uint8-)
* [`getTokenIndex(address tokenAddress)`](swap.md#Swap-getTokenIndex-address-)
* [`getAllowlist()`](swap.md#Swap-getAllowlist--)
* [`getDepositTimestamp(address user)`](swap.md#Swap-getDepositTimestamp-address-)
* [`getTokenBalance(uint8 index)`](swap.md#Swap-getTokenBalance-uint8-)
* [`getVirtualPrice()`](swap.md#Swap-getVirtualPrice--)
* [`calculateSwap(uint8 tokenIndexFrom, uint8 tokenIndexTo, uint256 dx)`](swap.md#Swap-calculateSwap-uint8-uint8-uint256-)
* [`calculateTokenAmount(address account, uint256[] amounts, bool deposit)`](swap.md#Swap-calculateTokenAmount-address-uint256---bool-)
* [`calculateRemoveLiquidity(address account, uint256 amount)`](swap.md#Swap-calculateRemoveLiquidity-address-uint256-)
* [`calculateRemoveLiquidityOneToken(address account, uint256 tokenAmount, uint8 tokenIndex)`](swap.md#Swap-calculateRemoveLiquidityOneToken-address-uint256-uint8-)
* [`calculateCurrentWithdrawFee(address user)`](swap.md#Swap-calculateCurrentWithdrawFee-address-)
* [`getAdminBalance(uint256 index)`](swap.md#Swap-getAdminBalance-uint256-)
* [`swap(uint8 tokenIndexFrom, uint8 tokenIndexTo, uint256 dx, uint256 minDy, uint256 deadline)`](swap.md#Swap-swap-uint8-uint8-uint256-uint256-uint256-)
* [`addLiquidity(uint256[] amounts, uint256 minToMint, uint256 deadline, bytes32[] merkleProof)`](swap.md#Swap-addLiquidity-uint256---uint256-uint256-bytes32---)
* [`removeLiquidity(uint256 amount, uint256[] minAmounts, uint256 deadline)`](swap.md#Swap-removeLiquidity-uint256-uint256---uint256-)
* [`removeLiquidityOneToken(uint256 tokenAmount, uint8 tokenIndex, uint256 minAmount, uint256 deadline)`](swap.md#Swap-removeLiquidityOneToken-uint256-uint8-uint256-uint256-)
* [`removeLiquidityImbalance(uint256[] amounts, uint256 maxBurnAmount, uint256 deadline)`](swap.md#Swap-removeLiquidityImbalance-uint256---uint256-uint256-)
* [`updateUserWithdrawFee(address recipient, uint256 transferAmount)`](swap.md#Swap-updateUserWithdrawFee-address-uint256-)
* [`withdrawAdminFees()`](swap.md#Swap-withdrawAdminFees--)
* [`setAdminFee(uint256 newAdminFee)`](swap.md#Swap-setAdminFee-uint256-)
* [`setSwapFee(uint256 newSwapFee)`](swap.md#Swap-setSwapFee-uint256-)
* [`setDefaultWithdrawFee(uint256 newWithdrawFee)`](swap.md#Swap-setDefaultWithdrawFee-uint256-)
* [`rampA(uint256 futureA, uint256 futureTime)`](swap.md#Swap-rampA-uint256-uint256-)
* [`stopRampA()`](swap.md#Swap-stopRampA--)
* [`disableGuard()`](swap.md#Swap-disableGuard--)
* [`isGuarded()`](swap.md#Swap-isGuarded--)

## Events:

* [`TokenSwap(address buyer, uint256 tokensSold, uint256 tokensBought, uint128 soldId, uint128 boughtId)`](swap.md#Swap-TokenSwap-address-uint256-uint256-uint128-uint128-)
* [`AddLiquidity(address provider, uint256[] tokenAmounts, uint256[] fees, uint256 invariant, uint256 lpTokenSupply)`](swap.md#Swap-AddLiquidity-address-uint256---uint256---uint256-uint256-)
* [`RemoveLiquidity(address provider, uint256[] tokenAmounts, uint256 lpTokenSupply)`](swap.md#Swap-RemoveLiquidity-address-uint256---uint256-)
* [`RemoveLiquidityOne(address provider, uint256 lpTokenAmount, uint256 lpTokenSupply, uint256 boughtId, uint256 tokensBought)`](swap.md#Swap-RemoveLiquidityOne-address-uint256-uint256-uint256-uint256-)
* [`RemoveLiquidityImbalance(address provider, uint256[] tokenAmounts, uint256[] fees, uint256 invariant, uint256 lpTokenSupply)`](swap.md#Swap-RemoveLiquidityImbalance-address-uint256---uint256---uint256-uint256-)
* [`NewAdminFee(uint256 newAdminFee)`](swap.md#Swap-NewAdminFee-uint256-)
* [`NewSwapFee(uint256 newSwapFee)`](swap.md#Swap-NewSwapFee-uint256-)
* [`NewWithdrawFee(uint256 newWithdrawFee)`](swap.md#Swap-NewWithdrawFee-uint256-)
* [`RampA(uint256 oldA, uint256 newA, uint256 initialTime, uint256 futureTime)`](swap.md#Swap-RampA-uint256-uint256-uint256-uint256-)
* [`StopRampA(uint256 currentA, uint256 time)`](swap.md#Swap-StopRampA-uint256-uint256-)

## Function `constructor(contract IERC20[] _pooledTokens, uint8[] decimals, string lpTokenName, string lpTokenSymbol, uint256 _a, uint256 _fee, uint256 _adminFee, uint256 _withdrawFee, contract IAllowlist _allowlist)` <a id="Swap-constructor-contract-IERC20---uint8---string-string-uint256-uint256-uint256-uint256-contract-IAllowlist-"></a>

No description

### Parameters:

* `_pooledTokens`: an array of ERC20s this pool will accept
* `decimals`: the decimals to use for each pooled token, eg 8 for WBTC. Cannot be larger than POOL\_PRECISION\_DECIMALS
* `lpTokenName`: the long-form name of the token to be deployed
* `lpTokenSymbol`: the short symbol for the token to be deployed
* `_a`: the amplification coefficient  _n_  \(n - 1\). See the StableSwap paper for details
* `_fee`: default swap fee to be initialized with
* `_adminFee`: default adminFee to be initialized with
* `_withdrawFee`: default withdrawFee to be initliazed with
* `_allowlist`: address of allowlist contract for guarded launch

## Function `getA() → uint256` <a id="Swap-getA--"></a>

See the StableSwap paper for details

### Return Values:

* A parameter

## Function `getAPrecise() → uint256` <a id="Swap-getAPrecise--"></a>

See the StableSwap paper for details

### Return Values:

* A parameter in its raw precision form

## Function `getToken(uint8 index) → contract IERC20` <a id="Swap-getToken-uint8-"></a>

No description

### Parameters:

* `index`: the index of the token

### Return Values:

* address of the token at given index

## Function `getTokenIndex(address tokenAddress) → uint8` <a id="Swap-getTokenIndex-address-"></a>

No description

### Parameters:

* `tokenAddress`: address of the token

### Return Values:

* the index of the given token address

## Function `getAllowlist() → contract IAllowlist` <a id="Swap-getAllowlist--"></a>

No description

### Return Values:

* the address of the allowlist contract casted to the IAllowlist interface

## Function `getDepositTimestamp(address user) → uint256` <a id="Swap-getDepositTimestamp-address-"></a>

No description

### Return Values:

* timestamp of the last deposit made by the given address

## Function `getTokenBalance(uint8 index) → uint256` <a id="Swap-getTokenBalance-uint8-"></a>

No description

### Parameters:

* `index`: the index of the token

### Return Values:

* current balance of the pooled token at given index with token's native precision

## Function `getVirtualPrice() → uint256` <a id="Swap-getVirtualPrice--"></a>

No description

### Return Values:

* the virtual price, scaled to the POOL\_PRECISION\_DECIMALS

## Function `calculateSwap(uint8 tokenIndexFrom, uint8 tokenIndexTo, uint256 dx) → uint256` <a id="Swap-calculateSwap-uint8-uint8-uint256-"></a>

No description

### Parameters:

* `tokenIndexFrom`: the token the user wants to sell
* `tokenIndexTo`: the token the user wants to buy
* `dx`: the amount of tokens the user wants to sell. If the token charges a fee on transfers, use the amount that gets transferred after the fee.

### Return Values:

* amount of tokens the user will receive

## Function `calculateTokenAmount(address account, uint256[] amounts, bool deposit) → uint256` <a id="Swap-calculateTokenAmount-address-uint256---bool-"></a>

This shouldn't be used outside frontends for user estimates.

### Parameters:

* `account`: address that is depositing or withdrawing tokens
* `amounts`: an array of token amounts to deposit or withdrawal, corresponding to pooledTokens. The amount should be in each pooled token's native precision. If a token charges a fee on transfers, use the amount that gets transferred after the fee.
* `deposit`: whether this is a deposit or a withdrawal

### Return Values:

* token amount the user will receive

## Function `calculateRemoveLiquidity(address account, uint256 amount) → uint256[]` <a id="Swap-calculateRemoveLiquidity-address-uint256-"></a>

No description

### Parameters:

* `account`: the address that is withdrawing tokens
* `amount`: the amount of LP tokens that would be burned on withdrawal

### Return Values:

* array of token balances that the user will receive

## Function `calculateRemoveLiquidityOneToken(address account, uint256 tokenAmount, uint8 tokenIndex) → uint256 availableTokenAmount` <a id="Swap-calculateRemoveLiquidityOneToken-address-uint256-uint8-"></a>

No description

### Parameters:

* `account`: the address that is withdrawing tokens
* `tokenAmount`: the amount of LP token to burn
* `tokenIndex`: index of which token will be withdrawn

### Return Values:

* availableTokenAmount calculated amount of underlying token

  available to withdraw

## Function `calculateCurrentWithdrawFee(address user) → uint256` <a id="Swap-calculateCurrentWithdrawFee-address-"></a>

returned value should be divided by FEE\_DENOMINATOR to convert to correct decimals

### Parameters:

* `user`: address you want to calculate withdraw fee of

### Return Values:

* current withdraw fee of the user

## Function `getAdminBalance(uint256 index) → uint256` <a id="Swap-getAdminBalance-uint256-"></a>

No description

### Parameters:

* `index`: Index of the pooled token

### Return Values:

* s token balance in the token's precision

## Function `swap(uint8 tokenIndexFrom, uint8 tokenIndexTo, uint256 dx, uint256 minDy, uint256 deadline) → uint256` <a id="Swap-swap-uint8-uint8-uint256-uint256-uint256-"></a>

No description

### Parameters:

* `tokenIndexFrom`: the token the user wants to swap from
* `tokenIndexTo`: the token the user wants to swap to
* `dx`: the amount of tokens the user wants to swap from
* `minDy`: the min amount the user would like to receive, or revert.
* `deadline`: latest timestamp to accept this transaction

## Function `addLiquidity(uint256[] amounts, uint256 minToMint, uint256 deadline, bytes32[] merkleProof) → uint256` <a id="Swap-addLiquidity-uint256---uint256-uint256-bytes32---"></a>

No description

### Parameters:

* `amounts`: the amounts of each token to add, in their native precision
* `minToMint`: the minimum LP tokens adding this amount of liquidity should mint, otherwise revert. Handy for front-running mitigation
* `deadline`: latest timestamp to accept this transaction
* `merkleProof`: data generated when constructing the allowlist merkle tree. Users can get this data off chain. Even if the address is in the allowlist, users must include a valid proof for this call to succeed. If the pool is no longer in the guarded release phase, this parameter is ignored.

### Return Values:

* amount of LP token user minted and received

## Function `removeLiquidity(uint256 amount, uint256[] minAmounts, uint256 deadline) → uint256[]` <a id="Swap-removeLiquidity-uint256-uint256---uint256-"></a>

Liquidity can always be removed, even when the pool is paused.

### Parameters:

* `amount`: the amount of LP tokens to burn
* `minAmounts`: the minimum amounts of each token in the pool acceptable for this burn. Useful as a front-running mitigation
* `deadline`: latest timestamp to accept this transaction

### Return Values:

* amounts of tokens user received

## Function `removeLiquidityOneToken(uint256 tokenAmount, uint8 tokenIndex, uint256 minAmount, uint256 deadline) → uint256` <a id="Swap-removeLiquidityOneToken-uint256-uint8-uint256-uint256-"></a>

No description

### Parameters:

* `tokenAmount`: the amount of the token you want to receive
* `tokenIndex`: the index of the token you want to receive
* `minAmount`: the minimum amount to withdraw, otherwise revert
* `deadline`: latest timestamp to accept this transaction

### Return Values:

* amount of chosen token user received

## Function `removeLiquidityImbalance(uint256[] amounts, uint256 maxBurnAmount, uint256 deadline) → uint256` <a id="Swap-removeLiquidityImbalance-uint256---uint256-uint256-"></a>

No description

### Parameters:

* `amounts`: how much of each token to withdraw
* `maxBurnAmount`: the max LP token provider is willing to pay to remove liquidity. Useful as a front-running mitigation.
* `deadline`: latest timestamp to accept this transaction

### Return Values:

* amount of LP tokens burned

## Function `updateUserWithdrawFee(address recipient, uint256 transferAmount)` <a id="Swap-updateUserWithdrawFee-address-uint256-"></a>

No description

### Parameters:

* `recipient`: address of the recipient of pool token
* `transferAmount`: amount of pool token to transfer

## Function `withdrawAdminFees()` <a id="Swap-withdrawAdminFees--"></a>

No description

## Function `setAdminFee(uint256 newAdminFee)` <a id="Swap-setAdminFee-uint256-"></a>

No description

### Parameters:

* `newAdminFee`: new admin fee to be applied on future transactions

## Function `setSwapFee(uint256 newSwapFee)` <a id="Swap-setSwapFee-uint256-"></a>

No description

### Parameters:

* `newSwapFee`: new swap fee to be applied on future transactions

## Function `setDefaultWithdrawFee(uint256 newWithdrawFee)` <a id="Swap-setDefaultWithdrawFee-uint256-"></a>

No description

### Parameters:

* `newWithdrawFee`: new withdraw fee to be applied on future deposits

## Function `rampA(uint256 futureA, uint256 futureTime)` <a id="Swap-rampA-uint256-uint256-"></a>

No description

### Parameters:

* `futureA`: the new A to ramp towards
* `futureTime`: timestamp when the new A should be reached

## Function `stopRampA()` <a id="Swap-stopRampA--"></a>

No description

## Function `disableGuard()` <a id="Swap-disableGuard--"></a>

No description

## Function `isGuarded() → bool` <a id="Swap-isGuarded--"></a>

No description

### Return Values:

* guarded\_ boolean value indicating whether the deposits should be guarded

## Event `TokenSwap(address buyer, uint256 tokensSold, uint256 tokensBought, uint128 soldId, uint128 boughtId)` <a id="Swap-TokenSwap-address-uint256-uint256-uint128-uint128-"></a>

No description

## Event `AddLiquidity(address provider, uint256[] tokenAmounts, uint256[] fees, uint256 invariant, uint256 lpTokenSupply)` <a id="Swap-AddLiquidity-address-uint256---uint256---uint256-uint256-"></a>

No description

## Event `RemoveLiquidity(address provider, uint256[] tokenAmounts, uint256 lpTokenSupply)` <a id="Swap-RemoveLiquidity-address-uint256---uint256-"></a>

No description

## Event `RemoveLiquidityOne(address provider, uint256 lpTokenAmount, uint256 lpTokenSupply, uint256 boughtId, uint256 tokensBought)` <a id="Swap-RemoveLiquidityOne-address-uint256-uint256-uint256-uint256-"></a>

No description

## Event `RemoveLiquidityImbalance(address provider, uint256[] tokenAmounts, uint256[] fees, uint256 invariant, uint256 lpTokenSupply)` <a id="Swap-RemoveLiquidityImbalance-address-uint256---uint256---uint256-uint256-"></a>

No description

## Event `NewAdminFee(uint256 newAdminFee)` <a id="Swap-NewAdminFee-uint256-"></a>

No description

## Event `NewSwapFee(uint256 newSwapFee)` <a id="Swap-NewSwapFee-uint256-"></a>

No description

## Event `NewWithdrawFee(uint256 newWithdrawFee)` <a id="Swap-NewWithdrawFee-uint256-"></a>

No description

## Event `RampA(uint256 oldA, uint256 newA, uint256 initialTime, uint256 futureTime)` <a id="Swap-RampA-uint256-uint256-uint256-uint256-"></a>

No description

## Event `StopRampA(uint256 currentA, uint256 time)` <a id="Swap-StopRampA-uint256-uint256-"></a>

No description

