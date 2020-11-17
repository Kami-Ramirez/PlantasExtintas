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

    ## -- Attaching packages ------------- tidyverse 1.3.0 --

    ## v ggplot2 3.3.0     v purrr   0.3.4
    ## v tibble  3.0.1     v dplyr   0.8.5
    ## v tidyr   1.0.3     v stringr 1.4.0
    ## v readr   1.3.1     v forcats 0.5.0

    ## -- Conflicts ---------------- tidyverse_conflicts() --
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

## Filtrando los datos para resolver el ejemplo 1

``` r
Chile= plants %>% 
  dplyr:: filter(country=="Chile") %>% 
  dplyr::select(binomial_name,country, red_list_category)

Chile
```

    ## # A tibble: 2 x 3
    ##   binomial_name           country red_list_category  
    ##   <chr>                   <chr>   <chr>              
    ## 1 Santalum fernandezianum Chile   Extinct            
    ## 2 Sophora toromiro        Chile   Extinct in the Wild

## resumen de especies por pais

``` r
resumen=plants %>%
  dplyr::filter(continent== "South America") %>% 
  group_by(country) %>%
  summarise(n_species = n())
resumen
```

    ## # A tibble: 9 x 2
    ##   country             n_species
    ##   <chr>                   <int>
    ## 1 Argentina                   1
    ## 2 Bolivia                     1
    ## 3 Brazil                     10
    ## 4 Chile                       2
    ## 5 Colombia                    6
    ## 6 Ecuador                    52
    ## 7 Peru                        4
    ## 8 Trinidad and Tobago         6
    ## 9 Venezuela                   1
