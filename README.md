
# Problems statement
1. analyze the differences in Market Rents across
various years.



Solutions
1. analyze the differences in Market Rents across
various years.
Tasks: 
Pairwise comparisons across years.
 Pairing the data help control for differences across Housing Units.
 Merge all five data files using the CONTROL variable.
 Keep only those housing units that have data on FMR for all five
years.

## Analysis Process
Import data
the data is downloaded from “Housing Affordability Data System” of the U.S. Department of
Housing and Urban Development. [HADS] : 'https://www.huduser.gov/portal/datasets/hads/hads.html' for years 2005, 2007, 2009, 20011 and 2013.

 Housing-level variables include,
̶ Number of rooms in the housing unit.
̶ The year it was built.
̶ Occupied or vacant, Rented or Owned
̶ Single family or multi-family structure.
̶ Number of units in the building.
̶ Market value, Housing costs.
̶ Number of people living, Household income.
̶ Type of residential area.
 Data made available every two years. 

Data preprocessing
- Reduce number of variables 
# List of Variables in the Data to be used in Capstone

| **Variable Name** | **Type** | **Explanation** |
|-------------------|----------|-----------------|
| **CONTROL** | Character String | A control variable for Housing Unit. Useful to match data across datasets from different years. |
| **AGE1** | Numerical | Age of head of household. |
| **METRO3** | Character (‘1’, ‘2’, ‘3’, ‘4’, or ‘5’) | Metropolitan status: <br> ‘1’ : Central City <br> ‘2’, ‘3’, ‘4’, ‘5’ : Others. |
| **REGION** | Character (‘1’, ‘2’, ‘3’, or ‘4’) | The four census regions—Northeast, Midwest, South, and West. |
| **LMED** | Numerical ($) | Area Median Income. |
| **FMR** | Numerical ($) | Fair Market Monthly Rent. |
| **IPOV** | Numerical ($) | Poverty Income threshold. |
| **BEDRMS** | Numerical | Number of Bedrooms in the unit. |
| **BUILT** | Numerical | Year the unit was built. |
| **STATUS** | Character (‘1’, ‘3’) | Occupied or Vacant. |
| **TYPE** | Numerical | Structure Type: <br> 1 - House, apartment, flat <br> 2 - Mobile home with no permanent room added <br> 3 - Mobile home with permanent room added <br> 4 - HU, in nontransient hotel, motel, etc <br> 5 - HU, in permanent transient hotel, motel, etc <br> 6 - HU, in rooming house <br> 7 - Boat or recreation vehicle <br> 9 - HU, not specified above. |
| **VALUE** | Numerical ($) | Current market value of unit. |
| **NUNITS** | Numerical | Number of Units in Building. |
| **ROOMS** | Numerical | Number of rooms in the unit. |
| **PER** | Numerical | Number of persons in Household. |
| **ZINC2** | Numerical ($) | Annual Household income. |
| **ZADEQ** | Character | Adequacy of unit: <br> ‘1’ - Adequate <br> ‘2’ - Moderately Inadequate <br> ‘3’ - Severely Inadequate <br> ‘-6’ - Vacant - No information. |
| **ZSMHC** | Numerical ($) | Monthly housing costs. For renters, housing cost is contract rent plus utility costs. For Owners, mortgage is not included. |
| **STRUCTURETYPE** | Numerical | Structure Type: <br> 1 - Single Family <br> 2 - 2-4 units <br> 3 - 5-19 units <br> 4 - 20-49 units <br> 5 - 50+ units <br> 6 - Mobile Home <br> -9 - Not Known. |
| **OWNRENT** | Character (‘1’, ‘2’) | ‘1’ - Owner: Owner occupied, vacant for sale, and sold but not occupied. <br> ‘2’ - Rental: Occupied units rented for cash and without payment of cash rent. Vacant for rent, vacant for rent or sale, and rented but not occupied. |
| **UTILITY** | Numerical ($) | Monthly utilities cost (gas, oil, electricity, other fuel, trash collection, and water). |
| **OTHERCOST** | Numerical ($) | Sum of ‘other monthly costs’ such as Home owners’ or renters’ insurance, Land rent (where distinct from unit rent), Condominium fees (where applicable), Other mobile home fees (where applicable). |
| **COST06** | Numerical ($) | Monthly mortgage payments assuming 6% interest. This applies only to “Owners”. |
| **COST08** | Numerical ($) | Monthly mortgage payments assuming 8% interest. This applies only to “Owners”. |
| **COST12** | Numerical ($) | Monthly mortgage payments assuming 12% interest. This applies only to “Owners”. |
| **COSTMED** | Numerical ($) | Monthly mortgage payments assuming median interest. This applies only to “Owners”. |
| **ASSISTED** | Numerical | Did the housing unit receive some governmental ‘assistance’? <br> 0 - Not assisted <br> 1 - Assisted <br> -9 - Not Known. |
Data Cleaning
- Data Errors: Remove values that is negative or value that very small below $1000
Housing units do the data files for the year 2005, 2007, 2009, 2011 and 2013 contain afteing delete housing units that have a market value of less than 1000 are 30514,27785,
31317, 85050 and 36675 respectively .   

