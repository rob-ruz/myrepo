GitHub test
================
Roberto Ruz Campos
23/6/2019

This is my first GitHub experience\!

Loaad required libraries

``` r
library(repurrrsive)
library(purrr)
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

The end.
