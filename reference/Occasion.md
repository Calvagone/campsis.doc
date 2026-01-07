# Define a new occasion. Occasions are defined by mapping occasion values to dose numbers. A new column will automatically be created in the exported dataset.

Define a new occasion. Occasions are defined by mapping occasion values
to dose numbers. A new column will automatically be created in the
exported dataset.

## Usage

``` r
Occasion(colname, values, doseNumbers)
```

## Arguments

- colname:

  name of the column that will be output in dataset

- values:

  the occasion numbers, any integer vector

- doseNumbers:

  the related dose numbers, any integer vector of same length as
  'values'

## Value

occasion object
