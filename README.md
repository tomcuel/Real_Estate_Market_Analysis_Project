# Real Estate Market Analysis Project 
> In the context of a statistics lesson on time series, this project analyzes the real estate market in Ille-et-Vilaine, France. Using historical transaction data, we aim to identify key factors influencing house prices and develop simple predictive models to estimate future prices.

The dataset can be found on the Kaggle website via this link(https://www.kaggle.com/datasets/cheneblanc/housing-prices-35-fr), or by searching for its name: Housing Prices France 35. Due to size constraints on GitHub, the dataset is not available in the repository. However, a sample of the dataset, containing only the relevant columns for modeling, is provided. All code is based on the initial dataset, though representative datasets can be used with minor adjustments.

#### Tables of contents
* [Path Tree](#path-tree)
* [Direct Links to Folders](#direct-links-to-folders)  
* [Running the code](#running-the-code) 
* [Project 1: Implementation of Newton's Method](#project-1-implementation-of-newtons-method)
* [Project 2: Image Deblurring](#project-2-image-deblurring)

## Path tree
```
Real_Estate_Market_Analysis_Project /
├── Datasets/
│   └── datasets
│
├── Results/
│   ├── Data_Cleaning/                
│   ├── Prediction/    
│   ├── Raw_Graphs/
│   └── Tendance_Saison/
│
└── R code
```

## Direct links to folders
* [TP1](./TP1/) : Implementation of the Newton's method for finding static equilibrium of a chain
    * [Results](./TP1/Results/) : contains folders to store the different result pictures
* [TP2](./TP2/) : Implementation of the proximal gradient methods for image deblurring  
    * [Results](./TP2/Results/) : contains folders to store the different result pictures


## Running the code 
You must have install R, either using it directly in VS-Code, or R-Studio (simpler but worst to code on I think)

On top of that you must install packages before using them  by making the following commmandes
```
install.packages("to_use")
library(to_use)
```
In this project, I used for different purpose the librairies just below :  
```
xts
dplyr
tidyr
dygraphs
lubridate
caret
ggplot2
GGally
corrplot
nortest
scales
zoo
mgcv
forecast
```

## Overview 
* Data preprocessing (outlier removal, missing value treatment, normalization).
* Exploratory data analysis (distribution, trends, seasonality).
* Statistical modeling (Gaussian kernel smoothing, polynomial regression, moving averages).
* Time series forecasting (exponential smoothing, validation, and prediction).





Data Processing

To ensure data quality, we applied the following preprocessing steps:

Outlier Detection and Removal

Initial price distribution analysis revealed extreme values.

Used boxplots and interquartile range (IQR) filtering to remove outliers.

Applied a log transformation to normalize price distributions.

Handling Missing Values

Identified missing values in price and room count attributes.

Used linear regression imputation based on correlated features.

Data Normalization

Standardized numerical features for better model performance.

After cleaning, the dataset was exported for further modeling and analysis.

Descriptive Analysis

We performed time-series visualization to detect trends and seasonal patterns:

Sales prices are increasing, reflecting inflation and rising property demand.

Price per square meter is rising, showing market expansion.

Number of transactions follows a seasonal pattern, with higher sales in summer and lower in winter.

Key observations:

Prices tend to increase over time.

A clear seasonality effect exists, impacting real estate trends.

The COVID-19 pandemic had a temporary effect on transactions.

Trend and Seasonality Extraction

To analyze trends, we applied several smoothing techniques:

Moving Averages

Used a 40-period window for trend extraction.

Used a 10-period window for seasonality extraction.

Gaussian Kernel Smoothing

Applied a Gaussian filter to smooth price trends.

Evaluated autocorrelation to verify model accuracy.

Local Polynomial Regression

Modeled price evolution using local polynomial approximations.

Compared residual autocorrelation with previous methods.

Exponential Smoothing

Implemented simple and double exponential smoothing.

Tuned hyperparameters (α) to minimize prediction errors.

Price Prediction

We built predictive models using historical data to estimate future prices.

Prediction on Known Data

Tested models against existing data to evaluate performance.

Local polynomials outperformed Gaussian kernels, which sometimes predicted negative prices.

Cross-Validation

Validated models using cross-validation.

Found that Gaussian models had significant prediction errors.

Forecasting Future Prices

Predicted price trends for the next year.

Observed a decline in total sales, likely due to COVID-19 market disruptions.

Key Findings:

Local polynomials and double exponential smoothing performed best for forecasting.

Gaussian models struggled with market irregularities.

COVID-19 effects introduced uncertainty, making predictions less reliable.

