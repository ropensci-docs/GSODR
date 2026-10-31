# Download and Return a data.table Object of GSOD Weather Data

Automates downloading, cleaning, reformatting of data from the Global
Surface Summary of the Day (GSOD) data provided by the [US National
Centers for Environmental Information
(NCEI)](https://www.ncei.noaa.gov/access/metadata/landing-page/bin/iso?id=gov.noaa.ncdc:C00516),
Three additional useful elements: saturation vapour pressure (es),
actual vapour pressure (ea) and relative humidity (RH) are calculated
and returned in the final data frame using the improved
August-Roche-Magnus approximation (Alduchov and Eskridge 1996).

## Usage

``` r
get_GSOD(
  years,
  station = NULL,
  country = NULL,
  max_missing = NULL,
  agroclimatology = FALSE
)
```

## Arguments

- years:

  Year(s) of weather data to download.

- station:

  Optional. Specify a station or multiple stations for which to
  retrieve, check and clean weather data using `STATION`. The NCEI
  reports years for which the data are available. This function checks
  against these years. However, not all cases are properly documented
  and in some cases files may not exist for download even though it is
  indicated that data was recorded for the station for a particular
  year. If a station is specified that does not have an existing file on
  the server, this function will silently fail and move on to existing
  files for download and cleaning.

- country:

  Optional. Specify a country for which to retrieve weather data; full
  name, 2 or 3 letter ISO or 2 letter FIPS codes can be used. All
  stations within the specified country will be returned.

- max_missing:

  Optional. The maximum number of days allowed to be missing from a
  station's data before it is excluded from final file output.

- agroclimatology:

  Optional. Logical. Only clean data for stations between latitudes 60
  and -60 for agroclimatology work, defaults to `FALSE`. Set to `TRUE`
  to include only stations within the confines of these latitudes.

## Value

A
[`data.table::data.table()`](https://rdrr.io/pkg/data.table/man/data.table.html)
object of GSOD weather data.

## Details

All units are converted to International System of Units (SI), *e.g*,
Fahrenheit to Celsius and inches to millimetres.

Data summarise each year by station, which include vapour pressure and
relative humidity elements calculated from existing data in GSOD.

All missing values in resulting files are represented as `NA` regardless
of which field they occur in.

For a complete list of the fields and description of the contents and
units, please refer to Appendix 1 in the
[GSODR](https://CRAN.R-project.org/package=GSODR) vignette,
[`vignette("GSODR", package = "GSODR")`](https://docs.ropensci.org/GSODR/articles/GSODR.md).

For more information see the description of the data provided by NCEI,
<https://www.ncei.noaa.gov/data/global-summary-of-the-day/doc/readme.txt>.

## Note

[GSODR](https://CRAN.R-project.org/package=GSODR) attempts to validate
year and station combination requests, however, in certain cases the
start and end date may encompass years where no data is available. In
these cases no data will be returned.

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
Meteorology and Climatology, 35(4), pp.601-609.
[doi:10.1175/1520-0450(1996)035\<0601:IMFAOS\>2.0.CO;2](https://doi.org/10.1175/1520-0450%281996%29035%3C0601%3AIMFAOS%3E2.0.CO%3B2)
.

## See also

[`reformat_GSOD()`](https://docs.ropensci.org/GSODR/reference/reformat_GSOD.md)

## Author

Adam H. Sparks, <adamhsparks@gmail.com>

## Examples

``` r
if (FALSE) { # interactive()
# Download weather station data for Toowoomba, Queensland for 2010
tbar <- get_GSOD(years = 2010, station = "955510-99999")

# Download weather data for the year 1929
w_1929 <- get_GSOD(years = 1929)

# Download weather data for the year 1929 for Ireland
ie_1929 <- get_GSOD(years = 1929, country = "Ireland")
}
```
