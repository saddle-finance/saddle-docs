An ownable contract allows the owner to pause and unpause the
contract without a delay.

Only methods using the provided modifiers will be paused.

# Functions:

- [`pause()`](#OwnerPausable-pause--)
- [`unpause()`](#OwnerPausable-unpause--)

# Function `pause()` {#OwnerPausable-pause--}

Pause the contract. Revert if already paused.

# Function `unpause()` {#OwnerPausable-unpause--}

Unpause the contract. Revert if already unpaused.
