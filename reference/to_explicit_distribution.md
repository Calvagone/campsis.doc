# Convert user-given distribution to an explicit Campsis distribution. Passed distribution can be: - a NULL value. In that case, it will be converted into an 'UndefinedDistribution'. - a single numeric value. In that case, it will be converted into a 'ConstantDistribution'. - a numeric vector. In that case, it will be converted into a 'FixedDistribution'. - all available types of distribution. In this case, no conversion is applied.

Convert user-given distribution to an explicit Campsis distribution.
Passed distribution can be: - a NULL value. In that case, it will be
converted into an 'UndefinedDistribution'. - a single numeric value. In
that case, it will be converted into a 'ConstantDistribution'. - a
numeric vector. In that case, it will be converted into a
'FixedDistribution'. - all available types of distribution. In this
case, no conversion is applied.

## Usage

``` r
to_explicit_distribution(distribution)
```

## Arguments

- distribution:

  user-given distribution

## Value

a distribution object
