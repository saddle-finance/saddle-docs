This contract is responsible for migrating old USD pool liquidity to the new ones.
Users can use this contract to remove their liquidity from the old pools and add them to the new
ones with a single transaction.

# Functions:

- [`constructor(struct SwapMigrator.MigrationData usdData_, address owner_)`](#SwapMigrator-constructor-struct-SwapMigrator-MigrationData-address-)
- [`migrateUSDPool(uint256 amount, uint256 minAmount)`](#SwapMigrator-migrateUSDPool-uint256-uint256-)
- [`rescue(contract IERC20 token, address to)`](#SwapMigrator-rescue-contract-IERC20-address-)

# Function `constructor(struct SwapMigrator.MigrationData usdData_, address owner_)` {#SwapMigrator-constructor-struct-SwapMigrator-MigrationData-address-}

Sets the storage variables and approves tokens to be used by the old and new swap contracts

## Parameters:

- `usdData_`: MigrationData struct with information about old and new USD pools

- `owner_`: owner that is allowed to call the `rescue()` function

# Function `migrateUSDPool(uint256 amount, uint256 minAmount) → uint256` {#SwapMigrator-migrateUSDPool-uint256-uint256-}

Migrates old USD pool's LPToken to the new pool

## Parameters:

- `amount`: Amount of old LPToken to migrate

- `minAmount`: Minimum amount of new LPToken to receive

# Function `rescue(contract IERC20 token, address to)` {#SwapMigrator-rescue-contract-IERC20-address-}

Rescues any token that may be sent to this contract accidentally.

## Parameters:

- `token`: Amount of old LPToken to migrate

- `to`: Minimum amount of new LPToken to receive
