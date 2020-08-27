
[![Travis build
status](https://travis-ci.org/levisc8/RPadrino.svg?branch=master)](https://travis-ci.org/levisc8/RPadrino)
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

### Usage

A small-ish copy of the Padrino Database is included as a package data
set. You can access it with the following code:

``` r

data("pdb_ex")
```

The next step is to identify the models we are interested in building.
At the moment, there is no functionality to do that - you’ll just have
to explore the *Metadata* table on your own. In the not so distant
future, there will be a set of functions that actually help query
specific columns of interest so the process of exploring the database is
less painful.

Once, we’ve identified the model(s) we want, we can build a list of
[`proto_ipm`’s](https://levisc8.github.io/ipmr/articles/proto-ipms.html).
This is an intermediate step between the database representation and a
set of iteration kernels. Once we have this, we can build an actual
model. Below, we extract a specific study, Levin et al. 2019, and
construct an IPM from the database object.

``` r

# Generate an index to subset the database with

subset_index <- pdb_ex$Metadata$ipm_id[pdb_ex$Metadata$corresponding_author == "Levin"]

# This lapply statement extracts all rows from the database that correspond to our desired study/studies

use_db       <- lapply(pdb_ex,
                       function(x, subset_ind) x[x$ipm_id %in% subset_ind, ],
                       subset_ind = subset_index)

# We can construct a single IPM at a time, or make a list of many IPMs

proto_list   <- make_proto_ipm(use_db, 
                               ipm_id = subset_index[1],
                               det_stoch = "det")


ipm_list     <- make_ipm(proto_list)
```

### Further steps

The package is documented [here]() and the database is documented
[here]().

### Contributing

Please note that the RPadrino project is released with a [Contributor
Code of
Conduct](https://contributor-covenant.org/version/2/0/CODE_OF_CONDUCT.html).
By contributing to this project, you agree to abide by its terms.
