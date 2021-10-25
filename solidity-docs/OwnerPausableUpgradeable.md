An ownable contract allows the owner to pause and unpause the
contract without a delay.

Only methods using the provided modifiers will be paused.

# Functions:

- [`pause()`](#OwnerPausableUpgradeable-pause--)
- [`unpause()`](#OwnerPausableUpgradeable-unpause--)

# Function `pause()` {#OwnerPausableUpgradeable-pause--}

Pause the contract. Revert if already paused.

# Function `unpause()` {#OwnerPausableUpgradeable-unpause--}

Unpause the contract. Revert if already unpaused.
