Assignment 1+2+3+4+5
================
Vishaylin J. Mahadeo

Assignment 1
============

Hello Octocat
-------------

I love Octocat. She's the coolest cat in town. ![](https://dl.dropboxusercontent.com/u/11805474/painblogr/biostats/images/octocat.png)

Assignment 2
============

Anscombe Dataset:
-----------------

``` r
data("anscombe")                      #loading anscombe dataset
dim(anscombe)                         #dimensions of dataset
```

    ## [1] 11  8

``` r
names(anscombe)                       #column titles
```

    ## [1] "x1" "x2" "x3" "x4" "y1" "y2" "y3" "y4"

``` r
head(anscombe, n = 6)                 #first 6 rows of dataset
```

    ##   x1 x2 x3 x4   y1   y2    y3   y4
    ## 1 10 10 10  8 8.04 9.14  7.46 6.58
    ## 2  8  8  8  8 6.95 8.14  6.77 5.76
    ## 3 13 13 13  8 7.58 8.74 12.74 7.71
    ## 4  9  9  9  8 8.81 8.77  7.11 8.84
    ## 5 11 11 11  8 8.33 9.26  7.81 8.47
    ## 6 14 14 14  8 9.96 8.10  8.84 7.04

``` r
tail(anscombe, n = 6)                 #last 6 rows of dataset
```

    ##    x1 x2 x3 x4    y1   y2   y3    y4
    ## 6  14 14 14  8  9.96 8.10 8.84  7.04
    ## 7   6  6  6  8  7.24 6.13 6.08  5.25
    ## 8   4  4  4 19  4.26 3.10 5.39 12.50
    ## 9  12 12 12  8 10.84 9.13 8.15  5.56
    ## 10  7  7  7  8  4.82 7.26 6.42  7.91
    ## 11  5  5  5  8  5.68 4.74 5.73  6.89

``` r
summary(anscombe)                     #summary of entire layout of dataset
```

    ##        x1             x2             x3             x4    
    ##  Min.   : 4.0   Min.   : 4.0   Min.   : 4.0   Min.   : 8  
    ##  1st Qu.: 6.5   1st Qu.: 6.5   1st Qu.: 6.5   1st Qu.: 8  
    ##  Median : 9.0   Median : 9.0   Median : 9.0   Median : 8  
    ##  Mean   : 9.0   Mean   : 9.0   Mean   : 9.0   Mean   : 9  
    ##  3rd Qu.:11.5   3rd Qu.:11.5   3rd Qu.:11.5   3rd Qu.: 8  
    ##  Max.   :14.0   Max.   :14.0   Max.   :14.0   Max.   :19  
    ##        y1               y2              y3              y4        
    ##  Min.   : 4.260   Min.   :3.100   Min.   : 5.39   Min.   : 5.250  
    ##  1st Qu.: 6.315   1st Qu.:6.695   1st Qu.: 6.25   1st Qu.: 6.170  
    ##  Median : 7.580   Median :8.140   Median : 7.11   Median : 7.040  
    ##  Mean   : 7.501   Mean   :7.501   Mean   : 7.50   Mean   : 7.501  
    ##  3rd Qu.: 8.570   3rd Qu.:8.950   3rd Qu.: 7.98   3rd Qu.: 8.190  
    ##  Max.   :10.840   Max.   :9.260   Max.   :12.74   Max.   :12.500

Assignment 3
============

Scatter plot showing columns x1 and y1 from Anscombe dataset
------------------------------------------------------------

<img src="./figures/xy_plot-1.svg" style="display: block; margin: auto;" /> Figure 1: Scatter plot showing Anscombe dataset, with line of regression of y1 on x1.

Assignment 4
============

Analgesic dataset import:
-------------------------

``` r
library(readr)
df <- read_csv("analgesic.csv")               #load analgesic dataset
```

Analgesic dataset summary
-------------------------

``` r
dim(df)                                       #dimensions of dataset
```

    ## [1] 40  5

``` r
names(df)                                     #column titles
```

    ## [1] "ID"            "Group"         "Measurement_1" "Measurement_2"
    ## [5] "Measurement_3"

``` r
head(df, n = 6)                               #first 6 rows of dataset
```

    ##   ID     Group Measurement_1 Measurement_2 Measurement_3
    ## 1  1 Analgesic            26            26            21
    ## 2  2 Analgesic            29            26            23
    ## 3  3 Analgesic            24            28            22
    ## 4  4 Analgesic            25            22            24
    ## 5  5 Analgesic            24            28            23
    ## 6  6 Analgesic            22            23            26

``` r
tail(df, n = 6)                               #last 6 rows of dataset
```

    ##    ID   Group Measurement_1 Measurement_2 Measurement_3
    ## 35 35 Placebo            17            21            15
    ## 36 36 Placebo            19            17            15
    ## 37 37 Placebo            14            19            13
    ## 38 38 Placebo            17            19            13
    ## 39 39 Placebo            11            20            18
    ## 40 40 Placebo            15            18            12

