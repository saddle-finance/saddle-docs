# OwnerPausable

An ownable contract allows the owner to pause and unpause the contract without a delay.

Only methods using the provided modifiers will be paused.

## Functions:

- [`pause()`](ownerpausable.md#OwnerPausable-pause--)
- [`unpause()`](ownerpausable.md#OwnerPausable-unpause--)

## Function `pause()` <a id="OwnerPausable-pause--"></a>

Pause the contract. Revert if already paused.

## Function `unpause()` <a id="OwnerPausable-unpause--"></a>

Unpause the contract. Revert if already unpaused.
