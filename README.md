# ereplace

This is a Stata package, originally written by Nick Cox, but which I maintain on the Boston College Statistical Software Components (SSC) archive. It is available to all Stata users by typing `ssc install ereplace` into the commmand prompt. Alternatively you can type `net install ereplace, from("https://github.com/Chris-Larkin/ereplace")`. 

`egen` and `egenmore` (available on SSC) contain a number of popular and powerful functions for cleaning and analyzing data and are essential to many users' workflows. In some instances, the user may want to replace existing variables in their data with a new variable after applying an `egen` function. `ereplace` allows this, and so helps keep data tidy as users are conducting cleaning/analysis, as well as reducing code verbosity. Consider the following examples.

```
//Install ereplace
ssc install ereplace

//Confirm egenmore modules are installed, and install if not
capture which egenmore
	if _rc!=0{
		ssc install egenmore
	}

//Bring in example data
sysuse e_example.dta, clear

```
#### Basic cleaning example without `ereplace`
```
*Remove non-numeric characters (excluding .) from string variable
egen new_strvar = sieve(strvar), char(.0123456789) //apply sieve function from egenmore
order new_strvar, a(strvar) //order variable in the same part of dataset
drop strvar //drop original variable
rename new_strvar strvar //rename new variable
```

#### Basic cleaning example with `ereplace`
```
*Same as above but with ereplace
ereplace strvar = sieve(strvar), char(.0123456789)
```
