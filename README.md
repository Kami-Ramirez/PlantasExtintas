Trabajo con plantas extintas
================

# Introduccion

En este documento trabajaremos para explorar la id de plantas q se
encuentran en silvestria segun la
[*IUCN*](https://www.iucnredlist.org/es/)

## Trabajando con los datos

Vamos a partir cargando los paquetes

``` r
library(tidyverse)
```

    ## -- Attaching packages ----------------

    ## v ggplot2 3.3.0     v purrr   0.3.4
    ## v tibble  3.0.1     v dplyr   0.8.5
    ## v tidyr   1.0.3     v stringr 1.4.0
    ## v readr   1.3.1     v forcats 0.5.0

    ## -- Conflicts -------------------------
    ## x dplyr::filter() masks stats::filter()
    ## x dplyr::lag()    masks stats::lag()

``` r
library(readr)
plants <- read_csv("https://raw.githubusercontent.com/rfordatascience/tidytuesday/master/data/2020/2020-08-18/plants.csv")
```

    ## Parsed with column specification:
    ## cols(
    ##   .default = col_double(),
    ##   binomial_name = col_character(),
    ##   country = col_character(),
    ##   continent = col_character(),
    ##   group = col_character(),
    ##   year_last_seen = col_character(),
    ##   red_list_category = col_character()
    ## )

    ## See spec(...) for full column specifications.
