# Create a dose adaptation.

Create a dose adaptation.

## Usage

``` r
DoseAdaptation(formula, compartments = NULL)
```

## Arguments

- formula:

  formula to apply, single character string, e.g. "AMT\*WT"

- compartments:

  compartment indexes or names where the formula needs to be applied,
  integer or character vector. Default is NULL (formula applied on all
  compartments)

## Value

a fixed covariate
