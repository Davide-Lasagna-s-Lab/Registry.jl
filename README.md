# Davide-Lasagna-s-Lab Julia Registry

Private Julia package registry for packages developed at
[Davide-Lasagna-s-Lab](https://github.com/Davide-Lasagna-s-Lab).

## Registered packages

| Package | Description |
|---------|-------------|
| [ChebUtils.jl](https://github.com/Davide-Lasagna-s-Lab/ChebUtils.jl) | Chebyshev utilities |
| [Continuation.jl](https://github.com/Davide-Lasagna-s-Lab/Continuation.jl) | Numerical continuation |
| [FDGrids.jl](https://github.com/Davide-Lasagna-s-Lab/FDGrids.jl) | Finite-difference grids and operators |
| [FDHelmoltzSolver.jl](https://github.com/Davide-Lasagna-s-Lab/FDHelmoltzSolver.jl) | FD Helmholtz solver |
| [Flows.jl](https://github.com/Davide-Lasagna-s-Lab/Flows.jl) | Time-integration for dynamical systems |
| [GMRES.jl](https://github.com/Davide-Lasagna-s-Lab/GMRES.jl) | GMRES iterative solver |
| [HaloArrays.jl](https://github.com/Davide-Lasagna-s-Lab/HaloArrays.jl) | MPI halo-exchange arrays |
| [NKRoots.jl](https://github.com/Davide-Lasagna-s-Lab/NKRoots.jl) | Newton–Krylov root finding |
| [NKSearch.jl](https://github.com/Davide-Lasagna-s-Lab/NKSearch.jl) | Newton–Krylov search |
| [NSEBase.jl](https://github.com/Davide-Lasagna-s-Lab/NSEBase.jl) | Navier–Stokes spectral base layer |
| [NSEBaseMPIExt.jl](https://github.com/Davide-Lasagna-s-Lab/NSEBaseMPIExt.jl) | MPI extension for NSEBase |
| [OpenKolmogorovFlow.jl](https://github.com/Davide-Lasagna-s-Lab/OpenKolmogorovFlow.jl) | Kolmogorov flow simulations |
| [ReSolver.jl](https://github.com/Davide-Lasagna-s-Lab/ReSolver.jl) | Resolvent analysis framework |
| [ReSolver-ChannelFlow.jl](https://github.com/Davide-Lasagna-s-Lab/ReSolver-ChannelFlow.jl) | ReSolver for plane channel flow |
| [ReSolver-ChannelFlowGPU.jl](https://github.com/Davide-Lasagna-s-Lab/ReSolver-ChannelFlowGPU.jl) | GPU extension for channel flow |
| [ReSolver-ChannelFlowMP.jl](https://github.com/Davide-Lasagna-s-Lab/ReSolver-ChannelFlowMP.jl) | Multi-precision channel flow |
| [ReSolver-SquareDuct.jl](https://github.com/Davide-Lasagna-s-Lab/ReSolver-SquareDuct.jl) | ReSolver for square-duct flow |
| [Resolvent.jl](https://github.com/Davide-Lasagna-s-Lab/Resolvent.jl) | Resolvent analysis tools |
| [Resolver-OptimAlgorithms.jl](https://github.com/Davide-Lasagna-s-Lab/Resolver-OptimAlgorithms.jl) | Optimisation algorithms for ReSolver |
| [SPOD.jl](https://github.com/Davide-Lasagna-s-Lab/SPOD.jl) | Spectral proper orthogonal decomposition |
| [StreamingRecurrenceAnalysis.jl](https://github.com/Davide-Lasagna-s-Lab/StreamingRecurrenceAnalysis.jl) | Streaming recurrence analysis |
| [ToySystems.jl](https://github.com/Davide-Lasagna-s-Lab/ToySystems.jl) | Toy dynamical systems for testing |

## Adding the registry

Run this once in any Julia session to make all packages installable with `Pkg.add`:

```julia
using Pkg
Pkg.Registry.add(Pkg.RegistrySpec(url = "https://github.com/Davide-Lasagna-s-Lab/Registry.jl"))
```

After that, install any package normally:

```julia
Pkg.add("NSEBase")
Pkg.add("FDGrids")
Pkg.add("ReSolverSquareDuct")
# etc.
```

## Updating the registry after a new package release

After bumping the version in a package's `Project.toml` and pushing the commit:

```julia
using LocalRegistry
register("/path/to/MyPackage.jl";
         registry = "/path/to/Registry.jl",
         push = true)
```

Or to register a new package for the first time, use the same `register` call —
`LocalRegistry` detects automatically whether it is a first registration or a version update.
