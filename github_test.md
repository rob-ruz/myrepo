GitHub test
================
Roberto Ruz Campos
23/6/2019

This is my first GitHub experience\!

Loaad required libraries

``` r
library(repurrrsive)
library(purrr)
library(magrittr)
library(tibble)
library(ggplot2)
library(dplyr)
library(viridis)
library(ggdark)
```

List all the GOT characters.

``` r
my_characters <- map_chr(got_chars, "name")
my_characters
```

    ##  [1] "Theon Greyjoy"      "Tyrion Lannister"   "Victarion Greyjoy" 
    ##  [4] "Will"               "Areo Hotah"         "Chett"             
    ##  [7] "Cressen"            "Arianne Martell"    "Daenerys Targaryen"
    ## [10] "Davos Seaworth"     "Arya Stark"         "Arys Oakheart"     
    ## [13] "Asha Greyjoy"       "Barristan Selmy"    "Varamyr"           
    ## [16] "Brandon Stark"      "Brienne of Tarth"   "Catelyn Stark"     
    ## [19] "Cersei Lannister"   "Eddard Stark"       "Jaime Lannister"   
    ## [22] "Jon Connington"     "Jon Snow"           "Aeron Greyjoy"     
    ## [25] "Kevan Lannister"    "Melisandre"         "Merrett Frey"      
    ## [28] "Quentyn Martell"    "Samwell Tarly"      "Sansa Stark"

How many nicknames each character have?

``` r
got <- set_names(got_chars, my_characters)
char_table <- got %>% 
  map_dbl(~length(.x[["aliases"]])) %>% 
  enframe()
knitr::kable(char_table)
```

| name               | value |
| :----------------- | ----: |
| Theon Greyjoy      |     4 |
| Tyrion Lannister   |    11 |
| Victarion Greyjoy  |     1 |
| Will               |     1 |
| Areo Hotah         |     1 |
| Chett              |     1 |
| Cressen            |     1 |
| Arianne Martell    |     1 |
| Daenerys Targaryen |    11 |
| Davos Seaworth     |     5 |
| Arya Stark         |    16 |
| Arys Oakheart      |     1 |
| Asha Greyjoy       |     2 |
| Barristan Selmy    |     5 |
| Varamyr            |     3 |
| Brandon Stark      |     3 |
| Brienne of Tarth   |     3 |
| Catelyn Stark      |     5 |
| Cersei Lannister   |     0 |
| Eddard Stark       |     3 |
| Jaime Lannister    |     4 |
| Jon Connington     |     1 |
| Jon Snow           |     8 |
| Aeron Greyjoy      |     2 |
| Kevan Lannister    |     1 |
| Melisandre         |     5 |
| Merrett Frey       |     1 |
| Quentyn Martell    |     4 |
| Samwell Tarly      |     7 |
| Sansa Stark        |     3 |
| Plot the results.  |       |

``` r
ggplot(char_table, aes(factor(name, level = order_vector), value)) +
  geom_col(aes(fill = factor(name, level = order_vector))) +
  ggtitle("Number of aliases of each character") +
  ylab("Number of aliases") + 
  xlab("Character Name") +
  scale_fill_viridis(discrete = TRUE) +
  dark_theme_light() +
  theme(legend.position = "none") +
  coord_flip()
```

![](github_test_files/figure-gfm/Bar%20Chart-1.png)<!-- -->

The end.
