# Saddle Registry

Saddle Registries provides a single source for integrating with the Saddle ecosystem. The Master Registry's  will maintain a collection of all current registries as well as a history of previous versions. One available registry is the Pool Registry that allows anyone to retrieve pool specific data as well as a history of all pool deployments. Events on the registry contracts will allow for listeners to be notified of any change in the Saddle ecvosystem related to new deployments or updates to existing deployments.<br><br>

## Master Registry<br>

This contract holds information on all available Saddle Registries.<br> 
| Network | Address                                                                                                            |
| :------------ | :------------------------------------------------------------------------------------------------------------------------- |
| `Ethereum`   | [0xc5ad17b98D7fe73B6dD3b0df5b3040457E68C045](https://etherscan.io/address/0xc5ad17b98D7fe73B6dD3b0df5b3040457E68C045#code) |

<br>

### Master Registry Events

* Retrieve all event of registries that have been added to the Master Registry:

    ``` python
    from web3 import Web3
    import json


    # Initialize web3 connection
    web3 = Web3(Web3.HTTPProvider('<provider>'))  
    ABI = json.loads('<contract_abi>')
    master_registry_addr = '0xc5ad17b98D7fe73B6dD3b0df5b3040457E68C045'
    registry_contract = web3.eth.contract(master_registry_addr, abi=ABI)

    # create the filter and print all entries of this event in the range of blocks provided
        filter = registry_contract.events.AddRegistry.createFilter(fromBlock=0, toBlock='latest')
        print(filter.get_all_entries())

    ```
<br>

## Pool Registry <br>

This contract holds the funtions to get deployment addresses and related info for all Saddle Pools. It allows for listening to events related to registry actions such as removing/adding pools, as well as any updates to existing pools. <br>

| Network | Address                                                                                                            |
| :------------ | :------------------------------------------------------------------------------------------------------------------------- |
| `Ethereum`   | [0xFb4DE84c4375d7c8577327153dE88f58F69EeC81](https://etherscan.io/address/0xFb4DE84c4375d7c8577327153dE88f58F69EeC81#code) |

<br>

### Pool Registry Interactions

The Pool Registry's functions allow you to fetch pool data is, as well as listen for pool events:

* Getting all available PoolData

    ```python
    from web3 import Web3
    import json


    def getPoolData():
        # Setup Web3 and registry contract
        w3 = Web3(Web3.HTTPProvider('<provider'))
        
        ABI = json.loads(<contract_abi>)
        pool_reg_addr = '0xFb4DE84c4375d7c8577327153dE88f58F69EeC81'
        registry_contract = w3.eth.contract(pool_reg_addr, abi=ABI)
        
        # Find the length of the registry
        registry_length = registry_contract.functions.getPoolsLength().call()
        
        # Get PoolData for each pool index
        for index in range(registry_length-1):
            pool_data = registry_contract.functions.getPoolDataAtIndex(index).call()
            
            PoolData_labels = [
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
            return_array = []
            for label in PoolData_labels:
                if label['type'] == 'bytes32':
                    return_array.append(((label['name'])+' : '+str((pool_data[PoolData_labels.index(lable)]).decode('utf-8'))))
                else:
                    return_array.append((label['name']+' : '+str(pool_data[PoolData_labels.index(label)])))
            print("\n".join(return_array))
            print("\n")
    ```
* Get all events that the PoolRegistry has ever produced
    ```python
    from web3 import Web3
    import json


    # Initialize web3 connection
    web3 = Web3(Web3.HTTPProvider('<provider>'))  
    ABI = json.loads('<contract_abi>')
    pool_registry_addr = '0xFb4DE84c4375d7c8577327153dE88f58F69EeC81'
    registry_contract = web3.eth.contract(pool_registry_addr, abi=ABI)

     # create the filter and print all entries of this event in the range of blocks provided
    filter = registry_contract.events.AddRegistry.createFilter(fromBlock=0, toBlock='latest')
    print(filter.get_all_entries())
    ```
