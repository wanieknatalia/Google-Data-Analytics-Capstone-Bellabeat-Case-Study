# $\textcolor{#E9967A}{Bellabeat\ case\ study}$

![image1](https://github.com/wanieknatalia/Google-Data-Analytics-Capstone-Bellabeat-Case-Study/blob/main/images/image1.png)
---

# Table of contents

* [1. About a company](#chapter1)
* [2. Ask phase](#chapter2)
    * [2.1. Business task](#section_2_1)
    * [2.2. Key stakeholders](#section_2_2)
* [3. Prepare phase](#chapter3)
    * [3.1. Used data](#section_3_1)
    * [3.2. Accessibility and privacy of data](#section_3_2)
    * [3.3. Data organization](#section_3_3)
    * [3.4. Data limitations and integrity](#section_3_4)
* [4. Process phase](#chapter4)
    * [4.1. Tools selected](#section_4_1)
    * [4.2. Datasets selected](#section_4_2)
    * [4.3. Cleaning process](#section_4_3)
* [5. Analyze and share phases](#chapter5)
    * [5.1. SQL dataset upload](#section_5_1)
    * [5.2. Device wearing frequency](#section_5_2)
    * [5.3. Dataset limitation](#section_5_3)
        * [5.3.1. Users limitation](#section_5_3_1)
        * [5.3.2. Date limitation](#section_5_3_2)
        * [5.3.3. Creating new tables](#section_5_3_3)
    * [5.4. Device usage time](#section_5_4)
    * [5.5. User categories by daily activity](#section_5_5)
        * [5.5.1. User categories by total steps](#section_5_5_1)
        * [5.5.2. User categories by losing weight probability](#section_5_5_2)
        * [5.5.3. User categories by active minutes](#section_5_5_3)
    * [5.6. Average activity](#section_5_6)
        * [5.6.1. Average activity per day of the week](#section_5_6_1)
    * [5.7. Average total steps per day of the week](#section_5_7)
    * [5.8. FitBit Hourly Activity goal](#section_5_8)
    * [5.9. Total steps, intensity and calories by hour](#section_5_9)
        * [5.9.1 Relationship between total steps, intensities and calories](#section_5_9_1)
    * [5.10. Sleeping time](#section_5_10)
        * [5.10.1. Sleep per day of the week](#section_5_10_1)
* [6. Act phase](#chapter6)
    * [6.1. Conclusions & recommendations](#section_6_1)

# 1. About a company <a class="anchor"  id="chapter1"></a>

Bellabeat is a high-tech manufacturer of health-focused products for women. According to the information on the
company's website Bellabeat is the go-to wellness brand for women with an ecosystem of products and services focused on
women’s health. They develop wearables and accompanying products that monitor biometric and lifestyle data to help women
better understand how their bodies work and make healthier choices. Their mission is to empower women to reconnect with
themselves, unleash their inner strengths and be what they were meant to be. They focus on giving women the tools to
live in harmony with themselves.

Bellabeat offers various products targeted at women:

* Bellabeat app: The Bellabeat app provides users with health data related to their activity, sleep, stress, menstrual
  cycle and mindfulness habits. This data can help users better understand their current habits and make healthy
  decisions. The Bellabeat app connects to their line of smart wellness products.
* Leaf: Bellabeat’s classic wellness tracker can be worn as a bracelet, necklace, or clip. The Leaf tracker connects to
  the Bellabeat app to track activity, sleep and stress.
* Time: This wellness watch combines the timeless look of a classic timepiece with smart technology to track user
  activity, sleep and stress. The Time watch connects to the Bellabeat app to provide you with insights into your daily
  wellness.
* Spring: This is a water bottle that tracks daily water intake using smart technology to ensure that you are
  appropriately hydrated throughout the day. The Spring bottle connects to the Bellabeat app to track your hydration
  levels.
* Bellabeat membership: Bellabeat also offers a subscription-based membership program for users. Membership gives users
  24/7 access to fully personalized guidance on nutrition, activity, sleep, health and beauty and mindfulness based on
  their lifestyle and goals.

# 2. Ask phase <a class="anchor"  id="chapter2"></a>

## 2.1. Business task <a class="anchor"  id="section_2_1"></a>

The goal of this project is to analyze smart device fitness data to unlock new growth opportunities and guide marketing
strategy for the Bellabeat company. Analyzing smart device data will help to gain insight into how non-Bellabeat
consumers are using their smart devices. Conclusions resulting from this study will help determine the current needs of
Bellabeat brand users and define the further direction of product development.

## 2.2. Key stakeholders <a class="anchor"  id="section_2_2"></a>

* Urška Sršen: Bellabeat’s cofounder and Chief Creative Officer
* Sando Mur: Mathematician and Bellabeat’s cofounder; key member of the Bellabeat executive team,
* Bellabeat marketing analytics team

# 3. Prepare phase <a class="anchor"  id="chapter3"></a>

## 3.1. Used data <a class="anchor"  id="section_3_1"></a>

18 datasets were downloaded from the dataset published by Möbius to Kaggle.com. The datasets were downloaded in .csv
file format and included long and wide formats.

As described by the data provider the dataset is generated by respondents to a distributed survey via Amazon Mechanical
Turk between 12.03.2016-12.05.2016. Thirty eligible Fitbit users consented to the submission of personal tracker data,
including minute-level output for physical activity, heart rate and sleep monitoring.

## 3.2. Accessibility and privacy of data <a class="anchor"  id="section_3_2"></a>

The dataset was published by Möbius to Kaggle.com under the CC0: Public Domain Creative Common License – waiving all
rights to the work and allowing for the dataset to be copied, modified, distributed and performed without asking for
permission. Data has been cited from Furberg, R., Brinton, J., Keating, M., & Ortiz, A. (2016). Crowd-sourced Fitbit
datasets 03.12.2016-05.12.2016  [https://doi.org/10.5281/zenodo.53894](https://doi.org/10.5281/zenodo.53894)

## 3.3. Data organization <a class="anchor"  id="section_3_3"></a>

The datasets selected for the analysis included data on the activity of 33 users (except for sleeping time data - 24
users) over a period of 31 days (12.04.2016-12.05.2016).

## 3.4. Data limitations and integrity <a class="anchor"  id="section_3_4"></a>

The description of the dataset presented on the Kaggle website indicates that the study was conducted in the period from
12.03.2016 to 12.05.2016 for 30 eligible Fitbit users. During the analysis, I found that the period covered by the study
was in fact 31 days from 12.04.2016 to 12.05.2016 with a variable number of users depending on the file and the date of
the study. The maximum number of users whose data was measured was 33.

I detected some issues with bias - some files (heartrate_seconds_merged, weightLogInfo_merged) have only 7-8 users,
which is too little to do credible research. In most of the files the situation is better - sample size is 33 - but a
larger sample size would be more representative of the population. Due to the limited (up to 31 days) measurement period
the timeframe for a more insightful analysis is relatively small.

The analyzed data was collected in 2016, so the dataset may be outdated for current trend analysis.
It isn’t known who the participants of a research are, but after preliminary analysis, it can be concluded that the data
refers to more and less active users. However, considering that Bellabeat’s target audience are women, considering only
this gender in the analysis could lead to more trustworthy results.

# 4. Process phase <a class="anchor"  id="chapter4"></a>

## 4.1. Tools selected <a class="anchor"  id="section_4_1"></a>

I chose Google Sheets for cleaning data and SQL to analyze them. I used Tableau to create charts presenting the analysis
results.

## 4.2. Datasets selected <a class="anchor"  id="section_4_2"></a>

I chose following datasets for the analysis:

* sleepDay_merged
* hourlySteps_merged
* hourlyIntensities_merged
* hourlyCalories_merged
* dailyActivity_merged

I dropped heartrate_seconds_merged and weightLogInfo_merged files from analysis because of lack of credibility of the
data (non-representative sample of data, small number of measurements). I considered the remaining files to be too
detailed and irrelevant for this analysis.

## 4.3. Cleaning process <a class="anchor"  id="section_4_3"></a>

I verified the data using data cleaning tools and formulas in Google Sheets. I’ve noticed that data and time formats are
not consistent in most files. During cleaning process I’ve made following steps in each dataset:

* Formatting date data into YYYY-MM-DD date format.
* Formatting time data into 00:00:00 format for consistency.
* Sorting data by Id and date.
* Searching for unique users (24 in sleepDay_merged file, 33 in the remaining files) and dates (31 days,
  12.04-12.05.2016) within the dataset.
* Checking for duplicate data using conditional formatting - I found and removed 3 rows of duplicate information within
  the sleepDay_merged file.
* Formatting all numerical data into number format with either no decimals or up to 2 decimals.
* Separating date and hour into two columns when needed for later analysis.

# 5. Analyze and share phases <a class="anchor"  id="chapter5"></a>

## 5.1. SQL dataset upload <a class="anchor"  id="section_5_1"></a>

In BigQuery, I created a project called `nw-capstone-project-bellabeat` and uploaded the `bellabeat_data` dataset
containing the cleared tables into it.

## 5.2. Device wearing frequency <a class="anchor"  id="section_5_2"></a>

At the beginning, I focused on the file containing the most aggregated information about the daily use of the tracker by
users.

First, I checked how often users wore the tracker during the study period. I have divided them into the following
categories:

* episodic - if the tracker was worn from 0 to 15 times in a month
* moderate - if the tracker was worn 16 to 25 times in a month
* regular - if the tracker was worn more than 25 times in a month.

```sql
SELECT
  UsersTab.TrackerUserType,
  ROUND(COUNT(UsersTab.TrackerUserType)/(
    SELECT
      COUNT(DISTINCT Id)
    FROM
      `nw-capstone-project-bellabeat.bellabeat_data.dailyActivity_merged_0`)*100,2) AS PercentageOfUsers
FROM (
  SELECT
    Id,
    CASE
      WHEN COUNT(Id) BETWEEN 0 AND 15 THEN "Episodic"
      WHEN COUNT(Id) BETWEEN 16
    AND 25 THEN "Moderate"
    ELSE
    "Regular"
  END
    AS TrackerUserType,
  FROM
    `nw-capstone-project-bellabeat.bellabeat_data.dailyActivity_merged_0`
  GROUP BY
    Id) AS UsersTab
GROUP BY
  UsersTab.TrackerUserType
```

| TrackerUserType | PercentageOfUsers  |
|-----------------|--------------------|
| Regular         | 87.88              |
| Moderate        | 09.09              |
| Episodic        | 03.03              |

<img src="https://github.com/wanieknatalia/Google-Data-Analytics-Capstone-Bellabeat-Case-Study/blob/main/images/image5.2.png" width="680">

## 5.3. Dataset limitation <a class="anchor"  id="section_5_3"></a>

### 5.3.1. Users limitation <a class="anchor"  id="section_5_3_1"></a>

The above results made me wonder whether in the case of episodic tracker users the collected data will actually be
sufficient to conduct a reliable analysis and will not disturb the actual data trend. I decided to check the wearing
time of the tracker individually for each user.

```sql
SELECT
  Id,
  COUNT (DISTINCT ActivityDate) AS NumberOfActiveDays
FROM
  `nw-capstone-project-bellabeat.bellabeat_data.dailyActivity_merged_0`
GROUP BY
  Id
ORDER BY
  NumberOfActiveDays DESC
```
| Id	| NumberOfActiveDays|
|-----|------|
|1503960366|	31|
|1624580081	|31|
|1844505072|	31|
|1927972279	|31|
|2022484408	|31|
|2026352035	|31|
|2320127002	|31|
|2873212765	|31|
|4020332650	|31|
|4319703577	|31|
|4388161847	|31|
|4445114986	|31|
|4558609924	|31|
|4702921684	|31|
|5553957443	|31|
|6962181067	|31|
|7086361926	|31|
|8053475328	|31|
|8378563200	|31|
|8583815059	|31|
|8877689391	|31|
|1644430081	|30|
|3977333714	|30|
|5577150313	|30|
|6290855005	|29|
|8792009665	|29|
|6117666160	|28|
|6775888955	|26|
|7007744171	|26|
|3372868164	|20|
|8253242879	|19|
|2347167796	|18|
|4057192912|	4|

<img src="https://github.com/wanieknatalia/Google-Data-Analytics-Capstone-Bellabeat-Case-Study/blob/main/images/image5.3.1.1.png" width="680">

Based on [the outlier calculator](https://miniwebtool.com/outlier-calculator/), I determined that in the given
set, the data for 4 users with ID numbers:

* 2347167796,
* 3372868164,
* 4057192912 and
* 8253242879

differ from the other results.

Then I checked whether in the case of the other analyzed files there are also users with fewer measurements during the
month.

In the case of datasets in files `hourlyCalories_merged`, `hourlyIntensities_merged` and `hourlySteps_merged `the
results were identical, while the dataset in file `sleepDay_merged` was too dispersed to identify any outliers. I did
not exclude the data of users using the tracker for less than 26 days (as in other files) for fear of too small
statistical sample.

```sql
SELECT
  Id,
  COUNT (DISTINCT ActivityDay) AS NumberOfActiveDays
FROM
  `nw-capstone-project-bellabeat.bellabeat_data.hourlyCalories_merged`
GROUP BY
  Id
ORDER BY
  NumberOfActiveDays DESC
  ```

```sql
SELECT
  Id,
  COUNT (DISTINCT ActivityDay) AS NumberOfActiveDays
FROM
  `nw-capstone-project-bellabeat.bellabeat_data.hourlyIntensities_merged`
GROUP BY
  Id
ORDER BY
  NumberOfActiveDays DESC
  ```

  ```sql
SELECT
  Id,
  COUNT (DISTINCT ActivityDay) AS NumberOfActiveDays
FROM
  `nw-capstone-project-bellabeat.bellabeat_data.hourlySteps_merged`
GROUP BY
  Id
ORDER BY
  NumberOfActiveDays DESC
  ```
|Id	|NumberOfActiveDays|
|-----|-----|
|1624580081|	31|
|1844505072|	31|
|1927972279|	31|
|2022484408|	31|
|2026352035|	31|
|2320127002|	31|
|2873212765|	31|
|4020332650|	31|
|4319703577|	31|
|4388161847|	31|
|4445114986|	31|
|4558609924|	31|
|4702921684|	31|
|5553957443|	31|
|6962181067|	31|
|7086361926|	31|
|8053475328|	31|
|8378563200|	31|
|8877689391|	31|
|1503960366|	30|
|1644430081|	30|
|5577150313|	30|
|8583815059|	30|
|3977333714|	29|
|6117666160|	28|
|6290855005|	28|
|8792009665|	28|
|6775888955|	26|
|7007744171|	26|
|3372868164|	20|
|2347167796|	18|
|8253242879|	18|
|4057192912|	4|

<img src="https://github.com/wanieknatalia/Google-Data-Analytics-Capstone-Bellabeat-Case-Study/blob/main/images/image5.3.1.2.png" width="680">

```sql
SELECT
  Id,
  COUNT (DISTINCT SleepDay) AS NumberOfActiveDays
FROM
  `nw-capstone-project-bellabeat.bellabeat_data.sleepDay_merged`
GROUP BY
  Id
ORDER BY
  NumberOfActiveDays DESC
```
|Id|	NumberOfActiveDays|
|----|----|
|5553957443|	31|
|6962181067|	31|
|8378563200|	31|
|2026352035|	28|
|3977333714|	28|
|4445114986|	28|
|4702921684|	27|
|4319703577|	26|
|5577150313|	26|
|1503960366|	25|
|7086361926|	24|
|4388161847|	23|
|6117666160|	18|
|2347167796|	15|
|8792009665|	15|
|4020332650|	8|
|1927972279|	5|
|4558609924|	5|
|1644430081|	4|
|1844505072|	3|
|6775888955|	3|
|8053475328|	3|
|7007744171|	2|
|2320127002|	1|

<img src="https://github.com/wanieknatalia/Google-Data-Analytics-Capstone-Bellabeat-Case-Study/blob/main/images/image5.3.1.3.png" width="680">

### 5.3.2. Date limitation <a class="anchor"  id="section_5_3_2"></a>

Due to the limitations in the number of users actively using the tracker, I decided to check whether such limitations
also apply to the period of using the device. So I created queries already on limited sets, excluding inactive users. In
the case of files `dailyActivity_merged`, `hourlyCalories_merged`, `hourlyIntensities_merged` and `hourlySteps_merged`,
again using the outlier calculator mentioned above, I noted the dates when the number of users is insufficient to obtain
a reliable analysis result. It was the last 5 days of measurements, i.e. from 08.05.2016 to 12.05.2016.

```sql
SELECT
  ActivityDate,
  COUNT(DISTINCT Id) AS NumberOfUsers
FROM
  `nw-capstone-project-bellabeat.bellabeat_data.dailyActivity_merged_0`
WHERE
  Id NOT IN ("2347167796",
    "3372868164",
    "4057192912",
    "8253242879")
GROUP BY
  ActivityDate
```
|ActivityDate|	NumberOfUsers|
|---|---|
|2016-04-12|	29|
|2016-04-13|	29|
|2016-04-14|	29|
|2016-04-15|	29|
|2016-04-16|	29|
|2016-04-17|	29|
|2016-04-18|	29|
|2016-04-19|	29|
|2016-04-20|	29|
|2016-04-21|	29|
|2016-04-22|	29|
|2016-04-23|	29|
|2016-04-24|	29|
|2016-04-25|	29|
|2016-04-26|	29|
|2016-04-27|	29|
|2016-04-28|	29|
|2016-04-29|	29|
|2016-04-30|	29|
|2016-05-01|	29|
|2016-05-02|	29|
|2016-05-03|	29|
|2016-05-04|	29|
|2016-05-05|	29|
|2016-05-06|	29|
|2016-05-07|	29|
|2016-05-08|	27|
|2016-05-09|	27|
|2016-05-10|	26|
|2016-05-11|	24|
|2016-05-12|	21|

For files `hourlyCalories_merged`, `hourlyIntensities_merged` and `hourlySteps_merged` the query result was identical.

```sql
SELECT
  ActivityDay,
  COUNT(DISTINCT Id) AS NumberOfUsers
FROM
  `nw-capstone-project-bellabeat.bellabeat_data.hourlyCalories_merged`
WHERE
  Id NOT IN (2347167796,
    3372868164,
    4057192912,
    8253242879)
GROUP BY
  ActivityDay
```

```sql
SELECT
  ActivityDay,
  COUNT(DISTINCT Id) AS NumberOfUsers
FROM
  `nw-capstone-project-bellabeat.bellabeat_data.hourlyIntensities_merged`
WHERE
  Id NOT IN (2347167796,
    3372868164,
    4057192912,
    8253242879)
GROUP BY
  ActivityDay
```

```sql
SELECT
  ActivityDay,
  COUNT(DISTINCT Id) AS NumberOfUsers
FROM
  `nw-capstone-project-bellabeat.bellabeat_data.hourlySteps_merged`
WHERE
  Id NOT IN (2347167796,
    3372868164,
    4057192912,
    8253242879)
GROUP BY
  ActivityDay
``` 
|ActivityDay|	NumberOfUsers|
|----|----|
|2016-04-12|	29|
|2016-04-13|	29|
|2016-04-14|	29|
|2016-04-15|	29|
|2016-04-16|	29|
|2016-04-17|	29|
|2016-04-18|	29|
|2016-04-19|	29|
|2016-04-20|	29|
|2016-04-21|	29|
|2016-04-22|	29|
|2016-04-23|	29|
|2016-04-24|	29|
|2016-04-25|	29|
|2016-04-26|	29|
|2016-04-27|	29|
|2016-04-28|	29|
|2016-04-29|	29|
|2016-04-30|	29|
|2016-05-01|	29|
|2016-05-02|	29|
|2016-05-03|	29|
|2016-05-04|	29|
|2016-05-05|	29|
|2016-05-06|	29|
|2016-05-07|	29|
|2016-05-08|	27|
|2016-05-09|	27|
|2016-05-10|	24|
|2016-05-11|	23|
|2016-05-12|	19|

In the query for the dataset `sleepDay_merged`, all users were considered and, once again, due to the dispersed
measurement values, it was not possible to identify outliers.

```sql
SELECT
  SleepDay,
  COUNT(DISTINCT Id) AS NumberOfUsers
FROM
  `nw-capstone-project-bellabeat.bellabeat_data.sleepDay_merged`
GROUP BY
  SleepDay
ORDER BY
  SleepDay
```
|SleepDay|	NumberOfUsers|
|----|----|
|2016-04-12|	13|
|2016-04-13|	14|
|2016-04-14|	13|
|2016-04-15|	17|
|2016-04-16|	14|
|2016-04-17|	12|
|2016-04-18|	10|
|2016-04-19|	14|
|2016-04-20|	15|
|2016-04-21|	15|
|2016-04-22|	13|
|2016-04-23|	15|
|2016-04-24|	13|
|2016-04-25|	12|
|2016-04-26|	14|
|2016-04-27|	14|
|2016-04-28|	16|
|2016-04-29|	15|
|2016-04-30|	15|
|2016-05-01|	16|
|2016-05-02|	13|
|2016-05-03|	12|
|2016-05-04|	12|
|2016-05-05|	12|
|2016-05-06|	12|
|2016-05-07|	13|
|2016-05-08|	14|
|2016-05-09|	11|
|2016-05-10|	12|
|2016-05-11|	11|
|2016-05-12|	8|

### 5.3.3. Creating new tables <a class="anchor"  id="section_5_3_3"></a>

As the data had already been properly cleaned, I relied on data limited to 29 users and 26 days for further analysis.
For this purpose, for each analyzed file (except `sleepDay_merged`) I created new limited tables that I used instead of
the base file.

```sql
CREATE TABLE
  bellabeat_data.dailyActivity_merged_limited AS (
  SELECT
    *
  FROM
    `nw-capstone-project-bellabeat.bellabeat_data.dailyActivity_merged_0`
  WHERE
    Id NOT IN ("2347167796",
      "3372868164",
      "4057192912",
      "8253242879")
    AND ActivityDate NOT IN ("2016-05-08",
      "2016-05-09",
      "2016-05-10",
      "2016-05-11",
      "2016-05-12") )
```

```sql
CREATE TABLE
  bellabeat_data.hourlySteps_merged_limited AS (
  SELECT
    *
  FROM
    `nw-capstone-project-bellabeat.bellabeat_data.hourlySteps_merged`
  WHERE
    Id NOT IN (2347167796,
      3372868164,
      4057192912,
      8253242879)
    AND ActivityDay NOT IN ("2016-05-08",
      "2016-05-09",
      "2016-05-10",
      "2016-05-11",
      "2016-05-12") ) 
```

```sql
CREATE TABLE
  bellabeat_data.hourlyIntensities_merged_limited AS (
  SELECT
    *
  FROM
    `nw-capstone-project-bellabeat.bellabeat_data.hourlyIntensities_merged`
  WHERE
    Id NOT IN (2347167796,
      3372868164,
      4057192912,
      8253242879)
    AND ActivityDay NOT IN ("2016-05-08",
      "2016-05-09",
      "2016-05-10",
      "2016-05-11",
      "2016-05-12") )
```

 ```sql
CREATE TABLE
  bellabeat_data.hourlyCalories_merged_limited AS (
  SELECT
    *
  FROM
    `nw-capstone-project-bellabeat.bellabeat_data.hourlyCalories_merged`
  WHERE
    Id NOT IN (2347167796,
      3372868164,
      4057192912,
      8253242879)
    AND ActivityDay NOT IN ("2016-05-08",
      "2016-05-09",
      "2016-05-10",
      "2016-05-11",
      "2016-05-12") ) 
 ```

## 5.4. Device usage time <a class="anchor"  id="section_5_4"></a>

Next I focused on the final analysis of the data. I started with the table `dailyActivity_merged_limited`.

I checked the number of logins and users in the new configuration. The result is 29 users measuring for 26 days - no
other configurations were recorded.

```sql
SELECT
  UserTab.NumberOfLogins,
  COUNT(UserTab.NumberOfLogins) AS NumberOfUsersLogged
FROM (
  SELECT
    Id,
    COUNT(Id) AS NumberOfLogins,
  FROM
    `nw-capstone-project-bellabeat.bellabeat_data.dailyActivity_merged_limited`
  GROUP BY
    Id) AS UserTab
GROUP BY
  UserTab.NumberOfLogins
ORDER BY
  UserTab.NumberOfLogins DESC
```

|NumberOfLogins	| NumberOfUsersLogged |
|-----|---------------------|
|  26| 29                  |

I also checked what percentage of users wore the tracker during the day. Of the active users of the application, there
was almost a 50/50 split between users wearing the tracker over more than 90% of the time during the day and those
wearing it more than 50% of the time during the day. In the study group there were no people whose average time of using
the device was less than half of the day.

```sql
SELECT
  DISTINCT TotalWearingPercentage.Id,
  CASE
    WHEN AVG(TotalWearingPercentage.PercentageOfTotalMinutesWorn) > 90 THEN "Almost all day"
    WHEN AVG(TotalWearingPercentage.PercentageOfTotalMinutesWorn) > 50
  AND AVG( TotalWearingPercentage.PercentageOfTotalMinutesWorn) <= 90 THEN "More than half a day"
  ELSE
  "Less than half a day"
END
  AS TrackerWearingTime
FROM (
  SELECT
    Id,
    ActivityDate,
    (SUM(SedentaryMinutes) + SUM(LightlyActiveMinutes) + SUM(FairlyActiveMinutes) + SUM(VeryActiveMinutes))/24/60*100 AS PercentageOfTotalMinutesWorn,
  FROM
    `nw-capstone-project-bellabeat.bellabeat_data.dailyActivity_merged_limited`
  GROUP BY
    Id,
    ActivityDate) AS TotalWearingPercentage
GROUP BY
  TotalWearingPercentage.Id
```
|Id|	TrackerWearingTime|
|----|----|
|1503960366|	More than half a day|
|1624580081|	Almost all day|
|1644430081|	Almost all day|
|1844505072|	Almost all day|
|1927972279|	Almost all day|
|2022484408|	Almost all day|
|2026352035|	More than half a day|
|2320127002|	Almost all day|
|2873212765|	Almost all day|
|3977333714|	More than half a day|
|4020332650|	Almost all day|
|4319703577|	More than half a day|
|4388161847|	More than half a day|
|4445114986|	More than half a day|
|4558609924|	Almost all day|
|4702921684|	More than half a day|
|5553957443|	More than half a day|
|5577150313|	More than half a day|
|6117666160|	More than half a day|
|6290855005|	Almost all day|
|6775888955|	Almost all day|
|6962181067|	More than half a day|
|7007744171|	Almost all day|
|7086361926|	More than half a day|
|8053475328|	Almost all day|
|8378563200|	More than half a day|
|8583815059|	Almost all day|
|8792009665|	More than half a day|
|8877689391|	Almost all day|

<img src="https://github.com/wanieknatalia/Google-Data-Analytics-Capstone-Bellabeat-Case-Study/blob/main/images/image5.4.png" width="680">

## 5.5. User categories by daily activity <a class="anchor"  id="section_5_5"></a>

The average number of steps taken during the day for the whole group was 7770,76, the average distance was 5,60 units (
there was no information about the entity in the source data or in the description of the data set) and the average
number of calories burned was 2371,85.

```sql
SELECT
  ROUND(AVG(TotalSteps),2) AS AverageSteps,
  ROUND(AVG(TotalDistance),2) AS AverageTotalDistance,
  ROUND(AVG(Calories),2) AS AverageCalories
FROM
  `nw-capstone-project-bellabeat.bellabeat_data.dailyActivity_merged_limited`
```

|   AverageSteps  |  AverageTotalDistance   |  AverageCalories   |
|-----|-----|-----|
|  7770,76   |  5,60   |  2371,85   |

### 5.5.1. User categories by total steps <a class="anchor"  id="section_5_5_1"></a>

In an
article ["How Many Steps a Day Is Considered Active?"](https://www.medicinenet.com/how_many_steps_a_day_is_considered_active/article.htm)
Pallavi Suyog Uttekar, MD pointed out that according to studies people who walk anywhere between 7500 and 10000 steps
per day can improve blood sugar levels, lower blood pressure and help improve symptoms of depression and anxiety. With
the result 7770,76 the study group as a whole met the above-described recommendations.

The author of the article made also the following classification of daily activity in terms of steps taken during the
day:

* Sedentary: Less than 5000 steps daily
* Low active: About 5000 to 7499 steps daily
* Somewhat active: About 7500 to 9999 steps daily
* Active: More than 10000 steps daily
* Highly active: More than 12500 steps daily

I checked the average number of steps taken by each of the study participants. I used the above classification to check
how many users fall into each activity category.

It turned out that the largest number are sedentary users, low active users and somehow active users. Much less are more
active users.

```sql
SELECT
  UserTab.UserCategory,
  COUNT(DISTINCT UserTab.Id) AS NumberOfUsers
FROM (
  SELECT
    Id,
    CASE
      WHEN AVG(TotalSteps) < 5000 THEN "Sedentary User"
      WHEN AVG(TotalSteps) >= 5000
    AND AVG(TotalSteps) <7500 THEN "Low Active User"
      WHEN AVG(TotalSteps) >= 7500 AND AVG(TotalSteps) <10000 THEN "Somewhat Active User"
      WHEN AVG(TotalSteps) >= 10000
    AND AVG(TotalSteps) <12500 THEN "Active User"
    ELSE
    "Highly Active User"
  END
    AS UserCategory
  FROM
    `nw-capstone-project-bellabeat.bellabeat_data.dailyActivity_merged_limited`
  GROUP BY
    Id) AS UserTab
GROUP BY
  UserTab.UserCategory
```

|   UserCategory  | NumberOfUsers |
|-----|---------------|
|  Highly Active User   | 3 |
|   Low Active User  | 7 |
|   Sedentary User  | 7 |
|  Active User   | 5 |
|   Somewhat Active User  | 7 

<img src="https://github.com/wanieknatalia/Google-Data-Analytics-Capstone-Bellabeat-Case-Study/blob/main/images/image5.5.1.png" width="680">

### 5.5.2. User categories by losing weight probability <a class="anchor"  id="section_5_5_2"></a>

According to [Cleveland Clinic's article](https://health.clevelandclinic.org/calories-burned-in-a-day/), over the course
of a day, people's natural calorie burn without any activity can range from 1300 to more than 2000, depending on their
age and sex.

Assuming that it needs to burn at least 2000 calories a day to lose weight effectively, 72,41% of participants on
average per day exceeded this threshold during the study period. With the result 2371,85 the study group met the
above-described recommendations.

```sql
SELECT
  ProbabilityTab.LosingWeightProbability,
  ROUND(COUNT(DISTINCT ProbabilityTab.Id)/(
    SELECT
      COUNT(DISTINCT Id)
    FROM
      `nw-capstone-project-bellabeat.bellabeat_data.dailyActivity_merged_limited`)*100,2) AS PercentOfUsers
FROM (
  SELECT
    Id,
    CASE
      WHEN AVG(Calories) < 2000 THEN "Weight loss less likely"
    ELSE
    "Weight loss more likely"
  END
    AS LosingWeightProbability
  FROM
    `nw-capstone-project-bellabeat.bellabeat_data.dailyActivity_merged_limited`
  GROUP BY
    Id) AS ProbabilityTab
GROUP BY
  ProbabilityTab.LosingWeightProbability
```

|   LosingWeightProbability  |    PercentOfUsers |
|-----|-----|
|   Weight loss less likely  |   0.27586206896551724  |
|   Weight loss more likely  |   0.72413793103448276  |

<img src="https://github.com/wanieknatalia/Google-Data-Analytics-Capstone-Bellabeat-Case-Study/blob/main/images/image5.5.2.png" width="680">

### 5.5.3. User categories by active minutes <a class="anchor"  id="section_5_5_3"></a>

According to [CDC recommendations](https://www.cdc.gov/physicalactivity/basics/adults/index.htm), each week adults need
150 minutes of moderate-intensity physical activity or 75 minutes a week of vigorous-intensity activity or an equivalent
combination to gain more health benefits.

In connection with the above, I determined whether the participants of the study met the given criteria. For this
purpose, I checked whether the sum of very active minutes and fairly active minutes for each user during the week is
greater than 150 or whether very active minutes alone is greater than 75. It turns out that the majority of people
participating in the study (58,6%) are able to maintain a weekly activity at an appropriate level.

```sql
SELECT
  Id,
  CASE
    WHEN (SUM(FairlyActiveMinutes) + SUM(VeryActiveMinutes))/(COUNT(DISTINCT ActivityDate)/7) >= 150 OR SUM( VeryActiveMinutes)/(COUNT(DISTINCT ActivityDate)/7) >= 75 THEN "Active person"
  ELSE
  "Non-active person"
END
  AS AvgActivity,
FROM
  `nw-capstone-project-bellabeat.bellabeat_data.dailyActivity_merged_limited`
GROUP BY
  Id
```
|Id|	AvgActivity|
|----|----|
|1624580081|	Non-active person|
|1644430081|	Active person|
|2022484408|	Active person|
|3977333714|	Active person|
|4319703577|	Non-active person|
|4388161847|	Active person|
|4702921684|	Active person|
|5577150313|	Active person|
|6775888955|	Active person|
|7007744171|	Active person|
|7086361926|	Active person|
|8583815059|	Active person|
|1844505072|	Non-active person|
|1927972279|	Non-active person|
|2026352035|	Non-active person|
|2320127002|	Non-active person|
|2873212765|	Active person|
|4020332650|	Non-active person|
|4445114986|	Non-active person|
|4558609924|	Non-active person|
|5553957443|	Active person|
|6117666160|	Non-active person|
|6290855005|	Non-active person|
|6962181067|	Active person|
|8053475328|	Active person|
|8378563200|	Active person|
|8792009665|	Non-active person|
|8877689391|	Active person|
|1503960366|	Active person|

<img src="https://github.com/wanieknatalia/Google-Data-Analytics-Capstone-Bellabeat-Case-Study/blob/main/images/image5.5.3.png" width="680">

## 5.6. Average activity <a class="anchor"  id="section_5_6"></a>

Based on the average amount of very active, fairly active, lightly active and sedentary minutes I checked what type of
activity prevails in the research group during the day. More than 80% of the time during the day was spent sedentary.

```sql
SELECT
  ROUND(AVG(VeryActiveMinutes),2) AS AvgOfVeryActiveMinutes,
  ROUND(AVG(FairlyActiveMinutes),2) AS AvgOfFairlyActiveMinutes,
  ROUND(AVG(LightlyActiveMinutes),2) AS AvgOfLightlyActiveMinutes,
  ROUND(AVG(SedentaryMinutes),2) AS AvgOfSedentaryMinutes
FROM
  `nw-capstone-project-bellabeat.bellabeat_data.dailyActivity_merged_limited`
```

|   AvgOfVeryActiveMinutes  | AvgOfFairlyActiveMinutes    |   AvgOfLightlyActiveMinutes  | AvgOfSedentaryMinutes    |
|-----|-----|-----|-----|
|   22.242705570291765  |   13.602122015915125  | 193.52652519893905    |   1003.0835543766563  |

<img src="https://github.com/wanieknatalia/Google-Data-Analytics-Capstone-Bellabeat-Case-Study/blob/main/images/image5.6.png" width="680">

### 5.6.1. Average activity per day of the week <a class="anchor"  id="section_5_6_1"></a>

I also decided to check how this activity is distributed during the week. Participants spent the most hours in a sitting
position on Mondays and the least - on Saturdays.

Interestingly, Mondays were also the days of the highest activity with a high level of intensity. I assume there is a
tendency to start intensive, ambitious training at the beginning of the week and lose motivation to continue exercising
in the following days.

```sql
SELECT
  CASE
    WHEN EXTRACT(DAYOFWEEK FROM ActivityDate) = 1 THEN "Sunday"
    WHEN EXTRACT(DAYOFWEEK
  FROM
    ActivityDate) = 2 THEN "Monday"
    WHEN EXTRACT(DAYOFWEEK FROM ActivityDate) = 3 THEN "Tuesday"
    WHEN EXTRACT(DAYOFWEEK
  FROM
    ActivityDate) = 4 THEN "Wednesday"
    WHEN EXTRACT(DAYOFWEEK FROM ActivityDate) = 5 THEN "Thursday"
    WHEN EXTRACT(DAYOFWEEK
  FROM
    ActivityDate) = 6 THEN "Friday"
    WHEN EXTRACT(DAYOFWEEK FROM ActivityDate) = 7 THEN "Saturday"
END
  AS DayOfWeek,
  ROUND(AVG(SedentaryMinutes),2) AS AvgSedentaryMinutesByDayOfWeek,
  ROUND(AVG(LightlyActiveMinutes),2) AS AvgLightlyActiveMinutesByDayOfWeek,
  ROUND(AVG(FairlyActiveMinutes),2) AS AvgFairlyActiveMinutesByDayOfWeek,
  ROUND(AVG(VeryActiveMinutes),2) AS AvgVeryActiveMinutesByDayOfWeek
FROM
  `nw-capstone-project-bellabeat.bellabeat_data.dailyActivity_merged_limited`
GROUP BY
  DayOfWeek
```
|DayOfWeek|	AvgSedentaryMinutesByDayOfWeek|	AvgLightlyActiveMinutesByDayOfWeek|	AvgFairlyActiveMinutesByDayOfWeek|	AvgVeryActiveMinutesByDayOfWeek|
|----|----|----|----|----|
|Monday|	1046.3|	185.34|	13.31|	23.99|
|Sunday|	1002.72|	165.83|	14.53|	21.25|
|Saturday|	955.11|	205.11|	14.61|	21.96|
|Friday|	1003.22|	205.54|	12.54|	21.53|
|Tuesday|	1012.47|	196.77|	14.28|	23.72|
|Thursday|	1008.33|	199.85|	13.39|	22.66|
|Wednesday|	1004.14|	187.27|	12.72|	20.78|

<img src="https://github.com/wanieknatalia/Google-Data-Analytics-Capstone-Bellabeat-Case-Study/blob/main/images/image5.6.1.1.png" width="680">
<img src="https://github.com/wanieknatalia/Google-Data-Analytics-Capstone-Bellabeat-Case-Study/blob/main/images/image5.6.1.2.png" width="680">
<img src="https://github.com/wanieknatalia/Google-Data-Analytics-Capstone-Bellabeat-Case-Study/blob/main/images/image5.6.1.3.png" width="680">
<img src="https://github.com/wanieknatalia/Google-Data-Analytics-Capstone-Bellabeat-Case-Study/blob/main/images/image5.6.1.4.png" width="680">

## 5.7. Average total steps per day of the week <a class="anchor"  id="section_5_7"></a>

I checked how the average number of steps performed by all users of the application was distributed during the week. It
turned out that the most active day in terms of the number of steps taken was Tuesday and the least active - Sunday.

```sql
SELECT
  CASE
    WHEN EXTRACT(DAYOFWEEK FROM ActivityDate) = 1 THEN "Sunday"
    WHEN EXTRACT(DAYOFWEEK
  FROM
    ActivityDate) = 2 THEN "Monday"
    WHEN EXTRACT(DAYOFWEEK FROM ActivityDate) = 3 THEN "Tuesday"
    WHEN EXTRACT(DAYOFWEEK
  FROM
    ActivityDate) = 4 THEN "Wednesday"
    WHEN EXTRACT(DAYOFWEEK FROM ActivityDate) = 5 THEN "Thursday"
    WHEN EXTRACT(DAYOFWEEK
  FROM
    ActivityDate) = 6 THEN "Friday"
    WHEN EXTRACT(DAYOFWEEK FROM ActivityDate) = 7 THEN "Saturday"
END
  AS DayOfWeek,
  ROUND(AVG(TotalSteps),2) AS AvgTotalStepsByDayOfWeek
FROM
  `nw-capstone-project-bellabeat.bellabeat_data.dailyActivity_merged_limited`
GROUP BY
  DayOfWeek
```

|  DayOfWeek   | AvgTotalStepsByWeekDay    |
|-----|-----|
|   Sunday  |  6856.64367816092   |
|  Tuesday   |    8288.948275862067 |
|    Thursday |  8167.6551724137935   |
|  Saturday   |   8049.4396551724158  |
|  Wednesday   |  7477.9310344827554   |
|    Friday |   7620.6637931034466  |
|  Monday   |  7683.7241379310371   |

<img src="https://github.com/wanieknatalia/Google-Data-Analytics-Capstone-Bellabeat-Case-Study/blob/main/images/image5.7.png" width="680">

## 5.8. FitBit Hourly Activity goal <a class="anchor"  id="section_5_8"></a>

The data that was the source of data for the analysis in question was collected by the FitBit tracker. One of the
functionalities of this device is to remind you to take at least 250 steps per hour within 9 hours (standard from 9:00
to 17:00, 7 days a week). I decided to check in what percentage each of the users managed to complete this challenge
during the month of measurements. Interestingly, among the users there were both those who completed the study with a
score of 100% and those who achieved a score of 0%. The average for the whole group was 72,83%.

```sql
SELECT
  Id,
  ROUND(COUNTIF(Tab1.AvgStepTotalPerHour > 250)/9,2)*100 AS HittingHourlyActivityGoalPercentage,
FROM (
  SELECT
    DISTINCT ActivityHour,
    Id,
    ROUND(AVG(StepTotal),2) AS AvgStepTotalPerHour
  FROM
    `nw-capstone-project-bellabeat.bellabeat_data.hourlySteps_merged_limited`
  WHERE
    ActivityHour BETWEEN "09:00:00"
    AND "17:00:00"
  GROUP BY
    Id,
    ActivityHour) AS Tab1
GROUP BY
  Id
```
|Id|	HittingHourlyActivityGoalPercantage|
|----|----|
|8053475328|	67|
|1644430081|	78|
|4558609924|	100|
|4319703577|	89|
|2320127002|	33|
|1503960366|	100|
|8877689391|	100|
|4388161847|	100|
|6775888955|	11|
|5553957443|	89|
|7086361926|	67|
|2873212765|	100|
|6290855005|	89|
|5577150313|	100|
|4445114986|	44|
|4020332650|	0|
|6117666160|	100|
|8378563200|	100|
|8583815059|	89|
|2026352035|	89|
|7007744171|	100|
|1927972279|	0|
|2022484408|	100|
|8792009665|	0|
|6962181067|	78|
|3977333714|	89|
|4702921684|	100|
|1844505072|	22|
|1624580081|	78|

<img src="https://github.com/wanieknatalia/Google-Data-Analytics-Capstone-Bellabeat-Case-Study/blob/main/images/image5.8.png" width="680">

## 5.9. Total steps, intensity and calories by hour <a class="anchor"  id="section_5_9"></a>

In order to examine the average number of steps depending on the hour, I analyzed the file `hourlySteps_merged_limited`.
18:00 was the time with the highest number of steps taken. This is probably due to the ability to devote more time to
activity after work. At 11:00 and 15:00 there was a noticeable decrease in the number of steps taken on the activity
curve.

```sql
SELECT
  ActivityHour,
  ROUND(AVG(StepTotal),2) AS AverageStepTotal
FROM
  `nw-capstone-project-bellabeat.bellabeat_data.hourlySteps_merged_limited`
GROUP BY
  ActivityHour
```
|ActivityHour|	AverageStepTotal|
|----|----|
|00:00:00|	47.586206896551687|
|01:00:00|	26.52589641434265|
|02:00:00|	17.864541832669303|
|03:00:00|	7.29216467463479|
|04:00:00|	13.65869853917663|
|05:00:00|	46.723771580345293|
|06:00:00|	191.40504648074406|
|07:00:00|	302.0916334661357|
|08:00:00|	430.97211155378494|
|09:00:00|	453.83798140770233|
|10:00:00|	464.06648936170217|
|11:00:00|	423.7978723404259|
|12:00:00|	541.31250000000011|
|13:00:00|	519.74601063829709|
|14:00:00|	531.70877659574467|
|15:00:00|	407.12765957446862|
|16:00:00|	496.55585106382972|
|17:00:00|	548.61037234042578|
|18:00:00|	591.6941489361709|
|19:00:00|	587.0545212765951|
|20:00:00|	350.88696808510656|
|21:00:00|	294.80585106382927|
|22:00:00|	250.75531914893597|
|23:00:00|	119.59308510638313|

<img src="https://github.com/wanieknatalia/Google-Data-Analytics-Capstone-Bellabeat-Case-Study/blob/main/images/image5.9.1.png" width="680">

In the case of the average intensity during the day, similar to the average number of steps taken, the lowest recorded
value was at 3:00 and the highest at 18:00, with drops at 11:00 and 15:00. The same results were obtained for the
average number of calories burned per day.

```sql
SELECT
  ActivityHour,
  ROUND(AVG(TotalIntensity),2) AS AverageTotalIntensity
FROM
  `nw-capstone-project-bellabeat.bellabeat_data.hourlyIntensities_merged_limited`
GROUP BY
  ActivityHour
```
|ActivityHour|	AverageTotalIntensity|
|----|----|
|00:00:00|	2.3408488063660471|
|01:00:00|	1.5936254980079685|
|02:00:00|	1.1208499335989377|
|03:00:00|	0.48207171314741043|
|04:00:00|	0.66666666666666663|
|05:00:00|	5.00398406374502|
|06:00:00|	8.2124833997344|
|07:00:00|	10.689243027888446|
|08:00:00|	14.715803452855242|
|09:00:00|	15.828685258964139|
|10:00:00|	17.022606382978726|
|11:00:00|	16.057180851063819|
|12:00:00|	19.501329787234045|
|13:00:00|	18.31515957446808|
|14:00:00|	18.203457446808514|
|15:00:00|	15.3311170212766|
|16:00:00|	17.530585106382979|
|17:00:00|	21.534574468085093|
|18:00:00|	22.065159574468076|
|19:00:00|	21.513297872340431|
|20:00:00|	14.176861702127654|
|21:00:00|	11.722074468085108|
|22:00:00|	9.321808510638304|
|23:00:00|	4.9773936170212778|

<img src="https://github.com/wanieknatalia/Google-Data-Analytics-Capstone-Bellabeat-Case-Study/blob/main/images/image5.9.2.png" width="680">

```sql
SELECT
  ActivityHour,
  ROUND(AVG(Calories),2) AS AverageCalories
FROM
  `nw-capstone-project-bellabeat.bellabeat_data.hourlyCalories_merged_limited`
GROUP BY
  ActivityHour
```
|ActivityHour|	AverageCalories|
|----|----|
|00:00:00|	73.08222811671088|
|01:00:00|	71.3014608233731|
|02:00:00|	70.06241699867202|
|03:00:00|	68.285524568393058|
|04:00:00|	69.013280212483423|
|05:00:00|	82.674634794156617|
|06:00:00|	88.946879150066479|
|07:00:00|	95.6533864541833|
|08:00:00|	104.54581673306771|
|09:00:00|	108.66799468791498|
|10:00:00|	110.39893617021286|
|11:00:00|	108.86835106382971|
|12:00:00|	118.00664893617028|
|13:00:00|	115.63031914893612|
|14:00:00|	115.89228723404261|
|15:00:00|	107.46941489361699|
|16:00:00|	114.00930851063835|
|17:00:00|	123.23803191489367|
|18:00:00|	125.22473404255314|
|19:00:00|	122.875|
|20:00:00|	103.24734042553192|
|21:00:00|	96.402925531914875|
|22:00:00|	90.168882978723431|
|23:00:00|	78.472074468085125|

<img src="https://github.com/wanieknatalia/Google-Data-Analytics-Capstone-Bellabeat-Case-Study/blob/main/images/image5.9.3.png" width="680">

### 5.9.1 Relationship between total steps, intensities and calories <a class="anchor"  id="section_5_9_1"></a>

Above results confirm the quite obvious close correlation between intensity, number of steps and calories burned.
However, in order to visually present the above thesis, I additionally compared all these values with each other.

```sql
SELECT
  CaloriesTab.ActivityHour,
  ROUND(AVG(CaloriesTab.Calories),2) AS AverageCalories,
  ROUND(AVG(StepsTab.StepTotal),2) AS AverageStepTotal,
FROM
  `nw-capstone-project-bellabeat.bellabeat_data.hourlyCalories_merged_limited` AS CaloriesTab
INNER JOIN
  `nw-capstone-project-bellabeat.bellabeat_data.hourlySteps_merged_limited` AS StepsTab
ON
  CaloriesTab.ActivityHour = StepsTab.ActivityHour
GROUP BY
  CaloriesTab.ActivityHour
```
|ActivityHour|	AverageCalories|	AverageStepTotal|
|----|----|----|
|00:00:00|	73.082228116711121|	47.586206896551253|
|01:00:00|	71.30146082337312|	26.525896414342931|
|02:00:00|	|70.062416998671608|	17.864541832669296|
|03:00:00|	68.2855245683965|	7.29216467463477|
|04:00:00|	69.013280212483778|	13.658698539176626|
|05:00:00|	82.674634794160653|	46.7237715803428|
|06:00:00|	88.946879150065314|	191.40504648074338|
|07:00:00|	95.653386454183675|	302.09163346614292|
|08:00:00|	104.54581673306998|	430.97211155378636|
|09:00:00|	108.66799468791518|	453.83798140770807|
|10:00:00|	110.39893617021325|	464.06648936171848|
|11:00:00|	108.86835106382946|	423.79787234041817|
|12:00:00|	118.00664893617123|	541.31249999999613|
|13:00:00|	115.63031914893264|	519.7460106383|
|14:00:00|	115.89228723404281|	531.708776595733|
|15:00:00|	107.46941489361585|	407.12765957447533|
|16:00:00|	114.00930851063811|	496.555851063828|
|17:00:00|	123.23803191489303|	548.61037234044272|
|18:00:00|	125.22473404255433|	591.69414893616806|
|19:00:00|	122.87500000000284|	587.0545212766217|
|20:00:00|	103.24734042553101|	350.88696808511196|
|21:00:00|	96.402925531914576|	294.8058510638316|
|22:00:00|	90.168882978723545|	250.75531914894074|
|23:00:00|	78.47207446808379|	119.59308510638031|

<img src="https://github.com/wanieknatalia/Google-Data-Analytics-Capstone-Bellabeat-Case-Study/blob/main/images/image5.9.1.1.png" width="680">

```sql
SELECT
  CaloriesTab.ActivityHour,
  ROUND(AVG(CaloriesTab.Calories),2) AS AverageCalories,
  ROUND(AVG(IntensitiesTab.TotalIntensity),2) AS AverageTotalIntensity
FROM
  `nw-capstone-project-bellabeat.bellabeat_data.hourlyCalories_merged_limited` AS CaloriesTab
INNER JOIN
  `nw-capstone-project-bellabeat.bellabeat_data.hourlyIntensities_merged_limited` AS IntensitiesTab
ON
  CaloriesTab.ActivityHour = IntensitiesTab.ActivityHour
GROUP BY
  CaloriesTab.ActivityHour
```
|ActivityHour|	AverageCalories|	AverageTotalIntensity|
|----|----|----|
|00:00:00|	73.082228116710439|	2.3408488063661017|
|01:00:00|	71.301460823373333|	1.5936254980079474|
|02:00:00|	70.062416998673683|	1.1208499335989415|
|03:00:00|	68.285524568393456|	0.48207171314740793|
|04:00:00|	69.013280212483991|	0.6666666666666583|
|05:00:00|	82.67463479415629|	5.0039840637450075|
|06:00:00|	88.9468791500665|	8.2124833997342765|
|07:00:00|	95.653386454185252|	10.689243027888448|
|08:00:00|	104.54581673306251|	14.715803452855207|
|09:00:00|	108.66799468791524|	15.828685258964107|
|10:00:00|	110.3989361702146|	17.02260638297977|
|11:00:00|	108.86835106382991|	16.057180851064082|
|12:00:00|	118.00664893617194|	19.501329787232958|
|13:00:00|	115.63031914893355|	18.315159574468076|
|14:00:00|	115.89228723404553|	18.203457446808873|
|15:00:00|	107.4694148936176|	15.331117021276613|
|16:00:00|	114.00930851064142|	17.530585106383167|
|17:00:00|	123.23803191489502|	21.534574468085335|
|18:00:00|	125.22473404255234|	22.065159574467977|
|19:00:00|	122.87499999999956|	21.513297872340853|
|20:00:00|	103.24734042552987|	14.176861702127571|
|21:00:00|	96.40292553191027|	11.722074468084996|
|22:00:00|	90.168882978725222|	9.3218085106382542|
|23:00:00|	78.472074468084216|	4.9773936170213453|

<img src="https://github.com/wanieknatalia/Google-Data-Analytics-Capstone-Bellabeat-Case-Study/blob/main/images/image5.9.1.2.png" width="680">

```sql
SELECT
  StepsTab.ActivityHour,
  ROUND(AVG(StepsTab.StepTotal),2) AS AverageStepTotal,
  ROUND(AVG(IntensitiesTab.TotalIntensity),2) AS AverageTotalIntensity
FROM
  `nw-capstone-project-bellabeat.bellabeat_data.hourlySteps_merged_limited` AS StepsTab
INNER JOIN
  `nw-capstone-project-bellabeat.bellabeat_data.hourlyIntensities_merged_limited` AS IntensitiesTab
ON
  StepsTab.ActivityHour = IntensitiesTab.ActivityHour
GROUP BY
  StepsTab.ActivityHour
```
|ActivityHour|	AverageStepTotal|	AverageTotalIntensity|
|----|----|----|
|00:00:00|	47.59|	2.34|
|01:00:00|	26.53|	1.59|
|02:00:00|	17.86|	1.12|
|03:00:00|	7.29|	0.48|
|04:00:00|	13.66|	0.67|
|05:00:00|	46.72|	5|
|06:00:00|	191.41|	8.21|
|07:00:00|	302.09|	10.69|
|08:00:00|	430.97|	14.72|
|09:00:00|	453.84|	15.83|
|10:00:00|	464.07|	17.02|
|11:00:00|	423.8|	16.06|
|12:00:00|	541.31|	19.5|
|13:00:00|	519.75|	18.32|
|14:00:00|	531.71|	18.2|
|15:00:00|	407.13|	15.33|
|16:00:00|	496.56|	17.53|
|17:00:00|	548.61|	21.53|
|18:00:00|	591.69|	22.07|
|19:00:00|	587.05|	21.51|
|20:00:00|	350.89|	14.18|
|21:00:00|	294.81|	11.72|
|22:00:00|	250.76|	9.32|
|23:00:00|	119.59|	4.98|

<img src="https://github.com/wanieknatalia/Google-Data-Analytics-Capstone-Bellabeat-Case-Study/blob/main/images/image5.9.1.3.png" width="680">

## 5.10. Sleeping time <a class="anchor"  id="section_5_10"></a>

Another aspect analyzed were the values from the `sleepDay_merged` file.

For each user, I calculated the average time spent sleeping and the average time spent in bed and then calculated the
ratio of the two values. The average for all tracker users was 91,20, which means that most of them had no problems
falling asleep.

Due to the dispersed quantitative nature of the data in the first graph, I marked in red the columns for which up to 10
measurements were made during the period under review. However, when visually comparing the time asleep to time in bed
ratio to the number of measurements, I noticed that the distribution of data in the case of a small number of
measurements and a larger number of measurements is similar.

The last element was the assessment of the quality of falling asleep. For 83,3% of users, the time asleep to time in bed
ratio was over 90.

```sql
SELECT
  Id,
  ROUND(AVG(TotalMinutesAsleep),2) AS AverageTotalMinutesAsleep,
  ROUND(AVG(TotalTimeInBed),2) AS AverageTotalTimeInBed,
  ROUND(AVG(TotalMinutesAsleep)/AVG(TotalTimeInBed)*100,2) AS TimeAsleepToTimeInBedRatio,
  CASE
    WHEN ROUND(AVG(TotalMinutesAsleep)/AVG(TotalTimeInBed)*100,2) <= 90 THEN "Poor"
  ELSE
  "Good"
END
  AS FallingAsleepQuality,
  COUNT(TotalMinutesAsleep) AS NumberOfMeasurements
FROM
  `nw-capstone-project-bellabeat.bellabeat_data.sleepDay_merged`
GROUP BY
  Id
```
|Id|	AverageTotalMinutesAsleep|	AverageTotalTimeInBed|	TimeAsleepToTimeInBedRatio|	FallingAsleepQuality|	NumberOfMeasurements|
|----|-----|-----|----|----|----|
|1503960366|	360.27999999999986|	383.20000000000005|	94.02|	Good|	25|
|1644430081|	294|	346|	84.97|	Poor|	4|
|1844505072|	652|	961|	67.85|	Poor|	3|
|1927972279|	417|	437.8|	95.25|	Good|	5|
|2026352035|	506.17857142857139|	537.64285714285722|	94.15|	Good|	28|
|2320127002|	61|	69|	88.41|	Poor|	1|
|2347167796|	446.8|	491.33333333333337|	90.94|	Good|	15|
|3977333714|	293.64285714285728|	461.14285714285711|	63.68|	Poor|	28|
|4020332650|	349.375|	379.75|	92|	Good|	8|
|4319703577|	476.65384615384613|	501.96153846153851|	94.96|	Good|	26|
|4388161847|	400.17391304347819|	423.21739130434781|	94.56|	Good|	23|
|4445114986|	385.17857142857144|	416.82142857142861|	92.41|	Good|	28|
|4558609924|	127.6|	140|	91.14|	Good|	5|
|4702921684|	417.48148148148152|	438.22222222222217|	95.27|	Good|	27|
|5553957443|	463.48387096774189|	505.8709677419356|	91.62|	Good|	31|
|5577150313|	431.99999999999994|	460.61538461538464|	93.79|	Good|	26|
|6117666160|	478.77777777777777|	510.16666666666669|	93.85|	Good|	18|
|6775888955|	349.66666666666669|	369|	94.76|	Good|	3|
|6962181067|	447.99999999999994|	466.12903225806451|	96.11|	Good|	31|
|7007744171|	68.5|	71.5|	95.8|	Good|	2|
|7086361926|	453.125|	466.41666666666669|	97.15|	Good|	24|
|8053475328|	297|	301.66666666666669|	98.45|	Good|	3|
|8378563200|	445.12903225806457|	485.93548387096774|	91.6|	Good|	31|
|8792009665|	435.66666666666674|	453.80000000000007|	96|	Good|	15|

<img src="https://github.com/wanieknatalia/Google-Data-Analytics-Capstone-Bellabeat-Case-Study/blob/main/images/image5.10.1.png" width="680">
<img src="https://github.com/wanieknatalia/Google-Data-Analytics-Capstone-Bellabeat-Case-Study/blob/main/images/image5.10.2.png" width="680">
<img src="https://github.com/wanieknatalia/Google-Data-Analytics-Capstone-Bellabeat-Case-Study/blob/main/images/image5.10.3.png" width="680">

### 5.10.1. Sleep per day of the week <a class="anchor"  id="section_5_10_1"></a>

An analysis of the sleep of study participants in terms of days of the week showed that they slept the least hours on
Thursdays and the most on Sundays. At the same time, Sunday was the day when the greatest difference between the time of
actual sleep and the time spent in bed was noticeable and the ratio of these two values was the least favorable. This
may mean that on that day it was important for the participants to take advantage of the moment of relaxation after the
working week and to postpone larger activities for other days of the week. In turn, it was on Thursdays that users fell
asleep the fastest. The ratio of sleep time to time spent in bed was the most favorable on Wednesdays. Unfortunately,
the average total sleep hours for the entire period did not exceed 7 hours.

```sql
SELECT
  CASE
    WHEN EXTRACT(DAYOFWEEK FROM SleepDay) = 1 THEN "Sunday"
    WHEN EXTRACT(DAYOFWEEK
  FROM
    SleepDay) = 2 THEN "Monday"
    WHEN EXTRACT(DAYOFWEEK FROM SleepDay) = 3 THEN "Tuesday"
    WHEN EXTRACT(DAYOFWEEK
  FROM
    SleepDay) = 4 THEN "Wednesday"
    WHEN EXTRACT(DAYOFWEEK FROM SleepDay) = 5 THEN "Thursday"
    WHEN EXTRACT(DAYOFWEEK
  FROM
    SleepDay) = 6 THEN "Friday"
    WHEN EXTRACT(DAYOFWEEK FROM SleepDay) = 7 THEN "Saturday"
END
  AS DayOfWeek,
  ROUND(AVG(TotalMinutesAsleep)/60,2) AS AvgTotalHoursAsleepByDayOfWeek,
  ROUND(AVG(TotalTimeInBed)/60,2) AS AvgTotalTimeInBedByDayOfWeek,
  ROUND((AVG(TotalTimeInBed)/60 - AVG(TotalMinutesAsleep)/60),2) AS TimeInBedAndAsleepDifference,
  ROUND(AVG(TotalMinutesAsleep)/AVG(TotalTimeInBed)*100,2) AS TimeAsleepToTimeInBedRatio
FROM
  `nw-capstone-project-bellabeat.bellabeat_data.sleepDay_merged`
GROUP BY
  DayOfWeek
```
|DayOfWeek|	AvgTotalHoursAsleepByWeekDay|	AvgTotalTimeInBedByWeekDay|	TimeInBedAndAsleepDifference|	TimeAsleepToTimeInBedRatio|
|----|----|-----|-----|-----|
|Tuesday|	6.7423076923076914|	7.3882051282051275|	0.64589743589743609|	91.26|
|Wednesday|	7.24469696969697|	7.8338383838383816|	0.58914141414141152|	92.48|
|Friday|	6.7570175438596491|	7.4175438596491245|	0.6605263157894754|	91.1|
|Saturday|	6.9845029239766072|	7.6640350877192978|	0.67953216374269054|	91.13|
|Sunday|	7.545757575757575|	8.391818181818179|	0.846060606060604|	89.92|
|Thursday|	6.6882812499999984|	7.2479166666666641|	0.55963541666666572|	92.28|
|Monday|	6.9916666666666654|	7.62246376811594|	0.630797101449275|	91.72|

<img src="https://github.com/wanieknatalia/Google-Data-Analytics-Capstone-Bellabeat-Case-Study/blob/main/images/image5.10.1.1.png" width="680">
<img src="https://github.com/wanieknatalia/Google-Data-Analytics-Capstone-Bellabeat-Case-Study/blob/main/images/image5.10.1.2.png" width="680">
<img src="https://github.com/wanieknatalia/Google-Data-Analytics-Capstone-Bellabeat-Case-Study/blob/main/images/image5.10.1.3.png" width="680">

# 6. Act phase <a class="anchor"  id="chapter6"></a>

## 6.1. Conclusions & recommendations <a class="anchor"  id="section_6_1"></a>

With the onset of the pandemic, there has been a clear trend towards greater daily use of both health monitoring devices
and connected home devices. The trend is particularly strong for smartwatches, fitness bands and voice-assisted
speakers.

As new products are launched, smart home devices will go from smart to intelligent, with tools giving consumers insight
into how the information they are presented with can lead to positive outcomes.

The most common metrics monitored by a smart device, including a smartphone, are: number of steps taken, heart rate,
sleep patterns, weight, calorie intake and stress level.
After analyzing FitBit Fitness Tracker Data, I found some insights that would help influence Bellabeat marketing
strategy:

| Insight                                                                                                                                                           | Recommendation                                                                                                                                                                                                                                                                                                                                                                                            |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Almost 50% of tracker users took fewer than the recommended 7,500 steps a day.                                                                                    | **Using hourly alerts** for several hours during the day to remind you to take a certain number of steps. As can be seen in the example of the FitBit tracker, alarge part of users managed to achieve 100% of the assumed activity (default 250 steps per hour from 9:00 a.m. to 5:00 p.m.).                                                                                                             |
| The decrease in activity at 11:00. and 15:00 is probably related to the need to devote oneself to work.                                                           | It is rather difficult to expect that working people will be able to find more time for activity during this period, but even in this case they can be supported by **smart reminders** them of the need **to get up and take a few steps**.                                                                                                                                                              |
| Most activity happens between 17:00 and 19:00.                                                                                                                    | **Using timeframe to motivate** customers to move to consolidate positive habits.                                                                                                                                                                                                                                                                                                                         |
| Mondays are the days of the highest activity with a high level of intensity.                                                                                      | Incorrectly selected exercises, too ambitious and of high intensity, usually started at the beginning of a new week, may result in loss of motivation to exercise later in the week. Data collected from Bellabeat products can be analyzed and - through the application - used to **provide appropriate recommendations, e.g. as to the type of exercise** that the user should perform on a given day. |
| More than 40% of people do not meet the recommendations regarding the weekly activity norm.                                                                       | The collected data should encourage more activity by **rewarding the user with praise** (e.g. badges for taking a certain number of steps so far) and **suggesting daily, weekly or monthly challenges** to the user.                                                                                                                                                                                     |
| Sunday is the day when tracker users have the most time to relax and wind down before going to sleep. Despite this, the actual sleep time did not exceed 8 hours. | **Setting a reminder**, based on observed sleep habits, **to wind down and prepare for sleep** to improve sleep duration and quality. The app could also offer useful materials to help customers fall asleep - e.g. meditation sessions, sleep techniques, relaxation music playlists.                                                                                                                   |

Additional suggestions:

* The application could also systematically display interesting facts and tips regarding healthy eating and lifestyle,
  which would also help improve sleep quality and fitness.
* In the event of an alarming health condition of the user, the system should suggest consulting a doctor and in the
  absence of reaction from the user - contact the previously indicated family member or hospital.
* The products could connect to other devices in the smart home, e.g. with a TV or speakers and also offer solutions
  such as the location of items such as keys or a telephone.
