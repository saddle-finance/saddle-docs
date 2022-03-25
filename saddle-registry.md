# Saddle Registry

The Saddle Registry holds a list of other registries as well as contracts and their historical versions.

## Master Registry

This contract holds the funtions to add a new Registry as well as retrieveing data from the Registry.

| Network | Address                                                                                                            |
| :------------ | :------------------------------------------------------------------------------------------------------------------------- |
| `Ethereum`   | [0xc5ad17b98D7fe73B6dD3b0df5b3040457E68C045](https://etherscan.io/address/0xc5ad17b98D7fe73B6dD3b0df5b3040457E68C045#code) |


## Contract Functions

The Registry can be interacted with the following functions:

* `resolveNameToLatestAddress`: Resolves a name input to the latest registry address.
    ```
        >>> await registry.resolveNameToLatestAddress(formatBytes32String('SaddleUSDPool'))
        '0x3911F80530595fBd01Ab1516Ab61255d75AEb066'
    ```
* `resolveNameAndVersionToAddress`: Allows you to provide both a name and a specific version of the registry address.
    ```
        >>> await registry.resolveNameAndVersionToAddress(formatBytes32String('SaddleUSDPool'), 0)
        '0x3911F80530595fBd01Ab1516Ab61255d75AEb066'
    ```
* `resolveNameToAllAddresses`: Returns an array of all addresses held in the registry of a given name.
    ```
        >>> await registry.resolveNameToAllAddresses(formatBytes32String('SaddleUSDPool'))
        ['0x0C8BAe14c9f9BF2c953997C881BEfaC7729FD314', '0x3911F80530595fBd01Ab1516Ab61255d75AEb066']
    ```
* `resolveAddressToRegistryData`: Returns the registry input entry data inlcuding the name, version, and a boolean value of whether the provided address is the latest version.
    ```
    >>> const reg_data = await registry.resolveAddressToRegistryData('0x3911F80530595fBd01Ab1516Ab61255d75AEb066')
    >>> const name = parseBytes32String(reg_data['name'])
    >>> const version = reg_data['version'].toNumber()
    >>> const isLatest = reg_data['isLatest']
    >>> console.log('name: ', name, ' version: ', version, ' isLatest: ', isLatest)
    name:  SaddleUSDPool  version:  1  isLatest:  true
    ```

