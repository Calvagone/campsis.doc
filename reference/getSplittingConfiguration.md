# Get splitting configuration for parallel export.

Get splitting configuration for parallel export.

## Usage

``` r
getSplittingConfiguration(dataset, hardware)
```

## Arguments

- dataset:

  Campsis dataset to export

- hardware:

  hardware configuration

## Value

splitting configuration list (if 'dataset_parallel' is enabled) or NA
(if 'dataset_parallel' disabled or if the length of the dataset is less
than the dataset export slice size)
