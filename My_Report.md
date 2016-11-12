# Wine Quality Exploration
Marinos Stathopoulos  



<br>
In this project, we used R to apply exploratory data analysis techniques to examine relationships in one variable, to multiple variables and explore a selected data set for distributions, outliers, and anomalies.The dataset contains red wine samples, where the inputs include objective tests (e.g. PH values) and the output is based on sensory data (median of at least 3 evaluations made by wine experts). Each expert graded the wine quality between 0 (very bad) and 10 (very excellent). Our goal is to explore this dataset for possible correlation of various input variables to the output variable of interest, wine quality. 
<br>
<br>

# 1. Dataset structure



### Dataset dimensions


```
## [1] 1599   13
```

### Dataset variables


```
##  [1] "X"                    "fixed.acidity"        "volatile.acidity"    
##  [4] "citric.acid"          "residual.sugar"       "chlorides"           
##  [7] "free.sulfur.dioxide"  "total.sulfur.dioxide" "density"             
## [10] "pH"                   "sulphates"            "alcohol"             
## [13] "quality"
```

### Feature types and samples


```
## 'data.frame':	1599 obs. of  13 variables:
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
```

### Feature summary stats


```
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
```

### Summary observations

*Fixed acidity:* minimum value 4.6 and maximum 15.9  
*Volatile acidity:* minimum value 0.12 and maximum 1.58  
*Citric acid:* minimum value 0 and maximum 1  
*Residual sugar:* minimum value 0.9 and maximum 15.5  
*Chlorides:* minimum value 0.01 and maximum 0.61  
*Free sulfur dioxide:* minimum value 1 and maximum 72  
*Total sulfur dioxide:* minimum value 6 and maximum 289  
*Density:* minimum value 0.99 and maximum 1  
*pH:* minimum value 2.7 and maximum 4  
*Sulphates:* minimum value 0.33 and maximum 2  
*Alcohol:* minimum value 8.4 and maximum 14.9  
*Quality:* minimum value is 3 and maximum is 8  

<br>


# 2. Univariate Plots Section

### Fixed acidity
(tartaric acid - g / dm^3)  
Most acids involved with wine or fixed or nonvolatile (do not evaporate readily).

![](Figs/Univariate_Plots-1.png)<!-- -->

```
##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
##    4.60    7.10    7.90    8.32    9.20   15.90
```
Fixed acidity is right-skewed, to high values, with a mean of 8.32 and a median of 7.9.
<br>



### Volatile acidity 
(acetic acid - g / dm^3)  
The amount of acetic acid in wine, which at too high of levels can lead to an unpleasant, vinegar taste.

![](Figs/unnamed-chunk-4-1.png)<!-- -->

```
##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
##  0.1200  0.3900  0.5200  0.5278  0.6400  1.5800
```
Volatile acidity is skewed to the right, with a clear mode around 0.6 and a another smaller peak (multimodal) around 0.4. It has a mean of 0.53 and a median of 0.52.
<br>

### Citric acid
(g / dm^3)  
Found in small quantities, citric acid can add 'freshness' and flavor to wines.

![](Figs/unnamed-chunk-5-1.png)<!-- -->

```
##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
##   0.000   0.090   0.260   0.271   0.420   1.000
```
Citric acid is right-skewed, with a clear mode in zero and a couple of smaller peaks to the right. The mean value is 0.27 and the median of 0.26.
<br>

### Residual sugar
(g / dm^3)  
The amount of sugar remaining after fermentation stops, it's rare to find wines with less than 1 gram/liter and wines with greater than 45 grams/liter are considered sweet.

![](Figs/unnamed-chunk-6-1.png)<!-- -->

```
##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
##   0.900   1.900   2.200   2.539   2.600  15.500
```
Residual sugar has a normal distribution with one peak at 2.2. It has a mean of 2.54 and a median of 2.2.
<br>

### Chlorides
(sodium chloride - g / dm^3)  
The amount of salt in the wine.

![](Figs/unnamed-chunk-7-1.png)<!-- -->

```
##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
## 0.01200 0.07000 0.07900 0.08747 0.09000 0.61100
```
Chlorides is skewed to the right, with a clear mode around 0.07. It has a mean of 0.087 and a median of 0.079.
<br>

