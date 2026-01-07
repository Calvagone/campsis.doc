# Define inter-occasion variability (IOV) into the dataset. A new variable of name 'colname' will be output into the dataset and will vary at each dose number according to the given distribution.

Define inter-occasion variability (IOV) into the dataset. A new variable
of name 'colname' will be output into the dataset and will vary at each
dose number according to the given distribution.

## Usage

``` r
IOV(colname, distribution, doseNumbers = NULL)
```

## Arguments

- colname:

  name of the column that will be output in dataset

- distribution:

  distribution

- doseNumbers:

  dose numbers, if provided, IOV is generated at these doses only. By
  default, IOV is generated for all doses.

## Value

an IOV object
