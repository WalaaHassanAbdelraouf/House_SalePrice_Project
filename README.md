# House Sale Price Prediction Project

This project aims to predict house sale prices using various machine learning models, including Lasso Regression, Decision Tree, and Random Forest. The dataset is based on the House Prices: Advanced Regression Techniques competition from Kaggle.

## Table of Contents

- [Introduction](#introduction)
- [Dataset](#dataset)
- [Data Preprocessing](#data-preprocessing)
- [Feature Engineering](#feature-engineering)
- [Modeling](#modeling)
- [Results](#results)

## Introduction

Predicting house prices is a crucial aspect of the real estate market, aiding buyers, sellers, and investors in making informed decisions. In this project, we developed machine learning models to predict house sale prices based on various features such as the total living area, number of bathrooms, house age, and many others.

## Dataset

The dataset used in this project is sourced from the Kaggle competition "[House Prices: Advanced Regression Techniques](https://www.kaggle.com/c/house-prices-advanced-regression-techniques)". The dataset contains numerous features related to the properties, such as:

- SalePrice - the property's sale price in dollars. This is the target variable that you're trying to predict.

- MSSubClass: The building class

- MSZoning: The general zoning classification

- LotFrontage: Linear feet of street connected to property

- LotArea: Lot size in square feet

- Street: Type of road access

- Alley: Type of alley access

- LotShape: General shape of property

- LandContour: Flatness of the property

- Utilities: Type of utilities available

- LotConfig: Lot configuration

- LandSlope: Slope of property

- Neighborhood: Physical locations within Ames city limits

- Condition1: Proximity to main road or railroad

- Condition2: Proximity to main road or railroad (if a second is present)

- BldgType: Type of dwelling

- HouseStyle: Style of dwelling

- OverallQual: Overall material and finish quality

- OverallCond: Overall condition rating

- YearBuilt: Original construction date

- YearRemodAdd: Remodel date

- RoofStyle: Type of roof

- RoofMatl: Roof material

- Exterior1st: Exterior covering on house

- Exterior2nd: Exterior covering on house (if more than one material)

- MasVnrType: Masonry veneer type

- MasVnrArea: Masonry veneer area in square feet

- ExterQual: Exterior material quality

- ExterCond: Present condition of the material on the exterior

- Foundation: Type of foundation

- BsmtQual: Height of the basement

- BsmtCond: General condition of the basement

- BsmtExposure: Walkout or garden level basement walls

- BsmtFinType1: Quality of basement finished area

- BsmtFinSF1: Type 1 finished square feet

- BsmtFinType2: Quality of second finished area (if present)

- BsmtFinSF2: Type 2 finished square feet

- BsmtUnfSF: Unfinished square feet of basement area

- TotalBsmtSF: Total square feet of basement area

- Heating: Type of heating

- HeatingQC: Heating quality and condition

- CentralAir: Central air conditioning

- Electrical: Electrical system

- 1stFlrSF: First Floor square feet

- 2ndFlrSF: Second floor square feet

- LowQualFinSF: Low quality finished square feet (all floors)

- GrLivArea: Above grade (ground) living area square feet

- BsmtFullBath: Basement full bathrooms

- BsmtHalfBath: Basement half bathrooms

- FullBath: Full bathrooms above grade

- HalfBath: Half baths above grade

- Bedroom: Number of bedrooms above basement level

- Kitchen: Number of kitchens

- KitchenQual: Kitchen quality

- TotRmsAbvGrd: Total rooms above grade (does not include bathrooms)

- Functional: Home functionality rating

- Fireplaces: Number of fireplaces

- FireplaceQu: Fireplace quality

- GarageType: Garage location

- GarageYrBlt: Year garage was built

- GarageFinish: Interior finish of the garage

- GarageCars: Size of garage in car capacity

- GarageArea: Size of garage in square feet

- GarageQual: Garage quality

- GarageCond: Garage condition

- PavedDrive: Paved driveway

- WoodDeckSF: Wood deck area in square feet

- OpenPorchSF: Open porch area in square feet

- EnclosedPorch: Enclosed porch area in square feet

- 3SsnPorch: Three season porch area in square feet

- ScreenPorch: Screen porch area in square feet

- PoolArea: Pool area in square feet

- PoolQC: Pool quality

- Fence: Fence quality

- MiscFeature: Miscellaneous feature not covered in other categories

- MiscVal: $Value of miscellaneous feature

- MoSold: Month Sold

- YrSold: Year Sold

- SaleType: Type of sale

- SaleCondition: Condition of sale

## Data Preprocessing

Data preprocessing steps included:

1. Handling Missing Values: Missing values were handled by imputing to ensure that the dataset was clean and suitable for modeling.
2. Feature Engineering: Additional features were created to improve the model's predictive power such as:
    - OverallScore: An overall score calculated based on various quality and condition metrics.
    - TotalLivingArea: The total living area of the house.
    - TotalBath: The total number of bathrooms.
    - TotalBsmtFinSF: Total basement finished square feet.
    - HouseAge: The age of the house.
    - GarageYrBlt: The year the garage was built.
    - TotalSqft: Total square footage of the house.
    - TotalOutdoorArea: Total outdoor area of the property.
4. Encoding Categorical Features: Target encoding and ordinal encoding methods were applied to convert categorical variables into a numerical format.

## Feature Engineering

We applied polynomial feature transformation on selected features to capture non-linear relationships. The selected features for polynomial transformation included:

- `OverallScore`, `TotalLivingArea`, `TotalBath`, `TotalBsmtFinSF`, `HouseAge`, `OverallGarageQual`, `PavedStreet`, `RemodAge`, `GarageYrBlt`, `TotalSqft`, `TotalOutdoorArea`.

## Modeling

We used three different machine learning models to predict the house prices:

1. Lasso Regression: Used to perform both variable selection and regularization to enhance the prediction accuracy.
2. Decision Tree: A tree-based model to capture complex non-linear relationships.
3. Random Forest: An ensemble of decision trees to improve prediction robustness.

### Model Training and Evaluation

Each model was trained on the training set and evaluated using the R-squared (R²) and Root Mean Squared Error (RMSE) metrics for both training and testing sets.

## Results

| Model             | R-squared (Training) | R-squared (Testing) | RMSE (Training) | RMSE (Testing) |
|-------------------|----------------------|---------------------|-----------------|----------------|
| Lasso Regression  | 0.972                | 0.850               | 12809.9480      | 33891.4868     |
| Decision Tree     |0.9975                | 0.9932              | 3838.9597       | 7232.0954      |
| Random Forest     | 0.9992               | 0.9939              | 2152.0785       | 6813.1984      |

