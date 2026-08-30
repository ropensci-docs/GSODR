# Get updates.txt With Information on Updates to the GSOD Data Set

Gets and imports the 'updates.txt' file that has a change log of GSOD
data. Changes are shown in order from most recent to oldest changes by
the "DATE" field. Column names follow
[GSODR](https://CRAN.R-project.org/package=GSODR) naming conventions.

## Usage

``` r
get_updates()
```

## Value

A
[`data.table::data.table()`](https://rdrr.io/pkg/data.table/man/data.table.html)
object

## Examples

``` r
if (FALSE) { # interactive()
get_updates()
}
```
