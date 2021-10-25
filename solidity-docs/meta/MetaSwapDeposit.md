This contract flattens the LP token in a MetaSwap pool for easier user access. MetaSwap must be
deployed before this contract can be initialized successfully.

For example, suppose there exists a base Swap pool consisting of [DAI, USDC, USDT].
Then a MetaSwap pool can be created with [sUSD, BaseSwapLPToken] to allow trades between either
the LP token or the underlying tokens and sUSD.

MetaSwapDeposit flattens the LP token and remaps them to a single array, allowing users
to ignore the dependency on BaseSwapLPToken. Using the above example, MetaSwapDeposit can act
as a Swap containing [sUSD, DAI, USDC, USDT] tokens.

# Functions:

- [`initialize(contract ISwap _baseSwap, contract IMetaSwap _metaSwap, contract IERC20 _metaLPToken)`](#MetaSwapDeposit-initialize-contract-ISwap-contract-IMetaSwap-contract-IERC20-)
- [`swap(uint8 tokenIndexFrom, uint8 tokenIndexTo, uint256 dx, uint256 minDy, uint256 deadline)`](#MetaSwapDeposit-swap-uint8-uint8-uint256-uint256-uint256-)
- [`addLiquidity(uint256[] amounts, uint256 minToMint, uint256 deadline)`](#MetaSwapDeposit-addLiquidity-uint256---uint256-uint256-)
- [`removeLiquidity(uint256 amount, uint256[] minAmounts, uint256 deadline)`](#MetaSwapDeposit-removeLiquidity-uint256-uint256---uint256-)
- [`removeLiquidityOneToken(uint256 tokenAmount, uint8 tokenIndex, uint256 minAmount, uint256 deadline)`](#MetaSwapDeposit-removeLiquidityOneToken-uint256-uint8-uint256-uint256-)
- [`removeLiquidityImbalance(uint256[] amounts, uint256 maxBurnAmount, uint256 deadline)`](#MetaSwapDeposit-removeLiquidityImbalance-uint256---uint256-uint256-)
- [`calculateTokenAmount(uint256[] amounts, bool deposit)`](#MetaSwapDeposit-calculateTokenAmount-uint256---bool-)
- [`calculateRemoveLiquidity(uint256 amount)`](#MetaSwapDeposit-calculateRemoveLiquidity-uint256-)
- [`calculateRemoveLiquidityOneToken(uint256 tokenAmount, uint8 tokenIndex)`](#MetaSwapDeposit-calculateRemoveLiquidityOneToken-uint256-uint8-)
- [`getToken(uint8 index)`](#MetaSwapDeposit-getToken-uint8-)
- [`calculateSwap(uint8 tokenIndexFrom, uint8 tokenIndexTo, uint256 dx)`](#MetaSwapDeposit-calculateSwap-uint8-uint8-uint256-)

# Function `initialize(contract ISwap _baseSwap, contract IMetaSwap _metaSwap, contract IERC20 _metaLPToken)` {#MetaSwapDeposit-initialize-contract-ISwap-contract-IMetaSwap-contract-IERC20-}

Sets the address for the base Swap contract, MetaSwap contract, and the
MetaSwap LP token contract.

## Parameters:

- `_baseSwap`: the address of the base Swap contract

- `_metaSwap`: the address of the MetaSwap contract

- `_metaLPToken`: the address of the MetaSwap LP token contract

# Function `swap(uint8 tokenIndexFrom, uint8 tokenIndexTo, uint256 dx, uint256 minDy, uint256 deadline) → uint256` {#MetaSwapDeposit-swap-uint8-uint8-uint256-uint256-uint256-}

Swap two underlying tokens using the meta pool and the base pool

## Parameters:

- `tokenIndexFrom`: the token the user wants to swap from

- `tokenIndexTo`: the token the user wants to swap to

- `dx`: the amount of tokens the user wants to swap from

- `minDy`: the min amount the user would like to receive, or revert.

- `deadline`: latest timestamp to accept this transaction

# Function `addLiquidity(uint256[] amounts, uint256 minToMint, uint256 deadline) → uint256` {#MetaSwapDeposit-addLiquidity-uint256---uint256-uint256-}

Add liquidity to the pool with the given amounts of tokens

## Parameters:

- `amounts`: the amounts of each token to add, in their native precision

- `minToMint`: the minimum LP tokens adding this amount of liquidity
  should mint, otherwise revert. Handy for front-running mitigation

- `deadline`: latest timestamp to accept this transaction

## Return Values:

- amount of LP token user minted and received

# Function `removeLiquidity(uint256 amount, uint256[] minAmounts, uint256 deadline) → uint256[]` {#MetaSwapDeposit-removeLiquidity-uint256-uint256---uint256-}

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

# Function `removeLiquidityOneToken(uint256 tokenAmount, uint8 tokenIndex, uint256 minAmount, uint256 deadline) → uint256` {#MetaSwapDeposit-removeLiquidityOneToken-uint256-uint8-uint256-uint256-}

Remove liquidity from the pool all in one token. Withdraw fee that decays linearly
over period of 4 weeks since last deposit will apply.

## Parameters:

- `tokenAmount`: the amount of the token you want to receive

- `tokenIndex`: the index of the token you want to receive

- `minAmount`: the minimum amount to withdraw, otherwise revert

- `deadline`: latest timestamp to accept this transaction

## Return Values:

- amount of chosen token user received

# Function `removeLiquidityImbalance(uint256[] amounts, uint256 maxBurnAmount, uint256 deadline) → uint256` {#MetaSwapDeposit-removeLiquidityImbalance-uint256---uint256-uint256-}

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

# Function `calculateTokenAmount(uint256[] amounts, bool deposit) → uint256` {#MetaSwapDeposit-calculateTokenAmount-uint256---bool-}

A simple method to calculate prices from deposits or
withdrawals, excluding fees but including slippage. This is
helpful as an input into the various "min" parameters on calls
to fight front-running. When withdrawing from the base pool in imbalanced
fashion, the recommended slippage setting is 0.2% or higher.

This shouldn't be used outside frontends for user estimates.

## Parameters:

- `amounts`: an array of token amounts to deposit or withdrawal,
  corresponding to pooledTokens. The amount should be in each
  pooled token's native precision. If a token charges a fee on transfers,
  use the amount that gets transferred after the fee.

- `deposit`: whether this is a deposit or a withdrawal

## Return Values:

- token amount the user will receive

# Function `calculateRemoveLiquidity(uint256 amount) → uint256[]` {#MetaSwapDeposit-calculateRemoveLiquidity-uint256-}

A simple method to calculate amount of each underlying
tokens that is returned upon burning given amount of LP tokens

## Parameters:

- `amount`: the amount of LP tokens that would be burned on withdrawal

## Return Values:

- array of token balances that the user will receive

# Function `calculateRemoveLiquidityOneToken(uint256 tokenAmount, uint8 tokenIndex) → uint256` {#MetaSwapDeposit-calculateRemoveLiquidityOneToken-uint256-uint8-}

Calculate the amount of underlying token available to withdraw
when withdrawing via only single token

## Parameters:

- `tokenAmount`: the amount of LP token to burn

- `tokenIndex`: index of which token will be withdrawn

## Return Values:

- availableTokenAmount calculated amount of underlying token
  available to withdraw

# Function `getToken(uint8 index) → contract IERC20` {#MetaSwapDeposit-getToken-uint8-}

Returns the address of the pooled token at given index. Reverts if tokenIndex is out of range.
This is a flattened representation of the pooled tokens.

## Parameters:

- `index`: the index of the token

## Return Values:

- address of the token at given index

# Function `calculateSwap(uint8 tokenIndexFrom, uint8 tokenIndexTo, uint256 dx) → uint256` {#MetaSwapDeposit-calculateSwap-uint8-uint8-uint256-}

Calculate amount of tokens you receive on swap

## Parameters:

- `tokenIndexFrom`: the token the user wants to sell

- `tokenIndexTo`: the token the user wants to buy

- `dx`: the amount of tokens the user wants to sell. If the token charges
  a fee on transfers, use the amount that gets transferred after the fee.

## Return Values:

- amount of tokens the user will receive
