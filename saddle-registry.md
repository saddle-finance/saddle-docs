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

    ``` typescript
    const hre = require("hardhat");
    const { ethers } = require("@nomiclabs/hardhat-ethers");
    import registry_abi from "../master_registry_abi.json";

    async function main() {

        // Initialize contract
        const registry = await hre.ethers.getContractAt(registry_abi, "0xc5ad17b98D7fe73B6dD3b0df5b3040457E68C045");

        // Get all AddRegistry events
        const provider = hre.ethers.provider;

        // Optionally you can add a 'topics' field to the filter to only search
        // for certain events
        const filter = {
            address: registry.address,
            fromBlock: 0,
            toBlock: 'latest',
        };
        const filtered_logs = await provider.getLogs(filter);

        // Setup interface for registry
        const iface = new hre.ethers.utils.Interface(registry_abi)
        // Parse each log into a readable event
        for (let i = 0; i < filtered_logs.length; i++) {
            const decoded = iface.parseLog(filtered_logs[i]);
            console.log(decoded);
        }
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

    ```typescript
    const hre = require("hardhat");
    const { ethers } = require("@nomiclabs/hardhat-ethers");
    const toNumber = hre.ethers.utils.toNumber
    import registry_abi from "../registry_abi.json";

    async function main() {

        // Initialize contract
        const registry = await hre.ethers.getContractAt(registry_abi['abi'], "0xFb4DE84c4375d7c8577327153dE88f58F69EeC81");

        // Find legth of registry
        const registryLength = (await registry.getPoolsLength()).toString();
        console.log(registryLength);

        // Get PoolDataAtIndex for each pool index and append to list
        let poolDataList = [];
        for (let i = 0; i < registryLength; i++) {
            const poolData = await registry.getPoolDataAtIndex(i);
            poolDataList.push(poolData);
        }
        console.log(poolDataList.length);

    }
    ```
* Get all events that the PoolRegistry has ever produced
    ```typescript
    const hre = require("hardhat");
    const { ethers } = require("@nomiclabs/hardhat-ethers");
    import registry_abi from "../registry_abi.json";

    async function main() {

        // Initialize contract
        const registry = await hre.ethers.getContractAt(registry_abi, "0xFb4DE84c4375d7c8577327153dE88f58F69EeC81");

        // Get all AddRegistry events
        const provider = hre.ethers.provider;
        
        // Optionally you can add a 'topics' field to the filter to only search
        // for certain events
        const filter = {
            address: registry.address,
            fromBlock: 0,
            toBlock: 'latest',
        };
        const filtered_logs = await provider.getLogs(filter);

        // Setup interface for registry
        const iface = new hre.ethers.utils.Interface(registry_abi)
        // Parse each log into a readable event
        for (let i = 0; i < filtered_logs.length; i++) {
            const decoded = iface.parseLog(filtered_logs[i]);
            console.log(decoded);
        }
    }
    ```
    