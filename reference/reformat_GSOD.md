# Tidy and Return a data.table Object of GSOD Data From Local Storage

This function automates cleaning and reformatting of GSOD station files
in  
“YEAR.tar.gz”, provided that they have been untarred or “STATION.csv”
format that have been downloaded from the United States National Center
for Environmental Information's (NCEI) download page. Three additional
useful elements: saturation vapour pressure (es), actual vapour pressure
(ea) and relative humidity (RH) are calculated and returned in the final
data frame using the improved August-Roche-Magnus approximation
(Alduchov and Eskridge 1996). All units are converted to International
System of Units (SI), *e.g.*, Fahrenheit to Celsius and inches to
millimetres.

## Usage

``` r
reformat_GSOD(dsn = NULL, file_list = NULL)
```

## Arguments

- dsn:

  User supplied full file path to location of data files on local disk
  for tidying.

- file_list:

  User supplied list of file paths to individual files of data on local
  disk for tidying. Ignored if `dsn` is set. Use if there are other
  files in the `dsn` that you do not wish to reformat.

## Value

A data frame as a
[`data.table::data.table()`](https://rdrr.io/pkg/data.table/man/data.table.html)
object of GSOD data.

## Details

If multiple stations are given, data are summarised for each year by
station, which include vapour pressure and relative humidity elements
calculated from existing data in GSOD. Else, a single station is tidied
and a data frame is returned.

All missing values in resulting files are represented as `NA` regardless
of which field they occur in.

Only station files in the original “csv” file format are supported by
this function. If you have downloaded the full annual (“YYYY.tar.gz”)
file you will need to extract the individual station files from the tar
file first to use this function.

Note that `reformat_GSOD()` will attempt to reformat any “.csv” files
found in the `dsn` that you provide. If there are non-GSOD files present
this will lead to errors.

For a complete list of the fields and description of the contents and
units, please refer to Appendix 1 in the
[GSODR](https://CRAN.R-project.org/package=GSODR) vignette,
[`vignette("GSODR", package = "GSODR")`](https://docs.ropensci.org/GSODR/articles/GSODR.md).

## Note

While [GSODR](https://CRAN.R-project.org/package=GSODR) does not
distribute GSOD weather data, users of the data should note the
conditions that the U.S. NCEI places upon the GSOD data. “The following
data and products may have conditions placed on their international
commercial use. They can be used within the U.S. or for non- commercial
international activities without restriction. The non-U.S. data cannot
be redistributed for commercial purposes. Re-distribution of these data
by others must provide this same notification. A log of IP addresses
accessing these data and products will be maintained and may be made
available to data providers.”

## References

Alduchov, O.A. and Eskridge, R.E., 1996. Improved Magnus form
approximation of saturation vapor pressure. Journal of Applied
Meteorology and Climatology, 35(4), pp.601-609. DOI:
\<10.1175%2F1520-0450%281996%29035%3C0601%3AIMFAOS%3E2.0.CO%3B2\>.

## See also

For automated downloading and tidying see the
[`get_GSOD()`](https://docs.ropensci.org/GSODR/reference/get_GSOD.md)
function, which provides expanded functionality for automatically
downloading and expanding annual GSOD files and cleaning station files.

[`get_GSOD()`](https://docs.ropensci.org/GSODR/reference/get_GSOD.md)

## Author

Adam H. Sparks, <adamhsparks@gmail.com>

## Examples

``` r
if (FALSE) { # interactive()

# Download data to 'tempdir()'
download.file(
  url =
    "https://www.ncei.noaa.gov/data/global-summary-of-the-day/access/2010/95551099999.csv",
  destfile = file.path(tempdir(), "95551099999.csv"),
  mode = "wb"
)

# Reformat station data files in R's tempdir() directory
tbar <- reformat_GSOD(dsn = tempdir())

tbar
}
```
