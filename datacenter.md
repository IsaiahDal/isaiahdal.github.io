# Measuring Business Value and Productivity Data Center

## I. Adding a new dataset.

### 1. Format CSV

The JavaScript function used to load the data assumes the following format:

* All variable names are listed in the first column.
* If a variable is "nested" under a variable that appears above it, it must have a greater indent.
  * Note that only the _relative_ length of the indent matters. 
* For example, a CSV containing GDP data may appear as follows:
```
"Gross Domestic Product", ...
"  Consumption",  ...
"    Goods", ...
"    Services", ...
"  Investment", ...
```
* The remaining columns each correspond to a year, with the first row in each column giving the year.
