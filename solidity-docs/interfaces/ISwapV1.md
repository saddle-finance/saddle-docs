# Functions:

- [`getA()`](#ISwapV1-getA--)
- [`getAllowlist()`](#ISwapV1-getAllowlist--)
- [`getToken(uint8 index)`](#ISwapV1-getToken-uint8-)
- [`getTokenIndex(address tokenAddress)`](#ISwapV1-getTokenIndex-address-)
- [`getTokenBalance(uint8 index)`](#ISwapV1-getTokenBalance-uint8-)
- [`getVirtualPrice()`](#ISwapV1-getVirtualPrice--)
- [`isGuarded()`](#ISwapV1-isGuarded--)
- [`calculateSwap(uint8 tokenIndexFrom, uint8 tokenIndexTo, uint256 dx)`](#ISwapV1-calculateSwap-uint8-uint8-uint256-)
- [`calculateTokenAmount(address account, uint256[] amounts, bool deposit)`](#ISwapV1-calculateTokenAmount-address-uint256---bool-)
- [`calculateRemoveLiquidity(address account, uint256 amount)`](#ISwapV1-calculateRemoveLiquidity-address-uint256-)
- [`calculateRemoveLiquidityOneToken(address account, uint256 tokenAmount, uint8 tokenIndex)`](#ISwapV1-calculateRemoveLiquidityOneToken-address-uint256-uint8-)
- [`initialize(contract IERC20[] pooledTokens, uint8[] decimals, string lpTokenName, string lpTokenSymbol, uint256 a, uint256 fee, uint256 adminFee, uint256 withdrawFee, address lpTokenTargetAddress)`](#ISwapV1-initialize-contract-IERC20---uint8---string-string-uint256-uint256-uint256-uint256-address-)
- [`swap(uint8 tokenIndexFrom, uint8 tokenIndexTo, uint256 dx, uint256 minDy, uint256 deadline)`](#ISwapV1-swap-uint8-uint8-uint256-uint256-uint256-)
- [`addLiquidity(uint256[] amounts, uint256 minToMint, uint256 deadline)`](#ISwapV1-addLiquidity-uint256---uint256-uint256-)
- [`removeLiquidity(uint256 amount, uint256[] minAmounts, uint256 deadline)`](#ISwapV1-removeLiquidity-uint256-uint256---uint256-)
- [`removeLiquidityOneToken(uint256 tokenAmount, uint8 tokenIndex, uint256 minAmount, uint256 deadline)`](#ISwapV1-removeLiquidityOneToken-uint256-uint8-uint256-uint256-)
- [`removeLiquidityImbalance(uint256[] amounts, uint256 maxBurnAmount, uint256 deadline)`](#ISwapV1-removeLiquidityImbalance-uint256---uint256-uint256-)
- [`updateUserWithdrawFee(address recipient, uint256 transferAmount)`](#ISwapV1-updateUserWithdrawFee-address-uint256-)

# Function `getA() → uint256` {#ISwapV1-getA--}

No description

# Function `getAllowlist() → contract IAllowlist` {#ISwapV1-getAllowlist--}

No description

# Function `getToken(uint8 index) → contract IERC20` {#ISwapV1-getToken-uint8-}

No description

# Function `getTokenIndex(address tokenAddress) → uint8` {#ISwapV1-getTokenIndex-address-}

No description

# Function `getTokenBalance(uint8 index) → uint256` {#ISwapV1-getTokenBalance-uint8-}

No description

# Function `getVirtualPrice() → uint256` {#ISwapV1-getVirtualPrice--}

No description

# Function `isGuarded() → bool` {#ISwapV1-isGuarded--}

No description

# Function `calculateSwap(uint8 tokenIndexFrom, uint8 tokenIndexTo, uint256 dx) → uint256` {#ISwapV1-calculateSwap-uint8-uint8-uint256-}

No description

# Function `calculateTokenAmount(address account, uint256[] amounts, bool deposit) → uint256` {#ISwapV1-calculateTokenAmount-address-uint256---bool-}

No description

# Function `calculateRemoveLiquidity(address account, uint256 amount) → uint256[]` {#ISwapV1-calculateRemoveLiquidity-address-uint256-}

No description

# Function `calculateRemoveLiquidityOneToken(address account, uint256 tokenAmount, uint8 tokenIndex) → uint256 availableTokenAmount` {#ISwapV1-calculateRemoveLiquidityOneToken-address-uint256-uint8-}

No description

# Function `initialize(contract IERC20[] pooledTokens, uint8[] decimals, string lpTokenName, string lpTokenSymbol, uint256 a, uint256 fee, uint256 adminFee, uint256 withdrawFee, address lpTokenTargetAddress)` {#ISwapV1-initialize-contract-IERC20---uint8---string-string-uint256-uint256-uint256-uint256-address-}

No description

# Function `swap(uint8 tokenIndexFrom, uint8 tokenIndexTo, uint256 dx, uint256 minDy, uint256 deadline) → uint256` {#ISwapV1-swap-uint8-uint8-uint256-uint256-uint256-}

No description

# Function `addLiquidity(uint256[] amounts, uint256 minToMint, uint256 deadline) → uint256` {#ISwapV1-addLiquidity-uint256---uint256-uint256-}

No description

# Function `removeLiquidity(uint256 amount, uint256[] minAmounts, uint256 deadline) → uint256[]` {#ISwapV1-removeLiquidity-uint256-uint256---uint256-}

No description

# Function `removeLiquidityOneToken(uint256 tokenAmount, uint8 tokenIndex, uint256 minAmount, uint256 deadline) → uint256` {#ISwapV1-removeLiquidityOneToken-uint256-uint8-uint256-uint256-}

No description

# Function `removeLiquidityImbalance(uint256[] amounts, uint256 maxBurnAmount, uint256 deadline) → uint256` {#ISwapV1-removeLiquidityImbalance-uint256---uint256-uint256-}

No description

# Function `updateUserWithdrawFee(address recipient, uint256 transferAmount)` {#ISwapV1-updateUserWithdrawFee-address-uint256-}

No description
