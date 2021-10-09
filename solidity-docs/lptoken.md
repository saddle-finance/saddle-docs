# LPToken

This token is an ERC20 detailed token with added capability to be minted by the owner. It is used to represent user's shares when providing liquidity to swap contracts.

## Functions:

- [`constructor(string name_, string symbol_, uint8 decimals_)`](lptoken.md#LPToken-constructor-string-string-uint8-)
- [`mint(address recipient, uint256 amount, bytes32[] merkleProof)`](lptoken.md#LPToken-mint-address-uint256-bytes32---)

## Function `constructor(string name_, string symbol_, uint8 decimals_)` <a id="LPToken-constructor-string-string-uint8-"></a>

Deploys LPToken contract with given name, symbol, and decimals

the caller of this constructor will become the owner of this contract

### Parameters:

- `name_`: name of this token
- `symbol_`: symbol of this token
- `decimals_`: number of decimals this token will be based on

## Function `mint(address recipient, uint256 amount, bytes32[] merkleProof)` <a id="LPToken-mint-address-uint256-bytes32---"></a>

Mints the given amount of LPToken to the recipient. During the guarded release phase, the total supply and the maximum number of the tokens that a single account can mint are limited.

only owner can call this mint function

### Parameters:

- `recipient`: address of account to receive the tokens
- `amount`: amount of tokens to mint
- `merkleProof`: the bytes32 array data that is used to prove recipient's address exists in the merkle tree stored in the allowlist contract. If the pool is not guarded, this parameter is ignored.
