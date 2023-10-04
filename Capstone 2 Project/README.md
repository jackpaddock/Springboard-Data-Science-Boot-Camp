![image](https://github.com/jackpaddock/Springboard-Data-Science-Boot-Camp/assets/129892021/129c58e6-8d15-4d8c-becd-0e5531ea278a)

# U.S. Wildfires - Is There a Greater Issue at Hand?

Wildfires are a significant environmental issue that also endanger human lives. Due to varying factors, their impact is immense and they tend to make headline news these days. In an ever changing world, my clients (conservationists and first responders) must better understand newfound wildfire related trends and adapt in order to more efficiently and effectively put wildfires out. In this project, I will explore underlying trends in recent American wildfire history and will leverage the correlations amongst the data to help my clients better understand the ever changing climate.

## 1. Data

Kaggle Dataset [here](https://www.kaggle.com/datasets/kkhandekar/total-wildfires-acres-affected-1983-2020?resource=download)

This Kaggle dataset is linked to The National Interagency Fire Center (NIFC). The NIFC works alongside other U.S. federal agencies in developing environmental focused regulations and by providing support and information to wildland fire personal and other emergency services employees, among other focuses. The dataset covers wildfires from 1985 to 2020.

## 2. Background on NIFC

## 3. Data Wrangling

Workbook [here](https://github.com/jackpaddock/Springboard-Data-Science-Boot-Camp/blob/master/Capstone%202%20Project/Capstone%202%20-%20Data%20Wrangling%20.ipynb)

This dataset is quite clean as is, so I did not need to apply drastic changes. Though, touch-up was needed to enhance the interpretability for my clients. Changes made include:

- Added currency and country fields for better interpretability
- Stripped commas and USD format of applicable fields.
- Converted data types to integer format since applicable numeric values are object format due to their USD format.
- Scaled all numeric values to same unit for ease of analysis
- Built in additional fields to capture key metrics

## 4. Exploratory Data Analysis (EDA)

Workbook [here](https://github.com/jackpaddock/Springboard-Data-Science-Boot-Camp/blob/master/Capstone%202%20Project/Capstone%202%20-%20Exploratory%20Data%20Analysis%20(EDA).ipynb)

![image](https://github.com/jackpaddock/Springboard-Data-Science-Boot-Camp/assets/129892021/6f823fee-1dee-4efe-9de4-a58e3d1b7199)
![image](https://github.com/jackpaddock/Springboard-Data-Science-Boot-Camp/assets/129892021/b3d17552-bfc7-4ed8-ae47-e99260715287)
![image](https://github.com/jackpaddock/Springboard-Data-Science-Boot-Camp/assets/129892021/92c0cdba-913f-4af4-bca7-52f9a00eb0c9)

We see that over time, the number of fires have declined while both the acres burnt and the total fire suppression cost have increased. This is a key finding for my clients and one that requires further investigation.

## 5. Modeling via Supervised Machine Learning

Workbook [here](https://github.com/jackpaddock/Springboard-Data-Science-Boot-Camp/blob/master/Capstone%202%20Project/Capstone%202%20-%20Modeling.ipynb)

I elected to work with Python's scikit-learn library, and I focused on [regression models](https://scikit-learn.org/stable/supervised_learning.html#supervised-learning). I tested my dataset on four models by allocating a 30%/70% test, train split. The linear regression model performed the best by a fairly large margin, so it was leveraged for predictions.

![580BE5E9-F8A6-4E07-B9EA-EB7A7AE80BF4](https://github.com/jackpaddock/Springboard-Data-Science-Boot-Camp/assets/129892021/20c9519e-d927-4ae8-ae76-2fbd222d5802)

> NOTE: I focused on RMSE, MAPE, and R Squared as my metrics to give me a more thorough understanding of the quality of the respective model performances. RMSE determines the absolute fit of the model to the data as it measures the average difference between a model's predicted values and its actual values. MAPE considers the sum of the individual absolute errors divided by the demand (each period separately). It is the average of the percentage errors. For both RMSE and MAPE, the lower the value the better. Finally, R Squared measures the proportion of variance in the dependent variable that can be explained by the independent variable. The greater the value the better. Vaguely, 0.65/65% or greater is considered pretty good.
>
> 

![B993CA44-136E-483B-94E7-6707DA211433_4_5005_c](https://github.com/jackpaddock/Springboard-Data-Science-Boot-Camp/assets/129892021/9fc195c5-72ef-459d-9e33-f5c511785cb2)

![A73F9C57-C089-4548-9D20-C84F1F4F1DC4_4_5005_c](https://github.com/jackpaddock/Springboard-Data-Science-Boot-Camp/assets/129892021/8bd65bea-e6bf-46d4-b5cb-23e8b519081c)

![4F3A9926-6AD5-4EFD-A688-D97DF29A6938_4_5005_c](https://github.com/jackpaddock/Springboard-Data-Science-Boot-Camp/assets/129892021/45759175-e1b1-4e55-8b3b-2b2dfe640120)

## 6. Linear Model Predictions

Workbook [here](https://github.com/jackpaddock/Springboard-Data-Science-Boot-Camp/blob/master/Capstone%202%20Project/Capstone%202%20-%20Modeling.ipynb)

> NOTE: This is the same workbook as the modeling one above. The predictions are incorporated for each model. For more details regardign the linear regression, see the modeling work towards the bottom of the workbook.

![image](https://github.com/jackpaddock/Springboard-Data-Science-Boot-Camp/assets/129892021/28d12608-64cb-42a8-a99d-971b056cff2b)

The model performs well at predicting Acres Burnt per Fire by using all features tied to my X variable. 

![image](https://github.com/jackpaddock/Springboard-Data-Science-Boot-Camp/assets/129892021/0af5b7e4-5af0-4532-84ff-fdf3b6575663)

By isolating the X variable to one feature, Acres Burnt, the model performs very well at predicting Acres Burnt per Fire over time.

## 7. Client Recommendations

Given that over time, the number of fires have declined while both the acres burnt and the total fire suppression cost have increased, recommendations are:

- Push local governments for more conversation resources and practices to be implemented to protect forests
- Make general public more aware of their potential impact on this crisis. Not all wildfires are naturally occuring.
- Increase staff capacities across conservation agencies and first responders to better handle wildfires so they can be put out more timely

## 8. Future Work

- Leverage an additional dataset or two focused on global CO2 levels to see if they factor into trends found in the Wildfire dataset
  - Dive into avenues that can explain why wildfires are most potent and costly even though the number of them over the years have declined  
- Explore impact of inflation over time to better flatten out analysis of cost features
- Explore which regions or states are most impacted by wildfires
