# Setup default plan for the given simulation or hardware settings. This plan will prioritise the distribution of workers in the following order: 1) Replicates (if 'replicate_parallel' is enabled) 2) Scenarios (if 'scenario_parallel' is enabled) 3) Dataset export / slices (if 'dataset_export' or 'slice_parallel' is enabled)

Setup default plan for the given simulation or hardware settings. This
plan will prioritise the distribution of workers in the following
order: 1) Replicates (if 'replicate_parallel' is enabled) 2) Scenarios
(if 'scenario_parallel' is enabled) 3) Dataset export / slices (if
'dataset_export' or 'slice_parallel' is enabled)

## Usage

``` r
setupPlanDefault(object)
```

## Arguments

- object:

  simulation or hardware settings

## Value

nothing
