# Validate Station Data for Years Available

Internal function: Validate Station Data for Years Available

## Usage

``` r
.validate_station_data_years(station, isd_history, years)
```

## Arguments

- station:

  User entered station ID

- isd_history:

  isd_history.csv from NCEI provided by GSODR

- years:

  User entered years for query

## Value

`station_id` value, "station", `NA` if no match with available data.
