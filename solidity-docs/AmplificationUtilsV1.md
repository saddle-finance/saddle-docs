A library to calculate and ramp the A parameter of a given `SwapUtils.Swap` struct.
This library assumes the struct is fully validated.

# Functions:

- [`getA(struct SwapUtilsV1.Swap self)`](#AmplificationUtilsV1-getA-struct-SwapUtilsV1-Swap-)
- [`getAPrecise(struct SwapUtilsV1.Swap self)`](#AmplificationUtilsV1-getAPrecise-struct-SwapUtilsV1-Swap-)
- [`rampA(struct SwapUtilsV1.Swap self, uint256 futureA_, uint256 futureTime_)`](#AmplificationUtilsV1-rampA-struct-SwapUtilsV1-Swap-uint256-uint256-)
- [`stopRampA(struct SwapUtilsV1.Swap self)`](#AmplificationUtilsV1-stopRampA-struct-SwapUtilsV1-Swap-)

# Events:

- [`RampA(uint256 oldA, uint256 newA, uint256 initialTime, uint256 futureTime)`](#AmplificationUtilsV1-RampA-uint256-uint256-uint256-uint256-)
- [`StopRampA(uint256 currentA, uint256 time)`](#AmplificationUtilsV1-StopRampA-uint256-uint256-)

# Function `getA(struct SwapUtilsV1.Swap self) → uint256` {#AmplificationUtilsV1-getA-struct-SwapUtilsV1-Swap-}

Return A, the amplification coefficient _ n _ (n - 1)

See the StableSwap paper for details

## Parameters:

- `self`: Swap struct to read from

## Return Values:

- A parameter

# Function `getAPrecise(struct SwapUtilsV1.Swap self) → uint256` {#AmplificationUtilsV1-getAPrecise-struct-SwapUtilsV1-Swap-}

Return A in its raw precision

See the StableSwap paper for details

## Parameters:

- `self`: Swap struct to read from

## Return Values:

- A parameter in its raw precision form

# Function `rampA(struct SwapUtilsV1.Swap self, uint256 futureA_, uint256 futureTime_)` {#AmplificationUtilsV1-rampA-struct-SwapUtilsV1-Swap-uint256-uint256-}

Start ramping up or down A parameter towards given futureA* and futureTime*
Checks if the change is too rapid, and commits the new A value only when it falls under
the limit range.

## Parameters:

- `self`: Swap struct to update

- `futureA_`: the new A to ramp towards

- `futureTime_`: timestamp when the new A should be reached

# Function `stopRampA(struct SwapUtilsV1.Swap self)` {#AmplificationUtilsV1-stopRampA-struct-SwapUtilsV1-Swap-}

Stops ramping A immediately. Once this function is called, rampA()
cannot be called for another 24 hours

## Parameters:

- `self`: Swap struct to update

# Event `RampA(uint256 oldA, uint256 newA, uint256 initialTime, uint256 futureTime)` {#AmplificationUtilsV1-RampA-uint256-uint256-uint256-uint256-}

No description

# Event `StopRampA(uint256 currentA, uint256 time)` {#AmplificationUtilsV1-StopRampA-uint256-uint256-}

No description
