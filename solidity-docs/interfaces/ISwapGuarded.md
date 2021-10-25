# Functions:

- [`getA()`](#ISwapGuarded-getA--)
- [`getAllowlist()`](#ISwapGuarded-getAllowlist--)
- [`getToken(uint8 index)`](#ISwapGuarded-getToken-uint8-)
- [`getTokenIndex(address tokenAddress)`](#ISwapGuarded-getTokenIndex-address-)
- [`getTokenBalance(uint8 index)`](#ISwapGuarded-getTokenBalance-uint8-)
- [`getVirtualPrice()`](#ISwapGuarded-getVirtualPrice--)
- [`isGuarded()`](#ISwapGuarded-isGuarded--)
- [`calculateSwap(uint8 tokenIndexFrom, uint8 tokenIndexTo, uint256 dx)`](#ISwapGuarded-calculateSwap-uint8-uint8-uint256-)
- [`calculateTokenAmount(uint256[] amounts, bool deposit)`](#ISwapGuarded-calculateTokenAmount-uint256---bool-)
- [`calculateRemoveLiquidity(uint256 amount)`](#ISwapGuarded-calculateRemoveLiquidity-uint256-)
- [`calculateRemoveLiquidityOneToken(uint256 tokenAmount, uint8 tokenIndex)`](#ISwapGuarded-calculateRemoveLiquidityOneToken-uint256-uint8-)
- [`swap(uint8 tokenIndexFrom, uint8 tokenIndexTo, uint256 dx, uint256 minDy, uint256 deadline)`](#ISwapGuarded-swap-uint8-uint8-uint256-uint256-uint256-)
- [`addLiquidity(uint256[] amounts, uint256 minToMint, uint256 deadline, bytes32[] merkleProof)`](#ISwapGuarded-addLiquidity-uint256---uint256-uint256-bytes32---)
- [`removeLiquidity(uint256 amount, uint256[] minAmounts, uint256 deadline)`](#ISwapGuarded-removeLiquidity-uint256-uint256---uint256-)
- [`removeLiquidityOneToken(uint256 tokenAmount, uint8 tokenIndex, uint256 minAmount, uint256 deadline)`](#ISwapGuarded-removeLiquidityOneToken-uint256-uint8-uint256-uint256-)
- [`removeLiquidityImbalance(uint256[] amounts, uint256 maxBurnAmount, uint256 deadline)`](#ISwapGuarded-removeLiquidityImbalance-uint256---uint256-uint256-)
- [`updateUserWithdrawFee(address recipient, uint256 transferAmount)`](#ISwapGuarded-updateUserWithdrawFee-address-uint256-)

# Function `getA() → uint256` {#ISwapGuarded-getA--}

No description

# Function `getAllowlist() → contract IAllowlist` {#ISwapGuarded-getAllowlist--}

No description

# Function `getToken(uint8 index) → contract IERC20` {#ISwapGuarded-getToken-uint8-}

No description

# Function `getTokenIndex(address tokenAddress) → uint8` {#ISwapGuarded-getTokenIndex-address-}

No description

# Function `getTokenBalance(uint8 index) → uint256` {#ISwapGuarded-getTokenBalance-uint8-}

No description

# Function `getVirtualPrice() → uint256` {#ISwapGuarded-getVirtualPrice--}

No description

# Function `isGuarded() → bool` {#ISwapGuarded-isGuarded--}

No description

# Function `calculateSwap(uint8 tokenIndexFrom, uint8 tokenIndexTo, uint256 dx) → uint256` {#ISwapGuarded-calculateSwap-uint8-uint8-uint256-}

No description

# Function `calculateTokenAmount(uint256[] amounts, bool deposit) → uint256` {#ISwapGuarded-calculateTokenAmount-uint256---bool-}

No description

# Function `calculateRemoveLiquidity(uint256 amount) → uint256[]` {#ISwapGuarded-calculateRemoveLiquidity-uint256-}

No description

# Function `calculateRemoveLiquidityOneToken(uint256 tokenAmount, uint8 tokenIndex) → uint256 availableTokenAmount` {#ISwapGuarded-calculateRemoveLiquidityOneToken-uint256-uint8-}

No description

# Function `swap(uint8 tokenIndexFrom, uint8 tokenIndexTo, uint256 dx, uint256 minDy, uint256 deadline) → uint256` {#ISwapGuarded-swap-uint8-uint8-uint256-uint256-uint256-}

No description

# Function `addLiquidity(uint256[] amounts, uint256 minToMint, uint256 deadline, bytes32[] merkleProof) → uint256` {#ISwapGuarded-addLiquidity-uint256---uint256-uint256-bytes32---}

No description

# Function `removeLiquidity(uint256 amount, uint256[] minAmounts, uint256 deadline) → uint256[]` {#ISwapGuarded-removeLiquidity-uint256-uint256---uint256-}

No description

# Function `removeLiquidityOneToken(uint256 tokenAmount, uint8 tokenIndex, uint256 minAmount, uint256 deadline) → uint256` {#ISwapGuarded-removeLiquidityOneToken-uint256-uint8-uint256-uint256-}

No description

# Function `removeLiquidityImbalance(uint256[] amounts, uint256 maxBurnAmount, uint256 deadline) → uint256` {#ISwapGuarded-removeLiquidityImbalance-uint256---uint256-uint256-}

No description

# Function `updateUserWithdrawFee(address recipient, uint256 transferAmount)` {#ISwapGuarded-updateUserWithdrawFee-address-uint256-}

No description