Data Analysis
1. Differences in market values between occupied and vacant housing units
Using Descriptive Statistics tool in Excel to assess the five datasets to evaluate the difference in values across years.
housing units are “Occupied” versus “not occupied”
across various years?

Number of housing that  are occcupied and vacant across years.

2005:  29440 Vs 1074

2007:  26466 Vs 1319

2009:  30081 Vs 1236

2011:  82078 Vs 2972

2013: 35418 Vs 1257

Investigate whether there is a difference in market values of occupied versus not occupied housing units across various years using a difference in means hypothesis test across the two sets of values (occupied versus unoccupied). 

Hypothesis testing: 
H0: µOccupied - µNot-Occupied =  0
HA: µOccupied - µNot-Occupied ≠  0   

Example for year 2005:
### Analysis of Market Values for Occupied vs. Vacant Housing Units (2005-2013)

#### Descriptive Statistics

| **Statistic**       | **Occupied Housing Units**  | **Vacant Housing Units**  |
|---------------------|-----------------------------|---------------------------|
| **Mean**            | 248,606.39                  | 239,377.81                |
| **Standard Error**  | 1,858.24                    | 11,268.02                 |
| **Median**          | 160,000                     | 155,500                   |
| **Mode**            | 200,000                     | 1,540,794                 |
| **Standard Deviation** | 279,310.94               | 264,738.45                |
| **Sample Variance** | 78,014,599,887              | 70,086,448,330            |
| **Kurtosis**        | 11.17                       | 12.52                     |
| **Skewness**        | 3.10                        | 3.20                      |
| **Range**           | 1,539,794                   | 1,538,294                 |
| **Minimum**         | 1,000                       | 2,500                     |
| **Maximum**         | 1,540,794                   | 1,540,794                 |
| **Sum**             | 5,616,764,132               | 132,136,553               |
| **Count**           | 22,593                       | 552                       |

#### T-Test: Two-Sample Assuming Equal Variances

| **Statistic**         | **Value**             |
|-----------------------|-----------------------|
| **Hypothesized Mean Difference** | 0 |
| **Pooled Variance**   | 77,825,842,531        |
| **Degrees of Freedom (df)** | 23,143              |
| **t Stat**            | 0.77                  |
| **t Critical (one-tail)** | 1.645             |
| **t Critical (two-tail)** | 1.960             |
| **P(T<=t) one-tail**  | 0.221                 |
| **P(T<=t) two-tail**  | 0.443                 |

#### Conclusion

- The **mean market value** for occupied units (248,606.39) is slightly higher than the mean for vacant units (239,377.81). 
- The **standard deviation** for occupied units is slightly larger (279,310.94 vs. 264,738.45), indicating greater variation in the market values of occupied housing units.
- The **skewness** and **kurtosis** suggest that both distributions are right-skewed and have high peakedness, particularly in the case of vacant units.

#### T-Test Results

- The **t-statistic** is 0.77, which is smaller than the **critical value** of 1.96 for a two-tailed test, thus I do not reject the null hypothesis that the occupied housing value greater than vacant housing value.

2. Fair market rent off Housing units

Here is the markdown text for your example using VLOOKUP to combine FMK across years:

### Example of 10 Rows Using VLOOKUP to Combine FMK Across Years

