Interface for Saddles Master Registry.


# Functions:
- [`addRegistry(bytes32 registryName, address registryAddress)`](#IMasterRegistry-addRegistry-bytes32-address-)
- [`resolveNameToLatestAddress(bytes32 name)`](#IMasterRegistry-resolveNameToLatestAddress-bytes32-)
- [`resolveNameAndVersionToAddress(bytes32 name, uint256 version)`](#IMasterRegistry-resolveNameAndVersionToAddress-bytes32-uint256-)
- [`resolveNameToAllAddresses(bytes32 name)`](#IMasterRegistry-resolveNameToAllAddresses-bytes32-)
- [`resolveAddressToRegistryData(address registryAddress)`](#IMasterRegistry-resolveAddressToRegistryData-address-)


# Function `addRegistry(bytes32 registryName, address registryAddress)` {#IMasterRegistry-addRegistry-bytes32-address-}
Add a new registry entry to the master list.


## Parameters:
- `registryName`: name for the registry

- `registryAddress`: address of the new registry
# Function `resolveNameToLatestAddress(bytes32 name) → address` {#IMasterRegistry-resolveNameToLatestAddress-bytes32-}
Resolves a name to the latest registry address. Reverts if no match is found.


## Parameters:
- `name`: name for the registry

## Return Values:
- address address of the latest registry with the matching name
# Function `resolveNameAndVersionToAddress(bytes32 name, uint256 version) → address` {#IMasterRegistry-resolveNameAndVersionToAddress-bytes32-uint256-}
Resolves a name and version to an address. Reverts if there is no registry with given name and version.


## Parameters:
- `name`: address of the registry you want to resolve to

- `version`: version of the registry you want to resolve to
# Function `resolveNameToAllAddresses(bytes32 name) → address[]` {#IMasterRegistry-resolveNameToAllAddresses-bytes32-}
Resolves a name to an array of all addresses. Reverts if no match is found.


## Parameters:
- `name`: name for the registry

## Return Values:
- address address of the latest registry with the matching name
# Function `resolveAddressToRegistryData(address registryAddress) → bytes32 name, uint256 version, bool isLatest` {#IMasterRegistry-resolveAddressToRegistryData-address-}
Resolves an address to registry entry data.


## Parameters:
- `registryAddress`: address of a registry you want to resolve

## Return Values:
- name name of the resolved registry

- version version of the resolved registry

- isLatest boolean flag of whether the given address is the latest version of the given registries with
matching name

