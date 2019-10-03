# Bogoliubov.jl

Sound wave modes and dynamics for cold gases.

## Types

Is it OK to use `VectorArray`s of `BdGMode`s, or should there be a `BdGModeVector` type?  That's all about efficiency, time will tell.

```
BdGMode
```
Has `Field` elements `u` and `v`, but is an N×M×2 `AbstractArray` for differential equation purposes.

```
BdGSpectrum
```
Mapping from frequencies to `BdGModes`.  Has a system, which could be `nothing`.  This is of type `Any` to avoid dependency on `BoseGas`.  It can be converted to a `VectorArray` of `BdGMode`s

```
BdGSpectrum(system::BoseGas, [range], onlypositivenorms=true)
```
Calls `oprm!` if necessary, then computes the spectrum.