| Year/FMR   | FMR_2005 | FMR_2007 | FMR_2009 | FMR_2011 | FMR_2013 |
|------------|----------|----------|----------|----------|----------|
| Row 1      | 519      | 616      | 685      | 711      | 737      |
| Row 2      | 600      | 605      | 670      | 673      | 657      |
| Row 3      | 788      | 807      | 897      | 935      | 988      |
| Row 4      | 702      | 778      | 743      | 796      | 773      |
| Row 5      | 546      | 599      | 503      | 531      | 552      |
| Row 6      | 680      | 757      | 861      | 895      | 949      |
| Row 7      | 1081     | 956      | 1037     | 1107     | 1239     |
| Row 8      | 1006     | 1097     | 1156     | 1235     | 1277     |
| Row 9      | 916      | 900      | 890      | 923      | 993      |
| Row 10     | 862      | 930      | 973      | 752      | 794      |

#### Formula to Combine FMK Values for Row 1:
```
=VLOOKUP($A2, thads2005!$A:$G, 7, FALSE)
```
This formula combines the FMK values for each year using VLOOKUP, where `$A2` refers to the row identifier for each year, and `thads2005!$A:$G` is the data range in the 2005 sheet.
```

### FMR Data Summary by Year

| **Statistic**       | **2005**   | **2007**   | **2009**   | **2011**   | **2013**   |
|---------------------|------------|------------|------------|------------|------------|
| **Mean**            | 929.04     | 977.77     | 1063.87    | 1116.38    | 1151.57    |
| **Standard Error**  | 2.04       | 2.08       | 2.26       | 2.44       | 2.43       |
| **Median**          | 863        | 908        | 983        | 1014       | 1082       |
| **Mode**            | 679        | 738        | 941        | 966        | 1032       |
| **Standard Deviation** | 331.02    | 337.06     | 367.36     | 396.70     | 394.26     |
| **Sample Variance** | 109572.68  | 113606.38  | 134955.84  | 157373.27  | 155443.11  |
| **Kurtosis**        | 2.99       | 2.44       | 2.31       | 2.07       | 1.75       |
| **Skewness**        | 1.42       | 1.35       | 1.30       | 1.30       | 1.16       |
| **Range**           | 3104       | 3013       | 3074       | 3162       | 3090       |
| **Minimum**         | 360        | 387        | 427        | 424        | 421        |
| **Maximum**         | 3464       | 3400       | 3501       | 3586       | 3511       |
| **Sum**             | 24,501,566 | 25,786,724 | 28,057,338 | 29,442,330 | 30,370,333 |
| **Count**           | 26,373     | 26,373     | 26,373     | 26,373     | 26,373     |

This table summarizes the key statistics for the FMR (Fair Market Rent) data from 2005 to 2013.
### Paired t-Test Results: FMR Comparison Between Years
 Null hypothesis for this analysis as follow:
  H0: FMR2007 - FMR2005 ≥  0 
  H0: FMR2009 - FMR2007 ≥  0 
    H0: FMR2011 - FMR2009 ≥  0 
    H0: FMR2013 - FMR2011 ≥  0 

#### 1. **2009 vs 2007 FMR Comparison**

| **Statistic**                | **FMR 2009**        | **FMR 2007**        |
|------------------------------|---------------------|---------------------|
| **Mean**                     | 1063.87             | 977.77              |
| **Variance**                 | 134,955.84          | 113,606.38          |
| **Observations**             | 26,373              | 26,373              |
| **Pearson Correlation**      | 0.9526              |                     |
| **Hypothesized Mean Difference** | 0               |                     |
| **Degrees of Freedom (df)** | 26,372              |                     |
| **t Stat**                   | 124.32              |                     |
| **p-value (one-tail)**       | 0                   |                     |
| **t Critical (one-tail)**    | 1.645               |                     |
| **p-value (two-tail)**       | 0                   |                     |
| **t Critical (two-tail)**    | 1.960               |                     |

#### 2. **2013 vs 2011 FMR Comparison**

| **Statistic**                | **FMR 2013**        | **FMR 2011**        |
|------------------------------|---------------------|---------------------|
| **Mean**                     | 1151.57             | 1116.38             |
| **Variance**                 | 155,443.11          | 157,373.27          |
| **Observations**             | 26,373              | 26,373              |
| **Pearson Correlation**      | 0.9692              |                     |
| **Hypothesized Mean Difference** | 0               |                     |
| **Degrees of Freedom (df)** | 26,372              |                     |
| **t Stat**                   | 58.21               |                     |
| **p-value (one-tail)**       | 0                   |                     |
| **t Critical (one-tail)**    | 1.645               |                     |
| **p-value (two-tail)**       | 0                   |                     |
| **t Critical (two-tail)**    | 1.960               |                     |

#### 3. **2007 vs 2005 FMR Comparison**

| **Statistic**                | **FMR 2007**        | **FMR 2005**        |
|------------------------------|---------------------|---------------------|
| **Mean**                     | 977.77              | 929.04              |
| **Variance**                 | 113,606.38          | 109,572.68          |
| **Observations**             | 26,373              | 26,373              |
| **Pearson Correlation**      | 0.9420              |                     |
| **Hypothesized Mean Difference** | 0               |                     |
| **Degrees of Freedom (df)** | 26,372              |                     |
| **t Stat**                   | 69.49               |                     |
| **p-value (one-tail)**       | 0                   |                     |
| **t Critical (one-tail)**    | 1.645               |                     |
| **p-value (two-tail)**       | 0                   |                     |
| **t Critical (two-tail)**    | 1.960               |                     |

#### 4. **2011 vs 2009 FMR Comparison**

| **Statistic**                | **FMR 2011**        | **FMR 2009**        |
|------------------------------|---------------------|---------------------|
| **Mean**                     | 1116.38             | 1063.87             |
| **Variance**                 | 157,373.27          | 134,955.84          |
| **Observations**             | 26,373              | 26,373              |
| **Pearson Correlation**      | 0.9576              |                     |
| **Hypothesized Mean Difference** | 0               |                     |
| **Degrees of Freedom (df)** | 26,372              |                     |
| **t Stat**                   | 74.15               |                     |
| **p-value (one-tail)**       | 0                   |                     |
| **t Critical (one-tail)**    | 1.645               |                     |
| **p-value (two-tail)**       | 0                   |                     |
| **t Critical (two-tail)**    | 1.960               |                     |

### Summary of Results

- **t-Statistic**: In all comparisons, the t-statistics are much higher than the critical values, indicating that the differences between the FMR values for each pair of years are statistically significant.
  
- **p-values**: All p-values (both one-tailed and two-tailed) are 0, which is far below the usual significance threshold of 0.05, confirming that there are significant differences in FMR values between the compared years.

### Conclusion

Based on the analysis, the fair market rent of housing units increased every year.

3. Regression for current market values 

4. Regression for future market values
Data Preprocessing: Choose only the ‘Single Family Units’, that is,
STRUCTURETYPE = 1 and TYPE = 1 and delete all data on housing units which are rental
units, OWNRENT = ‘2’

After data preprocessing:
 Calculate various descriptive statistics for the VALUE variable.
 Visualize the empirical distribution of VALUE.
 Plot a histogram of VALUE.
 Plot a histogram of Ln(VALUE).
Which of these two histograms more closely resemble a Bell curve?
 Select your set of independent variables or the X variables. 

REGRESSION equation: LN(VALUE)=β0​+β1​⋅Northeast+β2​⋅Midwest+β3​⋅South+β4​⋅LN(LMED)+β5​⋅LN(FMR)+β6​⋅LN(IPOV)+β7​⋅BEDRMS+β8​⋅BUILT+β9​⋅ROOMS+β10​⋅PER+β11​⋅LN(ZINC2)+β12​⋅ADEQUATE+β13​⋅LN(ZSMHC)+β14​⋅LN(UTILITY)+β15​⋅LN(OTHERCOST)
Note: 'Metro' is a dummy variable = 1 when METRO3 variable is = '1', otherwise it is =0
Note: 'Northeast', Midwest' and 'South' are dummy variables for the categorical variable REGION
Note: 'Adequate' is a dummy variable =1 when the categorical variable ZADEQ is ='1', otherwise it is =0
Note: This regression also takes a logarithmic transformation of many of the 'X' variables

### Histogram distribution of VALUE itself and LN(VALUES)

![alt text](image.png)

### SUMMARY OUTPUT

#### Regression Statistics
| Statistic                | Value         |
|--------------------------|---------------|
| Multiple R               | 0.739126834   |
| R Square                 | 0.546308476   |
| Adjusted R Square        | 0.546091094   |
| Standard Error           | 0.546111552   |
| Observations             | 31322         |

#### ANOVA
| df      | SS          | MS           | F         | Significance F |
|---------|-------------|--------------|-----------|----------------|
| Regression | 15          | 11242.62128  | 749.5080852  | 2513.122134   | 0              |
| Residual   | 31306       | 9336.633423  | 0.298237827  |               |                |
| Total      | 31321       | 20579.2547   |            |                |                |

#### Coefficients
| Coefficients           | Standard Error | t Stat       | P-value      | Lower 95%     | Upper 95%     | Lower 95.0%   | Upper 95.0%   |
|------------------------|----------------|--------------|--------------|---------------|---------------|---------------|---------------|
| Intercept              | 6.010642734    | 0.617554441  | 9.732976295  | 2.34639E-22   | 4.800211474   | 7.221073995   | 4.800211474   | 7.221073995   |
| β1 Northeast           | -0.133762682   | 0.011527675  | -11.60361288 | 4.57367E-31   | -0.156357384  | -0.11116798   | -0.156357384  | -0.11116798   |
| β2 Midwest             | -0.328831091   | 0.012172633  | -27.01396633 | 6.7504E-159  | -0.352689936  | -0.304972247  | -0.352689936  | -0.304972247  |
| β3 South               | -0.24279864    | 0.0106267    | -22.84798055 | 1.3279E-114  | -0.263627395  | -0.221969885  | -0.263627395  | -0.221969885  |
| β4 LN(LMED)            | 0.209763729    | 0.03182014   | 6.592168618  | 4.4033E-11   | 0.147394989   | 0.272132469   | 0.147394989   | 0.272132469   |
| β5 LN(FMR)             | 0.576059147    | 0.022911707  | 25.14256759  | 4.0121E-138  | 0.53115129    | 0.620967004   | 0.53115129    | 0.620967004   |
| β6 Ln(IPOV)            | -0.918815772   | 0.054380469  | -16.89606199 | 9.22629E-64  | -1.025403653  | -0.812227891  | -1.025403653  | -0.812227891  |
| β7 BEDRMS              | -0.055792729   | 0.006811251  | -8.191260367 | 2.68239E-16  | -0.069143052  | -0.042442407  | -0.069143052  | -0.042442407  |
| β8 BUILT               | 0.002161552    | 0.000127154  | 16.99945099  | 1.61571E-64  | 0.001912324   | 0.002410779   | 0.001912324   | 0.002410779   |
| β9 ROOMS               | 0.10242138     | 0.0029667    | 34.52367613  | 2.3037E-256  | 0.09660653    | 0.108236229   | 0.09660653    | 0.108236229   |
| β10 PER                | 0.136000692    | 0.011350106  | 11.98232823  | 5.19418E-33  | 0.113754034   | 0.158247351   | 0.113754034   | 0.158247351   |
| β11 LN(ZINC2)          | 0.094231184    | 0.00349148   | 26.98889779  | 1.3092E-158  | 0.087387745   | 0.101074623   | 0.087387745   | 0.101074623   |
| β12 ADEQUATE           | 0.125479543    | 0.019416195  | 6.462622706  | 1.04415E-10  | 0.087423028   | 0.163536057   | 0.087423028   | 0.163536057   |
| β13 LN(ZSMHC)          | 0.315841336    | 0.005822253  | 54.24726903  | 0            | 0.304429488   | 0.327253184   | 0.304429488   | 0.327253184   |
| β14 LN(UTILITY)        | -0.03173778    | 0.007476926  | -4.244763433 | 2.19454E-5   | -0.046392852  | -0.017082709  | -0.046392852  | -0.017082709  |
| β15 LN(OTHERCOST)      | 0.130820037    | 0.00304902   | 42.90560797  | 0            | 0.124843837   | 0.136796237   | 0.124843837   | 0.136796237   |

Summary Report

A Regression Model for the Market Value of Housing Units (using data for Year 2013).
Main points to be covered in the summary...
a.  We use the model that gives the best R-Square
b.  Note that the 'Y' variable has a natural logarithm taken and also some of the 'X' variables have a natural logarithm taken. So the interpretations will be either semi-log or the log-log interpretations.
c.  All p-values are below .05, indicating that all coefficients are statistically significant.

Interpretation of coefficients
- β0: No managerially relevant interpretation, since talking about a situation when all 'X' variables are zero does not make managerial sense.
- β1, β2: β3: When the housing unit is in the Northeast, Midwest, South region of the country, then the market value tends to be lower by 13.37%, 32.89%, 24.28% respectively as compared to a similar housing unit being in the West region, all other variables being kept at the same level.  
- β4: For every one percentage increase in the area median income, the market value increases by 0.21%, all other variables remaining at the same level.
- β5: For every one percentage increase in the fair market rent, the market value increases by 0.58%, all other variables remaining at the same level.
- β6: For every one percentage increase in the poverty income threshold, the market value decreases by 0.92%, all other variables remaining at the same level.
- β7: Every additional bedroom corresponds to a 5.58% decrease in the market value of the housing unit, all other variables being kept at the same level.
- β8: Every one year delay in the 'Year Built' of the housing unit, there is a 0.22% increase in the market value of the housing unit, all other variables being kept at the same level.
- β9: One additional room corresponds to a 10.24% increase in the market value of the housing unit, all other variables being kept at the same level.
- β10: Every additional person in the household corresponds to a 13.6% increase in the market value of the housing unit, all other variables being kept at the same level.
- β11: For every one percentage increase in the annual household income, the market value increases by 0.09%, all other variables remaining at the same level.
- β12: When the housing unit is classified as 'Adequate' as compared to other adequacy categorizations, then the market value tends to be higher by 12.55%, all other variables being kept at the same level.  
- β13:  For every one percentage increase in the monthly monthly costs, the market value increases by 0.32%, all other variables remaining at the same level.
- β14: For every one percentage increase in the monthly utility costs, the market value decreases by 0.03%, all other variables remaining at the same level.
- β15: For every one percentage increase in the monthly 'other' costs, the market value increases by 0.13%, all other variables remaining at the same level.

Interpretation of R-square
The R-square and adjusted R-square are about 0.55, indicating that the model explains about 55 percentage of variation in the market value of housing units.
 
Discussion of contributing factors for the Market value of Housing Units

The results emphasize the multifaceted nature of housing market values, where economic factors (income, rent, poverty) and physical characteristics of the property (size, rooms, year built) all play a critical role in determining market prices.

4. A Regression Model to predict the Market Value of Housing Units in Year 2013.

 Use the lag of X variables.
 Estimate a regression model using the 2013 VALUE variable and
the X variables from the 2011 data. Merge the VALUE variable from 2013 data into the 2011 data.
 (VLOOKUP command using the CONTROL variable to match the data files) 
![alt text](image-1.png)

 This will allow predictions about future market value of housing units


mean absolute deviation equation:
![alt text](image-2.png)

### REGRESSION 2: 
**Model**:  
LN(VALUE) = β0 + β1⋅Northeast + β2⋅Midwest + β3⋅South + β4⋅LN(LMED) + β5⋅LN(FMR) + β6⋅LN(IPOV) + β7⋅BEDRMS + β8⋅BUILT + β9⋅ROOMS + β10⋅PER + β11⋅LN(ZINC2) + β12⋅ADEQUATE + β13⋅LN(ZSMHC) + β14⋅LN(UTILITY) + β15⋅LN(OTHERCOST)

**Notes**:  
- 'Metro' is a dummy variable = 1 when METRO3 variable is = '1', otherwise it is = 0.  
- 'Northeast', 'Midwest', and 'South' are dummy variables for the categorical variable REGION.  
- 'Adequate' is a dummy variable = 1 when the categorical variable ZADEQ is = '1', otherwise it is = 0.  
- This regression also takes a logarithmic transformation of many of the 'X' variables.

### SUMMARY OUTPUT

#### Regression Statistics
| Statistic                | Value         |
|--------------------------|---------------|
| Multiple R               | 0.739126834   |
| R Square                 | 0.546308476   |
| Adjusted R Square        | 0.546091094   |
| Standard Error           | 0.546111552   |
| Observations             | 31322         |

#### ANOVA
| df      | SS          | MS           | F         | Significance F |
|---------|-------------|--------------|-----------|----------------|
| Regression | 15          | 11242.62128  | 749.5080852  | 2513.122134   | 0              |
| Residual   | 31306       | 9336.633423  | 0.298237827  |               |                |
| Total      | 31321       | 20579.2547   |            |                |                |

#### Coefficients
| Coefficients           | Standard Error | t Stat       | P-value      | Lower 95%     | Upper 95%     | Lower 95.0%   | Upper 95.0%   |
|------------------------|----------------|--------------|--------------|---------------|---------------|---------------|---------------|
| Intercept              | 6.010642734    | 0.617554441  | 9.732976295  | 2.34639E-22   | 4.800211474   | 7.221073995   | 4.800211474   | 7.221073995   |
| β1 Northeast           | -0.133762682   | 0.011527675  | -11.60361288 | 4.57367E-31   | -0.156357384  | -0.11116798   | -0.156357384  | -0.11116798   |
| β2 Midwest             | -0.328831091   | 0.012172633  | -27.01396633 | 6.7504E-159  | -0.352689936  | -0.304972247  | -0.352689936  | -0.304972247  |
| β3 South               | -0.24279864    | 0.0106267    | -22.84798055 | 1.3279E-114  | -0.263627395  | -0.221969885  | -0.263627395  | -0.221969885  |
| β4 LN(LMED)            | 0.209763729    | 0.03182014   | 6.592168618  | 4.4033E-11   | 0.147394989   | 0.272132469   | 0.147394989   | 0.272132469   |
| β5 LN(FMR)             | 0.576059147    | 0.022911707  | 25.14256759  | 4.0121E-138  | 0.53115129    | 0.620967004   | 0.53115129    | 0.620967004   |
| β6 Ln(IPOV)            | -0.918815772   | 0.054380469  | -16.89606199 | 9.22629E-64  | -1.025403653  | -0.812227891  | -1.025403653  | -0.812227891  |
| β7 BEDRMS              | -0.055792729   | 0.006811251  | -8.191260367 | 2.68239E-16  | -0.069143052  | -0.042442407  | -0.069143052  | -0.042442407  |
| β8 BUILT               | 0.002161552    | 0.000127154  | 16.99945099  | 1.61571E-64  | 0.001912324   | 0.002410779   | 0.001912324   | 0.002410779   |
| β9 ROOMS               | 0.10242138     | 0.0029667    | 34.52367613  | 2.3037E-256  | 0.09660653    | 0.108236229   | 0.09660653    | 0.108236229   |
| β10 PER                | 0.136000692    | 0.011350106  | 11.98232823  | 5.19418E-33  | 0.113754034   | 0.158247351   | 0.113754034   | 0.158247351   |
| β11 LN(ZINC2)          | 0.094231184    | 0.00349148   | 26.98889779  | 1.3092E-158  | 0.087387745   | 0.101074623   | 0.087387745   | 0.101074623   |
| β12 ADEQUATE           | 0.125479543    | 0.019416195  | 6.462622706  | 1.04415E-10  | 0.087423028   | 0.163536057   | 0.087423028   | 0.163536057   |
| β13 LN(ZSMHC)          | 0.315841336    | 0.005822253  | 54.24726903  | 0            | 0.304429488   | 0.327253184   | 0.304429488   | 0.327253184   |
| β14 LN(UTILITY)        | -0.03173778    | 0.007476926  | -4.244763433 | 2.19454E-5   | -0.046392852  | -0.017082709  | -0.046392852  | -0.017082709  |
| β15 LN(OTHERCOST)      | 0.130820037    | 0.00304902   | 42.90560797  | 0            | 0.124843837   | 0.136796237   | 0.124843837   | 0.136796237   |



### Example of Specific Rows from the Data:

| VALUE_2013 | LN(VALUE_2013) | Northeast | Midwest | South | LN(LMED) | LN(FMR) | LN(IPOV) | BEDRMS | BUILT | ROOMS | PER | LN(ZINC2) | ADEQUATE | LN(ZSMHC) | LN(UTILITY) | LN(OTHER COST) | VALUE_2011 | LN(VALUE_2011) | Predicted Ln(VALUE 2013) | Predicted (VALUE 2013) | Abs(Difference) | Mean Abs(Diff) [MAD] | AVERAGE |
|------------|----------------|-----------|---------|-------|----------|---------|----------|--------|-------|-------|-----|-----------|----------|-----------|-------------|----------------|------------|-----------------|--------------------------|------------------------|-----------------|----------------------|---------|
| 90000      | 11.40756495    | 0         | 1       | 0     | 11.03269371 | 6.782192056 | 10.02380072 | 3      | 1950  | 6     | 4   | 11.04196137 | 1        | 6.910750788 | 5.797070409 | 4.605170186 | 96000      | 11.47210347     | 11.67972061               | 118151.2201           | 22151.22008      | 88688.52731           | 242530  |
| 250000     | 12.4292162     | 0         | 0       | 1     | 10.84478304 | 6.863803391 | 9.509481538 | 5      | 1960  | 9     | 2   | 12.64109656 | 1        | 6.809039306 | 6.274762021 | 4.828313737 | 375000     | 12.8346813      | 12.24581538               | 208108.6086          | 166891.3914      |                       |         |
| 400000     | 12.89921983    | 0         | 0       | 0     | 11.07325704 | 7.00488199  | 9.271905728 | 2      | 2006  | 6     | 1   | 10.91319577 | 1        | 6.17586727  | 5.560361067 | 4.437737242 | 370000     | 12.82125828     | 12.36873965               | 235328.9618          | 134671.0382      |                       |         |
| 50000      | 10.81977828    | 0         | 1       | 0     | 11.0716259  | 6.826545224 | 9.275003885 | 3      | 1970  | 5     | 1   | 9.727883383 | 1        | 6.886531643 | 5.673323267 | 3.149882953 | 75000      | 11.22524339     | 11.67332742               | 117398.2664          | 42398.26639      |                       |         |
| 250000     | 12.4292162     | 1         | 0       | 0     | 11.28139686 | 6.913737351 | 9.605687802 | 2      | 1950  | 4     | 2   | 11.39618938 | 1        | 7.83991936  | 6.027474985 | 4.422848629 | 250000     | 12.4292162      | 12.13204556               | 185729.3086          | 64270.69143      |                       |         |

### Key Observations:

- **Predicted vs. Actual Values**: The natural logarithms of the actual housing values in 2013 (`LN(VALUE_2013)`) are predicted using the regression model. The model then exponentiates the predicted logarithmic values to derive the actual predicted housing values (`Predicted (VALUE 2013)`).

- **Abs(Difference)**: The **absolute difference** between the actual and predicted housing values for 2013 is computed. This value helps to gauge how close the model's predictions are to the real-world data.

- **Mean Abs(Diff) [MAD]**: The **Mean Absolute Difference** (MAD) is calculated to provide an overall measure of prediction accuracy. A lower MAD indicates a more accurate prediction model, with values closer to actual values.

### Model Performance Insights:

The data table allows comparison between the actual housing values in 2013 and those predicted by the regression model. By assessing the absolute differences and the MAD, one can determine the accuracy of the model's predictions and the potential for improvement.

This dataset is useful for evaluating predictive models in housing economics and can help refine strategies for more accurate real-estate forecasting.

Summary Report

(Please include a summary of your key findings here)



A Regression Model to predict the Market Value of Housing Units in Year 2013.

Main points to be covered in the summary...

a.  We use the same model from Assignment 3, except that the dependent variable is the 2013 Market Value while the independent variables are from the year 2011.
b.  We could also use an additional independent variable which is the Market Value of the housing unit in year 2011.
c.  We need to hold out 1000 housing units from the data and estimate the regression model on remaining data.
d. The coefficients from the regression model are to be then used to predict the Market Value in the 'Hold-out Data'. 
c. As a metric of prediction, we need to calculate the Mean Absolute Deviation (MAD) for our predictions.

Prediction in the 'Hold-out' Data

The regression model now has a R-square of 0.46 since we added the Market Value for year 2011 as an additional 'X' variable.

Using the coefficients from this regression model and using the set of 'X' variables in the hold out data we make predictions of the Market Value for the 1000 housing units held out. The MAD statistic (Mean Absolute Deviation) for the prediction turns out to be $88,688.53. This seems ok given that the average Market Value is around  $209,596.59.











































