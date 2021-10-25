This contract is responsible for custody of closely pegged assets (eg. group of stablecoins)
and automatic market making system. Users become an LP (Liquidity Provider) by depositing their tokens
in desired ratios for an exchange of the pool token that represents their share of the pool.
Users can burn pool tokens and withdraw their share of token(s).

Each time a swap between the pooled tokens happens, a set fee incurs which effectively gets
distributed to the LPs.

In case of emergencies, admin can pause additional deposits, swaps, or single-asset withdraws - which
stops the ratio of the tokens in the pool from changing.
Users can always withdraw their tokens via multi-asset withdraws.

MetaSwap is a modified version of Swap that allows Swap's LP token to be utilized in pooling with other tokens.
As an example, if there is a Swap pool consisting of [DAI, USDC, USDT], then a MetaSwap pool can be created
with [sUSD, BaseSwapLPToken] to allow trades between either the LP token or the underlying tokens and sUSD.
Note that when interacting with MetaSwap, users cannot deposit or withdraw via underlying tokens. In that case,
`MetaSwapDeposit.sol` can be additionally deployed to allow interacting with unwrapped representations of the tokens.

Most of the logic is stored as a library `MetaSwapUtils` for the sake of reducing contract's
deployment size.

# Functions:

- [`getVirtualPrice()`](#MetaSwap-getVirtualPrice--)
- [`calculateSwap(uint8 tokenIndexFrom, uint8 tokenIndexTo, uint256 dx)`](#MetaSwap-calculateSwap-uint8-uint8-uint256-)
- [`calculateSwapUnderlying(uint8 tokenIndexFrom, uint8 tokenIndexTo, uint256 dx)`](#MetaSwap-calculateSwapUnderlying-uint8-uint8-uint256-)
- [`calculateTokenAmount(uint256[] amounts, bool deposit)`](#MetaSwap-calculateTokenAmount-uint256---bool-)
- [`calculateRemoveLiquidityOneToken(uint256 tokenAmount, uint8 tokenIndex)`](#MetaSwap-calculateRemoveLiquidityOneToken-uint256-uint8-)
- [`initialize(contract IERC20[] _pooledTokens, uint8[] decimals, string lpTokenName, string lpTokenSymbol, uint256 _a, uint256 _fee, uint256 _adminFee, address lpTokenTargetAddress)`](#MetaSwap-initialize-contract-IERC20---uint8---string-string-uint256-uint256-uint256-address-)
- [`initializeMetaSwap(contract IERC20[] _pooledTokens, uint8[] decimals, string lpTokenName, string lpTokenSymbol, uint256 _a, uint256 _fee, uint256 _adminFee, address lpTokenTargetAddress, contract ISwap baseSwap)`](#MetaSwap-initializeMetaSwap-contract-IERC20---uint8---string-string-uint256-uint256-uint256-address-contract-ISwap-)
- [`swap(uint8 tokenIndexFrom, uint8 tokenIndexTo, uint256 dx, uint256 minDy, uint256 deadline)`](#MetaSwap-swap-uint8-uint8-uint256-uint256-uint256-)
- [`swapUnderlying(uint8 tokenIndexFrom, uint8 tokenIndexTo, uint256 dx, uint256 minDy, uint256 deadline)`](#MetaSwap-swapUnderlying-uint8-uint8-uint256-uint256-uint256-)
- [`addLiquidity(uint256[] amounts, uint256 minToMint, uint256 deadline)`](#MetaSwap-addLiquidity-uint256---uint256-uint256-)
- [`removeLiquidityOneToken(uint256 tokenAmount, uint8 tokenIndex, uint256 minAmount, uint256 deadline)`](#MetaSwap-removeLiquidityOneToken-uint256-uint8-uint256-uint256-)
- [`removeLiquidityImbalance(uint256[] amounts, uint256 maxBurnAmount, uint256 deadline)`](#MetaSwap-removeLiquidityImbalance-uint256---uint256-uint256-)

# Events:

- [`TokenSwapUnderlying(address buyer, uint256 tokensSold, uint256 tokensBought, uint128 soldId, uint128 boughtId)`](#MetaSwap-TokenSwapUnderlying-address-uint256-uint256-uint128-uint128-)

# Function `getVirtualPrice() → uint256` {#MetaSwap-getVirtualPrice--}

Get the virtual price, to help calculate profit

## Return Values:

- the virtual price, scaled to the POOL_PRECISION_DECIMALS

# Function `calculateSwap(uint8 tokenIndexFrom, uint8 tokenIndexTo, uint256 dx) → uint256` {#MetaSwap-calculateSwap-uint8-uint8-uint256-}

Calculate amount of tokens you receive on swap

## Parameters:

- `tokenIndexFrom`: the token the user wants to sell

- `tokenIndexTo`: the token the user wants to buy

- `dx`: the amount of tokens the user wants to sell. If the token charges
  a fee on transfers, use the amount that gets transferred after the fee.

## Return Values:

- amount of tokens the user will receive

# Function `calculateSwapUnderlying(uint8 tokenIndexFrom, uint8 tokenIndexTo, uint256 dx) → uint256` {#MetaSwap-calculateSwapUnderlying-uint8-uint8-uint256-}

Calculate amount of tokens you receive on swap. For this function,
the token indices are flattened out so that underlying tokens are represented.

## Parameters:

- `tokenIndexFrom`: the token the user wants to sell

- `tokenIndexTo`: the token the user wants to buy

- `dx`: the amount of tokens the user wants to sell. If the token charges
  a fee on transfers, use the amount that gets transferred after the fee.

## Return Values:

- amount of tokens the user will receive

# Function `calculateTokenAmount(uint256[] amounts, bool deposit) → uint256` {#MetaSwap-calculateTokenAmount-uint256---bool-}

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

# Function `calculateRemoveLiquidityOneToken(uint256 tokenAmount, uint8 tokenIndex) → uint256` {#MetaSwap-calculateRemoveLiquidityOneToken-uint256-uint8-}

Calculate the amount of underlying token available to withdraw
when withdrawing via only single token

## Parameters:

- `tokenAmount`: the amount of LP token to burn

- `tokenIndex`: index of which token will be withdrawn

## Return Values:

- availableTokenAmount calculated amount of underlying token
  available to withdraw

# Function `initialize(contract IERC20[] _pooledTokens, uint8[] decimals, string lpTokenName, string lpTokenSymbol, uint256 _a, uint256 _fee, uint256 _adminFee, address lpTokenTargetAddress)` {#MetaSwap-initialize-contract-IERC20---uint8---string-string-uint256-uint256-uint256-address-}

This overrides Swap's initialize function to prevent initializing
without the address of the base Swap contract.

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

# Function `initializeMetaSwap(contract IERC20[] _pooledTokens, uint8[] decimals, string lpTokenName, string lpTokenSymbol, uint256 _a, uint256 _fee, uint256 _adminFee, address lpTokenTargetAddress, contract ISwap baseSwap)` {#MetaSwap-initializeMetaSwap-contract-IERC20---uint8---string-string-uint256-uint256-uint256-address-contract-ISwap-}

Initializes this MetaSwap contract with the given parameters.
MetaSwap uses an existing Swap pool to expand the available liquidity.
\_pooledTokens array should contain the base Swap pool's LP token as
the last element. For example, if there is a Swap pool consisting of
[DAI, USDC, USDT]. Then a MetaSwap pool can be created with [sUSD, BaseSwapLPToken]
as \_pooledTokens.

This will also deploy the LPToken that represents users'
LP position. The owner of LPToken will be this contract - which means
only this contract is allowed to mint new tokens.

## Parameters:

- `_pooledTokens`: an array of ERC20s this pool will accept. The last
  element must be an existing Swap pool's LP token's address.

- `decimals`: the decimals to use for each pooled token,
  eg 8 for WBTC. Cannot be larger than POOL_PRECISION_DECIMALS

- `lpTokenName`: the long-form name of the token to be deployed

- `lpTokenSymbol`: the short symbol for the token to be deployed

- `_a`: the amplification coefficient _ n _ (n - 1). See the
  StableSwap paper for details

- `_fee`: default swap fee to be initialized with

- `_adminFee`: default adminFee to be initialized with

# Function `swap(uint8 tokenIndexFrom, uint8 tokenIndexTo, uint256 dx, uint256 minDy, uint256 deadline) → uint256` {#MetaSwap-swap-uint8-uint8-uint256-uint256-uint256-}

Swap two tokens using this pool

## Parameters:

- `tokenIndexFrom`: the token the user wants to swap from

- `tokenIndexTo`: the token the user wants to swap to

- `dx`: the amount of tokens the user wants to swap from

- `minDy`: the min amount the user would like to receive, or revert.

- `deadline`: latest timestamp to accept this transaction

# Function `swapUnderlying(uint8 tokenIndexFrom, uint8 tokenIndexTo, uint256 dx, uint256 minDy, uint256 deadline) → uint256` {#MetaSwap-swapUnderlying-uint8-uint8-uint256-uint256-uint256-}

Swap two tokens using this pool and the base pool.

## Parameters:

- `tokenIndexFrom`: the token the user wants to swap from

- `tokenIndexTo`: the token the user wants to swap to

- `dx`: the amount of tokens the user wants to swap from

- `minDy`: the min amount the user would like to receive, or revert.

- `deadline`: latest timestamp to accept this transaction

# Function `addLiquidity(uint256[] amounts, uint256 minToMint, uint256 deadline) → uint256` {#MetaSwap-addLiquidity-uint256---uint256-uint256-}

Add liquidity to the pool with the given amounts of tokens

## Parameters:

- `amounts`: the amounts of each token to add, in their native precision

- `minToMint`: the minimum LP tokens adding this amount of liquidity
  should mint, otherwise revert. Handy for front-running mitigation

- `deadline`: latest timestamp to accept this transaction

## Return Values:

- amount of LP token user minted and received

# Function `removeLiquidityOneToken(uint256 tokenAmount, uint8 tokenIndex, uint256 minAmount, uint256 deadline) → uint256` {#MetaSwap-removeLiquidityOneToken-uint256-uint8-uint256-uint256-}

Remove liquidity from the pool all in one token. Withdraw fee that decays linearly
over period of 4 weeks since last deposit will apply.

## Parameters:

- `tokenAmount`: the amount of the token you want to receive

- `tokenIndex`: the index of the token you want to receive

- `minAmount`: the minimum amount to withdraw, otherwise revert

- `deadline`: latest timestamp to accept this transaction

## Return Values:

- amount of chosen token user received

# Function `removeLiquidityImbalance(uint256[] amounts, uint256 maxBurnAmount, uint256 deadline) → uint256` {#MetaSwap-removeLiquidityImbalance-uint256---uint256-uint256-}

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

# Event `TokenSwapUnderlying(address buyer, uint256 tokensSold, uint256 tokensBought, uint128 soldId, uint128 boughtId)` {#MetaSwap-TokenSwapUnderlying-address-uint256-uint256-uint128-uint128-}

No description
