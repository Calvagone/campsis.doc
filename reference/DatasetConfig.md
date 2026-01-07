# Create a dataset configuration. This configuration allows CAMPSIS to know which are the default depot and observed compartments.

Create a dataset configuration. This configuration allows CAMPSIS to
know which are the default depot and observed compartments.

## Usage

``` r
DatasetConfig(
  defDepotCmt = 1,
  defObsCmt = 1,
  exportTSLD = FALSE,
  exportTDOS = FALSE,
  timeUnitDataset = "hour",
  timeUnitExport = "hour"
)
```

## Arguments

- defDepotCmt:

  default depot compartment, integer

- defObsCmt:

  default observation compartment, integer

- exportTSLD:

  export column TSLD (time since last dose), logical

- exportTDOS:

  export column TDOS (time of last dose), logical

- timeUnitDataset:

  unit of time in dataset, character ('hour' by default)

- timeUnitExport:

  unit of time in export, character ('hour' by default)

## Value

a dataset configuration
