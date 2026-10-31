# Validate data for missing days

Internal function: Validate data for missing days

## Usage

``` r
.validate_missing_days(max_missing, file_list)
```

## Arguments

- max_missing:

  User entered maximum permissible missing days

- GSOD_list:

  A list of GSOD files that have been downloaded from NCEI

## Value

A validated [`list()`](https://rdrr.io/r/base/list.html) of GSOD files
that meet requirements for missing days.
