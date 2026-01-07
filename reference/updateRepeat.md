# Update the repeat field (argument 'rep' in Bolus and Infusion constructors).

Update the repeat field (argument 'rep' in Bolus and Infusion
constructors).

## Usage

``` r
updateRepeat(object, rep, ref = NULL)

# S4 method for class 'bolus_wrapper,repeated_schedule,character'
updateRepeat(object, rep, ref = NULL)

# S4 method for class 'infusion_wrapper,repeated_schedule,character'
updateRepeat(object, rep, ref = NULL)

# S4 method for class 'bolus,repeated_schedule,character'
updateRepeat(object, rep, ref = NULL)

# S4 method for class 'infusion,repeated_schedule,character'
updateRepeat(object, rep, ref = NULL)

# S4 method for class 'treatment,repeated_schedule,character'
updateRepeat(object, rep, ref = NULL)

# S4 method for class 'arm,repeated_schedule,character'
updateRepeat(object, rep, ref = NULL)

# S4 method for class 'arms,repeated_schedule,character'
updateRepeat(object, rep, ref = NULL)

# S4 method for class 'dataset,repeated_schedule,character'
updateRepeat(object, rep, ref = NULL)
```

## Arguments

- object:

  generic object

- rep:

  repeated dosing schedule (definition) object

- ref:

  reference treatment name

## Value

updated object