### Free sulfur dioxide
(mg / dm^3)  
The free form of SO2 exists in equilibrium between molecular SO2 (as a dissolved gas) and bisulfite ion; it prevents microbial growth and the oxidation of wine.

![](Figs/unnamed-chunk-8-1.png)<!-- -->

```
##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
##    1.00    7.00   14.00   15.87   21.00   72.00
```
Free sulfur dioxide is skewed to the right, with a clear peak at 6. It has a mean of 15.9 and a median of 14.
<br>

### Total sulfur dioxide
(mg / dm^3)  
The amount of free and bound forms of S02; in low concentrations, SO2 is mostly undetectable in wine, but at free SO2 concentrations over 50 ppm, SO2 becomes evident in the nose and taste of wine.

![](Figs/unnamed-chunk-9-1.png)<!-- -->

```
##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
##    6.00   22.00   38.00   46.47   62.00  289.00
```
Total sulfur dioxide is clearly right-skewed, with a mode of 28, a mean of 46.5 and a median of 38.
<br>

### Density
(g / cm^3)  
The wine density is close to that of water depending on the percent alcohol and sugar content.

![](Figs/unnamed-chunk-10-1.png)<!-- -->

```
##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
##  0.9901  0.9956  0.9968  0.9967  0.9978  1.0040
```
Density has a normal single-peak distribution with all mode, mean and median at around 0,997.
<br>

### pH 
Describes how acidic or basic a wine is on a scale from 0 (very acidic) to 14 (very basic); most wines are between 3-4 on the pH scale.

![](Figs/unnamed-chunk-11-1.png)<!-- -->

```
##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
##   2.740   3.210   3.310   3.311   3.400   4.010
```
pH Total is also normally distributed, peaking at 3.3, with a mean of 3.1 and a median of 3.3.
<br>

### Sulphates
(potassium sulphate - g / dm3)  
A wine additive which can contribute to sulfur dioxide gas (S02) levels, which acts as an antimicrobial and antioxidant.

![](Figs/unnamed-chunk-12-1.png)<!-- -->

```
##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
##  0.3300  0.5500  0.6200  0.6581  0.7300  2.0000
```
Sulphates Total a slightly right-skewed distribution, with a peak close to 0.55, a mean of 0.66 and a median of 0.62.
<br>

### Alcohol
(% by volume)  
The percent alcohol content of the wine.

![](Figs/unnamed-chunk-13-1.png)<!-- -->

```
##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
##    8.40    9.50   10.20   10.42   11.10   14.90
```
Alcohol is clearly right-skewed, with a mode of 9.5, a mean of 10.4 and a median of 10.2.
<br>

###Quality 
(score between 0 and 10)  
Quality feature appears to have only 6 discrete values (3, 4, 5, 6, 7, 8).

![](Figs/unnamed-chunk-14-1.png)<!-- -->

```
##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
##   3.000   5.000   6.000   5.636   6.000   8.000
```
 Quality is quite normally distributed with a mode at 5, mean at 5.6 and median at 6.
<br>
  
## Univariate Analysis

<br>

#### What is the structure of your dataset?

There are 1599 red wine instances in the dataset, of the Portuguese "Vinho Verde" wine. In addition there are 12 different features with no missing Attribute Values:

1 - fixed acidity (tartaric acid - g / dm^3)  
2 - volatile acidity (acetic acid - g / dm^3)  
3 - citric acid (g / dm^3)  
4 - residual sugar (g / dm^3)  
5 - chlorides (sodium chloride - g / dm^3)  
6 - free sulfur dioxide (mg / dm^3)  
7 - total sulfur dioxide (mg / dm^3)  
8 - density (g / cm^3)  
9 - pH  
10 - sulphates (potassium sulphate - g / dm3)  
11 - alcohol (% by volume)  
12 - quality (score between 0 and 10)  

Most of the features are numerical except of 'X', which is an index, and “quality” which is categorical variable with only 6 discrete values.

<br>

#### What is/are the main feature(s) of interest in your dataset and what other features in the dataset will help support your investigation into your feature(s) of interest?

The feature of interest is the output variable "quality", thus we will examine which of the other input features might have a significant effect on it.

<br>

