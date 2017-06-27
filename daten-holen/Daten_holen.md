Twitter Untersuchung PE 2.0
================

-   [Test](#test)

``` r
library(readxl)
library(dplyr)
```

    ## 
    ## Attaching package: 'dplyr'

    ## The following objects are masked from 'package:stats':
    ## 
    ##     filter, lag

    ## The following objects are masked from 'package:base':
    ## 
    ##     intersect, setdiff, setequal, union

``` r
library(xlsx)
```

    ## Loading required package: rJava

    ## Loading required package: xlsxjars

``` r
library(tidyverse)
```

    ## Loading tidyverse: ggplot2
    ## Loading tidyverse: tibble
    ## Loading tidyverse: tidyr
    ## Loading tidyverse: readr
    ## Loading tidyverse: purrr

    ## Conflicts with tidy packages ----------------------------------------------

    ## filter(): dplyr, stats
    ## lag():    dplyr, stats

``` r
pers_de <- read_excel(
        "../Data/Pers.xlsx",
        sheet = 1,
        col_names = TRUE,
        col_types = NULL,
        na = "",
        skip = 0
        )
set.seed(123)
pers_de_sample <- sample_n(pers_de, 115)
saveRDS(pers_de, file = "../Data/pers_de.rds")
```

``` r
write.xlsx(x = pers_de_sample, file = "../Data/pers_sample.xlsx",
           sheetName = "DE", col.names = TRUE, showNA = TRUE, append = TRUE)
write.xlsx(x = pers_at_sample, file = "../Data/pers_sample.xlsx",
           sheetName = "AT", col.names = TRUE, showNA = TRUE, append = TRUE)
write.xlsx(x = pers_ch_sample, file = "../Data/pers_sample.xlsx",
           sheetName = "CH", col.names = TRUE, showNA = TRUE, append = TRUE)
```

``` r
pers_at <- read_excel(
        "../Data/Pers.xlsx",
        sheet = 2,
        col_names = TRUE,
        col_types = NULL,
        na = "",
        skip = 0
        )
set.seed(456)
pers_at_sample <- sample_n(pers_at, 83)
saveRDS(pers_at, file = "../Data/pers_at.rds")
```

``` r
pers_ch <- read_excel(
        "../Data/Pers.xlsx",
        sheet = 3,
        col_names = TRUE,
        col_types = NULL,
        na = "",
        skip = 0
        )
set.seed(789)
pers_ch_sample <- sample_n(pers_ch, 33)
saveRDS(pers_ch, file = "../Data/pers_ch.rds")
```

Test
====

*Test*
