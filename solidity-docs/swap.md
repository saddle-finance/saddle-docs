# Swap

This contract is responsible for custody of closely pegged assets \(eg. group of stablecoins\) and automatic market making system. Users become an LP \(Liquidity Provider\) by depositing their tokens in desired ratios for an exchange of the pool token that represents their share of the pool. Users can burn pool tokens and withdraw their share of token\(s\).

Each time a swap between the pooled tokens happens, a set fee incurs which effectively gets distributed to the LPs.

In case of emergencies, admin can pause additional deposits, swaps, or single-asset withdraws - which stops the ratio of the tokens in the pool from changing. Users can always withdraw their tokens via multi-asset withdraws.

Most of the logic is stored as a library `SwapUtils` for the sake of reducing contract's deployment size.

## Functions:

- [`constructor(contract IERC20[] _pooledTokens, uint8[] decimals, string lpTokenName, string lpTokenSymbol, uint256 _a, uint256 _fee, uint256 _adminFee, uint256 _withdrawFee, contract IAllowlist _allowlist)`](swap.md#Swap-constructor-contract-IERC20---uint8---string-string-uint256-uint256-uint256-uint256-contract-IAllowlist-)
- [`getA()`](swap.md#Swap-getA--)
- [`getAPrecise()`](swap.md#Swap-getAPrecise--)
- [`getToken(uint8 index)`](swap.md#Swap-getToken-uint8-)
- [`getTokenIndex(address tokenAddress)`](swap.md#Swap-getTokenIndex-address-)
- [`getAllowlist()`](swap.md#Swap-getAllowlist--)
- [`getDepositTimestamp(address user)`](swap.md#Swap-getDepositTimestamp-address-)
- [`getTokenBalance(uint8 index)`](swap.md#Swap-getTokenBalance-uint8-)
- [`getVirtualPrice()`](swap.md#Swap-getVirtualPrice--)
- [`calculateSwap(uint8 tokenIndexFrom, uint8 tokenIndexTo, uint256 dx)`](swap.md#Swap-calculateSwap-uint8-uint8-uint256-)
- [`calculateTokenAmount(address account, uint256[] amounts, bool deposit)`](swap.md#Swap-calculateTokenAmount-address-uint256---bool-)
- [`calculateRemoveLiquidity(address account, uint256 amount)`](swap.md#Swap-calculateRemoveLiquidity-address-uint256-)
- [`calculateRemoveLiquidityOneToken(address account, uint256 tokenAmount, uint8 tokenIndex)`](swap.md#Swap-calculateRemoveLiquidityOneToken-address-uint256-uint8-)
- [`calculateCurrentWithdrawFee(address user)`](swap.md#Swap-calculateCurrentWithdrawFee-address-)
- [`getAdminBalance(uint256 index)`](swap.md#Swap-getAdminBalance-uint256-)
- [`swap(uint8 tokenIndexFrom, uint8 tokenIndexTo, uint256 dx, uint256 minDy, uint256 deadline)`](swap.md#Swap-swap-uint8-uint8-uint256-uint256-uint256-)
- [`addLiquidity(uint256[] amounts, uint256 minToMint, uint256 deadline, bytes32[] merkleProof)`](swap.md#Swap-addLiquidity-uint256---uint256-uint256-bytes32---)
- [`removeLiquidity(uint256 amount, uint256[] minAmounts, uint256 deadline)`](swap.md#Swap-removeLiquidity-uint256-uint256---uint256-)
- [`removeLiquidityOneToken(uint256 tokenAmount, uint8 tokenIndex, uint256 minAmount, uint256 deadline)`](swap.md#Swap-removeLiquidityOneToken-uint256-uint8-uint256-uint256-)
- [`removeLiquidityImbalance(uint256[] amounts, uint256 maxBurnAmount, uint256 deadline)`](swap.md#Swap-removeLiquidityImbalance-uint256---uint256-uint256-)
- [`updateUserWithdrawFee(address recipient, uint256 transferAmount)`](swap.md#Swap-updateUserWithdrawFee-address-uint256-)
- [`withdrawAdminFees()`](swap.md#Swap-withdrawAdminFees--)
- [`setAdminFee(uint256 newAdminFee)`](swap.md#Swap-setAdminFee-uint256-)
- [`setSwapFee(uint256 newSwapFee)`](swap.md#Swap-setSwapFee-uint256-)
- [`setDefaultWithdrawFee(uint256 newWithdrawFee)`](swap.md#Swap-setDefaultWithdrawFee-uint256-)
- [`rampA(uint256 futureA, uint256 futureTime)`](swap.md#Swap-rampA-uint256-uint256-)
- [`stopRampA()`](swap.md#Swap-stopRampA--)
- [`disableGuard()`](swap.md#Swap-disableGuard--)
- [`isGuarded()`](swap.md#Swap-isGuarded--)

## Events:

- [`TokenSwap(address buyer, uint256 tokensSold, uint256 tokensBought, uint128 soldId, uint128 boughtId)`](swap.md#Swap-TokenSwap-address-uint256-uint256-uint128-uint128-)
- [`AddLiquidity(address provider, uint256[] tokenAmounts, uint256[] fees, uint256 invariant, uint256 lpTokenSupply)`](swap.md#Swap-AddLiquidity-address-uint256---uint256---uint256-uint256-)
- [`RemoveLiquidity(address provider, uint256[] tokenAmounts, uint256 lpTokenSupply)`](swap.md#Swap-RemoveLiquidity-address-uint256---uint256-)
- [`RemoveLiquidityOne(address provider, uint256 lpTokenAmount, uint256 lpTokenSupply, uint256 boughtId, uint256 tokensBought)`](swap.md#Swap-RemoveLiquidityOne-address-uint256-uint256-uint256-uint256-)
- [`RemoveLiquidityImbalance(address provider, uint256[] tokenAmounts, uint256[] fees, uint256 invariant, uint256 lpTokenSupply)`](swap.md#Swap-RemoveLiquidityImbalance-address-uint256---uint256---uint256-uint256-)
- [`NewAdminFee(uint256 newAdminFee)`](swap.md#Swap-NewAdminFee-uint256-)
- [`NewSwapFee(uint256 newSwapFee)`](swap.md#Swap-NewSwapFee-uint256-)
- [`NewWithdrawFee(uint256 newWithdrawFee)`](swap.md#Swap-NewWithdrawFee-uint256-)
- [`RampA(uint256 oldA, uint256 newA, uint256 initialTime, uint256 futureTime)`](swap.md#Swap-RampA-uint256-uint256-uint256-uint256-)
- [`StopRampA(uint256 currentA, uint256 time)`](swap.md#Swap-StopRampA-uint256-uint256-)

## Function `constructor(contract IERC20[] _pooledTokens, uint8[] decimals, string lpTokenName, string lpTokenSymbol, uint256 _a, uint256 _fee, uint256 _adminFee, uint256 _withdrawFee, contract IAllowlist _allowlist)` <a id="Swap-constructor-contract-IERC20---uint8---string-string-uint256-uint256-uint256-uint256-contract-IAllowlist-"></a>

Deploys this Swap contract with given parameters as default values. This will also deploy a LPToken that represents users LP position. The owner of LPToken will be this contract - which means only this contract is allowed to mint new tokens.

### Parameters:

- `_pooledTokens`: an array of ERC20s this pool will accept
- `decimals`: the decimals to use for each pooled token, eg 8 for WBTC. Cannot be larger than POOL_PRECISION_DECIMALS
- `lpTokenName`: the long-form name of the token to be deployed
- `lpTokenSymbol`: the short symbol for the token to be deployed
- `_a`: the amplification coefficient _n_ \(n - 1\). See the StableSwap paper for details
- `_fee`: default swap fee to be initialized with
- `_adminFee`: default adminFee to be initialized with
- `_withdrawFee`: default withdrawFee to be initliazed with
- `_allowlist`: address of allowlist contract for guarded launch

## Function `getA() → uint256` <a id="Swap-getA--"></a>

Return A, the amplification coefficient _n_ \(n - 1\)

See the StableSwap paper for details

### Return Values:

- A parameter

## Function `getAPrecise() → uint256` <a id="Swap-getAPrecise--"></a>

Return A in its raw precision form

See the StableSwap paper for details

### Return Values:

- A parameter in its raw precision form

## Function `getToken(uint8 index) → contract IERC20` <a id="Swap-getToken-uint8-"></a>

Return address of the pooled token at given index. Reverts if tokenIndex is out of range.

### Parameters:

- `index`: the index of the token

### Return Values:

- address of the token at given index

## Function `getTokenIndex(address tokenAddress) → uint8` <a id="Swap-getTokenIndex-address-"></a>

Return the index of the given token address. Reverts if no matching token is found.

### Parameters:

- `tokenAddress`: address of the token

### Return Values:

- the index of the given token address

## Function `getAllowlist() → contract IAllowlist` <a id="Swap-getAllowlist--"></a>

Reads and returns the address of the allowlist that is set during deployment of this contract

### Return Values:

- the address of the allowlist contract casted to the IAllowlist interface

## Function `getDepositTimestamp(address user) → uint256` <a id="Swap-getDepositTimestamp-address-"></a>

Return timestamp of last deposit of given address

### Return Values:

- timestamp of the last deposit made by the given address

## Function `getTokenBalance(uint8 index) → uint256` <a id="Swap-getTokenBalance-uint8-"></a>

Return current balance of the pooled token at given index

### Parameters:

- `index`: the index of the token

### Return Values:

- current balance of the pooled token at given index with token's native precision

## Function `getVirtualPrice() → uint256` <a id="Swap-getVirtualPrice--"></a>

Get the virtual price, to help calculate profit

### Return Values:

- the virtual price, scaled to the POOL_PRECISION_DECIMALS

## Function `calculateSwap(uint8 tokenIndexFrom, uint8 tokenIndexTo, uint256 dx) → uint256` <a id="Swap-calculateSwap-uint8-uint8-uint256-"></a>

Calculate amount of tokens you receive on swap

### Parameters:

- `tokenIndexFrom`: the token the user wants to sell
- `tokenIndexTo`: the token the user wants to buy
- `dx`: the amount of tokens the user wants to sell. If the token charges a fee on transfers, use the amount that gets transferred after the fee.

### Return Values:

- amount of tokens the user will receive

## Function `calculateTokenAmount(address account, uint256[] amounts, bool deposit) → uint256` <a id="Swap-calculateTokenAmount-address-uint256---bool-"></a>

A simple method to calculate prices from deposits or withdrawals, excluding fees but including slippage. This is helpful as an input into the various "min" parameters on calls to fight front-running

This shouldn't be used outside frontends for user estimates.

### Parameters:

- `account`: address that is depositing or withdrawing tokens
- `amounts`: an array of token amounts to deposit or withdrawal, corresponding to pooledTokens. The amount should be in each pooled token's native precision. If a token charges a fee on transfers, use the amount that gets transferred after the fee.
- `deposit`: whether this is a deposit or a withdrawal

### Return Values:

- token amount the user will receive

## Function `calculateRemoveLiquidity(address account, uint256 amount) → uint256[]` <a id="Swap-calculateRemoveLiquidity-address-uint256-"></a>

A simple method to calculate amount of each underlying tokens that is returned upon burning given amount of LP tokens

### Parameters:

- `account`: the address that is withdrawing tokens
- `amount`: the amount of LP tokens that would be burned on withdrawal

### Return Values:

- array of token balances that the user will receive

## Function `calculateRemoveLiquidityOneToken(address account, uint256 tokenAmount, uint8 tokenIndex) → uint256 availableTokenAmount` <a id="Swap-calculateRemoveLiquidityOneToken-address-uint256-uint8-"></a>

Calculate the amount of underlying token available to withdraw when withdrawing via only single token

### Parameters:

- `account`: the address that is withdrawing tokens
- `tokenAmount`: the amount of LP token to burn
- `tokenIndex`: index of which token will be withdrawn

### Return Values:

- availableTokenAmount calculated amount of underlying token

  available to withdraw

## Function `calculateCurrentWithdrawFee(address user) → uint256` <a id="Swap-calculateCurrentWithdrawFee-address-"></a>

Calculate the fee that is applied when the given user withdraws. The withdraw fee decays linearly over period of 4 weeks. For example, depositing and withdrawing right away will charge you the full amount of withdraw fee. But withdrawing after 4 weeks will charge you no additional fees.

returned value should be divided by FEE_DENOMINATOR to convert to correct decimals

### Parameters:

- `user`: address you want to calculate withdraw fee of

### Return Values:

- current withdraw fee of the user

## Function `getAdminBalance(uint256 index) → uint256` <a id="Swap-getAdminBalance-uint256-"></a>

This function reads the accumulated amount of admin fees of the token with given index

### Parameters:

- `index`: Index of the pooled token

### Return Values:

- s token balance in the token's precision

## Function `swap(uint8 tokenIndexFrom, uint8 tokenIndexTo, uint256 dx, uint256 minDy, uint256 deadline) → uint256` <a id="Swap-swap-uint8-uint8-uint256-uint256-uint256-"></a>

Swap two tokens using this pool

### Parameters:

- `tokenIndexFrom`: the token the user wants to swap from
- `tokenIndexTo`: the token the user wants to swap to
- `dx`: the amount of tokens the user wants to swap from
- `minDy`: the min amount the user would like to receive, or revert.
- `deadline`: latest timestamp to accept this transaction

## Function `addLiquidity(uint256[] amounts, uint256 minToMint, uint256 deadline, bytes32[] merkleProof) → uint256` <a id="Swap-addLiquidity-uint256---uint256-uint256-bytes32---"></a>

Add liquidity to the pool with given amounts during guarded launch phase. Only users with valid address and proof can successfully call this function. When this function is called after the guarded release phase is over, the merkleProof is ignored.

### Parameters:

- `amounts`: the amounts of each token to add, in their native precision
- `minToMint`: the minimum LP tokens adding this amount of liquidity should mint, otherwise revert. Handy for front-running mitigation
- `deadline`: latest timestamp to accept this transaction
- `merkleProof`: data generated when constructing the allowlist merkle tree. Users can get this data off chain. Even if the address is in the allowlist, users must include a valid proof for this call to succeed. If the pool is no longer in the guarded release phase, this parameter is ignored.

### Return Values:

- amount of LP token user minted and received

## Function `removeLiquidity(uint256 amount, uint256[] minAmounts, uint256 deadline) → uint256[]` <a id="Swap-removeLiquidity-uint256-uint256---uint256-"></a>

Burn LP tokens to remove liquidity from the pool. Withdraw fee that decays linearly over period of 4 weeks since last deposit will apply.

Liquidity can always be removed, even when the pool is paused.

### Parameters:

- `amount`: the amount of LP tokens to burn
- `minAmounts`: the minimum amounts of each token in the pool acceptable for this burn. Useful as a front-running mitigation
- `deadline`: latest timestamp to accept this transaction

### Return Values:

- amounts of tokens user received

## Function `removeLiquidityOneToken(uint256 tokenAmount, uint8 tokenIndex, uint256 minAmount, uint256 deadline) → uint256` <a id="Swap-removeLiquidityOneToken-uint256-uint8-uint256-uint256-"></a>

Remove liquidity from the pool all in one token. Withdraw fee that decays linearly over period of 4 weeks since last deposit will apply.

### Parameters:

- `tokenAmount`: the amount of the token you want to receive
- `tokenIndex`: the index of the token you want to receive
- `minAmount`: the minimum amount to withdraw, otherwise revert
- `deadline`: latest timestamp to accept this transaction

### Return Values:

- amount of chosen token user received

## Function `removeLiquidityImbalance(uint256[] amounts, uint256 maxBurnAmount, uint256 deadline) → uint256` <a id="Swap-removeLiquidityImbalance-uint256---uint256-uint256-"></a>

Remove liquidity from the pool, weighted differently than the pool's current balances. Withdraw fee that decays linearly over period of 4 weeks since last deposit will apply.

### Parameters:

- `amounts`: how much of each token to withdraw
- `maxBurnAmount`: the max LP token provider is willing to pay to remove liquidity. Useful as a front-running mitigation.
- `deadline`: latest timestamp to accept this transaction

### Return Values:

- amount of LP tokens burned

## Function `updateUserWithdrawFee(address recipient, uint256 transferAmount)` <a id="Swap-updateUserWithdrawFee-address-uint256-"></a>

Updates the user withdraw fee. This function can only be called by the pool token. Should be used to update the withdraw fee on transfer of pool tokens. Transferring your pool token will reset the 4 weeks period. If the recipient is already holding some pool tokens, the withdraw fee will be discounted in respective amounts.

### Parameters:

- `recipient`: address of the recipient of pool token
- `transferAmount`: amount of pool token to transfer

## Function `withdrawAdminFees()` <a id="Swap-withdrawAdminFees--"></a>

Withdraw all admin fees to the contract owner

## Function `setAdminFee(uint256 newAdminFee)` <a id="Swap-setAdminFee-uint256-"></a>

Update the admin fee. Admin fee takes portion of the swap fee.

### Parameters:

- `newAdminFee`: new admin fee to be applied on future transactions

## Function `setSwapFee(uint256 newSwapFee)` <a id="Swap-setSwapFee-uint256-"></a>

Update the swap fee to be applied on swaps

### Parameters:

- `newSwapFee`: new swap fee to be applied on future transactions

## Function `setDefaultWithdrawFee(uint256 newWithdrawFee)` <a id="Swap-setDefaultWithdrawFee-uint256-"></a>

Update the withdraw fee. This fee decays linearly over 4 weeks since user's last deposit.

### Parameters:

- `newWithdrawFee`: new withdraw fee to be applied on future deposits

## Function `rampA(uint256 futureA, uint256 futureTime)` <a id="Swap-rampA-uint256-uint256-"></a>

Start ramping up or down A parameter towards given futureA and futureTime Checks if the change is too rapid, and commits the new A value only when it falls under the limit range.

### Parameters:

- `futureA`: the new A to ramp towards
- `futureTime`: timestamp when the new A should be reached

## Function `stopRampA()` <a id="Swap-stopRampA--"></a>

Stop ramping A immediately. Reverts if ramp A is already stopped.

## Function `disableGuard()` <a id="Swap-disableGuard--"></a>

Disables the guarded launch phase, removing any limits on deposit amounts and addresses

## Function `isGuarded() → bool` <a id="Swap-isGuarded--"></a>

Reads and returns current guarded status of the pool

### Return Values:

- guarded\_ boolean value indicating whether the deposits should be guarded

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
