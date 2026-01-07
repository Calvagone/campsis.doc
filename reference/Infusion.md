# Create one or several infusion(s).

Create one or several infusion(s).

## Usage

``` r
Infusion(
  time,
  amount,
  compartment = NULL,
  f = NULL,
  lag = NULL,
  duration = NULL,
  rate = NULL,
  ii = NULL,
  addl = NULL,
  wrap = TRUE,
  ref = NULL,
  rep = NULL
)
```

## Arguments

- time:

  treatment time(s), numeric value or vector. First treatment time if
  used together with ii and addl.

- amount:

  amount to infuse, single numeric value

- compartment:

  compartment index or name to give the infusion(s). A vector of
  integers or names can be used for a complex model administration.

- f:

  fraction of infusion amount, list of distributions (one per
  compartment)

- lag:

  infusion lag time, , list of distributions (one per compartment)

- duration:

  infusion duration, list of distributions (one per compartment)

- rate:

  infusion rate, list of distributions (one per compartment)

- ii:

  inter-dose interval, requires argument 'time' to be a single numeric
  value

- addl:

  number of additional doses, requires argument 'time' to be a single
  integer value

- wrap:

  if TRUE, the infusion wrapper will be stored as is in the dataset,
  otherwise, it will be split into a list of infusions distinct in time.
  Default is TRUE.

- ref:

  any reference name used to identify this infusion, single character
  value

- rep:

  repeat the base dosing schedule several times, a 'repeated schedule'
  object is expected. Default is NULL (no repetition).

## Value

a single infusion or a list of infusions.
