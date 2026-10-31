# Find Nearest GSOD Stations to a Specified Latitude and Longitude

Given latitude and longitude values entered as decimal degrees (DD),
this function returns a list (as an atomic vector) of station ID values,
which can be used
in[`get_GSOD()`](https://docs.ropensci.org/GSODR/reference/get_GSOD.md)
to query for specific stations as an argument in the `station` parameter
of that function.

## Usage

``` r
nearest_stations(LAT, LON, distance)
```

## Arguments

- LAT:

  Latitude expressed as decimal degrees (DD) (WGS84)

- LON:

  Longitude expressed as decimal degrees (DD) (WGS84)

- distance:

  Distance in kilometres from point for which stations are to be
  returned.

## Value

A
[`data.table::data.table()`](https://rdrr.io/pkg/data.table/man/data.table.html)
with full station metadata including the distance from the user
specified coordinates from nearest to farthest.

## Note

The GSOD data, which are downloaded and manipulated by
[GSODR](https://CRAN.R-project.org/package=GSODR) stipulate that the
following notice should be given. “The following data and products may
have conditions placed on their international commercial use. They can
be used within the U.S. or for non- commercial international activities
without restriction. The non-U.S. data cannot be redistributed for
commercial purposes. Re-distribution of these data by others must
provide this same notification.”

## Author

Adam H. Sparks, <adamhsparks@gmail.com>

## Examples

``` r
if (FALSE) { # interactive()
# Find stations within a 100km radius of Toowoomba, QLD, AUS

n <- nearest_stations(LAT = -27.5598, LON = 151.9507, distance = 100)
n
}
```
