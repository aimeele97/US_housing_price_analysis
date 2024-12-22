# Housing Market Analysis: A Comprehensive Overview

## Table of Contents

1. **Business Problem Overview**
   - 1.1 Objective of the Study
   - 1.2 Scope and Data Description
2. **Problem Statement**
   - 2.1 Market Rent Analysis Across Years
   - 2.2 Hypothesis Testing for Market Value Differences
   - 2.3 Predicting Housing Market Values Using Regression
   - 2.4 Forecasting Future Housing Values
3. **Data Collection and Preprocessing**
   - 3.1 Data Sources
   - 3.2 Variables and Descriptions
   - 3.3 Data Cleaning
   - 3.4 Data Merging
4. **Methodology**
   - 4.1 Hypothesis Testing for Market Value Differences
   - 4.2 Regression Analysis for Market Value Prediction
   - 4.3 Future Market Value Forecasting
5. **Results and Discussion**
   - 5.1 Descriptive Statistics and Analysis
   - 5.2 Statistical Testing Results
   - 5.3 Predictive Modeling Outcomes
6. **Conclusion and Recommendations**
   - 6.1 Key Findings
   - 6.2 Policy Implications
   - 6.3 Recommendations for Stakeholders

---

## 1. Business Problem Overview

### 1.1 Objective of the Study
The objective of this study is to analyze trends in the housing market, focusing on the variation in market rents, housing unit values, and predictive modeling for future trends. The study uses historical housing data to provide insights on market dynamics over time, with the aim to inform policy decisions and market strategies.

### 1.2 Scope and Data Description
The data analyzed in this study is from the **Housing Affordability Data System (HADS)** provided by the U.S. Department of Housing and Urban Development. The dataset spans five key years: 2005, 2007, 2009, 2011, and 2013. Key housing-related variables include market value, rent prices, household income, number of rooms, and occupancy status, among others.

---

## 2. Problem Statement

### 2.1 Market Rent Analysis Across Years
This study examines the differences in market rents over the years to understand how housing affordability has evolved. By analyzing the **Fair Market Rent (FMR)** for different years, we aim to uncover trends and patterns that impact housing affordability.

### 2.2 Hypothesis Testing for Market Value Differences
We will conduct hypothesis tests to determine if there are statistically significant differences in market values across various years, particularly focusing on occupied versus vacant housing units. This is done through **t-tests** to compare market values between two groups.

### 2.3 Predicting Housing Market Values Using Regression
A regression model will be used to predict housing market values for the year 2013, based on a set of independent variables such as location, size, and type of structure. This will allow us to understand the factors that drive housing market prices.

### 2.4 Forecasting Future Housing Values
Lastly, we aim to forecast housing values for the upcoming years using the same regression techniques, adjusting for potential market changes.

---

## 3. Data Collection and Preprocessing

### 3.1 Data Sources
The data used in this analysis is collected from the **Housing Affordability Data System** (HADS) provided by HUD. The dataset contains housing-level variables collected across multiple years (2005, 2007, 2009, 2011, and 2013).

### 3.2 Variables and Descriptions

| **Variable Name** | **Type** | **Description** |
|-------------------|----------|-----------------|
| **CONTROL** | Character | Control variable for matching data across datasets |
| **AGE1** | Numerical | Age of the head of household |
| **METRO3** | Character | Metropolitan status |
| **FMR** | Numerical | Fair Market Rent |
| **VALUE** | Numerical | Current market value of housing unit |
| **BEDRMS** | Numerical | Number of bedrooms in the unit |
| **BUILT** | Numerical | Year the unit was built |
| **STATUS** | Character | Occupied or vacant |
| **TYPE** | Numerical | Type of structure (single-family, multi-family, etc.) |
| **OWNRENT** | Character | Owner-occupied or rental property |
| **UTILITY** | Numerical | Monthly utility costs |

### 3.3 Data Cleaning
Before analysis, the data was cleaned by removing any housing units with market values below $1,000 and correcting any discrepancies in the data.

### 3.4 Data Merging
The data was merged for five years (2005, 2007, 2009, 2011, and 2013) based on the **CONTROL** variable, which helps in matching housing units across different years.

---

## 4. Methodology

### 4.1 Hypothesis Testing for Market Value Differences
We used a **two-sample t-test** to evaluate whether there is a significant difference in the market values of occupied versus vacant housing units for each year. The null hypothesis states that the market values for both groups are equal, and the alternative hypothesis suggests they are different.

