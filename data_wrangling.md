data\_wrangling
================
Apoorva Srinivasan
10/1/2018

working with data wrangling

``` r
library(tidyverse)
```

    ## ── Attaching packages ──────────────────────────── tidyverse 1.2.1 ──

    ## ✔ ggplot2 3.0.0     ✔ purrr   0.2.5
    ## ✔ tibble  1.4.2     ✔ dplyr   0.7.6
    ## ✔ tidyr   0.8.1     ✔ stringr 1.3.1
    ## ✔ readr   1.1.1     ✔ forcats 0.3.0

    ## ── Conflicts ─────────────────────────────── tidyverse_conflicts() ──
    ## ✖ dplyr::filter() masks stats::filter()
    ## ✖ dplyr::lag()    masks stats::lag()

``` r
library(readr)
litters_data = read_csv(file = "./data/FAS_litters.csv")
```

    ## Parsed with column specification:
    ## cols(
    ##   Group = col_character(),
    ##   `Litter Number` = col_character(),
    ##   `GD0 weight` = col_double(),
    ##   `GD18 weight` = col_double(),
    ##   `GD of Birth` = col_integer(),
    ##   `Pups born alive` = col_integer(),
    ##   `Pups dead @ birth` = col_integer(),
    ##   `Pups survive` = col_integer()
    ## )

``` r
litters_data = janitor::clean_names(litters_data)
```

``` r
pups_data = read_csv(file = "./data/FAS_pups.csv")
```

    ## Parsed with column specification:
    ## cols(
    ##   `Litter Number` = col_character(),
    ##   Sex = col_integer(),
    ##   `PD ears` = col_integer(),
    ##   `PD eyes` = col_integer(),
    ##   `PD pivot` = col_integer(),
    ##   `PD walk` = col_integer()
    ## )

``` r
pups_data = janitor::clean_names(pups_data)
```

``` r
pulse_data = haven:::read_sas("./data/public_pulse_data.sas7bdat")
```