#### Did you create any new variables from existing variables in the dataset?

The outcome feature “quality” is converted to factor type with 6 discrete levels and the to a rating variable of three levels "bad"/"medium"/"good".

<br>

#### Of the features you investigated, were there any unusual distributions? Did you perform any operations on the data to tidy, adjust, or change the form of the data? If so, why did you do this?

Since the dataset is pretty well structured and there are no missing values, I only had to scale some of my variables to exclude outliers. 
  
<br>

# 3. Bivariate Plots Section

### Features correlation 
![](Figs/Bivariate_Plots-1.png)<!-- -->

<br>

Here we created a feature correlation plot in order to get a first sense on relations between our variables. Quality feature is our variable of interest and we don't notice any outstanding correlation with other variables. So lets further examine the correlation between input chemical variables and quality output, with the help of boxplots.



### Quality vs variables

![](Figs/unnamed-chunk-16-1.png)<!-- -->
<br>
<br>


Now we will examine the two variables, which correlate the strongest, to quality.  

### Quality vs alcohol

![](Figs/unnamed-chunk-17-1.png)<!-- -->

```
## factor(quality): 3
##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
##   8.400   9.725   9.925   9.955  10.580  11.000 
## -------------------------------------------------------- 
## factor(quality): 4
##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
##    9.00    9.60   10.00   10.27   11.00   13.10 
## -------------------------------------------------------- 
## factor(quality): 5
##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
##     8.5     9.4     9.7     9.9    10.2    14.9 
## -------------------------------------------------------- 
## factor(quality): 6
##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
##    8.40    9.80   10.50   10.63   11.30   14.00 
## -------------------------------------------------------- 
## factor(quality): 7
##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
##    9.20   10.80   11.50   11.47   12.10   14.00 
## -------------------------------------------------------- 
## factor(quality): 8
##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
##    9.80   11.32   12.15   12.09   12.88   14.00
```

### Quality vs volatile acidity

![](Figs/unnamed-chunk-18-1.png)<!-- -->

```
## factor(quality): 3
##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
##  0.4400  0.6475  0.8450  0.8845  1.0100  1.5800 
## -------------------------------------------------------- 
## factor(quality): 4
##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
##   0.230   0.530   0.670   0.694   0.870   1.130 
## -------------------------------------------------------- 
## factor(quality): 5
##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
##   0.180   0.460   0.580   0.577   0.670   1.330 
## -------------------------------------------------------- 
## factor(quality): 6
##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
##  0.1600  0.3800  0.4900  0.4975  0.6000  1.0400 
## -------------------------------------------------------- 
## factor(quality): 7
##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
##  0.1200  0.3000  0.3700  0.4039  0.4850  0.9150 
## -------------------------------------------------------- 
## factor(quality): 8
##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
##  0.2600  0.3350  0.3700  0.4233  0.4725  0.8500
```

<br>
Here we graphically presented the effect of Alcohol and Volatile acidity levels - the two strongest correlated to quality features- to the overall wine quality. As expected a positive correlation was noticed for Alcohol, meaning that higher levels of alcohol results better quality wines. Moreover we noticed a clear negative correlation of quality and volatile acidity.

Now in order to examine secondary "quality" correlations -strong correlations of "alcohol" and "volatile acidity" with the rest of the variables - lets draw the two most significant secondary relations, with the help of scatter plots and the addition of a smoothed conditional mean (blue line).

### Alcohol vs density

![](Figs/unnamed-chunk-19-1.png)<!-- -->

### Volatile acidity vs citric acid

![](Figs/unnamed-chunk-20-1.png)<!-- -->

<br>

Moreover, lets examine for 3rd degree "quality" correlations, meaning strong correlations of 2nd degree features "density" and "citric acid", with the strongest related  among the rest of the input variables, pH and fixed acidity.

### Density vs fixed acidity

![](Figs/unnamed-chunk-21-1.png)<!-- -->

### Citric acid vs fixed acidity

![](Figs/unnamed-chunk-22-1.png)<!-- -->

### Citric acid vs pH

![](Figs/unnamed-chunk-23-1.png)<!-- -->
In those two set of scatter plots, we have visually confirmed what was already expected from th Pearson's r values, concerning the 2nd and 3rd degree positive and negative relations between features.
<br>

