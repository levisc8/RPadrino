
[![Travis build
status](https://travis-ci.org/levisc8/RPadrino.svg?branch=master)](https://travis-ci.com/levisc8/RPadrino)
[![Codecov test
coverage](https://codecov.io/gh/levisc8/RPadrino/branch/master/graph/badge.svg)](https://codecov.io/gh/levisc8/RPadrino?branch=master)

## RPadrino

`RPadrino` is a package for interacting with the demography data base of
the same name. It will likely consist of wrappers to an SQL data base
that itself houses a suite of all known, published integral projection
models (IPMs). Additionally, we’ll build in some basic tools to
re-create the IPMs *as they were created in the original publication*.

## Scope

The goal of this package is basic data management, exploration, and
porting Padrino’s internal syntax to
[`ipmr`’s](https://levisc8.github.io/ipmr/) syntax. Ideally, one could
combine models from here with their own models for synthesis work, using
the `proto_ipm` as a common data structure to power the analysis.

### Installation

You can install RPadrino from github with:

``` r

if(!requireNamespace("remotes", quietly = TRUE)) {
  install.packages("remotes")
}

remotes::install_github("levisc8/RPadrino")
```

### Contributing

Please note that the RPadrino project is released with a [Contributor
Code of
Conduct](https://contributor-covenant.org/version/2/0/CODE_OF_CONDUCT.html).
By contributing to this project, you agree to abide by its terms.
