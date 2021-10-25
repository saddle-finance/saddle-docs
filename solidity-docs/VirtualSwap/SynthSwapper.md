Replacement of Virtual Synths in favor of gas savings. Allows swapping synths via the Synthetix protocol
or Saddle's pools. The `Bridge.sol` contract will deploy minimal clones of this contract upon initiating
any cross-asset swaps.

# Functions:

- [`constructor()`](#SynthSwapper-constructor--)
- [`initialize()`](#SynthSwapper-initialize--)
- [`swapSynth(bytes32 sourceKey, uint256 synthAmount, bytes32 destKey)`](#SynthSwapper-swapSynth-bytes32-uint256-bytes32-)
- [`swapSynthToToken(contract ISwap swap, contract IERC20 tokenFrom, uint8 tokenFromIndex, uint8 tokenToIndex, uint256 tokenFromAmount, uint256 minAmount, uint256 deadline, address recipient)`](#SynthSwapper-swapSynthToToken-contract-ISwap-contract-IERC20-uint8-uint8-uint256-uint256-uint256-address-)
- [`withdraw(contract IERC20 token, address recipient, uint256 withdrawAmount, bool shouldDestroy)`](#SynthSwapper-withdraw-contract-IERC20-address-uint256-bool-)
- [`destroy()`](#SynthSwapper-destroy--)

# Function `constructor()` {#SynthSwapper-constructor--}

Initializes the contract when deploying this directly. This prevents
others from calling initialize() on the target contract and setting themself as the owner.

# Function `initialize()` {#SynthSwapper-initialize--}

Sets the `owner` as the caller of this function

# Function `swapSynth(bytes32 sourceKey, uint256 synthAmount, bytes32 destKey) → uint256` {#SynthSwapper-swapSynth-bytes32-uint256-bytes32-}

Swaps the synth to another synth via the Synthetix protocol.

## Parameters:

- `sourceKey`: currency key of the source synth

- `synthAmount`: amount of the synth to swap

- `destKey`: currency key of the destination synth

## Return Values:

- amount of the destination synth received

# Function `swapSynthToToken(contract ISwap swap, contract IERC20 tokenFrom, uint8 tokenFromIndex, uint8 tokenToIndex, uint256 tokenFromAmount, uint256 minAmount, uint256 deadline, address recipient) → contract IERC20, uint256` {#SynthSwapper-swapSynthToToken-contract-ISwap-contract-IERC20-uint8-uint8-uint256-uint256-uint256-address-}

Approves the given `tokenFrom` and swaps it to another token via the given `swap` pool.

## Parameters:

- `swap`: the address of a pool to swap through

- `tokenFrom`: the address of the stored synth

- `tokenFromIndex`: the index of the token to swap from

- `tokenToIndex`: the token the user wants to swap to

- `tokenFromAmount`: the amount of the token to swap

- `minAmount`: the min amount the user would like to receive, or revert.

- `deadline`: latest timestamp to accept this transaction

- `recipient`: the address of the recipient

# Function `withdraw(contract IERC20 token, address recipient, uint256 withdrawAmount, bool shouldDestroy)` {#SynthSwapper-withdraw-contract-IERC20-address-uint256-bool-}

Withdraws the given amount of `token` to the `recipient`.

## Parameters:

- `token`: the address of the token to withdraw

- `recipient`: the address of the account to receive the token

- `withdrawAmount`: the amount of the token to withdraw

- `shouldDestroy`: whether this contract should be destroyed after this call

# Function `destroy()` {#SynthSwapper-destroy--}

Destroys this contract. Only owner can call this function.
