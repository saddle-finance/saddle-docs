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

- [`initialize(contract IERC20[] _pooledTokens, uint8[] decimals, string lpTokenName, string lpTokenSymbol, uint256 _a, uint256 _fee, uint256 _adminFee, address lpTokenTargetAddress)`](#SwapFlashLoan-initialize-contract-IERC20---uint8---string-string-uint256-uint256-uint256-address-)
- [`flashLoan(address receiver, contract IERC20 token, uint256 amount, bytes params)`](#SwapFlashLoan-flashLoan-address-contract-IERC20-uint256-bytes-)
- [`setFlashLoanFees(uint256 newFlashLoanFeeBPS, uint256 newProtocolFeeShareBPS)`](#SwapFlashLoan-setFlashLoanFees-uint256-uint256-)

# Events:

- [`FlashLoan(address receiver, uint8 tokenIndex, uint256 amount, uint256 amountFee, uint256 protocolFee)`](#SwapFlashLoan-FlashLoan-address-uint8-uint256-uint256-uint256-)

# Function `initialize(contract IERC20[] _pooledTokens, uint8[] decimals, string lpTokenName, string lpTokenSymbol, uint256 _a, uint256 _fee, uint256 _adminFee, address lpTokenTargetAddress)` {#SwapFlashLoan-initialize-contract-IERC20---uint8---string-string-uint256-uint256-uint256-address-}

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

# Function `flashLoan(address receiver, contract IERC20 token, uint256 amount, bytes params)` {#SwapFlashLoan-flashLoan-address-contract-IERC20-uint256-bytes-}

Borrow the specified token from this pool for this transaction only. This function will call
`IFlashLoanReceiver(receiver).executeOperation` and the `receiver` must return the full amount of the token
and the associated fee by the end of the callback transaction. If the conditions are not met, this call
is reverted.

## Parameters:

- `receiver`: the address of the receiver of the token. This address must implement the IFlashLoanReceiver
  interface and the callback function `executeOperation`.

- `token`: the protocol fee in bps to be applied on the total flash loan fee

- `amount`: the total amount to borrow in this transaction

- `params`: optional data to pass along to the callback function

# Function `setFlashLoanFees(uint256 newFlashLoanFeeBPS, uint256 newProtocolFeeShareBPS)` {#SwapFlashLoan-setFlashLoanFees-uint256-uint256-}

Updates the flash loan fee parameters. This function can only be called by the owner.

## Parameters:

- `newFlashLoanFeeBPS`: the total fee in bps to be applied on future flash loans

- `newProtocolFeeShareBPS`: the protocol fee in bps to be applied on the total flash loan fee

# Event `FlashLoan(address receiver, uint8 tokenIndex, uint256 amount, uint256 amountFee, uint256 protocolFee)` {#SwapFlashLoan-FlashLoan-address-uint8-uint256-uint256-uint256-}

No description
