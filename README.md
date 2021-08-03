# tableau_citibike

-----

Note: This repository is under development.

## Description
Analyze Citibike usage trends over time.

## Packages Used
Python (pandas, requests, zipfile, io, splinter, beautiful soup, webdriver_manager, os)

Tableau Public

## Step 1: Download the dataset
Used Python to scrape a list of urls for all of the citbike trip history csvs on
<a href="https://s3.amazonaws.com/tripdata/index.html" target="_blank">https://s3.amazonaws.com/tripdata/index.html</a>

## Step 2: Data Exploration
Determined that there were csvs for two cities within the dataset in Tableau by plotting station locations on a map.
* New York City Trip Data: YYYYMM-citibike-tripdata.csv
* Jersey City Trip Data:
JC-YYYYMM-citibike-tripdata.csv
![Data Locations](images/data_locations.png)

Used Python to determine that the datafiles had 3 distinct formats.

131 Files had this format
```plaintext
Data columns (total 16 columns):
 #   Column                   Non-Null Count  Dtype  
---  ------                   --------------  -----  
 0   tripduration             131 non-null    int64  
 1   starttime                131 non-null    object 
 2   stoptime                 131 non-null    object 
 3   start station id         131 non-null    int64  
 4   start station name       131 non-null    object 
 5   start station latitude   131 non-null    float64
 6   start station longitude  131 non-null    float64
 7   end station id           131 non-null    int64  
 8   end station name         131 non-null    object 
 9   end station latitude     131 non-null    float64
 10  end station longitude    131 non-null    float64
 11  bikeid                   131 non-null    int64  
 12  usertype                 131 non-null    object 
 13  birth year               128 non-null    object 
 14  gender                   131 non-null    int64
```

25 files from 2016 and 2017

```plaintext
Data columns (total 16 columns):
 #   Column                   Non-Null Count  Dtype  
---  ------                   --------------  -----  
 0   Trip Duration            25 non-null     int64  
 1   Start Time               25 non-null     object 
 2   Stop Time                25 non-null     object 
 3   Start Station ID         25 non-null     int64  
 4   Start Station Name       25 non-null     object 
 5   Start Station Latitude   25 non-null     float64
 6   Start Station Longitude  25 non-null     float64
 7   End Station ID           25 non-null     int64  
 8   End Station Name         25 non-null     object 
 9   End Station Latitude     25 non-null     float64
 10  End Station Longitude    25 non-null     float64
 11  Bike ID                  25 non-null     int64  
 12  User Type                25 non-null     object 
 13  Birth Year               25 non-null     int64  
 14  Gender                   25 non-null     int64
```

10 Files from 2021
```plaintext
Data columns (total 14 columns):
 #   Column              Non-Null Count  Dtype  
---  ------              --------------  -----  
 0   ride_id             10 non-null     object 
 1   rideable_type       10 non-null     object 
 2   started_at          10 non-null     object 
 3   ended_at            10 non-null     object 
 4   start_station_name  10 non-null     object 
 5   start_station_id    10 non-null     object 
 6   end_station_name    10 non-null     object 
 7   end_station_id      10 non-null     object 
 8   start_lat           10 non-null     float64
 9   start_lng           10 non-null     float64
 10  end_lat             10 non-null     float64
 11  end_lng             10 non-null     float64
 12  member_casual       10 non-null     object
```

## Step 3: Identify Data of Interest
Chose data from 2018 and 2019 for analysis.  These files have consistent formatting and are not disrupted by effects from the Covid-19 pandemic.


