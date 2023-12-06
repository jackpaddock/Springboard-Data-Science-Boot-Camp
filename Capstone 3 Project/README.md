![image](https://i0.wp.com/blog.tunemymusic.com/wp-content/uploads/2023/08/green-black-3D-Spotify-logo-alexander-shatov-JlO3-oY5ZlQ-unsplash.jpg?fit=400%2C250&ssl=1)

# Spotify Music 1921-2023 - What Makes a Track or Genre Popular and How Has Music Changed Over Time?

Evolution is a defining life theme. Regardless of the measure... people, technology, fashion, or even music, these aspects of life evolve under the pressure and impact of both one another and from the societies behind them from generation to generation. Each generation differs from the next and that is what is both telling and interesting. Why were certain measures defind in the ways they were to one generation but the same measures look and feel mch different to the next generation? In this project, I will explore the underlying music trends spanning 1921-2023, and I will leverage the correlations amongst the data to help my clients better understand the ever changing music industry from a consumer perspective.

## 1. Data

Kaggle Dataset 1 [here](https://www.kaggle.com/datasets/amitanshjoshi/spotify-1million-tracks)

Kaggle Dataset 2 [here](https://www.kaggle.com/datasets/ektanegi/spotifydata-19212020)

Both Kaggle datasets are from Spotify's API which is ideal for data quality and validation purposes. Hence, why I elected to leverage both for my analysis.

## 2. Data Wrangling

Workbook [here](https://github.com/jackpaddock/Springboard-Data-Science-Boot-Camp/blob/master/Capstone%203%20Project/Capstone%203%20-%20Data%20Wrangling.ipynb)

Both datasets are quite clean as is, so I did not need to apply drastic changes. Though, touch-up was needed to enhance the interpretability for my clients. Changes made include:

- 15 values or 0.13% of the artist_name field were missing. Filled with value "other" in Dataset1
- 1 value or 0.01% of the track_name field was missing. Filled with value "other."
- Converted track duration from milliseconds to minutes for better interpretability.
- Renamed fields for better interpretability.
- Deleted duplicate field in Dataset 2.
- Stripped brackets and quotes in artist_name field in Dataset 2.

## 3. Exploratory Data Analysis (EDA)

Workbook [here](https://github.com/jackpaddock/Springboard-Data-Science-Boot-Camp/blob/master/Capstone%203%20Project/Capstone%203%20-%20Exploratory%20Data%20Analysis.ipynb)

**Key Non-Feature Findings are Below:**
- There are 82 unique genres spanning 2000-2023
  - The 1921-1999 dataset (Dataset 2) does not have the "genre" feature, so I couldn't measure it
- Songs have become noticeably less acoustic over time as the average value was around 0.7-1 from 1921-1964, then the range became 0.42-0.61 from 1965-1975, then the range hung     around 0.30 or so from 1976-2023. 
- Track duration also has wavered and has a pattern of starting out at 3.83 in 1921, declining to sub 3 minutes or so up until increasing to sub 4 minutes or so around the 1940s,   it held strong and push sub 4.5 minutes or so for decades up until 2017 where it declined once again to the sub 4 minute or so range. Ironically, 2023's average track duration    is 3.8 which is very close to 1921's value. 
- Liveness has remained mostly unchanged, valence has not experienced much change either, and speechiness has reamined mostly the same, though, it has experienced more outlier      values across random years.
- As expected, energy has increased over time and it has held strong in the sub 0.60-00.65 range from 1979-2023. And, danceability has mostly remained the same which makes sense    as music is generational hence, danceability is subjective and relative to its era. Lastly, loudness has increased over time which likely is due to the advancement of             technology, the creation process (ex. use of cumputers, studios, etc that previous generations did not have access to), generational appetites, and so on.
- Tempo has gradually increased over time and its range between the maximum and minimum values are much tighter than I anticipated (123.41-100.40).

**The Top 25 Genres from 2000-2023:**
- ![image](https://github.com/jackpaddock/Springboard-Data-Science-Boot-Camp/assets/129892021/f1735020-fbda-4155-a580-abfe23808170)

- ![image](https://github.com/jackpaddock/Springboard-Data-Science-Boot-Camp/assets/129892021/3b2b3f1e-8afd-4655-8b5c-56585e2e2308)
- ![image](https://github.com/jackpaddock/Springboard-Data-Science-Boot-Camp/assets/129892021/4becea59-95e0-4cae-b625-75035e94574e)

- ![image](https://github.com/jackpaddock/Springboard-Data-Science-Boot-Camp/assets/129892021/ea4a444c-ff9b-45b8-bebc-737d55feddd5)
- ![image](https://github.com/jackpaddock/Springboard-Data-Science-Boot-Camp/assets/129892021/ac3499b7-1487-416c-a563-e24ab992aa15)

**Key Feature Findings are Below:**
- For the 2000-2023 datset:
  - While focusing on track's/genre's respective popularities, key insights were found. The following analysis is from an "on average" perspective. The less acoustic, the more         popular a track/genre is. Though, acousticness's impact on popularity is not strong. Energy's popularity sweet spot, which is measured between 0-1, hovers around 0.50-0.75.        The more danceable a track/genre, the more popular... 0.55-0.75 is the sweet spot. Valence is not a strong predictor of popularity while on the other hand, speechiness is.         The less speechiness, the more popular (sweet spot is 0-0.10). Loudness also is a strong predictor of popularity as its sweet spot is -15 to -5 dBs. Lastly, instrumentalness       is like valence where it's not a strong predictor of popularity, though, an instrumentallness of 0 is most popular.
- For the 1921-1999 datset:
  - While focusing on track's/genre's respective popularities, key insights were found. The following analysis is from an "on average" perspective. The less acoustic, the more         popular a track/genre is. Though, acousticness's impact on popularity is not strong. Energy's popularity sweet spot, which is measured between 0-1, hovers around 0.65-0.95         which is greater than the file_2000_2023_spotify dataframe. The more danceable a track/genre, the more popular... 0.55-0.75 is the sweet spot just like the                     
    file_2000_2023_spotify dataframe. Valence is not a strong predictor of popularity while on the other hand, speechiness is. The less speechiness, the more popular (sweet spot 
    is 0-0.05). Loudness also is a strong predictor of popularity as its sweet spot is -15 to -5 dBs. Lastly, instrumentalness is like valence where it's not a strong predictor of 
    popularity, though, an instrumentalness of 0 is most popular.


## 4. Modeling via Supervised Machine Learning

Workbook [here](https://github.com/jackpaddock/Springboard-Data-Science-Boot-Camp/blob/master/Capstone%203%20Project/Capstone_3_Pre_processing_Work_and_Modeling_Final.ipynb)

I elected to work with Python's scikit-learn library, and I focused on [regression analysis](https://scikit-learn.org/stable/supervised_learning.html#supervised-learning). I dropped features “Years,” “Country,” and “Currency.” The “Years” feature was dropped as regression analysis’ basis is not predicting time, so I did not see value in its inclusion. I tested the dataset on four models by allocating a 30%/70% test, train split with my target variable being the feature "Acres Burnt per Fire." The linear regression model performed the best by a fairly large margin, so it was leveraged for predictions.

![580BE5E9-F8A6-4E07-B9EA-EB7A7AE80BF4](https://github.com/jackpaddock/Springboard-Data-Science-Boot-Camp/assets/129892021/20c9519e-d927-4ae8-ae76-2fbd222d5802)

> NOTE: I focused on RMSE, MAPE, and R Squared as my metrics to give me a more thorough understanding of the quality of the respective model performances. RMSE determines the absolute fit of the model to the data as it measures the average difference between a model's predicted values and its actual values. MAPE considers the sum of the individual absolute errors divided by the demand (each period separately). It is the average of the percentage errors. For both RMSE and MAPE, the lower the value the better. Finally, R Squared measures the proportion of variance in the dependent variable that can be explained by the independent variable. The greater the value the better. Vaguely, 0.65/65% or greater is considered pretty good.
>
> 

![B993CA44-136E-483B-94E7-6707DA211433_4_5005_c](https://github.com/jackpaddock/Springboard-Data-Science-Boot-Camp/assets/129892021/9fc195c5-72ef-459d-9e33-f5c511785cb2)

![A73F9C57-C089-4548-9D20-C84F1F4F1DC4_4_5005_c](https://github.com/jackpaddock/Springboard-Data-Science-Boot-Camp/assets/129892021/8bd65bea-e6bf-46d4-b5cb-23e8b519081c)

![4F3A9926-6AD5-4EFD-A688-D97DF29A6938_4_5005_c](https://github.com/jackpaddock/Springboard-Data-Science-Boot-Camp/assets/129892021/45759175-e1b1-4e55-8b3b-2b2dfe640120)

## 5. Linear Model Predictions

Workbook [here](https://github.com/jackpaddock/Springboard-Data-Science-Boot-Camp/blob/master/Capstone%202%20Project/Capstone%202%20-%20Modeling.ipynb)

> NOTE: This is the same workbook as the modeling one above. The predictions are incorporated for each model. For more details regardign the linear regression, see the modeling work towards the bottom of the workbook.

![image](https://github.com/jackpaddock/Springboard-Data-Science-Boot-Camp/assets/129892021/28d12608-64cb-42a8-a99d-971b056cff2b)

The model performs well at predicting "Acres Burnt per Fire" by using all features tied to my X variable. 

![image](https://github.com/jackpaddock/Springboard-Data-Science-Boot-Camp/assets/129892021/0af5b7e4-5af0-4532-84ff-fdf3b6575663)

By isolating the X variable to one feature, "Acres Burnt," the model performs very well at predicting Acres Burnt per Fire over time.

## 6. Client Recommendations

Given that over time, the number of fires has declined while both the acres burnt and the total fire suppression cost have increased, recommendations are:

- Push local governments for more conversation resources and practices to be implemented to protect forests.
- Make the public more aware of their potential impact on this crisis. Not all wildfires are naturally occuring.
- Increase staff capacities across conservation agencies and first responders to better handle wildfires so they can be put out timelier.

## 7. Future Work

- Leverage an additional dataset or two focused on global CO2 levels to see if they factor into trends found in the Wildfire dataset.
  - Dive into avenues that can explain why wildfires are most potent and costly even though the number of them over the years have declined.
- Explore impact of inflation over time to better flatten out analysis of cost features.
- Explore which regions or states are most impacted by wildfires.

