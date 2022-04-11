Portfolio - Smoking during pregnancy
================
Marcus Minko
4/1/2022

### Load packages and data

``` r
library(tidyverse) 
library(tidymodels)
library(openintro)
data(ncbirths)
view(ncbirths)
?ncbirths
```

### Vizualize the proportion of low birth weight birth by smoking status of the mother

``` r
ncbirths %>% 
       ggplot(aes(x = lowbirthweight)) + geom_bar() + facet_wrap(~habit)
```

![](lab-12_files/figure-gfm/birth%20weight-1.png)<!-- -->

``` r
#Need to remove the missing values 

ncbirths <- na.omit(ncbirths)

#Recreate the visualization with labels and free scales

ncbirths %>% 
           ggplot(aes(x = lowbirthweight)) + geom_bar(fill = "steel blue") + facet_wrap(~habit, scales = "free") + labs(title = "Does Smoking Impact a Low Birth Weight", x = "Low Birth Weight", y = "Frequency") + theme_minimal()
```

![](lab-12_files/figure-gfm/birth%20weight-2.png)<!-- -->

``` r
# you can see that there is a greater proportion of low birth weights among smokers
```
