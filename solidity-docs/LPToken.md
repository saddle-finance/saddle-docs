# Functions:

- [`constructor(string name_, string symbol_, uint8 decimals_)`](#LPToken-constructor-string-string-uint8-)
- [`mint(address recipient, uint256 amount, bytes32[] merkleProof)`](#LPToken-mint-address-uint256-bytes32---)

# Function `constructor(string name_, string symbol_, uint8 decimals_)` {#LPToken-constructor-string-string-uint8-}

the caller of this constructor will become the owner of this contract

## Parameters:

- `name_`: name of this token

- `symbol_`: symbol of this token

- `decimals_`: number of decimals this token will be based on

# Function `mint(address recipient, uint256 amount, bytes32[] merkleProof)` {#LPToken-mint-address-uint256-bytes32---}

only owner can call this mint function

## Parameters:

- `recipient`: address of account to receive the tokens

- `amount`: amount of tokens to mint

- `merkleProof`: the bytes32 array data that is used to prove recipient's address exists in the merkle tree
  stored in the allowlist contract. If the pool is not guarded, this parameter is ignored.
