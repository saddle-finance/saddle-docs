# Functions:

- [`constructor(bytes32 merkleRoot_)`](#Allowlist-constructor-bytes32-)
- [`getPoolAccountLimit(address poolAddress)`](#Allowlist-getPoolAccountLimit-address-)
- [`getPoolCap(address poolAddress)`](#Allowlist-getPoolCap-address-)
- [`isAccountVerified(address account)`](#Allowlist-isAccountVerified-address-)
- [`verifyAddress(address account, bytes32[] merkleProof)`](#Allowlist-verifyAddress-address-bytes32---)
- [`setPoolAccountLimit(address poolAddress, uint256 accountLimit)`](#Allowlist-setPoolAccountLimit-address-uint256-)
- [`setPoolCap(address poolAddress, uint256 poolCap)`](#Allowlist-setPoolCap-address-uint256-)
- [`updateMerkleRoot(bytes32 merkleRoot_)`](#Allowlist-updateMerkleRoot-bytes32-)

# Events:

- [`PoolCap(address poolAddress, uint256 poolCap)`](#Allowlist-PoolCap-address-uint256-)
- [`PoolAccountLimit(address poolAddress, uint256 accountLimit)`](#Allowlist-PoolAccountLimit-address-uint256-)
- [`NewMerkleRoot(bytes32 merkleRoot)`](#Allowlist-NewMerkleRoot-bytes32-)

# Function `constructor(bytes32 merkleRoot_)` {#Allowlist-constructor-bytes32-}

No description

## Parameters:

- `merkleRoot_`: bytes32 that represent a merkle root node. This is generated off chain with the list of
  qualifying addresses.

# Function `getPoolAccountLimit(address poolAddress) → uint256` {#Allowlist-getPoolAccountLimit-address-}

No description

## Parameters:

- `poolAddress`: address of the pool

## Return Values:

- max mintable amount of the lp token per account

# Function `getPoolCap(address poolAddress) → uint256` {#Allowlist-getPoolCap-address-}

No description

## Parameters:

- `poolAddress`: address of the pool

# Function `isAccountVerified(address account) → bool` {#Allowlist-isAccountVerified-address-}

No description

## Parameters:

- `account`: the address to check if it has been verified

## Return Values:

- a boolean value representing whether the account has been verified in the past or the present merkle tree

# Function `verifyAddress(address account, bytes32[] merkleProof) → bool` {#Allowlist-verifyAddress-address-bytes32---}

No description

## Parameters:

- `account`: address to confirm its existence in the merkle tree

- `merkleProof`: data that is used to prove the existence of given parameters. This is generated
  during the creation of the merkle tree. Users should retrieve this data off-chain.

## Return Values:

- a boolean value that corresponds to whether the address with the proof has been verified in the past
  or if they exist in the current merkle tree.

# Function `setPoolAccountLimit(address poolAddress, uint256 accountLimit)` {#Allowlist-setPoolAccountLimit-address-uint256-}

No description

## Parameters:

- `poolAddress`: address of the pool

- `accountLimit`: the max number of the pool token a single user can mint

# Function `setPoolCap(address poolAddress, uint256 poolCap)` {#Allowlist-setPoolCap-address-uint256-}

No description

## Parameters:

- `poolAddress`: address of the pool

- `poolCap`: the max total supply of the pool token

# Function `updateMerkleRoot(bytes32 merkleRoot_)` {#Allowlist-updateMerkleRoot-bytes32-}

No description

## Parameters:

- `merkleRoot_`: a new merkle root node that contains a list of deposit allowed addresses

# Event `PoolCap(address poolAddress, uint256 poolCap)` {#Allowlist-PoolCap-address-uint256-}

No description

# Event `PoolAccountLimit(address poolAddress, uint256 accountLimit)` {#Allowlist-PoolAccountLimit-address-uint256-}

No description

# Event `NewMerkleRoot(bytes32 merkleRoot)` {#Allowlist-NewMerkleRoot-bytes32-}

No description
