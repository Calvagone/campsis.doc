# Get all distinct times for the specified object.

Get all distinct times for the specified object.

## Usage

``` r
getTimes(object, ...)

# S4 method for class 'treatment'
getTimes(object, unwrap = TRUE)

# S4 method for class 'observations'
getTimes(object, doseTimes = NULL)

# S4 method for class 'observations_set'
getTimes(object, doseTimes = NULL)

# S4 method for class 'arm'
getTimes(object)

# S4 method for class 'arms'
getTimes(object)

# S4 method for class 'events'
getTimes(object)

# S4 method for class 'dataset'
getTimes(object)
```

## Arguments

- object:

  any object

- ...:

  extra arguments like \`doseTimes\` in observations or \`unwrap\` in
  treatment

- unwrap:

  unwrap treatment before accessing the times, default value is TRUE

- doseTimes:

  times of the doses, only needed if a \[DosingSchedule()\] is referred
  to

## Value

numeric vector with all unique times, sorted
