# Netflix_DataAnalysis_project

### Project Overview
This project involves analyzing a dataset of Netflix shows and movies, focusing on key features such as title, director, cast, release year, rating, duration, and other relevant metadata. By exploring these attributes, the goal is to uncover meaningful insights about Netflix’s content 

### Data Sources
Netflix Data : The primary dataset used for this analysis is the "netflix_titles.csv" file , containing  a dataset of Netflix shows and movies, focusing on key features such as title, director, cast, release year, rating, duration, and other relevant metadata. 

### Tools 
- Excel - Data Cleaning 
- Sql Server - Data Analysis
- PowerBi - Creating Reports

### Data Cleaning and Preparation 
1. Data Loading and Inspection.
2. Handling Missing values.
3. Data Cleaning and Formatting.

### Exploratory Data Analysis 

EDA involved explorating the Netlix data to answer key questions , such as :

- What is the overall trend of watching movies among People?
- Which are the top countries with most Population watching Netflix ?
- Top Indian Directors making the netfliix Movies ?

### Data Analysis 
```sql
create table netflix_data.countries_released as
(
select *
from
(
SELECT show_id, Country_1 as country FROM netflix_data.countries
union 
SELECT show_id, Country_2 as country FROM netflix_data.countries
union 
SELECT show_id, Country_3 as country FROM netflix_data.countries
union 
SELECT show_id, Country_4 as country FROM netflix_data.countries
union 
SELECT show_id, Country_5 as country FROM netflix_data.countries
union 
SELECT show_id, Country_6 as country FROM netflix_data.countries
union 
SELECT show_id, Country_7 as country FROM netflix_data.countries
union 
SELECT show_id, Country_8 as country FROM netflix_data.countries
union 
SELECT show_id, Country_9 as country FROM netflix_data.countries
union 
SELECT show_id, Country_10 as country FROM netflix_data.countries
union 
SELECT show_id, Country_11 as country FROM netflix_data.countries
union
SELECT show_id, Country_12 as country FROM netflix_data.countries
 )a
where country IS NOT NULL
) 
;
```

```sql
create table netflix_data.netflix_directors as
(
select * from
(
SELECT show_id, director_1 as director FROM netflix_data.directors
union 
SELECT show_id, director_2 as director FROM netflix_data.directors
union 
SELECT show_id, director_3 as director FROM netflix_data.directors
union 
SELECT show_id, director_4 as director FROM netflix_data.directors
union 
SELECT show_id, director_5 as director FROM netflix_data.directors
union 
SELECT show_id, director_6 as director FROM netflix_data.directors
union 
SELECT show_id, director_7 as director FROM netflix_data.directors
union 
SELECT show_id, director_8 as director FROM netflix_data.directors
union 
SELECT show_id, director_9 as director FROM netflix_data.directors
union 
SELECT show_id, director_10 as director FROM netflix_data.directors
union 
SELECT show_id, director_11 as director FROM netflix_data.directors
union
SELECT show_id, director_12 as director FROM netflix_data.directors
union
SELECT show_id, director_13 as director FROM netflix_data.directors
 )a
where director IS NOT null
) 
;
```
```sql
select netflix_directors.show_id,country,director from
countries_released
inner join netflix_directors
on countries_released.show_id=netflix_directors.show_id
where country = 'India';
```
