# Functions:

- [`getA()`](#IMetaSwap-getA--)
- [`getToken(uint8 index)`](#IMetaSwap-getToken-uint8-)
- [`getTokenIndex(address tokenAddress)`](#IMetaSwap-getTokenIndex-address-)
- [`getTokenBalance(uint8 index)`](#IMetaSwap-getTokenBalance-uint8-)
- [`getVirtualPrice()`](#IMetaSwap-getVirtualPrice--)
- [`isGuarded()`](#IMetaSwap-isGuarded--)
- [`calculateSwap(uint8 tokenIndexFrom, uint8 tokenIndexTo, uint256 dx)`](#IMetaSwap-calculateSwap-uint8-uint8-uint256-)
- [`calculateSwapUnderlying(uint8 tokenIndexFrom, uint8 tokenIndexTo, uint256 dx)`](#IMetaSwap-calculateSwapUnderlying-uint8-uint8-uint256-)
- [`calculateTokenAmount(uint256[] amounts, bool deposit)`](#IMetaSwap-calculateTokenAmount-uint256---bool-)
- [`calculateRemoveLiquidity(uint256 amount)`](#IMetaSwap-calculateRemoveLiquidity-uint256-)
- [`calculateRemoveLiquidityOneToken(uint256 tokenAmount, uint8 tokenIndex)`](#IMetaSwap-calculateRemoveLiquidityOneToken-uint256-uint8-)
- [`initialize(contract IERC20[] _pooledTokens, uint8[] decimals, string lpTokenName, string lpTokenSymbol, uint256 _a, uint256 _fee, uint256 _adminFee, address lpTokenTargetAddress)`](#IMetaSwap-initialize-contract-IERC20---uint8---string-string-uint256-uint256-uint256-address-)
- [`initializeMetaSwap(contract IERC20[] _pooledTokens, uint8[] decimals, string lpTokenName, string lpTokenSymbol, uint256 _a, uint256 _fee, uint256 _adminFee, address lpTokenTargetAddress, contract ISwap baseSwap)`](#IMetaSwap-initializeMetaSwap-contract-IERC20---uint8---string-string-uint256-uint256-uint256-address-contract-ISwap-)
- [`swap(uint8 tokenIndexFrom, uint8 tokenIndexTo, uint256 dx, uint256 minDy, uint256 deadline)`](#IMetaSwap-swap-uint8-uint8-uint256-uint256-uint256-)
- [`swapUnderlying(uint8 tokenIndexFrom, uint8 tokenIndexTo, uint256 dx, uint256 minDy, uint256 deadline)`](#IMetaSwap-swapUnderlying-uint8-uint8-uint256-uint256-uint256-)
- [`addLiquidity(uint256[] amounts, uint256 minToMint, uint256 deadline)`](#IMetaSwap-addLiquidity-uint256---uint256-uint256-)
- [`removeLiquidity(uint256 amount, uint256[] minAmounts, uint256 deadline)`](#IMetaSwap-removeLiquidity-uint256-uint256---uint256-)
- [`removeLiquidityOneToken(uint256 tokenAmount, uint8 tokenIndex, uint256 minAmount, uint256 deadline)`](#IMetaSwap-removeLiquidityOneToken-uint256-uint8-uint256-uint256-)
- [`removeLiquidityImbalance(uint256[] amounts, uint256 maxBurnAmount, uint256 deadline)`](#IMetaSwap-removeLiquidityImbalance-uint256---uint256-uint256-)

# Function `getA() → uint256` {#IMetaSwap-getA--}

No description

# Function `getToken(uint8 index) → contract IERC20` {#IMetaSwap-getToken-uint8-}

No description

# Function `getTokenIndex(address tokenAddress) → uint8` {#IMetaSwap-getTokenIndex-address-}

No description

# Function `getTokenBalance(uint8 index) → uint256` {#IMetaSwap-getTokenBalance-uint8-}

No description

# Function `getVirtualPrice() → uint256` {#IMetaSwap-getVirtualPrice--}

No description

# Function `isGuarded() → bool` {#IMetaSwap-isGuarded--}

No description

# Function `calculateSwap(uint8 tokenIndexFrom, uint8 tokenIndexTo, uint256 dx) → uint256` {#IMetaSwap-calculateSwap-uint8-uint8-uint256-}

No description

# Function `calculateSwapUnderlying(uint8 tokenIndexFrom, uint8 tokenIndexTo, uint256 dx) → uint256` {#IMetaSwap-calculateSwapUnderlying-uint8-uint8-uint256-}

No description

# Function `calculateTokenAmount(uint256[] amounts, bool deposit) → uint256` {#IMetaSwap-calculateTokenAmount-uint256---bool-}

No description

# Function `calculateRemoveLiquidity(uint256 amount) → uint256[]` {#IMetaSwap-calculateRemoveLiquidity-uint256-}

No description

# Function `calculateRemoveLiquidityOneToken(uint256 tokenAmount, uint8 tokenIndex) → uint256 availableTokenAmount` {#IMetaSwap-calculateRemoveLiquidityOneToken-uint256-uint8-}

No description

# Function `initialize(contract IERC20[] _pooledTokens, uint8[] decimals, string lpTokenName, string lpTokenSymbol, uint256 _a, uint256 _fee, uint256 _adminFee, address lpTokenTargetAddress)` {#IMetaSwap-initialize-contract-IERC20---uint8---string-string-uint256-uint256-uint256-address-}

No description

# Function `initializeMetaSwap(contract IERC20[] _pooledTokens, uint8[] decimals, string lpTokenName, string lpTokenSymbol, uint256 _a, uint256 _fee, uint256 _adminFee, address lpTokenTargetAddress, contract ISwap baseSwap)` {#IMetaSwap-initializeMetaSwap-contract-IERC20---uint8---string-string-uint256-uint256-uint256-address-contract-ISwap-}

No description

# Function `swap(uint8 tokenIndexFrom, uint8 tokenIndexTo, uint256 dx, uint256 minDy, uint256 deadline) → uint256` {#IMetaSwap-swap-uint8-uint8-uint256-uint256-uint256-}

No description

# Function `swapUnderlying(uint8 tokenIndexFrom, uint8 tokenIndexTo, uint256 dx, uint256 minDy, uint256 deadline) → uint256` {#IMetaSwap-swapUnderlying-uint8-uint8-uint256-uint256-uint256-}

No description

# Function `addLiquidity(uint256[] amounts, uint256 minToMint, uint256 deadline) → uint256` {#IMetaSwap-addLiquidity-uint256---uint256-uint256-}

No description

# Function `removeLiquidity(uint256 amount, uint256[] minAmounts, uint256 deadline) → uint256[]` {#IMetaSwap-removeLiquidity-uint256-uint256---uint256-}

No description

# Function `removeLiquidityOneToken(uint256 tokenAmount, uint8 tokenIndex, uint256 minAmount, uint256 deadline) → uint256` {#IMetaSwap-removeLiquidityOneToken-uint256-uint8-uint256-uint256-}

No description

# Function `removeLiquidityImbalance(uint256[] amounts, uint256 maxBurnAmount, uint256 deadline) → uint256` {#IMetaSwap-removeLiquidityImbalance-uint256---uint256-uint256-}

No description