### 4.2 Regression Analysis for Market Value Prediction
Regression models were constructed to predict housing market values for the year 2013 based on independent variables such as property size, structure type, and regional factors. These models were then used to forecast future market values.

### 4.3 Future Market Value Forecasting
Based on the regression analysis, we used the model to project housing values for the upcoming year, considering factors like inflation, housing trends, and economic indicators.

---

## 5. Results and Discussion

### 5.1 Descriptive Statistics and Analysis
Descriptive statistics for market values and fair market rents were calculated to understand the general distribution and trends across the years. The results show increasing trends in rents and market values over time.

### 5.2 Statistical Testing Results
The **t-tests** for market values revealed that there are significant differences between occupied and vacant housing units in most years. The p-values for all t-tests were below 0.05, indicating significant differences.

### 5.3 Predictive Modeling Outcomes
Regression analysis showed that factors such as number of rooms, structure type, and region significantly impact housing values. Predictions for 2013 were found to be reliable, with a high correlation between predicted and actual values.

### Summary of Regression Analysis for the Market Value of Housing Units (Year 2013)

**Data Preprocessing & Descriptive Statistics:**
- We have filtered the dataset to include only the **'Single Family Units'** where **STRUCTURETYPE = 1** and **TYPE = 1** and removed data related to rental units (**OWNRENT = 2**).
- Descriptive statistics and histograms for the **VALUE** variable are calculated, showing the distribution of housing values before and after applying the natural logarithm transformation. The log-transformed values, **LN(VALUE)**, were tested for a closer resemblance to a normal (bell curve) distribution.

### Regression Model

The regression equation for predicting the **LN(VALUE)** (logarithmic transformation of housing values) is:

\[
\text{LN(VALUE)} = \beta_0 + \beta_1 \cdot \text{Northeast} + \beta_2 \cdot \text{Midwest} + \beta_3 \cdot \text{South} + \beta_4 \cdot \text{LN(LMED)} + \beta_5 \cdot \text{LN(FMR)} + \beta_6 \cdot \text{LN(IPOV)} + \beta_7 \cdot \text{BEDRMS} + \beta_8 \cdot \text{BUILT} + \beta_9 \cdot \text{ROOMS} + \beta_{10} \cdot \text{PER} + \beta_{11} \cdot \text{LN(ZINC2)} + \beta_{12} \cdot \text{ADEQUATE} + \beta_{13} \cdot \text{LN(ZSMHC)} + \beta_{14} \cdot \text{LN(UTILITY)} + \beta_{15} \cdot \text{LN(OTHERCOST)}
\]

Where:
- **Northeast**, **Midwest**, and **South** are dummy variables for the region.
- **LN(LMED)**: Logarithm of the area median income.
- **LN(FMR)**: Logarithm of the Fair Market Rent.
- **LN(IPOV)**: Logarithm of the poverty threshold.
- **BEDRMS**, **BUILT**, **ROOMS**, **PER**, **LN(ZINC2)**, **ADEQUATE**, **LN(ZSMHC)**, **LN(UTILITY)**, **LN(OTHERCOST)** represent different characteristics of the housing units.

### Summary Output from Regression Analysis

#### Regression Statistics:
- **Multiple R**: 0.739
- **R Square**: 0.546
- **Adjusted R Square**: 0.546
- **Standard Error**: 0.546
- **Observations**: 31,322

#### ANOVA:
- **Significance F**: 0 (indicating a highly significant model)
- **Regression SS**: 11,242.62
- **Residual SS**: 9,336.63
- **Total SS**: 20,579.25

#### Coefficients:
These values represent the impact of each independent variable on the **LN(VALUE)** (log-transformed value of housing units), and all coefficients have p-values below 0.05, indicating statistical significance.

