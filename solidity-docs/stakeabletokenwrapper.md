A wrapper for an ERC-20 that can be staked and withdrawn.

In this contract, staked tokens don't do anything- instead other
contracts can inherit from this one to add functionality.
/
c

# Functions:

- [`constructor(contract IERC20 _stakedToken)`](#StakeableTokenWrapper-constructor-contract-IERC20-)
- [`balanceOf(address account)`](#StakeableTokenWrapper-balanceOf-address-)
- [`stake(uint256 amount)`](#StakeableTokenWrapper-stake-uint256-)
- [`withdraw(uint256 amount)`](#StakeableTokenWrapper-withdraw-uint256-)

# Events:

- [`Staked(address user, uint256 amount)`](#StakeableTokenWrapper-Staked-address-uint256-)
- [`Withdrawn(address user, uint256 amount)`](#StakeableTokenWrapper-Withdrawn-address-uint256-)

# Function `constructor(contract IERC20 _stakedToken)` {#StakeableTokenWrapper-constructor-contract-IERC20-}

Creates a new StakeableTokenWrapper with given `_stakedToken` address

## Parameters:

- `_stakedToken`: address of a token that will be used to stake
  /

# Function `balanceOf(address account) → uint256` {#StakeableTokenWrapper-balanceOf-address-}

Read how much `account` has staked in this contract

## Parameters:

- `account`: address of an account

## Return Values:

- amount of total staked ERC20(this.stakedToken) by `account`
  /

# Function `stake(uint256 amount)` {#StakeableTokenWrapper-stake-uint256-}

Stakes given `amount` in this contract

## Parameters:

- `amount`: amount of ERC20(this.stakedToken) to stake
  /

# Function `withdraw(uint256 amount)` {#StakeableTokenWrapper-withdraw-uint256-}

Withdraws given `amount` from this contract

## Parameters:

- `amount`: amount of ERC20(this.stakedToken) to withdraw
  /

# Event `Staked(address user, uint256 amount)` {#StakeableTokenWrapper-Staked-address-uint256-}

No description

# Event `Withdrawn(address user, uint256 amount)` {#StakeableTokenWrapper-Withdrawn-address-uint256-}

No description
