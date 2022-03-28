# Saddle Registry

The Saddle Registry is used for storage and retrieval of Saddle registries and contracts.

## Master Registry

| Network | Address                                                                                                            |
| :------------ | :------------------------------------------------------------------------------------------------------------------------- |
| `Ethereum`   | [0xc5ad17b98D7fe73B6dD3b0df5b3040457E68C045](https://etherscan.io/address/0xc5ad17b98D7fe73B6dD3b0df5b3040457E68C045#code) |

The Master Registry can be interacted with the following functions:

### Master Registry Contract Functions

The Master Registry can be interacted with the following functions:

* `resolveNameToLatestAddress`: Resolves a name input to the latest registry address.
    ```
        >>> await registry.resolveNameToLatestAddress(formatBytes32String('USDPool'))
        '0xFb4DE84c4375d7c8577327153dE88f58F69EeC81'
    ```
* `resolveNameAndVersionToAddress`: Allows you to provide both a name and a specific version of the registry address.
    ```
        >>> await registry.resolveNameAndVersionToAddress(formatBytes32String('USDPool'), 0)
        '0xFb4DE84c4375d7c8577327153dE88f58F69EeC81'
    ```
* `resolveNameToAllAddresses`: Returns an array of all addresses held in the registry of a given name.
    ```
        >>> await registry.resolveNameToAllAddresses(formatBytes32String('USDPool'))
        ['0x0C8BAe14c9f9BF2c953997C881BEfaC7729FD314', '0xFb4DE84c4375d7c8577327153dE88f58F69EeC81']
    ```
* `resolveAddressToRegistryData`: Returns the registry input entry data inlcuding the name, version, and a boolean value of whether the provided address is the latest version.
    ```
    >>> const reg_data = await registry.resolveAddressToRegistryData('0xFb4DE84c4375d7c8577327153dE88f58F69EeC81')
    >>> const name = parseBytes32String(reg_data['name'])
    >>> const version = reg_data['version'].toNumber()
    >>> const isLatest = reg_data['isLatest']
    >>> console.log('name: ', name, ' version: ', version, ' isLatest: ', isLatest)
    name:  USDPool  version:  1  isLatest:  true
    ```

## Pool Registry

This contract holds the funtions to get deployment addresses and related info for all Saddle Pools

| Network | Address                                                                                                            |
| :------------ | :------------------------------------------------------------------------------------------------------------------------- |
| `Ethereum`   | [0xFb4DE84c4375d7c8577327153dE88f58F69EeC81](https://etherscan.io/address/0xFb4DE84c4375d7c8577327153dE88f58F69EeC81#code) |

### Pool Registry Public Variables:

* `poolsIndexOfPlusOne(address poolAddress)`: Resolves an address input to the current pool vitual price.
    ```python
    >>> result = registry_contract.poolsIndexOfPlusOne('0xaCb83E0633d6605c5001e2Ab59EF3C745547C8C7').call()
    False
    ```

### Pool Registry Contract Functions

The Pool Registry can be interacted with the following functions:

* `getPoolDataAtIndex(uint256 index)`: Resolves an index input to the Pool Registry data.
    ```python
    >>> registry_contract = w3.eth.contract(pool_reg_addr, abi=ABI)
    >>> result = registry_contract.functions.getPoolDataAtIndex(0).call()
    >>> PoolData_labels = [
        {'name':'poolAddress', 'type':'address'},
        {'name':'lpToken', 'type':'address'},
        {'name':'typeOfAsset', 'type':'uint8'},
        {'name':'poolName', 'type':'bytes32'},
        {'name':'targetAddress', 'type':'address'},
        {'name':'tokens', 'type':'address'},
        {'name':'underlyingTokens', 'type':'address'},
        {'name':'basePoolAddress', 'type':'address'},
        {'name':'metaSwapDepositAddress', 'type':'address'},
        {'name':'isSaddleApproved', 'type':'bool'},
        {'name':'isRemoved', 'type':'bool'},
        {'name':'isGuarded', 'type':'bool'}
        ]
    >>> for i in PoolData_labels:
        if i['type'] == 'bytes32':
            print(i['name'], ':', result[PoolData_labels.index(i)].decode('utf-8'))
        else:
            print(i['name'], ':', result[PoolData_labels.index(i)])
    
    poolAddress : 0xaCb83E0633d6605c5001e2Ab59EF3C745547C8C7
    lpToken : 0x5f86558387293b6009d7896A61fcc86C17808D62
    typeOfAsset : 2
    poolName : USDv2
    targetAddress : 0xc68BF77e33F1DF59D8247dd564da4c8C81519db6
    tokens : ['0x6B175474E89094C44Da98b954EedeAC495271d0F', '0xA0b86991c6218b36c1d19D4a2e9Eb0cE3606eB48', '0xdAC17F958D2ee523a2206206994597C13D831ec7']
    underlyingTokens : []
    basePoolAddress : 0x0000000000000000000000000000000000000000
    metaSwapDepositAddress : 0x0000000000000000000000000000000000000000
    isSaddleApproved : True
    isRemoved : False
    isGuarded : False
    ```
    ^ Other function calls will use the same format for returning PoolData
* `getPoolData(address poolAddress)`: Resolves an address input to the latest pool registry data.
    ```python
    >>> result = registry_contract.functions.getPoolData('0xaCb83E0633d6605c5001e2Ab59EF3C745547C8C7').call()
    poolAddress : 0xaCb83E0633d6605c5001e2Ab59EF3C745547C8C7
    lpToken : 0x5f86558387293b6009d7896A61fcc86C17808D62
    typeOfAsset : 2
    poolName : USDv2
    targetAddress : 0xc68BF77e33F1DF59D8247dd564da4c8C81519db6
    tokens : ['0x6B175474E89094C44Da98b954EedeAC495271d0F', '0xA0b86991c6218b36c1d19D4a2e9Eb0cE3606eB48', '0xdAC17F958D2ee523a2206206994597C13D831ec7']
    underlyingTokens : []
    basePoolAddress : 0x0000000000000000000000000000000000000000
    metaSwapDepositAddress : 0x0000000000000000000000000000000000000000
    isSaddleApproved : True
    isRemoved : False
    isGuarded : False
    ```
* `getPoolDataByName(bytes32 poolName)`: Resolves a name input to the latest pool registry data.
    ```python
    >>> result = registry_contract.functions.getPoolDataByName('USDv2').call()
    poolAddress : 0xaCb83E0633d6605c5001e2Ab59EF3C745547C8C7
    lpToken : 0x5f86558387293b6009d7896A61fcc86C17808D62
    typeOfAsset : 2
    poolName : USDv2
    targetAddress : 0xc68BF77e33F1DF59D8247dd564da4c8C81519db6
    tokens : ['0x6B175474E89094C44Da98b954EedeAC495271d0F', '0xA0b86991c6218b36c1d19D4a2e9Eb0cE3606eB48', '0xdAC17F958D2ee523a2206206994597C13D831ec7']
    underlyingTokens : []
    basePoolAddress : 0x0000000000000000000000000000000000000000
    metaSwapDepositAddress : 0x0000000000000000000000000000000000000000
    isSaddleApproved : True
    isRemoved : False
    isGuarded : False
    ```
* `getVirtualPrice(address poolAddress)`: Resolves an address input to the current pool vitual price.
    ```python
    >>> result = registry_contract.functions.getVirtualPrice('0xaCb83E0633d6605c5001e2Ab59EF3C745547C8C7').call()
    1003246662771594189
    ```
* `getA(address poolAddress)`: Resolves an address input to the current pool amplification value.
    ```python
    >>> result = registry_contract.functions.getA('0xaCb83E0633d6605c5001e2Ab59EF3C745547C8C7').call()
    400
    ```
* `getPaused(address poolAddress)`: Resolves an address input to a boolean of whether the pool is paused or not.
    ```python
    >>> result = registry_contract.functions.getPaused('0xaCb83E0633d6605c5001e2Ab59EF3C745547C8C7').call()
    False
    ```
* `getSwapStorage(address poolAddress)`: Resolves an address input to the SwapStorage struct of a given pool.
    ```python
    >>> result = registry_contract.functions.getSwapStorage('0xaCb83E0633d6605c5001e2Ab59EF3C745547C8C7').call()
    >>> SwapStorage_labels = [
        {'name':'initalA', 'type':'uint256'},
        {'name':'futureA', 'type':'uint256'},
        {'name':'initialATime', 'type':'uint256'},
        {'name':'futureATime', 'type':'uint256'},
        {'name':'swapFee', 'type':'uint256'},
        {'name':'adminFee', 'type':'uint256'},
        {'name':'lpToken', 'type':'uint256'}
        ]
    >>> for i in SwapStorage_labels:
            print(i['name'], result[SwapStorage_labels.index(i)])
    
    initalA 20000
    futureA 40000
    initialATime 1643232168
    futureATime 1644666450
    swapFee 4000000
    adminFee 5000000000
    lpToken 0x5f86558387293b6009d7896A61fcc86C17808D62
    ```
* `getTokens(address poolAddress)`: Resolves an address input to the addresses of tokens in the given pool.
    ```python
    >>> result = registry_contract.functions.getTokens('0xaCb83E0633d6605c5001e2Ab59EF3C745547C8C7').call()
    ['0x6B175474E89094C44Da98b954EedeAC495271d0F', '0xA0b86991c6218b36c1d19D4a2e9Eb0cE3606eB48', '0xdAC17F958D2ee523a2206206994597C13D831ec7']
    ```
* `getUnderlyingTokens(address poolAddress)`: Returns the underlying tokens of the given pool address. Base pools will return an empty array.
    ```python
    >>> result = registry_contract.functions.getUnderlyingTokens('0x0C8BAe14c9f9BF2c953997C881BEfaC7729FD314').call()
    ['0x57Ab1ec28D129707052df4dF418D58a2D46d5f51', '0x6B175474E89094C44Da98b954EedeAC495271d0F', '0xA0b86991c6218b36c1d19D4a2e9Eb0cE3606eB48', '0xdAC17F958D2ee523a2206206994597C13D831ec7']
    ```
* `getPoolsLength()`: Returns number of entries in the registry. Includes removed pools.
    ```python
    >>> result = registry_contract.functions.getPoolsLength().call()
    13
    ```
* `getEligiblePools(address from, address to)`: Returns an array of pool addresses that can swap between from and to.
    ```python
    >>> USDC_addr = Web3.toChecksumAddress('0xa0b86991c6218b36c1d19d4a2e9eb0ce3606eb48')
    >>> DAI_addr = Web3.toChecksumAddress('0x6b175474e89094c44da98b954eedeac495271d0f')
    >>> result = registry_contract.functions.getEligiblePools(USDC_addr,DAI_addr)().call()
    ['0xaCb83E0633d6605c5001e2Ab59EF3C745547C8C7', '0x3911F80530595fBd01Ab1516Ab61255d75AEb066']
    ```
* `getTokenBalances(address poolAddress)`: Returns an array of the balances of the tokens in the given pool.
    ```python
    >>> result = registry_contract.functions.getTokenBalances('0xaCb83E0633d6605c5001e2Ab59EF3C745547C8C7').call()
    [6123569751818177679494553, 5703267707851, 4917216403671]
    ```
* `getUnderlyingTokenBalances(address poolAddress)`: Returns an array of balances of the underlying tokens in the given pool.
    ```python
    >>> result = registry_contract.functions.getUnderlyingTokenBalances('0x0C8BAe14c9f9BF2c953997C881BEfaC7729FD314').call()
    [583662682207327154772, 6123569751818177679494553, 5703267707851, 4917216403671]
    ```
