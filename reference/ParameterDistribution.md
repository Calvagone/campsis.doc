# Create a parameter distribution. The resulting distribution is a log-normal distribution, with meanlog=log(THETA) and sdlog=sqrt(OMEGA).

Create a parameter distribution. The resulting distribution is a
log-normal distribution, with meanlog=log(THETA) and sdlog=sqrt(OMEGA).

## Usage

``` r
ParameterDistribution(model, theta, omega = NULL)
```

## Arguments

- model:

  model

- theta:

  corresponding THETA name, character

- omega:

  corresponding OMEGA name, character, NULL if not defined

## Value

a parameter distribution
