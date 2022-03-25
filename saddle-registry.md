# Saddle Registry

The Saddle Registry contract holds a list of other registries or contracts and its historical versions.

## MasterRegistry.sol

This contract holds the funtions to add a new Registry as well as retrieveing data from the Registry.

| Network | Address                                                                                                            |
| :------------ | :------------------------------------------------------------------------------------------------------------------------- |
| `Ethereum`   | [0xc5ad17b98D7fe73B6dD3b0df5b3040457E68C045](https://etherscan.io/address/0xc5ad17b98D7fe73B6dD3b0df5b3040457E68C045#code) |

### Contract Functions

`resolveNameToLatestAddress`: Resolves a name input to resolve to the current address of the contract of that name.

`resolveNameAndVersionToAddress`: Allows you to provide a specific version for the address you are looking for.

`resolveNameToAllAddresses`: Returns the history of registry data of a given name.

`resolveAddressToRegistryData`: Returns the name, version, and if the provided address is the latest address in the registry.


