# Allowlist

This contract is a registry holding information about how much each swap contract should contain upto. Swap.sol will rely on this contract to determine whether the pool cap is reached and also whether a user's deposit limit is reached.

## Functions:

* [`constructor(bytes32 merkleRoot_)`](allowlist.md#Allowlist-constructor-bytes32-)
* [`getPoolAccountLimit(address poolAddress)`](allowlist.md#Allowlist-getPoolAccountLimit-address-)
* [`getPoolCap(address poolAddress)`](allowlist.md#Allowlist-getPoolCap-address-)
* [`isAccountVerified(address account)`](allowlist.md#Allowlist-isAccountVerified-address-)
* [`verifyAddress(address account, bytes32[] merkleProof)`](allowlist.md#Allowlist-verifyAddress-address-bytes32---)
* [`setPoolAccountLimit(address poolAddress, uint256 accountLimit)`](allowlist.md#Allowlist-setPoolAccountLimit-address-uint256-)
* [`setPoolCap(address poolAddress, uint256 poolCap)`](allowlist.md#Allowlist-setPoolCap-address-uint256-)
* [`updateMerkleRoot(bytes32 merkleRoot_)`](allowlist.md#Allowlist-updateMerkleRoot-bytes32-)

## Events:

* [`PoolCap(address poolAddress, uint256 poolCap)`](allowlist.md#Allowlist-PoolCap-address-uint256-)
* [`PoolAccountLimit(address poolAddress, uint256 accountLimit)`](allowlist.md#Allowlist-PoolAccountLimit-address-uint256-)
* [`NewMerkleRoot(bytes32 merkleRoot)`](allowlist.md#Allowlist-NewMerkleRoot-bytes32-)

## Function `constructor(bytes32 merkleRoot_)` <a id="Allowlist-constructor-bytes32-"></a>

Creates this contract and sets the PoolCap of 0x0 with uint256\(0x54dd1e\) for crude checking whether an address holds this contract.

### Parameters:

* `merkleRoot_`: bytes32 that represent a merkle root node. This is generated off chain with the list of

  qualifying addresses.

## Function `getPoolAccountLimit(address poolAddress) → uint256` <a id="Allowlist-getPoolAccountLimit-address-"></a>

Returns the max mintable amount of the lp token per account in given pool address.

### Parameters:

* `poolAddress`: address of the pool

### Return Values:

* max mintable amount of the lp token per account

## Function `getPoolCap(address poolAddress) → uint256` <a id="Allowlist-getPoolCap-address-"></a>

Returns the maximum total supply of the pool token for the given pool address.

### Parameters:

* `poolAddress`: address of the pool

## Function `isAccountVerified(address account) → bool` <a id="Allowlist-isAccountVerified-address-"></a>

Returns true if the given account's existence has been verified against any of the past or the present merkle tree. Note that if it has been verified in the past, this function will return true even if the current merkle tree does not contain the account.

### Parameters:

* `account`: the address to check if it has been verified

### Return Values:

* a boolean value representing whether the account has been verified in the past or the present merkle tree

## Function `verifyAddress(address account, bytes32[] merkleProof) → bool` <a id="Allowlist-verifyAddress-address-bytes32---"></a>

Checks the existence of keccak256\(account\) as a node in the merkle tree inferred by the merkle root node stored in this contract. Pools should use this function to check if the given address qualifies for depositing. If the given account has already been verified with the correct merkleProof, this function will return true when merkleProof is empty. The verified status will be overwritten if the previously verified user calls this function with an incorrect merkleProof.

### Parameters:

* `account`: address to confirm its existence in the merkle tree
* `merkleProof`: data that is used to prove the existence of given parameters. This is generated during the creation of the merkle tree. Users should retrieve this data off-chain.

### Return Values:

* a boolean value that corresponds to whether the address with the proof has been verified in the past

  or if they exist in the current merkle tree.

## Function `setPoolAccountLimit(address poolAddress, uint256 accountLimit)` <a id="Allowlist-setPoolAccountLimit-address-uint256-"></a>

Sets the account limit of allowed deposit amounts for the given pool

### Parameters:

* `poolAddress`: address of the pool
* `accountLimit`: the max number of the pool token a single user can mint

## Function `setPoolCap(address poolAddress, uint256 poolCap)` <a id="Allowlist-setPoolCap-address-uint256-"></a>

Sets the max total supply of LPToken for the given pool address

### Parameters:

* `poolAddress`: address of the pool
* `poolCap`: the max total supply of the pool token

## Function `updateMerkleRoot(bytes32 merkleRoot_)` <a id="Allowlist-updateMerkleRoot-bytes32-"></a>

Updates the merkle root that is stored in this contract. This can only be called by the owner. If more addresses are added to the list, a new merkle tree and a merkle root node should be generated, and merkleRoot should be updated accordingly.

### Parameters:

* `merkleRoot_`: a new merkle root node that contains a list of deposit allowed addresses

## Event `PoolCap(address poolAddress, uint256 poolCap)` <a id="Allowlist-PoolCap-address-uint256-"></a>

No description

## Event `PoolAccountLimit(address poolAddress, uint256 accountLimit)` <a id="Allowlist-PoolAccountLimit-address-uint256-"></a>

No description

## Event `NewMerkleRoot(bytes32 merkleRoot)` <a id="Allowlist-NewMerkleRoot-bytes32-"></a>

No description

