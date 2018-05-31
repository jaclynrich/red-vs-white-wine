Red vs. White Wine
================
Jaclyn Rich
3/28/2018

-   [Data Overview](#data-overview)
    -   [White Wine](#white-wine)
    -   [Red Wine](#red-wine)
    -   [Combined Data](#combined-data)
-   [Univariate Plots and Analysis](#univariate-plots-and-analysis)
    -   [Fixed Acidity](#fixed-acidity)
    -   [Volatile Acidity](#volatile-acidity)
    -   [Citric Acid](#citric-acid)
    -   [Residual Sugar](#residual-sugar)
    -   [Chlorides](#chlorides)
    -   [Free Sulfur Dioxide](#free-sulfur-dioxide)
    -   [Total Sulfur Dioxide](#total-sulfur-dioxide)
    -   [Density](#density)
    -   [pH](#ph)
    -   [Sulphates](#sulphates)
    -   [Percent Alcohol](#percent-alcohol)
    -   [Quality](#quality)
    -   [Summary](#summary)
-   [Bivariate Plots and Analysis](#bivariate-plots-and-analysis)
-   [Multivariate Plots and Analysis](#multivariate-plots-and-analysis)
-   [Final Plots and Summary](#final-plots-and-summary)
-   [Reflection](#reflection)

Data Overview
-------------

Data Source: P. Cortez, A. Cerdeira, F. Almeida, T. Matos and J. Reis. Modeling wine preferences by data mining from physicochemical properties. In Decision Support Systems, Elsevier, 47(4):547-553. ISSN: 0167-9236.

The data sets originally consisted of 1599 Portuguese red wines and 4898 white wines with 12 features and an index variable (X); neither data set has null values. All of the features besides quality, which is ordinal, are continuous. The data sets were joined for a total of 6497 wines and a color field was added. The purpose of this report is to explore the chemical properties that distinguish red and white wines.

Features:

-   fixed.acidity: the amount of nonvolatile (tartaric) acid
    -   nonvolatile acids do not evaporate readily
-   volatile.acidity: the amount of volatile (acetic) acid
    -   higher levels will result in a distasteful, vinegary taste
-   citric.acid: the amount of citric acid
    -   adds a "freshness" and flavor to wines
    -   found in small quantities
-   residual.sugar: quantity of sugar remaining after the fermentation process is finished
    -   wines with more than 45 grams/liter are considered sweet
-   chlorides: quantity of salt
-   free.sulfur.dioxide: the amount of the free form of sulfur dioxide
    -   the free form exists in equilibrium between molecular sulfur dioxide (as a dissolved gas) and bisulfite ion
    -   it prevents microbial growth and oxidation of the wine
-   total.sulfur.dioxide: the amount of free and bound forms of sulfur dioxide
    -   in low amounts it is usually not noticeable
    -   in higher amounts it is apparent in the nose and taste of the wine
-   density: mass per unit of volume
-   pH: describes how acidic or basic the wine is
    -   pH scale goes from 0 (most acidic) to 14 (most basic)
-   sulphates: the amount of potassium sulphate
    -   potassium sulphate is a antimicrobial and antioxidant additive which can contribute to sulfur dioxide gas levels
-   alcohol: the percent volume of alcohol
-   quality: score between 0 (worst) and 10 (best)
    -   three independent taste testers rated each wine
    -   the median score was chosen as the quality

The amounts are in grams per liter.

### White Wine

    ## [1] 4898   13

    ## 'data.frame':    4898 obs. of  13 variables:
    ##  $ X                   : int  1 2 3 4 5 6 7 8 9 10 ...
    ##  $ fixed.acidity       : num  7 6.3 8.1 7.2 7.2 8.1 6.2 7 6.3 8.1 ...
    ##  $ volatile.acidity    : num  0.27 0.3 0.28 0.23 0.23 0.28 0.32 0.27 0.3 0.22 ...
    ##  $ citric.acid         : num  0.36 0.34 0.4 0.32 0.32 0.4 0.16 0.36 0.34 0.43 ...
    ##  $ residual.sugar      : num  20.7 1.6 6.9 8.5 8.5 6.9 7 20.7 1.6 1.5 ...
    ##  $ chlorides           : num  0.045 0.049 0.05 0.058 0.058 0.05 0.045 0.045 0.049 0.044 ...
    ##  $ free.sulfur.dioxide : num  45 14 30 47 47 30 30 45 14 28 ...
    ##  $ total.sulfur.dioxide: num  170 132 97 186 186 97 136 170 132 129 ...
    ##  $ density             : num  1.001 0.994 0.995 0.996 0.996 ...
    ##  $ pH                  : num  3 3.3 3.26 3.19 3.19 3.26 3.18 3 3.3 3.22 ...
    ##  $ sulphates           : num  0.45 0.49 0.44 0.4 0.4 0.44 0.47 0.45 0.49 0.45 ...
    ##  $ alcohol             : num  8.8 9.5 10.1 9.9 9.9 10.1 9.6 8.8 9.5 11 ...
    ##  $ quality             : int  6 6 6 6 6 6 6 6 6 6 ...

    ##        X        fixed.acidity    volatile.acidity  citric.acid    
    ##  Min.   :   1   Min.   : 3.800   Min.   :0.0800   Min.   :0.0000  
    ##  1st Qu.:1225   1st Qu.: 6.300   1st Qu.:0.2100   1st Qu.:0.2700  
    ##  Median :2450   Median : 6.800   Median :0.2600   Median :0.3200  
    ##  Mean   :2450   Mean   : 6.855   Mean   :0.2782   Mean   :0.3342  
    ##  3rd Qu.:3674   3rd Qu.: 7.300   3rd Qu.:0.3200   3rd Qu.:0.3900  
    ##  Max.   :4898   Max.   :14.200   Max.   :1.1000   Max.   :1.6600  
    ##  residual.sugar     chlorides       free.sulfur.dioxide
    ##  Min.   : 0.600   Min.   :0.00900   Min.   :  2.00     
    ##  1st Qu.: 1.700   1st Qu.:0.03600   1st Qu.: 23.00     
    ##  Median : 5.200   Median :0.04300   Median : 34.00     
    ##  Mean   : 6.391   Mean   :0.04577   Mean   : 35.31     
    ##  3rd Qu.: 9.900   3rd Qu.:0.05000   3rd Qu.: 46.00     
    ##  Max.   :65.800   Max.   :0.34600   Max.   :289.00     
    ##  total.sulfur.dioxide    density             pH          sulphates     
    ##  Min.   :  9.0        Min.   :0.9871   Min.   :2.720   Min.   :0.2200  
    ##  1st Qu.:108.0        1st Qu.:0.9917   1st Qu.:3.090   1st Qu.:0.4100  
    ##  Median :134.0        Median :0.9937   Median :3.180   Median :0.4700  
    ##  Mean   :138.4        Mean   :0.9940   Mean   :3.188   Mean   :0.4898  
    ##  3rd Qu.:167.0        3rd Qu.:0.9961   3rd Qu.:3.280   3rd Qu.:0.5500  
    ##  Max.   :440.0        Max.   :1.0390   Max.   :3.820   Max.   :1.0800  
    ##     alcohol         quality     
    ##  Min.   : 8.00   Min.   :3.000  
    ##  1st Qu.: 9.50   1st Qu.:5.000  
    ##  Median :10.40   Median :6.000  
    ##  Mean   :10.51   Mean   :5.878  
    ##  3rd Qu.:11.40   3rd Qu.:6.000  
    ##  Max.   :14.20   Max.   :9.000

    ##   X fixed.acidity volatile.acidity citric.acid residual.sugar chlorides
    ## 1 1           7.0             0.27        0.36           20.7     0.045
    ## 2 2           6.3             0.30        0.34            1.6     0.049
    ## 3 3           8.1             0.28        0.40            6.9     0.050
    ## 4 4           7.2             0.23        0.32            8.5     0.058
    ## 5 5           7.2             0.23        0.32            8.5     0.058
    ## 6 6           8.1             0.28        0.40            6.9     0.050
    ##   free.sulfur.dioxide total.sulfur.dioxide density   pH sulphates alcohol
    ## 1                  45                  170  1.0010 3.00      0.45     8.8
    ## 2                  14                  132  0.9940 3.30      0.49     9.5
    ## 3                  30                   97  0.9951 3.26      0.44    10.1
    ## 4                  47                  186  0.9956 3.19      0.40     9.9
    ## 5                  47                  186  0.9956 3.19      0.40     9.9
    ## 6                  30                   97  0.9951 3.26      0.44    10.1
    ##   quality
    ## 1       6
    ## 2       6
    ## 3       6
    ## 4       6
    ## 5       6
    ## 6       6

### Red Wine

    ## [1] 1599   13

    ## 'data.frame':    1599 obs. of  13 variables:
    ##  $ X                   : int  1 2 3 4 5 6 7 8 9 10 ...
    ##  $ fixed.acidity       : num  7.4 7.8 7.8 11.2 7.4 7.4 7.9 7.3 7.8 7.5 ...
    ##  $ volatile.acidity    : num  0.7 0.88 0.76 0.28 0.7 0.66 0.6 0.65 0.58 0.5 ...
    ##  $ citric.acid         : num  0 0 0.04 0.56 0 0 0.06 0 0.02 0.36 ...
    ##  $ residual.sugar      : num  1.9 2.6 2.3 1.9 1.9 1.8 1.6 1.2 2 6.1 ...
    ##  $ chlorides           : num  0.076 0.098 0.092 0.075 0.076 0.075 0.069 0.065 0.073 0.071 ...
    ##  $ free.sulfur.dioxide : num  11 25 15 17 11 13 15 15 9 17 ...
    ##  $ total.sulfur.dioxide: num  34 67 54 60 34 40 59 21 18 102 ...
    ##  $ density             : num  0.998 0.997 0.997 0.998 0.998 ...
    ##  $ pH                  : num  3.51 3.2 3.26 3.16 3.51 3.51 3.3 3.39 3.36 3.35 ...
    ##  $ sulphates           : num  0.56 0.68 0.65 0.58 0.56 0.56 0.46 0.47 0.57 0.8 ...
    ##  $ alcohol             : num  9.4 9.8 9.8 9.8 9.4 9.4 9.4 10 9.5 10.5 ...
    ##  $ quality             : int  5 5 5 6 5 5 5 7 7 5 ...

    ##        X          fixed.acidity   volatile.acidity  citric.acid   
    ##  Min.   :   1.0   Min.   : 4.60   Min.   :0.1200   Min.   :0.000  
    ##  1st Qu.: 400.5   1st Qu.: 7.10   1st Qu.:0.3900   1st Qu.:0.090  
    ##  Median : 800.0   Median : 7.90   Median :0.5200   Median :0.260  
    ##  Mean   : 800.0   Mean   : 8.32   Mean   :0.5278   Mean   :0.271  
    ##  3rd Qu.:1199.5   3rd Qu.: 9.20   3rd Qu.:0.6400   3rd Qu.:0.420  
    ##  Max.   :1599.0   Max.   :15.90   Max.   :1.5800   Max.   :1.000  
    ##  residual.sugar     chlorides       free.sulfur.dioxide
    ##  Min.   : 0.900   Min.   :0.01200   Min.   : 1.00      
    ##  1st Qu.: 1.900   1st Qu.:0.07000   1st Qu.: 7.00      
    ##  Median : 2.200   Median :0.07900   Median :14.00      
    ##  Mean   : 2.539   Mean   :0.08747   Mean   :15.87      
    ##  3rd Qu.: 2.600   3rd Qu.:0.09000   3rd Qu.:21.00      
    ##  Max.   :15.500   Max.   :0.61100   Max.   :72.00      
    ##  total.sulfur.dioxide    density             pH          sulphates     
    ##  Min.   :  6.00       Min.   :0.9901   Min.   :2.740   Min.   :0.3300  
    ##  1st Qu.: 22.00       1st Qu.:0.9956   1st Qu.:3.210   1st Qu.:0.5500  
    ##  Median : 38.00       Median :0.9968   Median :3.310   Median :0.6200  
    ##  Mean   : 46.47       Mean   :0.9967   Mean   :3.311   Mean   :0.6581  
    ##  3rd Qu.: 62.00       3rd Qu.:0.9978   3rd Qu.:3.400   3rd Qu.:0.7300  
    ##  Max.   :289.00       Max.   :1.0037   Max.   :4.010   Max.   :2.0000  
    ##     alcohol         quality     
    ##  Min.   : 8.40   Min.   :3.000  
    ##  1st Qu.: 9.50   1st Qu.:5.000  
    ##  Median :10.20   Median :6.000  
    ##  Mean   :10.42   Mean   :5.636  
    ##  3rd Qu.:11.10   3rd Qu.:6.000  
    ##  Max.   :14.90   Max.   :8.000

    ##   X fixed.acidity volatile.acidity citric.acid residual.sugar chlorides
    ## 1 1           7.4             0.70        0.00            1.9     0.076
    ## 2 2           7.8             0.88        0.00            2.6     0.098
    ## 3 3           7.8             0.76        0.04            2.3     0.092
    ## 4 4          11.2             0.28        0.56            1.9     0.075
    ## 5 5           7.4             0.70        0.00            1.9     0.076
    ## 6 6           7.4             0.66        0.00            1.8     0.075
    ##   free.sulfur.dioxide total.sulfur.dioxide density   pH sulphates alcohol
    ## 1                  11                   34  0.9978 3.51      0.56     9.4
    ## 2                  25                   67  0.9968 3.20      0.68     9.8
    ## 3                  15                   54  0.9970 3.26      0.65     9.8
    ## 4                  17                   60  0.9980 3.16      0.58     9.8
    ## 5                  11                   34  0.9978 3.51      0.56     9.4
    ## 6                  13                   40  0.9978 3.51      0.56     9.4
    ##   quality
    ## 1       5
    ## 2       5
    ## 3       5
    ## 4       6
    ## 5       5
    ## 6       5

### Combined Data

    ## [1] 6497   13

    ## 'data.frame':    6497 obs. of  13 variables:
    ##  $ fixed.acidity       : num  7.4 7.8 7.8 11.2 7.4 7.4 7.9 7.3 7.8 7.5 ...
    ##  $ volatile.acidity    : num  0.7 0.88 0.76 0.28 0.7 0.66 0.6 0.65 0.58 0.5 ...
    ##  $ citric.acid         : num  0 0 0.04 0.56 0 0 0.06 0 0.02 0.36 ...
    ##  $ residual.sugar      : num  1.9 2.6 2.3 1.9 1.9 1.8 1.6 1.2 2 6.1 ...
    ##  $ chlorides           : num  0.076 0.098 0.092 0.075 0.076 0.075 0.069 0.065 0.073 0.071 ...
    ##  $ free.sulfur.dioxide : num  11 25 15 17 11 13 15 15 9 17 ...
    ##  $ total.sulfur.dioxide: num  34 67 54 60 34 40 59 21 18 102 ...
    ##  $ density             : num  0.998 0.997 0.997 0.998 0.998 ...
    ##  $ pH                  : num  3.51 3.2 3.26 3.16 3.51 3.51 3.3 3.39 3.36 3.35 ...
    ##  $ sulphates           : num  0.56 0.68 0.65 0.58 0.56 0.56 0.46 0.47 0.57 0.8 ...
    ##  $ alcohol             : num  9.4 9.8 9.8 9.8 9.4 9.4 9.4 10 9.5 10.5 ...
    ##  $ quality             : int  5 5 5 6 5 5 5 7 7 5 ...
    ##  $ color               : Factor w/ 2 levels "white","red": 2 2 2 2 2 2 2 2 2 2 ...

    ##  fixed.acidity    volatile.acidity  citric.acid     residual.sugar  
    ##  Min.   : 3.800   Min.   :0.0800   Min.   :0.0000   Min.   : 0.600  
    ##  1st Qu.: 6.400   1st Qu.:0.2300   1st Qu.:0.2500   1st Qu.: 1.800  
    ##  Median : 7.000   Median :0.2900   Median :0.3100   Median : 3.000  
    ##  Mean   : 7.215   Mean   :0.3397   Mean   :0.3186   Mean   : 5.443  
    ##  3rd Qu.: 7.700   3rd Qu.:0.4000   3rd Qu.:0.3900   3rd Qu.: 8.100  
    ##  Max.   :15.900   Max.   :1.5800   Max.   :1.6600   Max.   :65.800  
    ##    chlorides       free.sulfur.dioxide total.sulfur.dioxide
    ##  Min.   :0.00900   Min.   :  1.00      Min.   :  6.0       
    ##  1st Qu.:0.03800   1st Qu.: 17.00      1st Qu.: 77.0       
    ##  Median :0.04700   Median : 29.00      Median :118.0       
    ##  Mean   :0.05603   Mean   : 30.53      Mean   :115.7       
    ##  3rd Qu.:0.06500   3rd Qu.: 41.00      3rd Qu.:156.0       
    ##  Max.   :0.61100   Max.   :289.00      Max.   :440.0       
    ##     density             pH          sulphates         alcohol     
    ##  Min.   :0.9871   Min.   :2.720   Min.   :0.2200   Min.   : 8.00  
    ##  1st Qu.:0.9923   1st Qu.:3.110   1st Qu.:0.4300   1st Qu.: 9.50  
    ##  Median :0.9949   Median :3.210   Median :0.5100   Median :10.30  
    ##  Mean   :0.9947   Mean   :3.219   Mean   :0.5313   Mean   :10.49  
    ##  3rd Qu.:0.9970   3rd Qu.:3.320   3rd Qu.:0.6000   3rd Qu.:11.30  
    ##  Max.   :1.0390   Max.   :4.010   Max.   :2.0000   Max.   :14.90  
    ##     quality        color     
    ##  Min.   :3.000   white:4898  
    ##  1st Qu.:5.000   red  :1599  
    ##  Median :6.000               
    ##  Mean   :5.818               
    ##  3rd Qu.:6.000               
    ##  Max.   :9.000

    ##      fixed.acidity volatile.acidity citric.acid residual.sugar chlorides
    ## 1266           7.2            0.570        0.05            2.3     0.081
    ## 539           12.9            0.350        0.49            5.8     0.066
    ## 3531           7.1            0.490        0.22            2.0     0.047
    ## 5709           5.0            0.255        0.22            2.7     0.043
    ## 1898           7.5            0.170        0.44           11.3     0.046
    ## 3482           7.7            0.300        0.42           14.3     0.045
    ## 163            7.8            0.530        0.04            1.7     0.076
    ## 969            9.0            0.400        0.43            2.4     0.068
    ## 6031           6.6            0.380        0.28            2.8     0.043
    ## 3106           8.1            0.200        0.49            8.1     0.051
    ##      free.sulfur.dioxide total.sulfur.dioxide density   pH sulphates
    ## 1266                16.0                 36.0 0.99564 3.38      0.60
    ## 539                  5.0                 35.0 1.00140 3.20      0.66
    ## 3531               146.5                307.5 0.99240 3.24      0.37
    ## 5709                46.0                153.0 0.99238 3.75      0.76
    ## 1898                65.0                146.0 0.99700 3.17      0.45
    ## 3482                45.0                213.0 0.99910 3.18      0.63
    ## 163                 17.0                 31.0 0.99640 3.33      0.56
    ## 969                 29.0                 46.0 0.99430 3.20      0.60
    ## 6031                17.0                 67.0 0.98924 3.21      0.47
    ## 3106                51.0                205.0 0.99540 3.10      0.52
    ##      alcohol quality color
    ## 1266    10.3       6   red
    ## 539     12.0       7   red
    ## 3531    11.0       3 white
    ## 5709    11.3       6 white
    ## 1898    10.0       6 white
    ## 3482     9.2       5 white
    ## 163     10.0       6   red
    ## 969     12.2       6   red
    ## 6031    13.2       6 white
    ## 3106    11.0       6 white

It is worth noting that there are 1177 duplicated records in the combined data set. The original paper did not remove these duplicate records. I have also kept the repeated rows, since from the description of the data it seems as though each row is a distinct variety, and removing them would no longer make this data set reflective of the prevalence of certain wines; if certain characteristics of wine are more common, then this frequency should be reflected in the data set.

Additionally, there are more than three times as many white wines than red wines in the data. This is important to keep in mind when training for classification based on color.

    ## [1] 1177

Univariate Plots and Analysis
-----------------------------

### Fixed Acidity

Note that for all displays of summary statistics, the red wines will appear on top and that for all univariate and bivariate plots (except the scatter matrix) red wine data is shown in plum purple and white wine data is shown in a light green.

    ##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
    ##    4.60    7.10    7.90    8.32    9.20   15.90

    ##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
    ##   3.800   6.300   6.800   6.855   7.300  14.200

![](red_vs_white_wine_files/figure-markdown_github/unnamed-chunk-7-1.jpeg)

Since the counts for red wine are so much lower, I plotted the them separately.

![](red_vs_white_wine_files/figure-markdown_github/unnamed-chunk-8-1.jpeg)

    ## 
    ##   (3,4]   (4,5]   (5,6]   (6,7]   (7,8]   (8,9]  (9,10] (10,11] (11,12] 
    ##       0       9      62     291     496     300     188     118      76 
    ## (12,13] (13,14] (14,15] (15,16] 
    ##      39      12       3       5

    ## 
    ##   (3,4]   (4,5]   (5,6]   (6,7]   (7,8]   (8,9]  (9,10] (10,11] (11,12] 
    ##       2      52     704    2350    1396     322      65       5       1 
    ## (12,13] (13,14] (14,15] (15,16] 
    ##       0       0       1       0

The distribution of the fixed acidity for red wines is slightly skewed to the right, with the last quartile being much more spread out than the other three. The mass of the data lies between 7 and 8.5, with all of the values between 4.6 and 15.9. There are only a few values greater than 14, although they do pull the mean up slightly.

The distribution of the fixed acidity for white wines is much more symmetric, with only a handful of data points lying above 10. The mass of the data lies between 6 and 7.5. It is clear that the fixed acidity for red wines is more spread out than that of white wines, and is generally lower.

### Volatile Acidity

    ##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
    ##  0.1200  0.3900  0.5200  0.5278  0.6400  1.5800

    ##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
    ##  0.0800  0.2100  0.2600  0.2782  0.3200  1.1000

![](red_vs_white_wine_files/figure-markdown_github/unnamed-chunk-11-1.jpeg)

![](red_vs_white_wine_files/figure-markdown_github/unnamed-chunk-12-1.jpeg)

![](red_vs_white_wine_files/figure-markdown_github/unnamed-chunk-13-1.jpeg)

Once again the white wines have a much more clustered distribution as compared with the red; since the mass of the data occurs in such a small range, many of the larger values are shown as outliers on the boxplot. Overall the red wines have more volatile acid than the whites; this discrepancy is much more marked than that of fixed acid levels. Since the data was long-tailed and the data is spread over more than an order of magnitude, I also plotted it on a log base 10 scale, where it looks normally distributed.

### Citric Acid

    ##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
    ##   0.000   0.090   0.260   0.271   0.420   1.000

    ##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
    ##  0.0000  0.2700  0.3200  0.3342  0.3900  1.6600

![](red_vs_white_wine_files/figure-markdown_github/unnamed-chunk-15-1.jpeg)

![](red_vs_white_wine_files/figure-markdown_github/unnamed-chunk-16-1.jpeg)

![](red_vs_white_wine_files/figure-markdown_github/unnamed-chunk-17-1.jpeg)

The data for white wine is fairly symmetric, with a slightly longer tail on the right side. We can see from the histogram and the small box on the box and whisker plot that most of the data lies within a small range (about 0.2 - 0.4). This also means that many of the lower and high-valued points are considered outliers.

The mass of the red wine data is much more spread out and all of the data has a smaller range than the white wine. The histogram shows three tall spikes, around 0, 0.25, and 0.50. More than 8% of the data points have 0 grams of citric acid per liter. All of the data points are less than 0.8, except for one outlier which has 1 g/L.

    ## [1] 0.08255159

Red wine has lower levels of citric acid than white wine; about 50% of the red wines have more than 0.25 g/L, whereas about 75% of white wines have more than that.

### Residual Sugar

    ##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
    ##   0.900   1.900   2.200   2.539   2.600  15.500

    ##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
    ##   0.600   1.700   5.200   6.391   9.900  65.800

![](red_vs_white_wine_files/figure-markdown_github/unnamed-chunk-20-1.jpeg)

We can clearly see white wines are vastly sweeter than reds overall. There is one sweet white wine (defined as greater than 45 g/L) with 65.8 g/L. Some of the larger values and all outliers for the white wine were excluded from the histogram below in order to get a better look at the data.

![](red_vs_white_wine_files/figure-markdown_github/unnamed-chunk-21-1.jpeg)

![](red_vs_white_wine_files/figure-markdown_github/unnamed-chunk-22-1.jpeg)

Red and white wines each have a large peak around 2-2.5. While after this peak, red wines decrease rapidly and have a very long tail, white wines decrease, but maintain a higher level of sweeter wines. Even after a log10 transformation of the x-axis, the distribution of residual sugar in red wines is still slightly skewed to the right. The transformation condenses the right side of the white wines data into one mass, making the data look bimodal.

### Chlorides

    ##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
    ## 0.01200 0.07000 0.07900 0.08747 0.09000 0.61100

    ##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
    ## 0.00900 0.03600 0.04300 0.04577 0.05000 0.34600

![](red_vs_white_wine_files/figure-markdown_github/unnamed-chunk-24-1.jpeg)

![](red_vs_white_wine_files/figure-markdown_github/unnamed-chunk-25-1.jpeg)

![](red_vs_white_wine_files/figure-markdown_github/unnamed-chunk-26-1.jpeg)

White wines have lower levels of chlorides in general; most white wines have less than 0.07 grams of chlorides per liter, where as 75% of reds have greater than this amount. Chloride distributions for both colors are very clustered, but with a significant number of outliers, and some lying very far away from the mass of the data. Even after a log transformation both distributions are very long tailed. Additionally, the scale also emphasizes some of the lower values.

### Free Sulfur Dioxide

    ##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
    ##    1.00    7.00   14.00   15.87   21.00   72.00

    ##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
    ##    2.00   23.00   34.00   35.31   46.00  289.00

![](red_vs_white_wine_files/figure-markdown_github/unnamed-chunk-28-1.jpeg)

![](red_vs_white_wine_files/figure-markdown_github/unnamed-chunk-29-1.jpeg)

![](red_vs_white_wine_files/figure-markdown_github/unnamed-chunk-30-1.jpeg)

The distribution for red wines has a much smaller range and fewer outliers than that of the whites. White wines also have one outlier at 239 that is more than 100 g/L greater than the next largest value. Red wines have much less sulfur dioxide; more than 75% of reds have less than 23 g/L, while whites have only 25% of points below this value.

### Total Sulfur Dioxide

    ##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
    ##    6.00   22.00   38.00   46.47   62.00  289.00

    ##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
    ##     9.0   108.0   134.0   138.4   167.0   440.0

![](red_vs_white_wine_files/figure-markdown_github/unnamed-chunk-32-1.jpeg)

![](red_vs_white_wine_files/figure-markdown_github/unnamed-chunk-33-1.jpeg)

The distributions for total sulfur dioxide look drastically different from each other, although they do look somewhat similar to those for free sulfur dioxide. The distribution for white wines looks normal, with some high outliers. The distribution for red wines is skewed to the right, also with a few outliers. Overall, white wines have much higher levels of sulfur dioxide with almost all the red wines having less sulfur dioxide than 50% of white wines.

### Density

    ##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
    ##  0.9901  0.9956  0.9968  0.9967  0.9978  1.0040

    ##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
    ##  0.9871  0.9917  0.9937  0.9940  0.9961  1.0390

![](red_vs_white_wine_files/figure-markdown_github/unnamed-chunk-35-1.jpeg)

Red wines are more dense than white wines overall, but there are some large outliers for the density of white wines. However, even though the range for white wines is larger, it still very small at only 0.0519. It is worth noting that most wines are slightly less dense than water, which has a density of 1.

### pH

    ##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
    ##   2.740   3.210   3.310   3.311   3.400   4.010

    ##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
    ##   2.720   3.090   3.180   3.188   3.280   3.820

![](red_vs_white_wine_files/figure-markdown_github/unnamed-chunk-37-1.jpeg)

![](red_vs_white_wine_files/figure-markdown_github/unnamed-chunk-38-1.jpeg)

The shapes of the distributions for white and red wine pHs look very similar, but with the reds shifted slightly higher. This indicates that red wines are slightly more basic and white wines are slightly more acidic. Both distributions have tails on both ends, and look approximately normally distributed.

### Sulphates

    ##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
    ##  0.3300  0.5500  0.6200  0.6581  0.7300  2.0000

    ##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
    ##  0.2200  0.4100  0.4700  0.4898  0.5500  1.0800

![](red_vs_white_wine_files/figure-markdown_github/unnamed-chunk-40-1.jpeg)

![](red_vs_white_wine_files/figure-markdown_github/unnamed-chunk-41-1.jpeg)

![](red_vs_white_wine_files/figure-markdown_github/unnamed-chunk-42-1.jpeg)

The boxplots for both distributions look very similar, although red wines have more significant outliers. White wines are log-normal, but red wines still have high values after the log transformation. White wines also have less sulphates than red wines, with 75% of white wines having less than 0.55 g/L, and only 25% of red wines having less than this amount.

### Percent Alcohol

    ##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
    ##    8.40    9.50   10.20   10.42   11.10   14.90

    ##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
    ##    8.00    9.50   10.40   10.51   11.40   14.20

![](red_vs_white_wine_files/figure-markdown_github/unnamed-chunk-44-1.jpeg)

![](red_vs_white_wine_files/figure-markdown_github/unnamed-chunk-45-1.jpeg)

The shapes of the distributions for the percent alcohol in red and white wines are practically identical. They both peak around 9.5 and have very similar means and quartiles. The distribution for red wines have a slightly longer tail and a few outliers.

### Quality

    ##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
    ##   3.000   5.000   6.000   5.636   6.000   8.000

    ##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
    ##   3.000   5.000   6.000   5.878   6.000   9.000

![](red_vs_white_wine_files/figure-markdown_github/unnamed-chunk-47-1.jpeg)

We can see that red and white wines have very similar proportions for wines with quality scores of 3 and 4. Red wines in this data set are of slightly lower quality; they have a greater proportion of wines with a score of 5 and a lower portion that are scored 6, 7, and 8, as compared with whites. Additionally, the maximum quality score for white wines is 9, whereas the highest score awarded to a red wine is 8.

### Summary

For red vs. white wine classification, it is important to know which variables most clearly split the data according to color. We can see that the values for volatile acidity, residual sugar, chlorides, and total sulfur dioxide show the most clear distinction between the colors. These variables are the most likely to be included in a future classification model.

Bivariate Plots and Analysis
----------------------------

![](red_vs_white_wine_files/figure-markdown_github/unnamed-chunk-48-1.jpeg)

Unsurprisingly the two variables with the strongest correlation are free sulfur dioxide and total sulfur dioxide at 0.72. The next strongest relationship is a negative one between density and percent alcohol at -0.69. Residual sugar and density also have a moderately strong relationship with a correlation of 0.55 It is also interesting to note that quality has the strongest positive relationship with percent alcohol and negative relationships with density and volatile acidity. It is important that we know which variables in the data are strongly correlated in case we want to perform a regression.

![](red_vs_white_wine_files/figure-markdown_github/unnamed-chunk-49-1.jpeg)

When we look at the correlations between variables for each color we can see some relationships not apparent when we looked at the relationships regardless of wine color. Both red and white wines have a strong negative relationship between pH and quality, meaning the as the pH increases, or the wine becomes more basic, the quality decreases. For white wines the strongest relationship is between chlorides and pH, at 0.84; this relationship was non-existent in the aggregated correlation matrix, with a correlation of 0.04 between these variables. Red wines have much stronger relationships between volatile acidity and other variables as compared with white wines; residual sugar and pH have moderately strong positive relationships with volatile acidity, and sulphates have a moderately strong negative one with it.

In order to aid in classification according to wine color, it will be most helpful to find pairs of variables that show the greatest separation between the classes.

The scatterplots above are not centered around the mass of the data because of outliers. Note that the axis dimensions for the individual scatterplots below were altered in order to feature the majority of the data.

![](red_vs_white_wine_files/figure-markdown_github/unnamed-chunk-50-1.jpeg)

![](red_vs_white_wine_files/figure-markdown_github/unnamed-chunk-51-1.jpeg)

![](red_vs_white_wine_files/figure-markdown_github/unnamed-chunk-52-1.jpeg)

![](red_vs_white_wine_files/figure-markdown_github/unnamed-chunk-53-1.jpeg)

![](red_vs_white_wine_files/figure-markdown_github/unnamed-chunk-54-1.jpeg)

![](red_vs_white_wine_files/figure-markdown_github/unnamed-chunk-55-1.jpeg)

![](red_vs_white_wine_files/figure-markdown_github/unnamed-chunk-56-1.jpeg)

![](red_vs_white_wine_files/figure-markdown_github/unnamed-chunk-57-1.jpeg)

![](red_vs_white_wine_files/figure-markdown_github/unnamed-chunk-58-1.jpeg)

![](red_vs_white_wine_files/figure-markdown_github/unnamed-chunk-59-1.jpeg)

All of the scatterplots shown display fairly strong clustering of wine by color; the two classes are fairly well separated, but none are linearly separable. In most of the plots there are some white wines that are interspersed throughout the red wines, while red wines that are not within their own cluster do not extend too far into the white wine cluster. Unsurprisingly, the variables that show the best class separation in univariate plots also do so when combined with other variables in the bivariate plots. From these plots we can see that the interaction of some of the variables together could be very useful in a classification model.

Multivariate Plots and Analysis
-------------------------------

![](red_vs_white_wine_files/figure-markdown_github/unnamed-chunk-60-1.jpeg)

In the plots above we can see that white wines have a much greater variation in residual sugar as compared with red wines; there are only a few sweeter red wines in the data. We can also see that for white wines that the wines with less alcohol have more residual sugar. However, sugar does not vary as consistently with the total sulfur dioxide, The sweetest white wines have higher levels of sulfur dioxide, however sugar levels do not vary as consistently along total sulfur dioxide as they do along percent alcohol.

    ## [1] 66

The data was subsetted to trim the top 1% of data points according to residual sugar, since the outliers were not allowing the plot to show the full range of color.

![](red_vs_white_wine_files/figure-markdown_github/unnamed-chunk-62-1.jpeg)

The change in residual sugar is that much more striking according to density. The more dense the wine, the more residual sugar in it. Additionally we can see that only red wines with a density greater than 0.995 have higher levels of sugar.

![](red_vs_white_wine_files/figure-markdown_github/unnamed-chunk-63-1.jpeg)

White wines with greater total sulfur dioxide have greater densities, however most red wines have much lower levels of total sulfur dioxide, yet still attain high levels of density.

![](red_vs_white_wine_files/figure-markdown_github/unnamed-chunk-64-1.jpeg)

The strongest correlation between variables is between alcohol and density. We can also clearly see that white wines with the greatest density and percent alcohol have the highest levels of residual sugar. While this correlation is not as strong in red wines and residual sugar does not vary along alcohol and density as it does in whites, there is a small group of reds with low alcohol and high density that have a high amount of residual sugar.

Final Plots and Summary
-----------------------

![](red_vs_white_wine_files/figure-markdown_github/unnamed-chunk-65-1.jpeg)

Total sulfur dioxide shows the greatest separation of sulfur dioxide by class. We can clearly see that here is not a huge overlap between the colors and that white wines have a normal distribution and reds are skewed to the right. This plot indicates that this variable could be used successfully in a classification model based on color.

![](red_vs_white_wine_files/figure-markdown_github/unnamed-chunk-66-1.jpeg)

Although there are some red and white wines interspersed around clusters of the opposite color, the two classes show a distinct and clear separation with a fairly wide margin. This plot indicates that these two variables could be used successfully in a classification model based on color.

![](red_vs_white_wine_files/figure-markdown_github/unnamed-chunk-67-1.jpeg)

This plot shows that while density and alcohol alone are not enough to show a separation based on wine color, the addition of residual sugar would help to explain the differences in red and white wines.

Reflection
----------

I started by trying to understand each individual variable across red and white wines to see if it would be feasible to eventually create a classifier for color. Using the results of the univariate plots and the scatterplot matrix, I then explored two variables at a time to see if this would increase the distinction between red and white wines. Finally I investigated three variables at a time to see how they interact and separate the classes. I was pleasantly surprised that the red and white wines showed such clear clusters in many of the bivariate plots. I also explored the relationship between the chemical properties of the wine and quality, and unfortunately the relationships were not nearly as strong. Additionally, classifying based on quality or a rating class (e.g. 3-4 = poor, 5-6 = good, 7-9 = excellent) is a much more difficult task owing to the fact that good wines vastly outnumber poor and excellent wines

As aforementioned there are wines with with duplicate properties which could inflate measures of accuracy for any future classification models. Additionally, conclusions from these explorations and future classification tasks would be limited since the data set only contains a sample of Portuguese wines. It would be interesting to explore if these relationships held up when using a data set with wines from around the world.