# Bivariate Analysis

<br>

#### Talk about some of the relationships you observed in this part of the investigation. How did the feature(s) of interest vary with other features in the dataset?

To begin our exploration on how variables correlate with each other we first used correlation matrix and table to get a sense of the variables relations. As mentioned earlier, quality the main feature of interest, surprisingly did not present really strong correlation to any of the input features. In this context, box plots were used to examine the quality's strongest relations: Alcohol (0.48) and Volatile acidity (-0.39). Quality and alcohol presented a clear positive relationship, while quality and Volatile acidity had an inverse, negative relation.

<br>

#### Did you observe any interesting relationships between the other features (not the main feature(s) of interest)?

After investigating quality's relations with other features in the dataset (Volatile acidity & Alcohol), we examined 2nd and 3rd degree correlations of those, with the rest of the variables. During this process, we observed the following significant correlations with the respective Pearson's r values:

**1st Degree Correlations**  
- Quality vs Alcohol (0.48)   
- Quality vs Volatile acidity (-0.39)  
**2nd Degree Correlations**  
- Alcohol vs Density (-0.5)  
- Volatile acidity vs citric acid (-0.55)  
**3rd Degree Correlations**  
- Density vs fixed.acidity (0.67)  
- Citric acid vs pH (-0.54)  


<br>

#### What was the strongest relationship you found?

The strongest relationships observed within the dataset variables, were A) a negative one between **fixed acidity** and **ph** with Pearson’s r equal to 0.668 and B) a positive one between **fixed acidity** and **density** with Pearson’s r equal to -0.683.

<br>

# 4. Multivariate Plots Section

<br>
Following, in this section we will run a multivariate analysis of all features within the three degrees of correlation. We will achieve this by plotting those variables like in the previous section, only this time we will add a third variable to our plots, “rating”. We will try this in order to get a better and more complete sense, of input features and the overall effect on the wines quality. Our choice of color scheme, was made so that the ordering of categories is more intuitive, so as to help us better explore the presented relations.

As mentioned earlier a “rating” variable was created, which is a classification of quality, as follows:
Quality level equal to 3-4, corresponds to bad rating.
Quality level equal to 5-6, corresponds to medium rating.
Quality level equal to 7-8, corresponds to good rating. Moving on to the plotting section, we group two  scater plot variations for each relation examined as follows:
<br>

### 1st Degree correlations  


#### Alcohol vs Volatile acidity vs Quality  

![](Figs/Multivariate_Plots-1.png)<!-- -->
First we present alcohol and volatile acidity the two 1st degree correlation variables, colored by rating. We notice how good quality wines mainly present higher levels of alcohol and lower levels of volatile acidity concentration, bad quality wines the opposite. And as expected medium quality wines, which are the most frequent case, spread along middle values within a relatively extended range.

<br>

### 2nd Degree correlations  

#### Density vs Alcohol vs Quality  

![](Figs/unnamed-chunk-25-1.png)<!-- -->
Here is the first out of two, 2nd degree correlation pair variables, density and alcohol, again colored by rating. We notice how good quality wines have a positive correlation with both features, since they occupy the high alcohol/high density areas. On the other hand, bad quality wines lie on medium-low alcohol and density areas.

<br>

#### Citric acid vs Volatile acidity vs Quality  

![](Figs/unnamed-chunk-26-1.png)<!-- -->


In this second set of plots, we examine how citric acid and volatile acidity relate with each other, together with wine rating. Here we see that the majority of good quality wines have low volatile acidity and medium to high citric acid. However we notice a second smaller group of good quality wines, lying write in the opposite direction. Again medium quality wines cover the space in between.  
<br>

### 3rd Degree correlations  

#### Density vs Fixed acidity vs Quality  

![](Figs/unnamed-chunk-27-1.png)<!-- -->
In this first of two, 3rd degree of correlation set of plots, we plot density against fixed acidity colored by rating. First of all we can see a clear positive correlation between the two examined features. In addition we notice here, that all three quality rating groups seem to occupy more or less the same medium density and fixed acidity area, with good quality wines area shifted to a relatively higher fixed acidity range.  

<br>

#### Citric acid vs pH vs Quality  

