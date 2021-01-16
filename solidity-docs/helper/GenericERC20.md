# Functions:

- [`constructor(string name_, string symbol_, uint8 decimals_)`](#GenericERC20-constructor-string-string-uint8-)
- [`mint(address recipient, uint256 amount)`](#GenericERC20-mint-address-uint256-)

# Function `constructor(string name_, string symbol_, uint8 decimals_)` {#GenericERC20-constructor-string-string-uint8-}

the caller of this constructor will become the owner of this contract

## Parameters:

- `name_`: name of this token

- `symbol_`: symbol of this token

- `decimals_`: number of decimals this token will be based on

# Function `mint(address recipient, uint256 amount)` {#GenericERC20-mint-address-uint256-}

only owner can call this mint function

## Parameters:

- `recipient`: address of account to receive the tokens

- `amount`: amount of tokens to mint
