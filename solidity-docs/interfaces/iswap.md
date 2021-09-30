# ISwap

## Functions:

* [`getA()`](iswap.md#ISwap-getA--)
* [`getAllowlist()`](iswap.md#ISwap-getAllowlist--)
* [`getToken(uint8 index)`](iswap.md#ISwap-getToken-uint8-)
* [`getTokenIndex(address tokenAddress)`](iswap.md#ISwap-getTokenIndex-address-)
* [`getTokenBalance(uint8 index)`](iswap.md#ISwap-getTokenBalance-uint8-)
* [`getVirtualPrice()`](iswap.md#ISwap-getVirtualPrice--)
* [`isGuarded()`](iswap.md#ISwap-isGuarded--)
* [`calculateSwap(uint8 tokenIndexFrom, uint8 tokenIndexTo, uint256 dx)`](iswap.md#ISwap-calculateSwap-uint8-uint8-uint256-)
* [`calculateTokenAmount(uint256[] amounts, bool deposit)`](iswap.md#ISwap-calculateTokenAmount-uint256---bool-)
* [`calculateRemoveLiquidity(uint256 amount)`](iswap.md#ISwap-calculateRemoveLiquidity-uint256-)
* [`calculateRemoveLiquidityOneToken(uint256 tokenAmount, uint8 tokenIndex)`](iswap.md#ISwap-calculateRemoveLiquidityOneToken-uint256-uint8-)
* [`swap(uint8 tokenIndexFrom, uint8 tokenIndexTo, uint256 dx, uint256 minDy, uint256 deadline)`](iswap.md#ISwap-swap-uint8-uint8-uint256-uint256-uint256-)
* [`addLiquidity(uint256[] amounts, uint256 minToMint, uint256 deadline, bytes32[] merkleProof)`](iswap.md#ISwap-addLiquidity-uint256---uint256-uint256-bytes32---)
* [`removeLiquidity(uint256 amount, uint256[] minAmounts, uint256 deadline)`](iswap.md#ISwap-removeLiquidity-uint256-uint256---uint256-)
* [`removeLiquidityOneToken(uint256 tokenAmount, uint8 tokenIndex, uint256 minAmount, uint256 deadline)`](iswap.md#ISwap-removeLiquidityOneToken-uint256-uint8-uint256-uint256-)
* [`removeLiquidityImbalance(uint256[] amounts, uint256 maxBurnAmount, uint256 deadline)`](iswap.md#ISwap-removeLiquidityImbalance-uint256---uint256-uint256-)
* [`updateUserWithdrawFee(address recipient, uint256 transferAmount)`](iswap.md#ISwap-updateUserWithdrawFee-address-uint256-)

## Function `getA() → uint256` <a id="ISwap-getA--"></a>

No description

## Function `getAllowlist() → contract IAllowlist` <a id="ISwap-getAllowlist--"></a>

No description

## Function `getToken(uint8 index) → contract IERC20` <a id="ISwap-getToken-uint8-"></a>

No description

## Function `getTokenIndex(address tokenAddress) → uint8` <a id="ISwap-getTokenIndex-address-"></a>

No description

## Function `getTokenBalance(uint8 index) → uint256` <a id="ISwap-getTokenBalance-uint8-"></a>

No description

## Function `getVirtualPrice() → uint256` <a id="ISwap-getVirtualPrice--"></a>

No description

## Function `isGuarded() → bool` <a id="ISwap-isGuarded--"></a>

No description

## Function `calculateSwap(uint8 tokenIndexFrom, uint8 tokenIndexTo, uint256 dx) → uint256` <a id="ISwap-calculateSwap-uint8-uint8-uint256-"></a>

No description

## Function `calculateTokenAmount(uint256[] amounts, bool deposit) → uint256` <a id="ISwap-calculateTokenAmount-uint256---bool-"></a>

No description

## Function `calculateRemoveLiquidity(uint256 amount) → uint256[]` <a id="ISwap-calculateRemoveLiquidity-uint256-"></a>

No description

## Function `calculateRemoveLiquidityOneToken(uint256 tokenAmount, uint8 tokenIndex) → uint256 availableTokenAmount` <a id="ISwap-calculateRemoveLiquidityOneToken-uint256-uint8-"></a>

No description

## Function `swap(uint8 tokenIndexFrom, uint8 tokenIndexTo, uint256 dx, uint256 minDy, uint256 deadline) → uint256` <a id="ISwap-swap-uint8-uint8-uint256-uint256-uint256-"></a>

No description

## Function `addLiquidity(uint256[] amounts, uint256 minToMint, uint256 deadline, bytes32[] merkleProof) → uint256` <a id="ISwap-addLiquidity-uint256---uint256-uint256-bytes32---"></a>

No description

## Function `removeLiquidity(uint256 amount, uint256[] minAmounts, uint256 deadline) → uint256[]` <a id="ISwap-removeLiquidity-uint256-uint256---uint256-"></a>

No description

## Function `removeLiquidityOneToken(uint256 tokenAmount, uint8 tokenIndex, uint256 minAmount, uint256 deadline) → uint256` <a id="ISwap-removeLiquidityOneToken-uint256-uint8-uint256-uint256-"></a>

No description

## Function `removeLiquidityImbalance(uint256[] amounts, uint256 maxBurnAmount, uint256 deadline) → uint256` <a id="ISwap-removeLiquidityImbalance-uint256---uint256-uint256-"></a>

No description

## Function `updateUserWithdrawFee(address recipient, uint256 transferAmount)` <a id="ISwap-updateUserWithdrawFee-address-uint256-"></a>

No description

