This contract is responsible for cross-asset swaps using the Synthetix protocol as the bridging exchange.
There are three types of supported cross-asset swaps, tokenToSynth, synthToToken, and tokenToToken.

1. tokenToSynth
   Swaps a supported token in a saddle pool to any synthetic asset (e.g. tBTC -> sAAVE).

2. synthToToken
   Swaps any synthetic asset to a suported token in a saddle pool (e.g. sDEFI -> USDC).

3. tokenToToken
   Swaps a supported token in a saddle pool to one in another pool (e.g. renBTC -> DAI).

Due to the settlement periods of synthetic assets, the users must wait until the trades can be completed.
Users will receive an ERC721 token that represents pending cross-asset swap. Once the waiting period is over,
the trades can be settled and completed by calling the `completeToSynth` or the `completeToToken` function.
In the cases of pending `synthToToken` or `tokenToToken` swaps, the owners of the pending swaps can also choose
to withdraw the bridging synthetic assets instead of completing the swap.

# Functions:

- [`constructor(address synthSwapperAddress)`](#Bridge-constructor-address-)
- [`getProxyAddressFromTargetSynthKey(bytes32 synthKey)`](#Bridge-getProxyAddressFromTargetSynthKey-bytes32-)
- [`getPendingSwapInfo(uint256 itemId)`](#Bridge-getPendingSwapInfo-uint256-)
- [`withdraw(uint256 itemId, uint256 amount)`](#Bridge-withdraw-uint256-uint256-)
- [`completeToSynth(uint256 itemId)`](#Bridge-completeToSynth-uint256-)
- [`calcCompleteToToken(uint256 itemId, uint256 swapAmount)`](#Bridge-calcCompleteToToken-uint256-uint256-)
- [`completeToToken(uint256 itemId, uint256 swapAmount, uint256 minAmount, uint256 deadline)`](#Bridge-completeToToken-uint256-uint256-uint256-uint256-)
- [`calcTokenToSynth(contract ISwap swap, uint8 tokenFromIndex, bytes32 synthOutKey, uint256 tokenInAmount)`](#Bridge-calcTokenToSynth-contract-ISwap-uint8-bytes32-uint256-)
- [`tokenToSynth(contract ISwap swap, uint8 tokenFromIndex, bytes32 synthOutKey, uint256 tokenInAmount, uint256 minAmount)`](#Bridge-tokenToSynth-contract-ISwap-uint8-bytes32-uint256-uint256-)
- [`calcSynthToToken(contract ISwap swap, bytes32 synthInKey, uint8 tokenToIndex, uint256 synthInAmount)`](#Bridge-calcSynthToToken-contract-ISwap-bytes32-uint8-uint256-)
- [`synthToToken(contract ISwap swap, bytes32 synthInKey, uint8 tokenToIndex, uint256 synthInAmount, uint256 minMediumSynthAmount)`](#Bridge-synthToToken-contract-ISwap-bytes32-uint8-uint256-uint256-)
- [`calcTokenToToken(contract ISwap[2] swaps, uint8 tokenFromIndex, uint8 tokenToIndex, uint256 tokenFromAmount)`](#Bridge-calcTokenToToken-contract-ISwap-2--uint8-uint8-uint256-)
- [`tokenToToken(contract ISwap[2] swaps, uint8 tokenFromIndex, uint8 tokenToIndex, uint256 tokenFromAmount, uint256 minMediumSynthAmount)`](#Bridge-tokenToToken-contract-ISwap-2--uint8-uint8-uint256-uint256-)
- [`setSynthIndex(contract ISwap swap, uint8 synthIndex, bytes32 currencyKey)`](#Bridge-setSynthIndex-contract-ISwap-uint8-bytes32-)
- [`getSynthIndex(contract ISwap swap)`](#Bridge-getSynthIndex-contract-ISwap-)
- [`getSynthAddress(contract ISwap swap)`](#Bridge-getSynthAddress-contract-ISwap-)
- [`getSynthKey(contract ISwap swap)`](#Bridge-getSynthKey-contract-ISwap-)
- [`updateExchangerCache()`](#Bridge-updateExchangerCache--)

# Events:

- [`SynthIndex(address swap, uint8 synthIndex, bytes32 currencyKey, address synthAddress)`](#Bridge-SynthIndex-address-uint8-bytes32-address-)
- [`TokenToSynth(address requester, uint256 itemId, contract ISwap swapPool, uint8 tokenFromIndex, uint256 tokenFromInAmount, bytes32 synthToKey)`](#Bridge-TokenToSynth-address-uint256-contract-ISwap-uint8-uint256-bytes32-)
- [`SynthToToken(address requester, uint256 itemId, contract ISwap swapPool, bytes32 synthFromKey, uint256 synthFromInAmount, uint8 tokenToIndex)`](#Bridge-SynthToToken-address-uint256-contract-ISwap-bytes32-uint256-uint8-)
- [`TokenToToken(address requester, uint256 itemId, contract ISwap[2] swapPools, uint8 tokenFromIndex, uint256 tokenFromAmount, uint8 tokenToIndex)`](#Bridge-TokenToToken-address-uint256-contract-ISwap-2--uint8-uint256-uint8-)
- [`Settle(address requester, uint256 itemId, contract IERC20 settleFrom, uint256 settleFromAmount, contract IERC20 settleTo, uint256 settleToAmount, bool isFinal)`](#Bridge-Settle-address-uint256-contract-IERC20-uint256-contract-IERC20-uint256-bool-)
- [`Withdraw(address requester, uint256 itemId, contract IERC20 synth, uint256 synthAmount, bool isFinal)`](#Bridge-Withdraw-address-uint256-contract-IERC20-uint256-bool-)

# Function `constructor(address synthSwapperAddress)` {#Bridge-constructor-address-}

Deploys this contract and initializes the master version of the SynthSwapper contract. The address to
the Synthetix protocol's Exchanger contract is also set on deployment.

# Function `getProxyAddressFromTargetSynthKey(bytes32 synthKey) → contract IERC20` {#Bridge-getProxyAddressFromTargetSynthKey-bytes32-}

Returns the address of the proxy contract targeting the synthetic asset with the given `synthKey`.

## Parameters:

- `synthKey`: the currency key of the synth

## Return Values:

- address of the proxy contract

# Function `getPendingSwapInfo(uint256 itemId) → enum Bridge.PendingSwapType swapType, uint256 secsLeft, address synth, uint256 synthBalance, address tokenTo` {#Bridge-getPendingSwapInfo-uint256-}

Returns various information of a pending swap represented by the given `itemId`. Information includes
the type of the pending swap, the number of seconds left until it can be settled, the address and the balance
of the synth this swap currently holds, and the address of the destination token.

## Parameters:

- `itemId`: ID of the pending swap

## Return Values:

- swapType the type of the pending virtual swap,
  secsLeft number of seconds left until this swap can be settled,
  synth address of the synth this swap uses,
  synthBalance amount of the synth this swap holds,
  tokenTo the address of the destination token

# Function `withdraw(uint256 itemId, uint256 amount)` {#Bridge-withdraw-uint256-uint256-}

Settles and withdraws the synthetic asset without swapping it to a token in a Saddle pool. Only the owner
of the ERC721 token of `itemId` can call this function. Reverts if the given `itemId` does not represent a
`synthToToken` or a `tokenToToken` swap.

## Parameters:

- `itemId`: ID of the pending swap

- `amount`: the amount of the synth to withdraw

# Function `completeToSynth(uint256 itemId)` {#Bridge-completeToSynth-uint256-}

Completes the pending `tokenToSynth` swap by settling and withdrawing the synthetic asset.
Reverts if the given `itemId` does not represent a `tokenToSynth` swap.

## Parameters:

- `itemId`: ERC721 token ID representing a pending `tokenToSynth` swap

# Function `calcCompleteToToken(uint256 itemId, uint256 swapAmount) → uint256` {#Bridge-calcCompleteToToken-uint256-uint256-}

Calculates the expected amount of the token to receive on calling `completeToToken()` with
the given `swapAmount`.

## Parameters:

- `itemId`: ERC721 token ID representing a pending `SynthToToken` or `TokenToToken` swap

- `swapAmount`: the amount of bridging synth to swap from

## Return Values:

- expected amount of the token the user will receive

# Function `completeToToken(uint256 itemId, uint256 swapAmount, uint256 minAmount, uint256 deadline)` {#Bridge-completeToToken-uint256-uint256-uint256-uint256-}

Completes the pending `SynthToToken` or `TokenToToken` swap by settling the bridging synth and swapping
it to the desired token. Only the owners of the pending swaps can call this function.

## Parameters:

- `itemId`: ERC721 token ID representing a pending `SynthToToken` or `TokenToToken` swap

- `swapAmount`: the amount of bridging synth to swap from

- `minAmount`: the minimum amount of the token to receive - reverts if this amount is not reached

- `deadline`: the timestamp representing the deadline for this transaction - reverts if deadline is not met

# Function `calcTokenToSynth(contract ISwap swap, uint8 tokenFromIndex, bytes32 synthOutKey, uint256 tokenInAmount) → uint256` {#Bridge-calcTokenToSynth-contract-ISwap-uint8-bytes32-uint256-}

Calculates the expected amount of the desired synthetic asset the caller will receive after completing
a `TokenToSynth` swap with the given parameters. This calculation does not consider the settlement periods.

## Parameters:

- `swap`: the address of a Saddle pool to use to swap the given token to a bridging synth

- `tokenFromIndex`: the index of the token to swap from

- `synthOutKey`: the currency key of the desired synthetic asset

- `tokenInAmount`: the amount of the token to swap form

## Return Values:

- the expected amount of the desired synth

# Function `tokenToSynth(contract ISwap swap, uint8 tokenFromIndex, bytes32 synthOutKey, uint256 tokenInAmount, uint256 minAmount) → uint256` {#Bridge-tokenToSynth-contract-ISwap-uint8-bytes32-uint256-uint256-}

Initiates a cross-asset swap from a token supported in the `swap` pool to any synthetic asset.
The caller will receive an ERC721 token representing their ownership of the pending cross-asset swap.

## Parameters:

- `swap`: the address of a Saddle pool to use to swap the given token to a bridging synth

- `tokenFromIndex`: the index of the token to swap from

- `synthOutKey`: the currency key of the desired synthetic asset

- `tokenInAmount`: the amount of the token to swap form

- `minAmount`: the amount of the token to swap form

## Return Values:

- ID of the ERC721 token sent to the caller

# Function `calcSynthToToken(contract ISwap swap, bytes32 synthInKey, uint8 tokenToIndex, uint256 synthInAmount) → uint256, uint256` {#Bridge-calcSynthToToken-contract-ISwap-bytes32-uint8-uint256-}

Calculates the expected amount of the desired token the caller will receive after completing
a `SynthToToken` swap with the given parameters. This calculation does not consider the settlement periods or
any potential changes of the `swap` pool composition.

## Parameters:

- `swap`: the address of a Saddle pool to use to swap the given token to a bridging synth

- `synthInKey`: the currency key of the synth to swap from

- `tokenToIndex`: the index of the token to swap to

- `synthInAmount`: the amount of the synth to swap form

## Return Values:

- the expected amount of the bridging synth and the expected amount of the desired token

# Function `synthToToken(contract ISwap swap, bytes32 synthInKey, uint8 tokenToIndex, uint256 synthInAmount, uint256 minMediumSynthAmount) → uint256` {#Bridge-synthToToken-contract-ISwap-bytes32-uint8-uint256-uint256-}

Initiates a cross-asset swap from a synthetic asset to a supported token. The caller will receive
an ERC721 token representing their ownership of the pending cross-asset swap.

## Parameters:

- `swap`: the address of a Saddle pool to use to swap the given token to a bridging synth

- `synthInKey`: the currency key of the synth to swap from

- `tokenToIndex`: the index of the token to swap to

- `synthInAmount`: the amount of the synth to swap form

- `minMediumSynthAmount`: the minimum amount of the bridging synth at pre-settlement stage

## Return Values:

- the ID of the ERC721 token sent to the caller

# Function `calcTokenToToken(contract ISwap[2] swaps, uint8 tokenFromIndex, uint8 tokenToIndex, uint256 tokenFromAmount) → uint256, uint256` {#Bridge-calcTokenToToken-contract-ISwap-2--uint8-uint8-uint256-}

Calculates the expected amount of the desired token the caller will receive after completing
a `TokenToToken` swap with the given parameters. This calculation does not consider the settlement periods or
any potential changes of the pool compositions.

## Parameters:

- `swaps`: the addresses of the two Saddle pools used to do the cross-asset swap

- `tokenFromIndex`: the index of the token in the first `swaps` pool to swap from

- `tokenToIndex`: the index of the token in the second `swaps` pool to swap to

- `tokenFromAmount`: the amount of the token to swap from

## Return Values:

- the expected amount of bridging synth at pre-settlement stage and the expected amount of the desired
  token

# Function `tokenToToken(contract ISwap[2] swaps, uint8 tokenFromIndex, uint8 tokenToIndex, uint256 tokenFromAmount, uint256 minMediumSynthAmount) → uint256` {#Bridge-tokenToToken-contract-ISwap-2--uint8-uint8-uint256-uint256-}

Initiates a cross-asset swap from a token in one Saddle pool to one in another. The caller will receive
an ERC721 token representing their ownership of the pending cross-asset swap.

## Parameters:

- `swaps`: the addresses of the two Saddle pools used to do the cross-asset swap

- `tokenFromIndex`: the index of the token in the first `swaps` pool to swap from

- `tokenToIndex`: the index of the token in the second `swaps` pool to swap to

- `tokenFromAmount`: the amount of the token to swap from

- `minMediumSynthAmount`: the minimum amount of the bridging synth at pre-settlement stage

## Return Values:

- the ID of the ERC721 token sent to the caller

# Function `setSynthIndex(contract ISwap swap, uint8 synthIndex, bytes32 currencyKey)` {#Bridge-setSynthIndex-contract-ISwap-uint8-bytes32-}

Registers the index and the address of the supported synth from the given `swap` pool. The matching currency key must
be supplied for a successful registration.

## Parameters:

- `swap`: the address of the pool that contains the synth

- `synthIndex`: the index of the supported synth in the given `swap` pool

- `currencyKey`: the currency key of the synth in bytes32 form

# Function `getSynthIndex(contract ISwap swap) → uint8` {#Bridge-getSynthIndex-contract-ISwap-}

Returns the index of the supported synth in the given `swap` pool. Reverts if the `swap` pool
is not registered.

## Parameters:

- `swap`: the address of the pool that contains the synth

## Return Values:

- the index of the supported synth

# Function `getSynthAddress(contract ISwap swap) → address` {#Bridge-getSynthAddress-contract-ISwap-}

Returns the address of the supported synth in the given `swap` pool. Reverts if the `swap` pool
is not registered.

## Parameters:

- `swap`: the address of the pool that contains the synth

## Return Values:

- the address of the supported synth

# Function `getSynthKey(contract ISwap swap) → bytes32` {#Bridge-getSynthKey-contract-ISwap-}

Returns the currency key of the supported synth in the given `swap` pool. Reverts if the `swap` pool
is not registered.

## Parameters:

- `swap`: the address of the pool that contains the synth

## Return Values:

- the currency key of the supported synth

# Function `updateExchangerCache()` {#Bridge-updateExchangerCache--}

Updates the stored address of the `EXCHANGER` contract. When the Synthetix team upgrades their protocol,
a new Exchanger contract is deployed. This function manually updates the stored address.

# Event `SynthIndex(address swap, uint8 synthIndex, bytes32 currencyKey, address synthAddress)` {#Bridge-SynthIndex-address-uint8-bytes32-address-}

No description

# Event `TokenToSynth(address requester, uint256 itemId, contract ISwap swapPool, uint8 tokenFromIndex, uint256 tokenFromInAmount, bytes32 synthToKey)` {#Bridge-TokenToSynth-address-uint256-contract-ISwap-uint8-uint256-bytes32-}

No description

# Event `SynthToToken(address requester, uint256 itemId, contract ISwap swapPool, bytes32 synthFromKey, uint256 synthFromInAmount, uint8 tokenToIndex)` {#Bridge-SynthToToken-address-uint256-contract-ISwap-bytes32-uint256-uint8-}

No description

# Event `TokenToToken(address requester, uint256 itemId, contract ISwap[2] swapPools, uint8 tokenFromIndex, uint256 tokenFromAmount, uint8 tokenToIndex)` {#Bridge-TokenToToken-address-uint256-contract-ISwap-2--uint8-uint256-uint8-}

No description

# Event `Settle(address requester, uint256 itemId, contract IERC20 settleFrom, uint256 settleFromAmount, contract IERC20 settleTo, uint256 settleToAmount, bool isFinal)` {#Bridge-Settle-address-uint256-contract-IERC20-uint256-contract-IERC20-uint256-bool-}

No description

# Event `Withdraw(address requester, uint256 itemId, contract IERC20 synth, uint256 synthAmount, bool isFinal)` {#Bridge-Withdraw-address-uint256-contract-IERC20-uint256-bool-}

No description
