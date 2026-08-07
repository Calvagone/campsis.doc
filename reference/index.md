# Package index

## Dataset elements

- [`Arm()`](https://calvagone.github.io/campsis.doc/reference/Arm.md) :
  Create a treatment arm.
- [`Bolus()`](https://calvagone.github.io/campsis.doc/reference/Bolus.md)
  : Create one or several bolus(es).
- [`Bootstrap()`](https://calvagone.github.io/campsis.doc/reference/Bootstrap.md)
  : Create a bootstrap object.
- [`Covariate()`](https://calvagone.github.io/campsis.doc/reference/Covariate.md)
  : Create a non time-varying (fixed) covariate.
- [`Dataset()`](https://calvagone.github.io/campsis.doc/reference/Dataset.md)
  : Create a dataset.
- [`DatasetConfig()`](https://calvagone.github.io/campsis.doc/reference/DatasetConfig.md)
  : Create a dataset configuration. This configuration allows Campsis to
  know which are the default depot and observed compartments.
- [`DoseAdaptation()`](https://calvagone.github.io/campsis.doc/reference/DoseAdaptation.md)
  : Create a dose adaptation.
- [`EventCovariate()`](https://calvagone.github.io/campsis.doc/reference/EventCovariate.md)
  : Create an event covariate. These covariates can be modified further
  in interruption events.
- [`Infusion()`](https://calvagone.github.io/campsis.doc/reference/Infusion.md)
  : Create one or several infusion(s).
- [`IOV()`](https://calvagone.github.io/campsis.doc/reference/IOV.md) :
  Define inter-occasion variability (IOV) into the dataset. A new
  variable of name 'colname' will be output into the dataset and will
  vary at each dose number according to the given distribution.
- [`Observations()`](https://calvagone.github.io/campsis.doc/reference/Observations.md)
  : Create an observations list. Please note that the provided 'times'
  will automatically be sorted. Duplicated times will be removed.
- [`Occasion()`](https://calvagone.github.io/campsis.doc/reference/Occasion.md)
  : Define a new occasion. Occasions are defined by mapping occasion
  values to dose numbers. A new column will automatically be created in
  the exported dataset.
- [`TimeVaryingCovariate()`](https://calvagone.github.io/campsis.doc/reference/TimeVaryingCovariate.md)
  : Create a time-varying covariate. This covariate will be implemented
  using EVID=2 rows in the exported dataset and will not use
  interruption events.

## Distributions

- [`BinomialDistribution()`](https://calvagone.github.io/campsis.doc/reference/BinomialDistribution.md)
  : Binomial distribution.
- [`BootstrapDistribution()`](https://calvagone.github.io/campsis.doc/reference/BootstrapDistribution.md)
  : Create a bootstrap distribution. During function sampling, Campsis
  will generate values depending on the given data and arguments.
- [`ConstantDistribution()`](https://calvagone.github.io/campsis.doc/reference/ConstantDistribution.md)
  : Create a constant distribution. Its value will be constant across
  all generated samples.
- [`DiscreteDistribution()`](https://calvagone.github.io/campsis.doc/reference/DiscreteDistribution.md)
  : Discrete distribution.
- [`EtaDistribution()`](https://calvagone.github.io/campsis.doc/reference/EtaDistribution.md)
  : Create an ETA distribution. The resulting distribution is a normal
  distribution, with mean=0 and sd=sqrt(OMEGA).
- [`FixedDistribution()`](https://calvagone.github.io/campsis.doc/reference/FixedDistribution.md)
  : Create a fixed distribution. Each sample will be assigned a fixed
  value coming from vector 'values'.
- [`FunctionDistribution()`](https://calvagone.github.io/campsis.doc/reference/FunctionDistribution.md)
  : Create a function distribution. During distribution sampling, the
  provided function will be responsible for generating values for each
  sample. If first argument of this function is not the size (n), please
  tell which argument corresponds to the size 'n' (e.g. list(size="n")).
- [`LogNormalDistribution()`](https://calvagone.github.io/campsis.doc/reference/LogNormalDistribution.md)
  : Create a log normal distribution.
- [`NormalDistribution()`](https://calvagone.github.io/campsis.doc/reference/NormalDistribution.md)
  : Create a normal distribution.
- [`ParameterDistribution()`](https://calvagone.github.io/campsis.doc/reference/ParameterDistribution.md)
  : Create a parameter distribution. The resulting distribution is a
  log-normal distribution, with meanlog=log(THETA) and
  sdlog=sqrt(OMEGA).
- [`UniformDistribution()`](https://calvagone.github.io/campsis.doc/reference/UniformDistribution.md)
  : Create an uniform distribution.

## Dosing schedules and helpers

- [`DosingSchedule()`](https://calvagone.github.io/campsis.doc/reference/DosingSchedule.md)
  : Dosing schedule constructor.
- [`CyclicSchedule()`](https://calvagone.github.io/campsis.doc/reference/CyclicSchedule.md)
  : Cyclic schedule constructor.
- [`RepeatAtSchedule()`](https://calvagone.github.io/campsis.doc/reference/RepeatAtSchedule.md)
  : 'Repeat at' schedule constructor. Note that the time 0 for the base
  pattern will be added by default if not provided.
- [`TimeSequence()`](https://calvagone.github.io/campsis.doc/reference/TimeSequence.md)
  : Instantiate a new time sequence.
- [`TimeVector()`](https://calvagone.github.io/campsis.doc/reference/TimeVector.md)
  : Instantiate a new time vector

## Dataset shortcuts

- [`set_label()`](https://calvagone.github.io/campsis.doc/reference/set_label.md)
  : Set the label.
- [`set_subjects()`](https://calvagone.github.io/campsis.doc/reference/set_subjects.md)
  : Set the number of subjects.
- [`update_addl()`](https://calvagone.github.io/campsis.doc/reference/update_addl.md)
  : Update the number of additional doses (ADDL).
- [`update_amount()`](https://calvagone.github.io/campsis.doc/reference/update_amount.md)
  : Update amount.
- [`update_ii()`](https://calvagone.github.io/campsis.doc/reference/update_ii.md)
  : Update the inter-dose interval (II).
- [`update_repeat()`](https://calvagone.github.io/campsis.doc/reference/update_repeat.md)
  : Update the repeat field (argument 'rep' in Bolus and Infusion
  constructors).

## Create events

- [`Event()`](https://calvagone.github.io/campsis.doc/reference/Event.md)
  : Create an interruption event.
- [`Events()`](https://calvagone.github.io/campsis.doc/reference/Events.md)
  : Create a list of interruption events.

## Create scenarios

- [`Scenario()`](https://calvagone.github.io/campsis.doc/reference/Scenario.md)
  : Create an scenario.
- [`Scenarios()`](https://calvagone.github.io/campsis.doc/reference/Scenarios.md)
  : Create a list of scenarios.
- [`ReplaceAction()`](https://calvagone.github.io/campsis.doc/reference/ReplaceAction.md)
  : Create a replace action.

## Sample distributions

- [`sample()`](https://calvagone.github.io/campsis.doc/reference/sample.md)
  : Sample generic object.

## Predefined output functions

- [`DefaultOutfun()`](https://calvagone.github.io/campsis.doc/reference/DefaultOutfun.md)
  : Default output function (identity function).
- [`Outfun()`](https://calvagone.github.io/campsis.doc/reference/Outfun.md)
  : Create a new output function
- [`Outfuns()`](https://calvagone.github.io/campsis.doc/reference/Outfuns.md)
  : Create a collection of output functions.
- [`PIOutfun()`](https://calvagone.github.io/campsis.doc/reference/PIOutfun.md)
  : Create a prediction interval output function
- [`StatsOutfun()`](https://calvagone.github.io/campsis.doc/reference/StatsOutfun.md)
  : Create a statistics output function
- [`NCATableOutfun()`](https://calvagone.github.io/campsis.doc/reference/NCATableOutfun.md)
  : Create a NCA table output function

## Plotting utilities (main methods)

- [`scatter_plot()`](https://calvagone.github.io/campsis.doc/reference/scatter_plot.md)
  : Scatter plot (S3 generic).
- [`shaded_plot()`](https://calvagone.github.io/campsis.doc/reference/shaded_plot.md)
  : Shaded plot / prediction interval plot (S3 generic).
- [`spaghetti_plot()`](https://calvagone.github.io/campsis.doc/reference/spaghetti_plot.md)
  : Spaghetti plot (S3 generic).
- [`vpc_plot()`](https://calvagone.github.io/campsis.doc/reference/vpc_plot.md)
  : VPC plot (S3 generic).

## Plotting utilities (S3 methods)

- [`scatter_plot(`*`<std_campsis_tbl>`*`)`](https://calvagone.github.io/campsis.doc/reference/scatter_plot.std_campsis_tbl.md)
  : Scatter plot for standard Campsis simulation output.
- [`shaded_plot(`*`<std_campsis_tbl>`*`)`](https://calvagone.github.io/campsis.doc/reference/shaded_plot.std_campsis_tbl.md)
  : Shaded plot for standard Campsis simulation output.
- [`spaghetti_plot(`*`<std_campsis_tbl>`*`)`](https://calvagone.github.io/campsis.doc/reference/spaghetti_plot.std_campsis_tbl.md)
  : Spaghetti plot for standard Campsis simulation output.
- [`vpc_plot(`*`<pi_campsis_tbl>`*`)`](https://calvagone.github.io/campsis.doc/reference/vpc_plot.pi_campsis_tbl.md)
  : VPC plot for prediction-interval Campsis output.
- [`vpc_plot(`*`<std_campsis_tbl>`*`)`](https://calvagone.github.io/campsis.doc/reference/vpc_plot.std_campsis_tbl.md)
  : VPC plot for standard Campsis simulation output.

## Simulate

- [`simulate()`](https://calvagone.github.io/campsis.doc/reference/simulate.md)
  : Simulate function.

## Simulation settings

- [`DefaultSettings()`](https://calvagone.github.io/campsis.doc/reference/DefaultSettings.md)
  : Create default settings.
- [`Declare()`](https://calvagone.github.io/campsis.doc/reference/Declare.md)
  : Create declare settings.
- [`Hardware()`](https://calvagone.github.io/campsis.doc/reference/Hardware.md)
  : Create hardware settings.
- [`NOCB()`](https://calvagone.github.io/campsis.doc/reference/NOCB.md)
  : Create NOCB settings.
- [`Outfun()`](https://calvagone.github.io/campsis.doc/reference/Outfun.md)
  : Create a new output function
- [`Progress()`](https://calvagone.github.io/campsis.doc/reference/Progress.md)
  : Create progress settings.
- [`Settings()`](https://calvagone.github.io/campsis.doc/reference/Settings.md)
  : Create advanced simulation settings.
- [`Solver()`](https://calvagone.github.io/campsis.doc/reference/Solver.md)
  : Create solver settings.
- [`SimulationProgress()`](https://calvagone.github.io/campsis.doc/reference/SimulationProgress.md)
  : Create a simulation progress object.
- [`campsis_handler()`](https://calvagone.github.io/campsis.doc/reference/campsis_handler.md)
  : Suggested Campsis handler for showing the progress bar.
- [`setup_plan_default()`](https://calvagone.github.io/campsis.doc/reference/setup_plan_default.md)
  : Setup default plan for the given simulation or hardware settings.
  This plan will prioritise the distribution of workers in the following
  order: 1) Replicates (if 'replicate_parallel' is enabled) 2) Scenarios
  (if 'scenario_parallel' is enabled) 3) Dataset export / slices (if
  'dataset_export' or 'slice_parallel' is enabled)
- [`setup_plan_sequential()`](https://calvagone.github.io/campsis.doc/reference/setup_plan_sequential.md)
  : Setup plan as sequential (i.e. no parallelisation).

## Time conversion utilities

- [`convert_time()`](https://calvagone.github.io/campsis.doc/reference/convert_time.md)
  : Convert numeric time vector based on the provided units.
- [`days()`](https://calvagone.github.io/campsis.doc/reference/days.md)
  : Convert days to hours.
- [`get_available_time_units()`](https://calvagone.github.io/campsis.doc/reference/get_available_time_units.md)
  : Return the list of available time units.
- [`hours()`](https://calvagone.github.io/campsis.doc/reference/hours.md)
  : Convert hours to hours (do nothing).
- [`minutes()`](https://calvagone.github.io/campsis.doc/reference/minutes.md)
  : Convert minutes to hours.
- [`months()`](https://calvagone.github.io/campsis.doc/reference/months.md)
  : Convert pharma months (1 month = 4 weeks) to hours.
- [`seconds()`](https://calvagone.github.io/campsis.doc/reference/seconds.md)
  : Convert seconds to hours.
- [`standardise_time()`](https://calvagone.github.io/campsis.doc/reference/standardise_time.md)
  : Standardise time to hours.
- [`weeks()`](https://calvagone.github.io/campsis.doc/reference/weeks.md)
  : Convert weeks to hours.
- [`years()`](https://calvagone.github.io/campsis.doc/reference/years.md)
  : Convert pharma years (1 year = 12\*4 weeks) to hours.

## For advanced use

- [`as.numeric(`*`<time_sequence>`*`)`](https://calvagone.github.io/campsis.doc/reference/as.numeric-time_sequence-method.md)
  : Time sequence to numeric vector.
- [`as.numeric(`*`<time_vector>`*`)`](https://calvagone.github.io/campsis.doc/reference/as.numeric-time_vector-method.md)
  : Time vector to numeric vector.
- [`apply_action()`](https://calvagone.github.io/campsis.doc/reference/apply_action.md)
  : Apply some action on the given object.
- [`apply_compartment_characteristics()`](https://calvagone.github.io/campsis.doc/reference/apply_compartment_characteristics.md)
  : Apply compartment characteristics from model. In practice, only
  compartment infusion duration needs to be applied.
- [`apply_outfun()`](https://calvagone.github.io/campsis.doc/reference/apply_outfun.md)
  : Apply output function(s) on the given Campsis results.
- [`compute_pi()`](https://calvagone.github.io/campsis.doc/reference/compute_pi.md)
  : Compute the prediction interval summary over time.
- [`compute_stats()`](https://calvagone.github.io/campsis.doc/reference/compute_stats.md)
  : Compute generic statistics over time.
- [`dosing_only()`](https://calvagone.github.io/campsis.doc/reference/dosing_only.md)
  : Filter Campsis output on dosing rows.
- [`generate_iiv()`](https://calvagone.github.io/campsis.doc/reference/generate_iiv.md)
  : Generate IIV matrix for the given Campsis model.
- [`generate_iiv_()`](https://calvagone.github.io/campsis.doc/reference/generate_iiv_.md)
  : Generate IIV matrix for the given OMEGA matrix.
- [`get_campsis_option()`](https://calvagone.github.io/campsis.doc/reference/get_campsis_option.md)
  : Get Campsis option logic.
- [`get_covariates()`](https://calvagone.github.io/campsis.doc/reference/get_covariates.md)
  : Get all covariates (fixed / time-varying / event covariates).
- [`get_event_covariates()`](https://calvagone.github.io/campsis.doc/reference/get_event_covariates.md)
  : Get all event-related covariates.
- [`get_fixed_covariates()`](https://calvagone.github.io/campsis.doc/reference/get_fixed_covariates.md)
  : Get all fixed covariates.
- [`get_iovs()`](https://calvagone.github.io/campsis.doc/reference/get_iovs.md)
  : Get all IOV objects.
- [`get_occasions()`](https://calvagone.github.io/campsis.doc/reference/get_occasions.md)
  : Get all occasions.
- [`get_splitting_configuration()`](https://calvagone.github.io/campsis.doc/reference/get_splitting_configuration.md)
  : Get splitting configuration for parallel export.
- [`get_times()`](https://calvagone.github.io/campsis.doc/reference/get_times.md)
  : Get all distinct times for the specified object.
- [`get_time_varying_covariates()`](https://calvagone.github.io/campsis.doc/reference/get_time_varying_covariates.md)
  : Get all time-varying covariates.
- [`length(`*`<arm>`*`)`](https://calvagone.github.io/campsis.doc/reference/length-arm-method.md)
  : Return the number of subjects contained in this arm.
- [`length(`*`<cyclic_schedule>`*`)`](https://calvagone.github.io/campsis.doc/reference/length-cyclic_schedule-method.md)
  : Return the number of repetition cycles.
- [`length(`*`<dataset>`*`)`](https://calvagone.github.io/campsis.doc/reference/length-dataset-method.md)
  : Return the number of subjects contained in this dataset.
- [`length(`*`<repeat_at_schedule>`*`)`](https://calvagone.github.io/campsis.doc/reference/length-repeat_at_schedule-method.md)
  : Return the number of repetition cycles.
- [`nhanes`](https://calvagone.github.io/campsis.doc/reference/nhanes.md)
  : NHANES database (demographics and body measure data combined, from
  2017-2018).
- [`obs_only()`](https://calvagone.github.io/campsis.doc/reference/obs_only.md)
  : Filter Campsis output on observation rows.
- [`repeat_schedule()`](https://calvagone.github.io/campsis.doc/reference/repeat_schedule.md)
  : Repeat schedule.
- [`retrieve_parameter_value()`](https://calvagone.github.io/campsis.doc/reference/retrieve_parameter_value.md)
  : Retrieve the parameter value (standardized) for the specified
  parameter name.
- [`unwrap_treatment()`](https://calvagone.github.io/campsis.doc/reference/unwrap_treatment.md)
  : Unwrap treatment.

## Exported classes

- [`arm-class`](https://calvagone.github.io/campsis.doc/reference/arm-class.md)
  : Arm class.
- [`arms-class`](https://calvagone.github.io/campsis.doc/reference/arms-class.md)
  : Arms class.
- [`binomial_distribution-class`](https://calvagone.github.io/campsis.doc/reference/binomial_distribution-class.md)
  : Binomial distribution class.
- [`bolus-class`](https://calvagone.github.io/campsis.doc/reference/bolus-class.md)
  : Bolus class.
- [`bolus_wrapper-class`](https://calvagone.github.io/campsis.doc/reference/bolus_wrapper-class.md)
  : Bolus wrapper class.
- [`bootstrap-class`](https://calvagone.github.io/campsis.doc/reference/bootstrap-class.md)
  : Bootstrap class.
- [`bootstrap_distribution-class`](https://calvagone.github.io/campsis.doc/reference/bootstrap_distribution-class.md)
  : Bootstrap distribution class.
- [`campsis_metadata-class`](https://calvagone.github.io/campsis.doc/reference/campsis_metadata-class.md)
  : Campsis metadata class.
- [`campsis_tbl-class`](https://calvagone.github.io/campsis.doc/reference/campsis_tbl-class.md)
  [`campsis_tbl`](https://calvagone.github.io/campsis.doc/reference/campsis_tbl-class.md)
  : Campsis table class (see this class as an interface)
- [`constant_distribution-class`](https://calvagone.github.io/campsis.doc/reference/constant_distribution-class.md)
  : Constant distribution class.
- [`covariate-class`](https://calvagone.github.io/campsis.doc/reference/covariate-class.md)
  : Covariate class.
- [`covariates-class`](https://calvagone.github.io/campsis.doc/reference/covariates-class.md)
  : Covariates class.
- [`cyclic_schedule-class`](https://calvagone.github.io/campsis.doc/reference/cyclic_schedule-class.md)
  : Cyclic schedule class.
- [`dataset-class`](https://calvagone.github.io/campsis.doc/reference/dataset-class.md)
  : Dataset class.
- [`dataset_config-class`](https://calvagone.github.io/campsis.doc/reference/dataset_config-class.md)
  : Dataset configuration class.
- [`declare_settings-class`](https://calvagone.github.io/campsis.doc/reference/declare_settings-class.md)
  : Declare settings class.
- [`default_outfun-class`](https://calvagone.github.io/campsis.doc/reference/default_outfun-class.md)
  : Default output function class.
- [`default_settings-class`](https://calvagone.github.io/campsis.doc/reference/default_settings-class.md)
  : Default settings class.
- [`discrete_distribution-class`](https://calvagone.github.io/campsis.doc/reference/discrete_distribution-class.md)
  : Discrete distribution class.
- [`distribution-class`](https://calvagone.github.io/campsis.doc/reference/distribution-class.md)
  : Distribution class. See this class as an interface.
- [`dose_adaptation-class`](https://calvagone.github.io/campsis.doc/reference/dose_adaptation-class.md)
  : Dose adaptation class.
- [`dose_adaptations-class`](https://calvagone.github.io/campsis.doc/reference/dose_adaptations-class.md)
  : Dose adaptations class.
- [`dosing_schedule-class`](https://calvagone.github.io/campsis.doc/reference/dosing_schedule-class.md)
  : Dosing schedule class.
- [`event-class`](https://calvagone.github.io/campsis.doc/reference/event-class.md)
  : Event class.
- [`event_covariate-class`](https://calvagone.github.io/campsis.doc/reference/event_covariate-class.md)
  : Event covariate class.
- [`events-class`](https://calvagone.github.io/campsis.doc/reference/events-class.md)
  : Events class.
- [`fixed_covariate-class`](https://calvagone.github.io/campsis.doc/reference/fixed_covariate-class.md)
  : Fixed covariate class.
- [`fixed_distribution-class`](https://calvagone.github.io/campsis.doc/reference/fixed_distribution-class.md)
  : Fixed distribution class.
- [`function_distribution-class`](https://calvagone.github.io/campsis.doc/reference/function_distribution-class.md)
  : Function distribution class.
- [`hardware_settings-class`](https://calvagone.github.io/campsis.doc/reference/hardware_settings-class.md)
  : Hardware settings class.
- [`infusion-class`](https://calvagone.github.io/campsis.doc/reference/infusion-class.md)
  : Infusion class.
- [`infusion_wrapper-class`](https://calvagone.github.io/campsis.doc/reference/infusion_wrapper-class.md)
  : Infusion wrapper class.
- [`internal_settings-class`](https://calvagone.github.io/campsis.doc/reference/internal_settings-class.md)
  : Internal settings class (transient object from the simulation
  settings).
- [`lognormal_distribution-class`](https://calvagone.github.io/campsis.doc/reference/lognormal_distribution-class.md)
  : Log normal distribution class.
- [`mrgsolve_engine-class`](https://calvagone.github.io/campsis.doc/reference/mrgsolve_engine-class.md)
  : mrgsolve engine class.
- [`nca_table_outfun-class`](https://calvagone.github.io/campsis.doc/reference/nca_table_outfun-class.md)
  : NCA table output function class.
- [`normal_distribution-class`](https://calvagone.github.io/campsis.doc/reference/normal_distribution-class.md)
  : Normal distribution class.
- [`nocb_settings-class`](https://calvagone.github.io/campsis.doc/reference/nocb_settings-class.md)
  : NOCB settings class.
- [`pi_campsis_tbl-class`](https://calvagone.github.io/campsis.doc/reference/pi_campsis_tbl-class.md)
  [`pi_campsis_tbl`](https://calvagone.github.io/campsis.doc/reference/pi_campsis_tbl-class.md)
  : Prediction Interval (PI) Campsis table class
- [`pi_outfun-class`](https://calvagone.github.io/campsis.doc/reference/pi_outfun-class.md)
  : Prediction interval output function class.
- [`protocol-class`](https://calvagone.github.io/campsis.doc/reference/protocol-class.md)
  : Protocol class.
- [`observations-class`](https://calvagone.github.io/campsis.doc/reference/observations-class.md)
  : Observations class.
- [`observations_set-class`](https://calvagone.github.io/campsis.doc/reference/observations_set-class.md)
  : Observations set class.
- [`occasion-class`](https://calvagone.github.io/campsis.doc/reference/occasion-class.md)
  : Occasion class.
- [`occasions-class`](https://calvagone.github.io/campsis.doc/reference/occasions-class.md)
  : Occasions class.
- [`outfun-class`](https://calvagone.github.io/campsis.doc/reference/outfun-class.md)
  : Output function class.
- [`outfuns-class`](https://calvagone.github.io/campsis.doc/reference/outfuns-class.md)
  : Output functions class (i.e. a collection of output functions).
- [`progress_settings-class`](https://calvagone.github.io/campsis.doc/reference/progress_settings-class.md)
  : Progress settings class.
- [`repeated_schedule-class`](https://calvagone.github.io/campsis.doc/reference/repeated_schedule-class.md)
  : Repeated schedule class. See this class as an interface.
- [`repeat_at_schedule-class`](https://calvagone.github.io/campsis.doc/reference/repeat_at_schedule-class.md)
  : 'Repeat at' schedule class.
- [`replace_action-class`](https://calvagone.github.io/campsis.doc/reference/replace_action-class.md)
  : Replace action class.
- [`rxode_engine-class`](https://calvagone.github.io/campsis.doc/reference/rxode_engine-class.md)
  : rxode2 engine class.
- [`scenario-class`](https://calvagone.github.io/campsis.doc/reference/scenario-class.md)
  : Scenario class.
- [`scenario_action-class`](https://calvagone.github.io/campsis.doc/reference/scenario_action-class.md)
  : Scenario action class.
- [`scenario_actions-class`](https://calvagone.github.io/campsis.doc/reference/scenario_actions-class.md)
  : Scenario actions class.
- [`scenarios-class`](https://calvagone.github.io/campsis.doc/reference/scenarios-class.md)
  : Scenarios class.
- [`simulation_engine-class`](https://calvagone.github.io/campsis.doc/reference/simulation_engine-class.md)
  : Simulation engine class.
- [`simulation_settings-class`](https://calvagone.github.io/campsis.doc/reference/simulation_settings-class.md)
  : Simulation settings class.
- [`simulation_progress-class`](https://calvagone.github.io/campsis.doc/reference/simulation_progress-class.md)
  : Simulation progress class.
- [`stats_outfun-class`](https://calvagone.github.io/campsis.doc/reference/stats_outfun-class.md)
  : Statistics output function class.
- [`std_campsis_tbl-class`](https://calvagone.github.io/campsis.doc/reference/std_campsis_tbl-class.md)
  [`std_campsis_tbl`](https://calvagone.github.io/campsis.doc/reference/std_campsis_tbl-class.md)
  : Standard Campsis table class
- [`solver_settings-class`](https://calvagone.github.io/campsis.doc/reference/solver_settings-class.md)
  : Solver settings class. See ?mrgsolve::update. See ?rxode2::rxSolve.
- [`stats_campsis_tbl-class`](https://calvagone.github.io/campsis.doc/reference/stats_campsis_tbl-class.md)
  [`stats_campsis_tbl`](https://calvagone.github.io/campsis.doc/reference/stats_campsis_tbl-class.md)
  : Statistics Campsis table class
- [`time_sequence-class`](https://calvagone.github.io/campsis.doc/reference/time_sequence-class.md)
  : Time sequence class.
- [`time_varying_covariate-class`](https://calvagone.github.io/campsis.doc/reference/time_varying_covariate-class.md)
  : Time-varying covariate class.
- [`time_vector-class`](https://calvagone.github.io/campsis.doc/reference/time_vector-class.md)
  : Time vector class.
- [`treatment-class`](https://calvagone.github.io/campsis.doc/reference/treatment-class.md)
  : Treatment class.
- [`treatment_iov-class`](https://calvagone.github.io/campsis.doc/reference/treatment_iov-class.md)
  : Treatment IOV class.
- [`treatment_iovs-class`](https://calvagone.github.io/campsis.doc/reference/treatment_iovs-class.md)
  : Treatment IOV's class.
- [`undefined_distribution-class`](https://calvagone.github.io/campsis.doc/reference/undefined_distribution-class.md)
  : Undefined distribution class. This type of object is automatically
  created in method to_explicit_distribution() when the user does not
  provide a concrete distribution. This is because S4 objects do not
  accept NULL values.
- [`undefined_schedule-class`](https://calvagone.github.io/campsis.doc/reference/undefined_schedule-class.md)
  : Undefined schedule class.
- [`uniform_distribution-class`](https://calvagone.github.io/campsis.doc/reference/uniform_distribution-class.md)
  : Uniform distribution class.
