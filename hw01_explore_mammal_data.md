Homework 1–Data frame exploration
================

## Data frame exploration

THe dataset used in this homework is a spread-sheet obtain online. It
contains data from which conclusions that were drawn in the article
“Sleep in Mammals: Ecological and Constitutional Correlates” by
Allison, T. and Cicchetti, D. (1976), *Science*, November 12, vol. 194,
pp. 732-734.

Some rows that contain missing values and some columns were removed from
the data, and it was saved as mammals.csv file.

### Setting up

First, to import the .csv file into R.

``` r
data.file = "mammals.csv"
dat = read.csv(data.file, header = TRUE)
```

### Exploration of data frame

A few funtions as `head`, `ncol`, `str`, and `summary` will be shown as
follows.

``` r
head(dat)
```

    ##                     Species BodyWeight ParadoxicalSleep TotalSleep
    ## 1 African giant pouched rat      1.000              2.0        8.3
    ## 2          Asian elephant     2547.000              1.8        3.9
    ## 3                 Baboon        10.550              0.7        9.8
    ## 4            Big brown bat       0.023              3.9       19.7
    ## 5         Brazilian tapir      160.000              1.0        6.2
    ## 6                    Cat         3.300              3.6       14.5
    ##   LifeSpan OverallDanger PredationIndex
    ## 1      4.5             3              3
    ## 2     69.0             4              3
    ## 3     27.0             4              4
    ## 4     19.0             1              1
    ## 5     30.4             4              4
    ## 6     28.0             1              1

``` r
ncol(dat)
```

    ## [1] 7

``` r
str(dat)
```

    ## 'data.frame':    41 obs. of  7 variables:
    ##  $ Species         : Factor w/ 41 levels "African giant pouched rat",..: 1 2 3 4 5 6 7 8 9 10 ...
    ##  $ BodyWeight      : num  1 2547 10.55 0.023 160 ...
    ##  $ ParadoxicalSleep: num  2 1.8 0.7 3.9 1 3.6 1.4 1.5 2.1 0 ...
    ##  $ TotalSleep      : num  8.3 3.9 9.8 19.7 6.2 14.5 9.7 12.5 8.4 8.6 ...
    ##  $ LifeSpan        : num  4.5 69 27 19 30.4 28 50 7 3.5 50 ...
    ##  $ OverallDanger   : int  3 4 4 1 4 1 1 4 1 2 ...
    ##  $ PredationIndex  : int  3 3 4 1 4 1 1 5 1 2 ...

``` r
summary(dat)
```

    ##                       Species     BodyWeight       ParadoxicalSleep
    ##  African giant pouched rat: 1   Min.   :   0.005   Min.   :0.000   
    ##  Asian elephant           : 1   1st Qu.:   0.280   1st Qu.:0.900   
    ##  Baboon                   : 1   Median :   2.000   Median :1.800   
    ##  Big brown bat            : 1   Mean   :  91.931   Mean   :1.929   
    ##  Brazilian tapir          : 1   3rd Qu.:  10.000   3rd Qu.:2.400   
    ##  Cat                      : 1   Max.   :2547.000   Max.   :6.600   
    ##  (Other)                  :35                                      
    ##    TotalSleep       LifeSpan      OverallDanger   PredationIndex 
    ##  Min.   : 2.90   Min.   :  2.00   Min.   :1.000   Min.   :1.000  
    ##  1st Qu.: 8.20   1st Qu.:  5.00   1st Qu.:1.000   1st Qu.:2.000  
    ##  Median : 9.80   Median : 10.40   Median :2.000   Median :3.000  
    ##  Mean   :10.81   Mean   : 19.11   Mean   :2.634   Mean   :2.902  
    ##  3rd Qu.:13.70   3rd Qu.: 27.00   3rd Qu.:4.000   3rd Qu.:4.000  
    ##  Max.   :19.90   Max.   :100.00   Max.   :5.000   Max.   :5.000  
    ## 

### Extracting columns and making some plots

First, let’s extract some columns

``` r
predation_index = dat$PredationIndex
danger_index = dat$OverallDanger
```

Plot a dot plot that has two variables that are body weight and life
span

``` r
plot(danger_index, predation_index)
```

![](hw01_explore_mammal_data_files/figure-gfm/unnamed-chunk-4-1.png)<!-- -->
