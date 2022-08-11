Interface for Saddle Pool Registry. 


# Functions:
- [`poolsIndexOfPlusOne(address poolAddress)`](#IPoolRegistry-poolsIndexOfPlusOne-address-)
- [`poolsIndexOfNamePlusOne(bytes32 poolName)`](#IPoolRegistry-poolsIndexOfNamePlusOne-bytes32-)
- [`addPool(struct IPoolRegistry.PoolInputData inputData)`](#IPoolRegistry-addPool-struct-IPoolRegistry-PoolInputData-)
- [`addCommunityPool(struct IPoolRegistry.PoolData data)`](#IPoolRegistry-addCommunityPool-struct-IPoolRegistry-PoolData-)
- [`approvePool(address poolAddress)`](#IPoolRegistry-approvePool-address-)
- [`updatePool(struct IPoolRegistry.PoolData poolData)`](#IPoolRegistry-updatePool-struct-IPoolRegistry-PoolData-)
- [`removePool(address poolAddress)`](#IPoolRegistry-removePool-address-)
- [`getPoolData(address poolAddress)`](#IPoolRegistry-getPoolData-address-)
- [`getPoolDataAtIndex(uint256 index)`](#IPoolRegistry-getPoolDataAtIndex-uint256-)
- [`getPoolDataByName(bytes32 poolName)`](#IPoolRegistry-getPoolDataByName-bytes32-)
- [`getVirtualPrice(address poolAddress)`](#IPoolRegistry-getVirtualPrice-address-)
- [`getA(address poolAddress)`](#IPoolRegistry-getA-address-)
- [`getPaused(address poolAddress)`](#IPoolRegistry-getPaused-address-)
- [`getSwapStorage(address poolAddress)`](#IPoolRegistry-getSwapStorage-address-)
- [`getTokens(address poolAddress)`](#IPoolRegistry-getTokens-address-)
- [`getUnderlyingTokens(address poolAddress)`](#IPoolRegistry-getUnderlyingTokens-address-)
- [`getPoolsLength()`](#IPoolRegistry-getPoolsLength--)
- [`getEligiblePools(address from, address to)`](#IPoolRegistry-getEligiblePools-address-address-)
- [`getTokenBalances(address poolAddress)`](#IPoolRegistry-getTokenBalances-address-)
- [`getUnderlyingTokenBalances(address poolAddress)`](#IPoolRegistry-getUnderlyingTokenBalances-address-)


# Function `poolsIndexOfPlusOne(address poolAddress) → uint256` {#IPoolRegistry-poolsIndexOfPlusOne-address-}
Returns the index + 1 of the pool address in the registry


## Parameters:
- `poolAddress`: address to look for
# Function `poolsIndexOfNamePlusOne(bytes32 poolName) → uint256` {#IPoolRegistry-poolsIndexOfNamePlusOne-bytes32-}
Returns the index + 1 of the pool name in the registry


## Parameters:
- `poolName`: pool name in bytes32 format to look for
# Function `addPool(struct IPoolRegistry.PoolInputData inputData)` {#IPoolRegistry-addPool-struct-IPoolRegistry-PoolInputData-}
Add a new pool to the registry

Before adding a meta pool, the user must first add the underlying base pool.
Only Swap and MetaSwap contracts need to be added.
## Parameters:
- `inputData`: PoolInputData struct for the new pool

# Function `addCommunityPool(struct IPoolRegistry.PoolData data)` {#IPoolRegistry-addCommunityPool-struct-IPoolRegistry-PoolData-}
Add a new pool to the registry

Before adding a meta pool, the user must first add the underlying base pool.
Only Swap and MetaSwap contracts need to be added.
## Parameters:
- `data`: PoolInputData struct for the new pool

# Function `approvePool(address poolAddress)` {#IPoolRegistry-approvePool-address-}
Approve community deployed pools to be upgraded as Saddle owned

since array entries are difficult to remove, we modify the entry to mark it
as a Saddle owned pool.

## Parameters:
- `poolAddress`: address of the community pool
# Function `updatePool(struct IPoolRegistry.PoolData poolData)` {#IPoolRegistry-updatePool-struct-IPoolRegistry-PoolData-}
Overwrite existing entry with new PoolData


## Parameters:
- `poolData`: new PoolData struct to store
# Function `removePool(address poolAddress)` {#IPoolRegistry-removePool-address-}
Remove pool from the registry

Since arrays are not easily reducable, the entry will be marked as removed.

## Parameters:
- `poolAddress`: address of the pool to remove
# Function `getPoolData(address poolAddress) → struct IPoolRegistry.PoolData` {#IPoolRegistry-getPoolData-address-}
Returns PoolData for given pool address


## Parameters:
- `poolAddress`: address of the pool to read
# Function `getPoolDataAtIndex(uint256 index) → struct IPoolRegistry.PoolData` {#IPoolRegistry-getPoolDataAtIndex-uint256-}
Returns PoolData at given index


## Parameters:
- `index`: index of the pool to read
# Function `getPoolDataByName(bytes32 poolName) → struct IPoolRegistry.PoolData` {#IPoolRegistry-getPoolDataByName-bytes32-}
Returns PoolData with given name


## Parameters:
- `poolName`: name of the pool to read
# Function `getVirtualPrice(address poolAddress) → uint256` {#IPoolRegistry-getVirtualPrice-address-}
Returns virtual price of the given pool address


## Parameters:
- `poolAddress`: address of the pool to read
# Function `getA(address poolAddress) → uint256` {#IPoolRegistry-getA-address-}
Returns A of the given pool address


## Parameters:
- `poolAddress`: address of the pool to read
# Function `getPaused(address poolAddress) → bool` {#IPoolRegistry-getPaused-address-}
Returns the paused status of the given pool address


## Parameters:
- `poolAddress`: address of the pool to read
# Function `getSwapStorage(address poolAddress) → struct IPoolRegistry.SwapStorageData swapStorageData` {#IPoolRegistry-getSwapStorage-address-}
Returns the SwapStorage struct of the given pool address


## Parameters:
- `poolAddress`: address of the pool to read
# Function `getTokens(address poolAddress) → contract IERC20[]` {#IPoolRegistry-getTokens-address-}
Returns the tokens of the given pool address


## Parameters:
- `poolAddress`: address of the pool to read
# Function `getUnderlyingTokens(address poolAddress) → contract IERC20[]` {#IPoolRegistry-getUnderlyingTokens-address-}
Returns the underlying tokens of the given pool address. Base pools will return an empty array.


## Parameters:
- `poolAddress`: address of the pool to read
# Function `getPoolsLength() → uint256` {#IPoolRegistry-getPoolsLength--}
Returns number of entries in the registry. Includes removed pools
in the list as well.

# Function `getEligiblePools(address from, address to) → address[] eligiblePools` {#IPoolRegistry-getEligiblePools-address-address-}
Returns an array of pool addresses that can swap between from and to


## Parameters:
- `from`: address of the token to swap from

- `to`: address of the token to swap to

## Return Values:
- eligiblePools array of pool addresses that can swap between from and to
# Function `getTokenBalances(address poolAddress) → uint256[] balances` {#IPoolRegistry-getTokenBalances-address-}
Returns an array of balances of the tokens


## Parameters:
- `poolAddress`: address of the pool to look up the token balances for

## Return Values:
- balances array of token balances
# Function `getUnderlyingTokenBalances(address poolAddress) → uint256[] balances` {#IPoolRegistry-getUnderlyingTokenBalances-address-}
Returns an array of balances of the tokens


## Parameters:
- `poolAddress`: address of the pool to look up the token balances for

## Return Values:
- balances array of token balances

