# Changelog

## campsis 1.8.1

- Fix warnings from package ‘future’
  [\#188](https://github.com/Calvagone/campsis/issues/188)
- Update pkgdown website
  [\#191](https://github.com/Calvagone/campsis/issues/191)

## campsis 1.8.0

- JSON-based interface to import Campsis datasets
  [\#184](https://github.com/Calvagone/campsis/issues/184)
- Test failure under mrgsolve 1.7.0
  [\#186](https://github.com/Calvagone/campsis/issues/186)
- Update vdiffr tests
  [\#187](https://github.com/Calvagone/campsis/issues/187)

## campsis 1.7.0

CRAN release: 2025-04-04

- Bolus/Infusion: accept a vector of compartment names (1 or several)
  [\#176](https://github.com/Calvagone/campsis/issues/176)
- Bolus/Infusion: store arguments ‘as is’ in wrapper objects
  [\#177](https://github.com/Calvagone/campsis/issues/177)
- Bolus/Infusions: vectorize compartment properties
  [\#178](https://github.com/Calvagone/campsis/issues/178)
- Implement method ‘updateAmount’
  [\#179](https://github.com/Calvagone/campsis/issues/179)
- Implement methods ‘updateII’ and ‘updateADDL’
  [\#180](https://github.com/Calvagone/campsis/issues/180)
- Repeat the initial dosing schedule based on cycle duration
  [\#181](https://github.com/Calvagone/campsis/issues/181)
- Update pkgdown website before release
  [\#182](https://github.com/Calvagone/campsis/issues/182)

## campsis 1.6.0

CRAN release: 2025-02-09

- Add option to sample uncertainty from SIR or bootstrap output
  [\#87](https://github.com/Calvagone/campsis/issues/87)
- Include omegas and sigmas when simulating with uncertainty
  [\#150](https://github.com/Calvagone/campsis/issues/150)
- Warning raised: ‘package:stats’ may not be available when loading
  [\#157](https://github.com/Calvagone/campsis/issues/157)
- Future globals max size exceeded
  [\#166](https://github.com/Calvagone/campsis/issues/166)
- Method rxode2 should be called with envir set to NULL
  [\#167](https://github.com/Calvagone/campsis/issues/167)
- Allow Campsis model to be replicated beforehand when simulating with
  uncertainty [\#168](https://github.com/Calvagone/campsis/issues/168)
- Parameter uncertainty generation now managed by Campsismod
  [\#169](https://github.com/Calvagone/campsis/issues/169)
- Do not recompile mrgsolve model when SIGMAs change
  [\#170](https://github.com/Calvagone/campsis/issues/170)
- Get rid of plyr package
  [\#171](https://github.com/Calvagone/campsis/issues/171)
- Integration of the replication settings
  [\#172](https://github.com/Calvagone/campsis/issues/172)

## campsis 1.5.5

CRAN release: 2024-11-26

- Arm label mapping must first verify the ARM column exists
  [\#155](https://github.com/Calvagone/campsis/issues/155)
- Code coverage does not appear on codecov.io anymore
  [\#161](https://github.com/Calvagone/campsis/issues/161)
- Optionally skip tests using R options
  [\#162](https://github.com/Calvagone/campsis/issues/162)
- Do not build vignettes on CRAN
  [\#163](https://github.com/Calvagone/campsis/issues/163)
- Update pkgdown documentation
  [\#164](https://github.com/Calvagone/campsis/issues/164)

## campsis 1.5.4

CRAN release: 2024-08-30

- Add ‘label’ argument to ‘Dataset’ constructor
  [\#151](https://github.com/Calvagone/campsis/issues/151)
- Export of ‘SCENARIO’ column should be slightly revised
  [\#152](https://github.com/Calvagone/campsis/issues/152)

## campsis 1.5.3

CRAN release: 2024-07-01

- Argument outfun should be more flexible
  [\#146](https://github.com/Calvagone/campsis/issues/146)
- Function ‘vpcPlot’ not working with scenarios
  [\#147](https://github.com/Calvagone/campsis/issues/147)

## campsis 1.5.2

CRAN release: 2024-04-12

- Time unit support (dataset inputs / dataset export)
  [\#140](https://github.com/Calvagone/campsis/issues/140)
- Change ID column name in nhanes dataset
  [\#143](https://github.com/Calvagone/campsis/issues/143)

## campsis 1.5.1

CRAN release: 2024-02-16

- Progressr: call to tick() at the level of the slice may slow down the
  simulation (in specific circumstances)
  [\#130](https://github.com/Calvagone/campsis/issues/130)
- Layers added to multiple-arm dataset should apply to all arms
  [\#133](https://github.com/Calvagone/campsis/issues/133)
- Make NHANES data (DEMO + BMX) available in package campsis
  [\#134](https://github.com/Calvagone/campsis/issues/134)
- Bootstrap layer not shown when show is called on dataset
  [\#135](https://github.com/Calvagone/campsis/issues/135)
- Don’t raise exception when 2 boluses/infusions are given at same time
  [\#136](https://github.com/Calvagone/campsis/issues/136)
- Covariate name should be trimmed
  [\#137](https://github.com/Calvagone/campsis/issues/137)

## campsis 1.5.0

CRAN release: 2023-10-13

- Revise model library
  [\#126](https://github.com/Calvagone/campsis/issues/126)
- Improve default plots
  [\#125](https://github.com/Calvagone/campsis/issues/125)
- Add binomial distribution
  [\#124](https://github.com/Calvagone/campsis/issues/124)
- Quickly assign subjects using setSubjects
  [\#123](https://github.com/Calvagone/campsis/issues/123)
- Remove warnings generated by tidyverse
  [\#118](https://github.com/Calvagone/campsis/issues/118)

## campsis 1.4.1

CRAN release: 2023-04-24

- Packages in Suggests should be used conditionally
  [\#117](https://github.com/Calvagone/campsis/issues/117)

## campsis 1.4.0

CRAN release: 2023-04-13

- Run replicates in parallel
  [\#107](https://github.com/Calvagone/campsis/issues/107)
- Run scenarios in parallel
  [\#111](https://github.com/Calvagone/campsis/issues/111)
- Parallelise export of dataset
  [\#109](https://github.com/Calvagone/campsis/issues/109)
- Rework simulation settings
  [\#110](https://github.com/Calvagone/campsis/issues/110)
- Mrgsolve: don’t recompile model for each replicate
  [\#93](https://github.com/Calvagone/campsis/issues/93)
- Write new vignette about parallelisation
  [\#113](https://github.com/Calvagone/campsis/issues/113)
- Replace progress package by progressr package
  [\#108](https://github.com/Calvagone/campsis/issues/108)
- Write new vignette about progress bar
  [\#113](https://github.com/Calvagone/campsis/issues/113)
- Remove RxODE from the suggested packages (removed from CRAN)
  [\#106](https://github.com/Calvagone/campsis/issues/106)
- Remove messages output by rxode2 in console
  [\#114](https://github.com/Calvagone/campsis/issues/114)

## campsis 1.3.1

- Add scatter plot
  [\#103](https://github.com/Calvagone/campsis/issues/103).
- Use model_suite instead of model_library
  [\#101](https://github.com/Calvagone/campsis/issues/101)

## campsis 1.3.0

CRAN release: 2022-06-01

- Add new simulation engine rxode2
  [\#92](https://github.com/Calvagone/campsis/issues/92).
- Refactor all tests to support multiple simulation engines
  [\#92](https://github.com/Calvagone/campsis/issues/92)

## campsis 1.2.2

- Fix CRAN issues on M1 Mac architecture
  [\#90](https://github.com/Calvagone/campsis/issues/90).
- Remove call to suppressMessages when building mrgsolve model
  [\#91](https://github.com/Calvagone/campsis/issues/91)
- Export TSLD / TDOS columns on demand
  [\#94](https://github.com/Calvagone/campsis/issues/94)

## campsis 1.2.1

CRAN release: 2022-05-03

- Add a progress bar in simulations.
- Minor bug fixes
  ([\#85](https://github.com/Calvagone/campsis/issues/85),
  [\#86](https://github.com/Calvagone/campsis/issues/86)).

## campsis 1.2.0

CRAN release: 2022-02-16

- Added a `NEWS.md` file to track changes to the package.
- Initial release of campsis on CRAN.
