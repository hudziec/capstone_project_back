# Capstone Project - Ames Housing Data

## Introduction

For my Capstone Project I decided to do a data analysis project, this interests me greatly considering my background as a licensed land surveyor. For nearly twenty years I've been involved with the physical development of real estate and this project offered me a look into another aspect of the industry. Additionally, processing data is something I am familiar with, all be it from a different industry. I've processed data from field crews containing angles and distances depicting physical locations, this has made me comfortable with interpreting data and running statistical analysis on data (least squares adjustment and compass rule) for accuracy and precision of physical locations.

The Ames Housing data has been used numerously as projects for data science, my intention was not to recycle the data that has been used before but to hopefully show it as a benchmark for comparison of my skills. Being new to this industry, my intention was not to "reinvent the wheel" but to demonstrate a foundation of skills that I hope I'll be able to  build on given an opportunity.

## Problem Statement

The purpose of this project was to make a linear regression model to predict housing price. this was to be evaluated by how close I came to the price indicated in the data set I chose. the scope of my project evolved as I realized the extent of the data, the form it was in and what the skills I possessed could process it.


## Data Cleaning and EDA

After printing out the commands to analyze the columns I was given and familiarizing myself with the data, I devised a plan. This plan revolved around keeping and transforming the "qualitative" columns over the "quantitively" ones. Quantitative variables (commonly called numerical variables) are variables that are measured on a numeric scale. This lends well to a linear regression model since these do not have to be converted to another data type. However, large unique values, such as Lot Area, may break my model even though it is a major indicator of lot sale price. This approach seemed counter intuitive at first, as I realized I’d be eliminating columns I knew had direct influence on sale price. My focus turned to Qualitative variables (commonly called categorical variables) are variables that are not measured on a numeric scale. Choosing this approach involved more data type conversion but I suspected that the higher categorical variables, as "excellent" or "good" might tend to be associated with a higher sale price.

## Exploratory Visualizations

#### Analysis of Heatmap of the Correlation Matrix

Examining the map, the darker colors show correlation between columns. The objective of this output is to predict salesprice, columns that correlate best are garage_cars, fireplaces, totrms_abvgrd, full_bath, heating_qc, exter_qual & overall_qaul. These columns have a .45 correlation and higher.

#### Create scatterplots for each of the columns that correlate with sales price

Before analysis of the correlated columns, let’s see what the price of houses is doing given our timeframe. There appears to be a drop-in price from 2009 and 2010. The bulk of house sales appear to be within about 150,000 and 200,000.

#### What can this scatter plot tell us about the model?

    -If all the points fell on a diagonal line, we would have a perfect fit.

    -If the model was more "cloud-like", the worse our fit would be.

    -There outliers of are model are not extreme and appear to follow a normal distribution.

From the scatter plot that was generated, few outliners were identified. This raised concerns that the model may have been overfit.

## Pre-processing

#### What can the model score tell us about the model?

    -Closer to 1 desirable

    -Not scale dependent.

    -A residual value of 0.8 means that 80% of the variability in the data are explained by our model, relative to a model with no     predictors.

    -As you add more variables, residuals will never decrease (with linear regression).

#### What is K-Folds Cross Validation?

    -K-fold cross-validation takes the idea of a single train/test split and expands it to multiple tests across different             train/test splits of your data.

    -K-fold cross-validation builds K models — one for each train/test pair — and evaluates those models on each respective test
    set.

    -The K-fold cross-validation scores appear to be in proximity to out model score indicating that our data is regular and
    redundant thus giving us confidence in its accuracy and precision.

Model score on the data yielded good results. Concerns over overfitting the model mentioned above were eased by running a K-Folds Cross Validation. The results yielded were in line with the model score giving more surety that the columns choose lent well to the model and that there were not too many irregularities.

## Inferential Visualizations

After generating sales price data for lots in the clean_text.csv, opening the sample_sub_reg.csv and seeing how it compared was a task. Realizing the sample_sub_reg.csv was a mean price for all lots rather than for individual lots reflected that the same had to be done with our data. After our task completion, it was determined that our generated mean sales price was 1.6% (rounded to 2.0 for error) lower than the target mean sales price.

## Business Recommendations

My business recommendation would to be to dive deeper into how houses are evaluated. This pertains to the column determination of how conditions and qualities columns of house features are determined. Who, what or how these columns, condition and quality, are being determined is the ultimate price determinate? Apart from condition and quality columns, the house features of garage_cars, fireplaces, totrms_abvgrd, full_bath, heating_qc, are the are most desirable for Iowa. The house features that are specific for Iowa have to be garage_cars, fireplaces, heating_qc. Iowa being in rural northern area lends to the fact that most home buyers are rely on cars for transportation rather that public transportation. Home buyer are looking to protect their vehicle by keeping them out of the weather. In relation to this northern area, heat is important given the fireplaces and heating_qc have high importance. The information derived from this model is Ames, Iowa specific. Given data from another region this model would identify house features unique to that region. In other words, it's all about the data!
