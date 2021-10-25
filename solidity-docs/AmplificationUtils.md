A library to calculate and ramp the A parameter of a given `SwapUtils.Swap` struct.
This library assumes the struct is fully validated.

# Functions:

- [`getA(struct SwapUtils.Swap self)`](#AmplificationUtils-getA-struct-SwapUtils-Swap-)
- [`getAPrecise(struct SwapUtils.Swap self)`](#AmplificationUtils-getAPrecise-struct-SwapUtils-Swap-)
- [`rampA(struct SwapUtils.Swap self, uint256 futureA_, uint256 futureTime_)`](#AmplificationUtils-rampA-struct-SwapUtils-Swap-uint256-uint256-)
- [`stopRampA(struct SwapUtils.Swap self)`](#AmplificationUtils-stopRampA-struct-SwapUtils-Swap-)

# Events:

- [`RampA(uint256 oldA, uint256 newA, uint256 initialTime, uint256 futureTime)`](#AmplificationUtils-RampA-uint256-uint256-uint256-uint256-)
- [`StopRampA(uint256 currentA, uint256 time)`](#AmplificationUtils-StopRampA-uint256-uint256-)

# Function `getA(struct SwapUtils.Swap self) → uint256` {#AmplificationUtils-getA-struct-SwapUtils-Swap-}

Return A, the amplification coefficient _ n _ (n - 1)

See the StableSwap paper for details

## Parameters:

- `self`: Swap struct to read from

## Return Values:

- A parameter

# Function `getAPrecise(struct SwapUtils.Swap self) → uint256` {#AmplificationUtils-getAPrecise-struct-SwapUtils-Swap-}

Return A in its raw precision

See the StableSwap paper for details

## Parameters:

- `self`: Swap struct to read from

## Return Values:

- A parameter in its raw precision form

# Function `rampA(struct SwapUtils.Swap self, uint256 futureA_, uint256 futureTime_)` {#AmplificationUtils-rampA-struct-SwapUtils-Swap-uint256-uint256-}

Start ramping up or down A parameter towards given futureA* and futureTime*
Checks if the change is too rapid, and commits the new A value only when it falls under
the limit range.

## Parameters:

- `self`: Swap struct to update

- `futureA_`: the new A to ramp towards

- `futureTime_`: timestamp when the new A should be reached

# Function `stopRampA(struct SwapUtils.Swap self)` {#AmplificationUtils-stopRampA-struct-SwapUtils-Swap-}

Stops ramping A immediately. Once this function is called, rampA()
cannot be called for another 24 hours

## Parameters:

- `self`: Swap struct to update

# Event `RampA(uint256 oldA, uint256 newA, uint256 initialTime, uint256 futureTime)` {#AmplificationUtils-RampA-uint256-uint256-uint256-uint256-}

No description

# Event `StopRampA(uint256 currentA, uint256 time)` {#AmplificationUtils-StopRampA-uint256-uint256-}

No description
