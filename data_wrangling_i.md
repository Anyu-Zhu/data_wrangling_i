data\_wrangling\_i
================
Anyu Zhu
9/23/2021

## Import some data

I want to import `FAS_litters.csv`

``` r
litters_df = read_csv("data_import_examples/FAS_litters.csv")
```

    ## 
    ## ── Column specification ────────────────────────────────────────────────────────
    ## cols(
    ##   Group = col_character(),
    ##   `Litter Number` = col_character(),
    ##   `GD0 weight` = col_double(),
    ##   `GD18 weight` = col_double(),
    ##   `GD of Birth` = col_double(),
    ##   `Pups born alive` = col_double(),
    ##   `Pups dead @ birth` = col_double(),
    ##   `Pups survive` = col_double()
    ## )

clean the names.

``` r
litters_df = janitor::clean_names(litters_df)
names(litters_df)
```

    ## [1] "group"           "litter_number"   "gd0_weight"      "gd18_weight"    
    ## [5] "gd_of_birth"     "pups_born_alive" "pups_dead_birth" "pups_survive"

look at the dataset

``` r
View(litters_df)
# skimmer package: overview of dataset
skimr::skim(litters_df)
```

## Arguments in `read_csv`

``` r
litters_df = read_csv("data_import_examples/FAS_litters.csv",
                      skip = 5,
                      col_names = FALSE)
```

## Parsing columns

``` r
litters_data = read_csv(file = "data_import_examples/FAS_litters.csv",
  col_types = cols(
    Group = col_character(),
    `Litter Number` = col_character(),
    `GD0 weight` = col_double(),
    `GD18 weight` = col_double(),
    `GD of Birth` = col_integer(),
    `Pups born alive` = col_integer(),
    `Pups dead @ birth` = col_integer(),
    `Pups survive` = col_integer()
  )
)
```

## Reading from Excel

``` r
mlb11_df = read_excel("data_import_examples/mlb11.xlsx")
```

## LotR word read

``` r
fellow_df = read_excel("data_import_examples/LotR_Words.xlsx", range = "B3:D6")
```

## read a SAS file

``` r
pulsa_df = read_sas("data_import_examples/public_pulse_data.sas7bdat")
```

## export data

``` r
write_csv(fellow_df, "data_import_examples/fellowship_words.csv")
```
