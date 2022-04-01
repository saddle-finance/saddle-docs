This contract holds list and pool data of pools deployed. It also includes pool creation/removal related events.



# Functions:
- [`constructor(address admin, address poolOwner)`](#PoolRegistry-constructor-address-address-)
- [`addCommunityPool(struct IPoolRegistry.PoolData data)`](#PoolRegistry-addCommunityPool-struct-IPoolRegistry-PoolData-)
- [`addPool(struct IPoolRegistry.PoolInputData inputData)`](#PoolRegistry-addPool-struct-IPoolRegistry-PoolInputData-)
- [`approvePool(address poolAddress)`](#PoolRegistry-approvePool-address-)
- [`updatePool(struct IPoolRegistry.PoolData poolData)`](#PoolRegistry-updatePool-struct-IPoolRegistry-PoolData-)
- [`removePool(address poolAddress)`](#PoolRegistry-removePool-address-)
- [`getPoolDataAtIndex(uint256 index)`](#PoolRegistry-getPoolDataAtIndex-uint256-)
- [`getPoolData(address poolAddress)`](#PoolRegistry-getPoolData-address-)
- [`getPoolDataByName(bytes32 poolName)`](#PoolRegistry-getPoolDataByName-bytes32-)
- [`getVirtualPrice(address poolAddress)`](#PoolRegistry-getVirtualPrice-address-)
- [`getA(address poolAddress)`](#PoolRegistry-getA-address-)
- [`getPaused(address poolAddress)`](#PoolRegistry-getPaused-address-)
- [`getSwapStorage(address poolAddress)`](#PoolRegistry-getSwapStorage-address-)
- [`getTokens(address poolAddress)`](#PoolRegistry-getTokens-address-)
- [`getUnderlyingTokens(address poolAddress)`](#PoolRegistry-getUnderlyingTokens-address-)
- [`getPoolsLength()`](#PoolRegistry-getPoolsLength--)
- [`getEligiblePools(address from, address to)`](#PoolRegistry-getEligiblePools-address-address-)
- [`getTokenBalances(address poolAddress)`](#PoolRegistry-getTokenBalances-address-)
- [`getUnderlyingTokenBalances(address poolAddress)`](#PoolRegistry-getUnderlyingTokenBalances-address-)

# Events:
- [`AddPool(address poolAddress, uint256 index, struct IPoolRegistry.PoolData poolData)`](#PoolRegistry-AddPool-address-uint256-struct-IPoolRegistry-PoolData-)
- [`AddCommunityPool(address poolAddress, uint256 index, struct IPoolRegistry.PoolData poolData)`](#PoolRegistry-AddCommunityPool-address-uint256-struct-IPoolRegistry-PoolData-)
- [`UpdatePool(address poolAddress, uint256 index, struct IPoolRegistry.PoolData poolData)`](#PoolRegistry-UpdatePool-address-uint256-struct-IPoolRegistry-PoolData-)
- [`RemovePool(address poolAddress, uint256 index)`](#PoolRegistry-RemovePool-address-uint256-)

# Function `constructor(address admin, address poolOwner)` {#PoolRegistry-constructor-address-address-}
Deploy this contract and set appropriate roles

caller of this function will be set as the owner on deployment
## Parameters:
- `admin`: address who should have the DEFAULT_ADMIN_ROLE

# Function `addCommunityPool(struct IPoolRegistry.PoolData data)` {#PoolRegistry-addCommunityPool-struct-IPoolRegistry-PoolData-}
Add a new pool to the registry

Before adding a meta pool, the user must first add the underlying base pool.
Only Swap and MetaSwap contracts need to be added.
## Parameters:
- `data`: PoolInputData struct for the new pool

# Function `addPool(struct IPoolRegistry.PoolInputData inputData)` {#PoolRegistry-addPool-struct-IPoolRegistry-PoolInputData-}
Add a new pool to the registry

Before adding a meta pool, the user must first add the underlying base pool.
Only Swap and MetaSwap contracts need to be added.
## Parameters:
- `inputData`: PoolInputData struct for the new pool

# Function `approvePool(address poolAddress)` {#PoolRegistry-approvePool-address-}
Approve community deployed pools to be upgraded as Saddle owned

since array entries are difficult to remove, we modify the entry to mark it
as a Saddle owned pool.

## Parameters:
- `poolAddress`: address of the community pool
# Function `updatePool(struct IPoolRegistry.PoolData poolData)` {#PoolRegistry-updatePool-struct-IPoolRegistry-PoolData-}
Overwrite existing entry with new PoolData


## Parameters:
- `poolData`: new PoolData struct to store
# Function `removePool(address poolAddress)` {#PoolRegistry-removePool-address-}
Remove pool from the registry

Since arrays are not easily reducable, the entry will be marked as removed.

## Parameters:
- `poolAddress`: address of the pool to remove
# Function `getPoolDataAtIndex(uint256 index) → struct IPoolRegistry.PoolData` {#PoolRegistry-getPoolDataAtIndex-uint256-}
Returns PoolData at given index


## Parameters:
- `index`: index of the pool to read
# Function `getPoolData(address poolAddress) → struct IPoolRegistry.PoolData` {#PoolRegistry-getPoolData-address-}
Returns PoolData for given pool address


## Parameters:
- `poolAddress`: address of the pool to read
# Function `getPoolDataByName(bytes32 poolName) → struct IPoolRegistry.PoolData` {#PoolRegistry-getPoolDataByName-bytes32-}
Returns PoolData with given name


## Parameters:
- `poolName`: name of the pool to read
# Function `getVirtualPrice(address poolAddress) → uint256` {#PoolRegistry-getVirtualPrice-address-}
Returns virtual price of the given pool address


## Parameters:
- `poolAddress`: address of the pool to read
# Function `getA(address poolAddress) → uint256` {#PoolRegistry-getA-address-}
Returns A of the given pool address


## Parameters:
- `poolAddress`: address of the pool to read
# Function `getPaused(address poolAddress) → bool` {#PoolRegistry-getPaused-address-}
Returns the paused status of the given pool address


## Parameters:
- `poolAddress`: address of the pool to read
# Function `getSwapStorage(address poolAddress) → struct IPoolRegistry.SwapStorageData swapStorageData` {#PoolRegistry-getSwapStorage-address-}
Returns the SwapStorage struct of the given pool address


## Parameters:
- `poolAddress`: address of the pool to read
# Function `getTokens(address poolAddress) → contract IERC20[] tokens` {#PoolRegistry-getTokens-address-}
Returns the tokens of the given pool address


## Parameters:
- `poolAddress`: address of the pool to read
# Function `getUnderlyingTokens(address poolAddress) → contract IERC20[] underlyingTokens` {#PoolRegistry-getUnderlyingTokens-address-}
Returns the underlying tokens of the given pool address. Base pools will return an empty array.


## Parameters:
- `poolAddress`: address of the pool to read
# Function `getPoolsLength() → uint256` {#PoolRegistry-getPoolsLength--}
Returns number of entries in the registry. Includes removed pools
in the list as well.

# Function `getEligiblePools(address from, address to) → address[] eligiblePools` {#PoolRegistry-getEligiblePools-address-address-}
Returns an array of pool addresses that can swap between from and to


## Parameters:
- `from`: address of the token to swap from

- `to`: address of the token to swap to

## Return Values:
- eligiblePools array of pool addresses that can swap between from and to
# Function `getTokenBalances(address poolAddress) → uint256[] balances` {#PoolRegistry-getTokenBalances-address-}
Returns an array of balances of the tokens


## Parameters:
- `poolAddress`: address of the pool to look up the token balances for

## Return Values:
- balances array of token balances
# Function `getUnderlyingTokenBalances(address poolAddress) → uint256[] balances` {#PoolRegistry-getUnderlyingTokenBalances-address-}
Returns an array of balances of the tokens


## Parameters:
- `poolAddress`: address of the pool to look up the token balances for

## Return Values:
- balances array of token balances

# Event `AddPool(address poolAddress, uint256 index, struct IPoolRegistry.PoolData poolData)` {#PoolRegistry-AddPool-address-uint256-struct-IPoolRegistry-PoolData-}
Add a new registry entry to the master list.


## Parameters:
- `poolAddress`: address of the added pool

- `index`: index of the added pool in the pools list

- `poolData`: added pool data
# Event `AddCommunityPool(address poolAddress, uint256 index, struct IPoolRegistry.PoolData poolData)` {#PoolRegistry-AddCommunityPool-address-uint256-struct-IPoolRegistry-PoolData-}
Add a new registry entry to the master list.


## Parameters:
- `poolAddress`: address of the added pool

- `index`: index of the added pool in the pools list

- `poolData`: added pool data
# Event `UpdatePool(address poolAddress, uint256 index, struct IPoolRegistry.PoolData poolData)` {#PoolRegistry-UpdatePool-address-uint256-struct-IPoolRegistry-PoolData-}
Add a new registry entry to the master list.


## Parameters:
- `poolAddress`: address of the updated pool

- `index`: index of the updated pool in the pools list

- `poolData`: updated pool data
# Event `RemovePool(address poolAddress, uint256 index)` {#PoolRegistry-RemovePool-address-uint256-}
Add a new registry entry to the master list.


## Parameters:
- `poolAddress`: address of the removed pool

- `index`: index of the removed pool in the pools list