![](Figs/unnamed-chunk-28-1.png)<!-- -->
In this final set of plots, we explore citric acid against pH, again colored by rating. Here there is a clear separation of good and bad quality wine: most of the bad wines lie in low citric acid and medium high pH areas, while good wines lie in high citric acid and relatively medium to low pH. Again in both good and bad ratings we notice small groups of observation following a relatively different pattern. 

<br>

## Multivariate Analysis

<br>

#### Talk about some of the relationships you observed in this part of the investigation.

In this section we have used a set of scater plots to graphically demonstrate the relations of 1st, 2nd and 3rd degree related variables (Citric Acid vs Volatile Acidity, Density vs Alcohol, Citric acid vs Volatile acidity, Density vs Fixed acidity, Fixed acidity vs Citric acid & Citric acid vs pH), using classified quality ("rating") as a third plot variable in the form of color. 

By looking at this set of plots we have visually verified positive and negative feature correlation, previously gotten in numerical form of Pearson's r values. More specifically we have came to the following outcome: The majority of good quality wines have high values of alcohol, low  volatile acidity, medium-low density, medium-high citric acid, medium fixed acidity and finally medium-low pH.

<br>

# 5. Final Plots and Summary

### Plot One
![](Figs/Plot_One-1.png)<!-- -->

### Description One

We used boxplots to graphically demonstrate the effect of Alcohol levels to the overall wine quality, and as expected a positive correlation was noticed, indicating that higher levels of alcohol results better quality wines.  

<br>

### Plot Two
![](Figs/Plot_Two-1.png)<!-- -->

```
## 
## 	Pearson's product-moment correlation
## 
## data:  wines$density and wines$alcohol
## t = -22.838, df = 1597, p-value < 2.2e-16
## alternative hypothesis: true correlation is not equal to 0
## 95 percent confidence interval:
##  -0.5322547 -0.4583061
## sample estimates:
##        cor 
## -0.4961798
```

### Description Two
We used scater plot and added a smoothed conditional mean, to graphically demonstrate the relation of Alcohol and Density, and as expected from the Pearson’s r equal to -0.496, a significant negative correlation was noticed, indicating that higher levels of density results lower levels of Alcohol, which in turn results worse quality wines.  

<br>

### Plot Three
![](Figs/Plot_Three-1.png)<!-- -->

```
## 
## 	Pearson's product-moment correlation
## 
## data:  wines$citric.acid and wines$volatile.acidity
## t = -26.489, df = 1597, p-value < 2.2e-16
## alternative hypothesis: true correlation is not equal to 0
## 95 percent confidence interval:
##  -0.5856550 -0.5174902
## sample estimates:
##        cor 
## -0.5524957
```

### Description Three

Here we have used a scater plot to graphically demonstrate the relation of Citric Acid and Volatile Acidity, using classified quality ("rating") as a third plot variable in the form of color. By looking at the plot we can easily notice the negative correlation between Citric Acid and Volatile Acidity, with Pearson's r value equal to -0.5525 . Here we see how the three colored areas, which correspond to bad, medium and good quality wines, are correlated to x and y variables. In other words how high levels of Citric Acid and low of Volatile Acidity result better quality wines and the opposite, which was expected from the respective correlation values (0.2264 and -0.3906) presented earlier.  

<br>

# 6. Reflection
In this challenging project I had the opportunity to develop and apply my exploratory data analysis skills, in order to analyse a well structured Portuguese "Vinho Verde" red wine dataset. The dataset consisted of 1599 instances and 12 features. Our main objective was to find strong correlation within the various features and ultimately determine their effect in overall wine quality. After using graphical and numerical analysis, we determined first, second and third degree feature correlations, and the extent they affect our feature of interest. As a next task, it would be interesting to examine whether applying machine learning in our dataset, could provide an accurate prediction of a wine's quality, based on given features.   

Throughout the analysis process, I have struggled a bit switching from python to R, a rather not traditional programming language. But soon, while getting more and more familiar with it, I enjoyed exploring and implementing the R's amazing statistical potential, both graphical and numerical, for eda purposes. Overall, learning R - a statistically oriented programming language with great functionality, libraries and amazing data visualization capacity - was a challenging but very rewarding journey and I look forward for the next project.

<br>
<br>

