# Tensor4All Registry

[![Registry Consistency](https://github.com/tensor4all/T4ARegistry/actions/workflows/registry-consistency-ci.yml/badge.svg)](https://github.com/tensor4all/T4ARegistry/actions/workflows/registry-consistency-ci.yml)

This registry is intended for packages developed as part of the Tensor4All project. It simplifies installation and resolution of dependencies for users. To add this registry to your installation of julia, type the following in a REPL:

```console
$ julia
               _
   _       _ _(_)_     |  Documentation: https://docs.julialang.org
  (_)     | (_) (_)    |
   _ _   _| |_  __ _   |  Type "?" for help, "]?" for Pkg help.
  | | | | | | |/ _` |  |
  | | |_| | | | (_| |  |  Version 1.9.4 (2023-11-14)
 _/ |\__'_|_|_|\__'_|  |  Official https://julialang.org/ release
|__/                   |

julia> using Pkg; Pkg.Registry.add(RegistrySpec(url="git@github.com:tensor4all/T4ARegistry.git"))
julia> exit()
```

Now, all packages should be available for installation using the usual `add` command. For instance,

```julia
julia> import Pkg; Pkg.add("Quantics")
```

should install `Quantics.jl`.

## Packages registered in General registry

Our Julia packages `TensorCrossInterpolation`, `QuanticsGrids`, `QuanticsTCI` are registered in the official Julia registry(named `General`). If we update these packages, please register the new version in General registry using JuliaHub. See https://help.juliahub.com/juliahub/stable/contribute/ to learn how to register new version.

## Troubleshooting

Note that you need to have an SSH key added to your account and readable by julia's package manager. For many versions, this requires a specific format. If you encounter any error messages related to SSH, or if the package manager fails to add the registry after repeatedly asking for a key file, refer to this document:
[https://github.com/GunnarFarneback/LocalRegistry.jl/blob/master/docs/ssh_keys.md](https://github.com/GunnarFarneback/LocalRegistry.jl/blob/master/docs/ssh_keys.md)

You may want to set the environment variable `JULIA_PKG_USE_CLI_GIT=true`. See [Using an External git Binary with Julia's Package Manager](https://github.com/GunnarFarneback/LocalRegistry.jl/blob/master/docs/ssh_keys.md#2-using-an-external-git-binary-with-julias-package-manager).

```console
$  JULIA_PKG_USE_CLI_GIT=true julia
               _
   _       _ _(_)_     |  Documentation: https://docs.julialang.org
  (_)     | (_) (_)    |
   _ _   _| |_  __ _   |  Type "?" for help, "]?" for Pkg help.
  | | | | | | |/ _` |  |
  | | |_| | | | (_| |  |  Version 1.9.4 (2023-11-14)
 _/ |\__'_|_|_|\__'_|  |  Official https://julialang.org/ release
|__/                   |

julia> ENV["JULIA_PKG_USE_CLI_GIT"]
"true"
```
