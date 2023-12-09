![image](https://i0.wp.com/blog.tunemymusic.com/wp-content/uploads/2023/08/green-black-3D-Spotify-logo-alexander-shatov-JlO3-oY5ZlQ-unsplash.jpg?fit=400%2C250&ssl=1)

# Spotify Music 1921-2023 - What Makes a Track or Genre Popular and How Has Music Changed Over Time?

Evolution is a defining life theme. Regardless of the measure... people, technology, fashion, or even music, these aspects of life evolve under the pressure and impact of both one another and from the societies behind them from generation to generation. Each generation differs from the next and that is what is both telling and interesting. Why were certain measures defined in the ways they were to one generation, but the same measures look and feel much different to the next generation? In this project, I will explore the underlying music trends spanning 1921-2023, and I will leverage the correlations amongst the data to help my clients better understand the ever-changing music industry. 

## 1. Data

Kaggle Dataset 1 [here](https://www.kaggle.com/datasets/amitanshjoshi/spotify-1million-tracks)

Kaggle Dataset 2 [here](https://www.kaggle.com/datasets/ektanegi/spotifydata-19212020)

Both Kaggle datasets are from Spotify's API which is ideal for data quality and validation purposes. Hence, why I elected to leverage both for my analysis.

## 2. Data Wrangling

Workbook [here](https://github.com/jackpaddock/Springboard-Data-Science-Boot-Camp/blob/master/Capstone%203%20Project/Capstone%203%20-%20Data%20Wrangling.ipynb)

Both datasets are quite clean as is, so I did not need to apply drastic changes. Though, touch-up was needed to enhance the interpretability. Changes made include:

- 15 values or 0.13% of the artist_name field were missing. Filled with value "other" in Dataset 1.
- 1 value or 0.01% of the track_name field was missing. Filled with value "other" in Dataset 1.
- Converted track duration from milliseconds to minutes for better interpretability in both Datasets.
- Renamed fields for better interpretability in both Datasets.
- Deleted duplicate field in Dataset 2.
- Stripped brackets and quotes in artist_name field in Dataset 2.

## 3. Exploratory Data Analysis (EDA)

Workbook [here](https://github.com/jackpaddock/Springboard-Data-Science-Boot-Camp/blob/master/Capstone%203%20Project/Capstone%203%20-%20Exploratory%20Data%20Analysis.ipynb)

![image](https://github.com/jackpaddock/Springboard-Data-Science-Boot-Camp/assets/129892021/4b8ac583-b8e5-44fa-be24-e38710a87d03)


**Key Non-Feature Findings are Below:**
- There are 82 unique genres spanning 2000-2023
  - The 1921-1999 dataset (Dataset 2) does not have the "genre" feature, so I couldn't measure it.
- Songs have become noticeably less acoustic over time as the average value was around 0.7-1 from 1921-1964, then the range became 0.42-0.61 from 1965-1975, then the range hung      around 0.30 or so from 1976-2023. Meaning, music has shifted to being louder/more energetic/more tempo based/etc. Perhaps this is due to the creation of more genres over time?
- Track duration also has wavered and has a pattern of starting out at 3.83 in 1921, declining to sub 3 minutes or so up until increasing to sub 4 minutes or so around the 1940s,    it held strong and push sub 4.5 minutes or so for decades up until 2017 where it declined once again to the sub 4 minute or so range. Ironically, 2023's average track duration     is 3.8 which is very close to 1921's value. See graphs below!
- Liveness has remained mostly unchanged, valence has not experienced much change either, and speechiness has remained mostly the same, though, it has experienced more outlier       values across random years.
- As expected, energy has increased over time, and it has held strong in the sub 0.60-00.65 range from 1979-2023. And danceability has mostly remained the same which makes sense     as music is generational hence, danceability is subjective and relative to its era. Lastly, loudness has increased over time which likely is due to the advancement of              technology, the creation process (ex. use of computers, studios, etc that previous generations did not have access to), generational appetites, and so on.
- Tempo has gradually increased over time and its range between the maximum and minimum values are much tighter than I anticipated (123.41-100.40).

**The Top 25 Genres from 2000-2023:**
- ![image](https://github.com/jackpaddock/Springboard-Data-Science-Boot-Camp/assets/129892021/f1735020-fbda-4155-a580-abfe23808170)

- ![image](https://github.com/jackpaddock/Springboard-Data-Science-Boot-Camp/assets/129892021/3b2b3f1e-8afd-4655-8b5c-56585e2e2308)
  > Over 400k tracks had a popularity score between 0-10. That is astounding and reflects close to 1/3 of the data alone. Inversely, only 15k tracks score above 60.
  >
  >
- ![image](https://github.com/jackpaddock/Springboard-Data-Science-Boot-Camp/assets/129892021/4becea59-95e0-4cae-b625-75035e94574e)
  > Over 40k tracks had a popularity score between 0-10. Like Dataset 1, this reflects a significant portion of the data. In this case, it reflects about 1/4 of it. Inversely,         just over 3k tracks score above 60.
  > 

- ![image](https://github.com/jackpaddock/Springboard-Data-Science-Boot-Camp/assets/129892021/ea4a444c-ff9b-45b8-bebc-737d55feddd5)
- ![image](https://github.com/jackpaddock/Springboard-Data-Science-Boot-Camp/assets/129892021/ac3499b7-1487-416c-a563-e24ab992aa15)

**Key Feature Findings are Below:**
- For the 2000-2023 dataset (Dataset 1):
  - While focusing on track's/genre's respective popularities, key insights were found. The following analysis is from an "on average" perspective. The less acoustic, the more         popular      a track/genre is. Though, acousticness's impact on popularity is not strong. Energy's popularity sweet spot, which is measured between 0-1, hovers around 0.50-0.75.        The more             danceable a track/genre, the more popular... 0.55-0.75 is the sweet spot. Valence is not a strong predictor of popularity while on the other hand, speechiness is.         The less              speechiness, the more popular (sweet spot is 0-0.10). Loudness also is a strong predictor of popularity as its sweet spot is -15 to -5 dBs. Lastly, instrumentalness       is like valence       where it's not a     strong predictor of popularity, though, an instrumentallness of 0 is most popular.
- For the 1921-1999 dataset (Dataset 2):
  - While focusing on track's/genre's respective popularities, key insights were found. The following analysis is from an "on average" perspective. The less acoustic, the more         popular      a track/genre is. Though, acousticness's impact on popularity is not strong. Energy's popularity sweet spot, which is measured between 0-1, hovers around 0.65-0.95         which is greater     than the file_2000_2023_spotify dataframe. The more danceable a track/genre, the more popular... 0.55-0.75 is the sweet spot just like the                     
    file_2000_2023_spotify dataframe. Valence is not a strong predictor of popularity while on the other hand, speechiness is. The less speechiness, the more popular (sweet spot 
    is 0-0.05). Loudness also is a strong predictor of popularity as its sweet spot is -15 to -5 dBs. Lastly, instrumentalness is like valence where it's not a strong predictor of 
    popularity, though, an instrumentalness of 0 is most popular.


## 4. Modeling via Supervised Machine Learning

Workbook [here](https://github.com/jackpaddock/Springboard-Data-Science-Boot-Camp/blob/master/Capstone%203%20Project/Capstone_3_Pre_processing_Work_and_Modeling_Final.ipynb)

I elected to work with Python's scikit-learn library, and I focused on [regression analysis](https://scikit-learn.org/stable/supervised_learning.html#supervised-learning). For Dataset 1, I dropped features 'artist_name', 'genre', 'time_signature', 'track_id', 'track_name' and for Dataset 2, I dropped features 'artist_name', 'explicit', 'id', 'track_name.' I tested the datasets on six models by allocating a 20%/80% test, train split with my target variable being the feature 'popularity.' For each dataset, the XGB regression model performed the best by a slight margins, so they were leveraged for respective predictions for each dataset.

![image](https://github.com/jackpaddock/Springboard-Data-Science-Boot-Camp/assets/129892021/0a2efd06-22d8-4581-9efe-a77f11e3356c)


![image](https://github.com/jackpaddock/Springboard-Data-Science-Boot-Camp/assets/129892021/fb3a80ec-8702-42be-8905-ffdc5ba2d52e)

> NOTE: I focused on RMSE, MAPE, and R Squared as my metrics to give me a more thorough understanding of the quality of the respective model performances. RMSE determines the absolute fit of the model to the data as it measures the average difference between a model's predicted values and its actual values. MAPE considers the sum of the individual absolute errors divided by the demand (each period separately). It is the average of the percentage errors. For both RMSE and MAPE, the lower the value the better. Finally, R Squared measures the proportion of variance in the dependent variable that can be explained by the independent variable. The greater the value the better. Vaguely, 0.65/65% or greater is considered pretty good.
>
> 

![B993CA44-136E-483B-94E7-6707DA211433_4_5005_c](https://github.com/jackpaddock/Springboard-Data-Science-Boot-Camp/assets/129892021/9fc195c5-72ef-459d-9e33-f5c511785cb2)

![A73F9C57-C089-4548-9D20-C84F1F4F1DC4_4_5005_c](https://github.com/jackpaddock/Springboard-Data-Science-Boot-Camp/assets/129892021/8bd65bea-e6bf-46d4-b5cb-23e8b519081c)

![4F3A9926-6AD5-4EFD-A688-D97DF29A6938_4_5005_c](https://github.com/jackpaddock/Springboard-Data-Science-Boot-Camp/assets/129892021/45759175-e1b1-4e55-8b3b-2b2dfe640120)

## 5. XGB Model Predictions

Workbook [here](https://github.com/jackpaddock/Springboard-Data-Science-Boot-Camp/blob/master/Capstone%203%20Project/Capstone_3_Pre_processing_Work_and_Modeling_Final.ipynb)

> NOTE: This is the same workbook as the modeling one above. The predictions are incorporated for each model. For more details regardiNG the XGB regression, see the modeling work towards the bottom of the workbook.
>
The first graph for each model shows the difference between the actual dependent feature vs the predicted dependent feature.

The model tied to Dataset 1 performs well at predicting 'popularity' by using all features tied to the X variable. 
![image](https://github.com/jackpaddock/Springboard-Data-Science-Boot-Camp/assets/129892021/29096af0-a214-4d44-be3f-5f4f02f7d57a)
![image](https://github.com/jackpaddock/Springboard-Data-Science-Boot-Camp/assets/129892021/49308f34-8bbd-4aba-a747-7df3e7050e48)

The model tied to Dataset 2 does not perform well at predicting 'popularity' by using all features tied to the X variable.
![image](https://github.com/jackpaddock/Springboard-Data-Science-Boot-Camp/assets/129892021/6f631d6c-a29b-4394-84cb-eef481c43769)
![image](https://github.com/jackpaddock/Springboard-Data-Science-Boot-Camp/assets/129892021/79e48d92-6dc7-4c18-ab6a-763d2f7d10f5)

## 6. Client Recommendations

Given the music industry's fluctuation over time:

- Stay up to date on trends and shifts in the industry year-over-year... it moves faster these days.
  - Remain flexible so one can cater more efficiently to trends and shifts.
- Cater venues/shows to feature the most popular artists to ensure profitability benchmarks are hit... so provide your target audience(s) with who they want, if possible.
  - Explore merchandise for most popular artists as well.
- Understand that track/artist/genre popularity varies by generation and that popularity is affected by numerous features varying from danceability, energy, loudness, valence and so on.
- For artists seeking to craft a popular track, be mindful of the most popular recent genres which are pop, hip-hop, dance and house among a few others. Being mindful of strong feature           correlations such as energy and loudness (strong positive) and  acousticness and energy or loudness (strong negative) will also aid in your creation process. 

## 7. Future Work

- Hit Spotify's API to pull more data tied to the years 1921-1999. The primary goal would be to have scale like Dataset 1 where the row count is over one million and where each      line item    is grouped by genre like Dataset 1. This thought assumes the results would be better than Dataset 2.
- Explore impact of cultural changes over time to understand its impact on genre popularity.
- Leverage an additional dataset to explore which regions or states in the U.S. or broader scale... which countries prefer which genres over time.
- Leverage an additional dataset, if available, to explore social media's impact on genre or artist popularity over time.