| Variable              | Coefficient    | Interpretation                                                                                                                                     |
|-----------------------|----------------|---------------------------------------------------------------------------------------------------------------------------------------------------|
| **Intercept**          | 6.01           | The base value when all other variables are zero (which does not make sense in a practical context).                                               |
| **β1 - Northeast**     | -0.13          | Housing value in the Northeast is 13.37% lower compared to the West region, holding other factors constant.                                         |
| **β2 - Midwest**       | -0.33          | Housing value in the Midwest is 32.89% lower compared to the West region, holding other factors constant.                                           |
| **β3 - South**         | -0.24          | Housing value in the South is 24.28% lower compared to the West region, holding other factors constant.                                             |
| **β4 - LN(LMED)**      | 0.21           | A 1% increase in the area median income results in a 0.21% increase in housing value, holding other factors constant.                             |
| **β5 - LN(FMR)**       | 0.58           | A 1% increase in the Fair Market Rent results in a 0.58% increase in housing value, holding other factors constant.                               |
| **β6 - LN(IPOV)**      | -0.92          | A 1% increase in the poverty income threshold results in a 0.92% decrease in housing value, holding other factors constant.                        |
| **β7 - BEDRMS**        | -0.06          | An additional bedroom corresponds to a 5.58% decrease in housing value, holding other factors constant.                                            |
| **β8 - BUILT**         | 0.22           | For every one-year delay in the age of the housing unit, the market value increases by 0.22%, holding other factors constant.                      |
| **β9 - ROOMS**         | 0.10           | An additional room corresponds to a 10.24% increase in housing value, holding other factors constant.                                              |
| **β10 - PER**          | 0.14           | An additional person in the household corresponds to a 13.6% increase in housing value, holding other factors constant.                           |
| **β11 - LN(ZINC2)**    | 0.09           | A 1% increase in household income leads to a 0.09% increase in housing value, holding other factors constant.                                        |
| **β12 - ADEQUATE**     | 0.13           | Housing units classified as 'Adequate' have 12.55% higher value compared to those classified as non-Adequate.                                      |
| **β13 - LN(ZSMHC)**    | 0.32           | A 1% increase in monthly costs leads to a 0.32% increase in housing value, holding other factors constant.                                          |
| **β14 - LN(UTILITY)**  | -0.03          | A 1% increase in utility costs results in a 0.03% decrease in housing value, holding other factors constant.                                         |
| **β15 - LN(OTHERCOST)**| 0.13           | A 1% increase in other costs corresponds to a 0.13% increase in housing value, holding other factors constant.                                      |

### Discussion on Contributing Factors:

- **Regional Differences**: The housing market values in the Northeast, Midwest, and South are all significantly lower compared to the West region, highlighting geographical price disparities.
- **Income & Rent**: The higher the area median income and fair market rent, the higher the housing market value.
- **Poverty**: Higher poverty thresholds correlate with a decrease in housing market value.
- **Physical Characteristics**: More bedrooms and additional rooms correlate with higher housing values, while more people in a household also tend to increase the market value.
- **Adequacy**: Housing units classified as "Adequate" have significantly higher market values compared to those not classified as such.

### Regression Predictions and MAD (Mean Absolute Deviation):

By using the model, we can predict the future market values of housing units based on variables from the previous years (2011 data). The predictions can help understand housing trends and the expected value changes over time.

Additionally, the **Mean Absolute Deviation (MAD)** helps assess the accuracy of the predictions by measuring the average absolute difference between predicted and actual values.

#### Example from Data (Predicted Values):

| VALUE_2013 | Predicted LN(VALUE_2013) | Predicted VALUE_2013 | Absolute Difference (MAD) |
|------------|--------------------------|----------------------|---------------------------|
| 90,000     | 11.4075                  | 118,151.22           | 22,151.22                 |
| 250,000    | 12.4292                  | 208,108.61           | 166,891.39                |

The model's **MAD** can be calculated for a given dataset to assess prediction performance. 

### Conclusion:
- The regression model explains around **55%** of the variation in housing values and gives us useful insights into factors influencing market prices.
- Future predictions for housing values are possible with the model, providing significant value for housing market analysis and decision-making.
---

## 6. Conclusion and Recommendations

### 6.1 Key Findings
The study found that market rents and housing values have consistently increased over the years. There are significant differences in market values between occupied and vacant units, with occupied units typically having higher market values.

### 6.2 Policy Implications
The increasing trend in housing rents may indicate a growing affordability issue for lower-income households. Policymakers should consider interventions to control rent inflation and increase housing accessibility.

### 6.3 Recommendations for Stakeholders
- **Real Estate Investors**: Focus on areas with high growth in market values and rents.
- **Government Agencies**: Implement rent controls and affordable housing programs to address increasing rent pressures.
- **Homebuyers**: Consider long-term market trends and potential appreciation when purchasing properties.

This analysis provides valuable insights into housing market trends and offers actionable recommendations for both market participants and policymakers.