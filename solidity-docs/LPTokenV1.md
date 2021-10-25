This token is an ERC20 detailed token with added capability to be minted by the owner.
It is used to represent user's shares when providing liquidity to swap contracts.

Only Swap contracts should initialize and own LPToken contracts.

# Functions:

- [`initialize(string name, string symbol)`](#LPTokenV1-initialize-string-string-)
- [`mint(address recipient, uint256 amount)`](#LPTokenV1-mint-address-uint256-)

# Function `initialize(string name, string symbol) → bool` {#LPTokenV1-initialize-string-string-}

Initializes this LPToken contract with the given name and symbol

The caller of this function will become the owner. A Swap contract should call this
in its initializer function.

## Parameters:

- `name`: name of this token

- `symbol`: symbol of this token

# Function `mint(address recipient, uint256 amount)` {#LPTokenV1-mint-address-uint256-}

Mints the given amount of LPToken to the recipient.

only owner can call this mint function

## Parameters:

- `recipient`: address of account to receive the tokens

- `amount`: amount of tokens to mint
