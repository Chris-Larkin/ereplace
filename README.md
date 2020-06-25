# ereplace

This is a Stata package, originally written by Nick Cox, but which I maintain on the Boston College Statistical Software Components (SSC) archive. It is available to all Stata users by typing `ssc install ereplace` into the commmand prompt. Alternatively you can type `net install ereplace, from("https://github.com/Chris-Larkin/ereplace")`. 

`egen` and `egenmore` (available on SSC) contain a number of popular and powerful functions for cleaning and analyzing data and are essential to many users' workflows. In some instances, the user may want to replace existing variables in their data with a new variable after applying an `egen` function. `ereplace` allows this, and so helps keep data tidy as users are conducting cleaning/analysis, as well as reducing code verbosity. Consider the following examples.

#### Basic cleaning example without `ereplace`





#### Basic cleaning example with `ereplace`
