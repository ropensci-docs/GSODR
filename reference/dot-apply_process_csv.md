# Process .gz files

Internal function: Process .gz files

## Usage

``` r
.apply_process_csv(file_list, isd_history)
```

## Arguments

- file_list:

  List of GSOD files

- isd_history:

  isd_history.csv file from NCEI provided by GSODR

## Value

A `data.table` of GSOD weather data.