``` r
summary(df)                                   #summary of entire layout
```

    ##        ID           Group           Measurement_1   Measurement_2 
    ##  Min.   : 1.00   Length:40          Min.   :10.00   Min.   : 8.0  
    ##  1st Qu.:10.75   Class :character   1st Qu.:17.00   1st Qu.:17.0  
    ##  Median :20.50   Mode  :character   Median :20.00   Median :20.0  
    ##  Mean   :20.50                      Mean   :20.12   Mean   :20.7  
    ##  3rd Qu.:30.25                      3rd Qu.:24.00   3rd Qu.:25.0  
    ##  Max.   :40.00                      Max.   :30.00   Max.   :32.0  
    ##  Measurement_3  
    ##  Min.   :12.00  
    ##  1st Qu.:16.00  
    ##  Median :20.50  
    ##  Mean   :20.52  
    ##  3rd Qu.:24.25  
    ##  Max.   :30.00

Analgesic dataset grouped by measurements
-----------------------------------------

``` r
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
library(tidyr)
gathered <- gather(data = df,
                   key = measurement, 
                   value = data, Measurement_1:Measurement_3,
                   na.rm = FALSE,
                   convert = FALSE,
                   factor_key = FALSE)        #gather into measurement column
by_id <- group_by(gathered, ID)               #group by subect ID
report <- summarize(by_id, mean(data))        #average of measurements by_id
report                                        #print results
```

    ## # A tibble: 40 x 2
    ##       ID mean(data)
    ##    <int>      <dbl>
    ## 1      1   24.33333
    ## 2      2   26.00000
    ## 3      3   24.66667
    ## 4      4   23.66667
    ## 5      5   25.00000
    ## 6      6   23.66667
    ## 7      7   26.66667
    ## 8      8   23.33333
    ## 9      9   22.66667
    ## 10    10   24.00000
    ## # ... with 30 more rows

Assignment 5
============

Chicken weights
---------------

**Null hypothesis:** Chicken feed has no effect on chicken weight

**Alternative hypothesis:** Chicken feed has a direct effect on chicken weight

Unpaired, Parametric data set with more than 2 groups therefore a One-Way ANOVA is required to test hypothesis.

Significance interval set at 95%, df = 5.

If p value &lt; F-value then reject null hypothesis.

``` r
library(readr)
df_chicken <- read_csv("chick-weights.csv")           #load dataset
boxplot(weight ~ feed, data = df_chicken)             #parametric check
```

![](README_files/figure-markdown_github/chicken%20(chunk%201)-1.png)

``` r
chicken_test <- aov(weight ~ feed, data = df_chicken) #1-way ANOVA test
summary(chicken_test)                                 #summary of test
```

    ##             Df Sum Sq Mean Sq F value   Pr(>F)    
    ## feed         5 231129   46226   15.37 5.94e-10 ***
    ## Residuals   65 195556    3009                     
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1

F-value = 15.37 , p-value = 5.94e-10. p&lt; F, therefore reject null hypothesis.

Therefore we can conclude that chicken feed has a direct effect on chicken weight.

The Hot Zone
------------

**Null hypothesis:** Drinking water does not cause gastroenteritis.

**Alternative hypothesis:** Drinking water did cause gastroenteritis.

Unpaired, non-parametric, categorical dataset. Therefore a Fisher's Exact test will be used to test hypothesis.

Significance interval set at 95%, reject null hypothesis if p &lt; 0.05

``` r
df_hot <- read_csv("gastroenteritis.csv")             #load dataset
df_table <- table(df_hot$Consumption, df_hot$Outcome) #create contiguency tab
hot_test <- fisher.test(df_table)                     #Fishers test
hot_test
```

    ## 
    ##  Fisher's Exact Test for Count Data
    ## 
    ## data:  df_table
    ## p-value < 2.2e-16
    ## alternative hypothesis: two.sided

p = 2.2e-16 therefore reject null hypothesis.

In conclusion the drinking water did cause gasteroenteritis.

Nausea
------

**Null hypothesis:** 5HT3 receptor blocker does not reduce nausea in breast cancer patients.

**Alternative hypthesis:** 5HT3 receptor blocker does reduce nausea in breast cancer patients.

Paired, parametric, ordinal dataset. Therefore a McNemar;s Chi-Squared with continuity correction required.

Significance interval set at 95%, reject null hypothesis if p &lt; 0.05

``` r
df_nausea <- read_csv("nausea.csv")           #load dataset
nausea_new <- df_nausea[-8,-1]                #exclude outlier
nausea_new
```

    ## # A tibble: 7 x 2
    ##   Nausea_before Nausea_after
    ##           <int>        <int>
    ## 1             3            2
    ## 2             4            0
    ## 3             6            1
    ## 4             2            3
    ## 5             2            1
    ## 6             4            1
    ## 7             5            0

``` r
boxplot(nausea_new)                           #parametric check
```

![](README_files/figure-markdown_github/nausea-1.png)

``` r
wilcox.test(nausea_new$Nausea_before, nausea_new$Nausea_after, paired=TRUE)   #Wilcox stat test
```

    ## Warning in wilcox.test.default(nausea_new$Nausea_before, nausea_new
    ## $Nausea_after, : cannot compute exact p-value with ties

    ## 
    ##  Wilcoxon signed rank test with continuity correction
    ## 
    ## data:  nausea_new$Nausea_before and nausea_new$Nausea_after
    ## V = 26, p-value = 0.04983
    ## alternative hypothesis: true location shift is not equal to 0

p-value = 0.04983, therefore reject null hypothesis.

In conclusion the 5Ht3 receptor blocker does reduce nausea in breast cancer patients.
