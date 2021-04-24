# StakeableTokenWrapper

A wrapper for an ERC-20 that can be staked and withdrawn.

In this contract, staked tokens don't do anything- instead other contracts can inherit from this one to add functionality. / c

## Functions:

* [`constructor(contract IERC20 _stakedToken)`](stakeabletokenwrapper.md#StakeableTokenWrapper-constructor-contract-IERC20-)
* [`balanceOf(address account)`](stakeabletokenwrapper.md#StakeableTokenWrapper-balanceOf-address-)
* [`stake(uint256 amount)`](stakeabletokenwrapper.md#StakeableTokenWrapper-stake-uint256-)
* [`withdraw(uint256 amount)`](stakeabletokenwrapper.md#StakeableTokenWrapper-withdraw-uint256-)

## Events:

* [`Staked(address user, uint256 amount)`](stakeabletokenwrapper.md#StakeableTokenWrapper-Staked-address-uint256-)
* [`Withdrawn(address user, uint256 amount)`](stakeabletokenwrapper.md#StakeableTokenWrapper-Withdrawn-address-uint256-)

## Function `constructor(contract IERC20 _stakedToken)` <a id="StakeableTokenWrapper-constructor-contract-IERC20-"></a>

Creates a new StakeableTokenWrapper with given `_stakedToken` address

### Parameters:

* `_stakedToken`: address of a token that will be used to stake

  /

## Function `balanceOf(address account) → uint256` <a id="StakeableTokenWrapper-balanceOf-address-"></a>

Read how much `account` has staked in this contract

### Parameters:

* `account`: address of an account

### Return Values:

* amount of total staked ERC20\(this.stakedToken\) by `account`

  /

## Function `stake(uint256 amount)` <a id="StakeableTokenWrapper-stake-uint256-"></a>

Stakes given `amount` in this contract

### Parameters:

* `amount`: amount of ERC20\(this.stakedToken\) to stake

  /

## Function `withdraw(uint256 amount)` <a id="StakeableTokenWrapper-withdraw-uint256-"></a>

Withdraws given `amount` from this contract

### Parameters:

* `amount`: amount of ERC20\(this.stakedToken\) to withdraw

  /

## Event `Staked(address user, uint256 amount)` <a id="StakeableTokenWrapper-Staked-address-uint256-"></a>

No description

## Event `Withdrawn(address user, uint256 amount)` <a id="StakeableTokenWrapper-Withdrawn-address-uint256-"></a>

No description

