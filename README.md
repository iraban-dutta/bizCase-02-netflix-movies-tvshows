# bizCase-02-netflix-movies-tvshows

## Business Problem:
Netflix is one of the most popular media and video streaming platforms. They have over 10000 movies or tv shows available on their platform. The dataset consists of listings of all the movies and tv shows available on Netflix, along with details such as - cast, directors, ratings, release year, duration, etc.
Analyze the data and generate insights that could help Netflix in deciding which type of shows/movies to produce and how they can grow the business in different countries

## bizCase Highlights:
- Data cleaning: Dealing with list values/nested string values in the dataset
  - For example: a particular movie can belong to multiple Genres (like Drama, Comedy)
  - In such cases, the data was presented as follows: 'Dramas, Comedy'
  - We have used python string functions and pandas effectively to handle such data
- We have performed extensive EDA to address the business problem.
  - Throughout the notebook, we have frequently plotted a lot of graphs and used methods like pd.melt, pd.pivot, pd.pivot_table to restructure the data in order to get the desired information
- We have performed the EDA on movies and tv-shows seperately and finally compared the two together

## Business Insights & Recommendations:

### **1. Movies vs TV-Shows**  

***1.1. INSIGHTS:***
-  The content in Netflix can be classfied into 2 segments: Movies and TV shows
-  From the data it is very evident that Movies outnumber the TV-Shows. 
-  We can also see how Movies and TV-Shows were added on Neflix over time:  
    -  The number of Movies added over time (2016 onwards) has clearly dominated that of the TV-Shows as evident from below.
![movies_vs_shows_count](https://user-images.githubusercontent.com/108816719/215268594-9697cd4d-6999-423f-91d8-af2272a7bf6c.png)
![movies_vs_shows_count_overTime](https://user-images.githubusercontent.com/108816719/215268694-d80bf5f3-a166-4bee-b37b-419af2b0760c.png)

***1.2. Possible reasons for more  Movies than TV-Shows:***
-  We can assume that the demand of Movies on Netflix is more than that of TV-Shows.
-  The time to consume a movie is far less than that of a TV-Show thus making it more suitable for watching.
-  Usually TV-Shows will have a single story told over many episodes and many people may not simply have the time to watch a complete TV-Shows.

***1.3. Recent trends on Movies vs TV-Shows***
-  However we see that there is an increase in the number of TV-shows added over the years (from 2016 to 2020). This is a good sign as it indicates that TV-Shows is a growing niche market. 
-  At the same time we see that the number of movies added across the same time frame had increased and peaked in 2019 and then started to decline from there on
![movies_vs_shows_count_byYear](https://user-images.githubusercontent.com/108816719/215268775-d4b8ea29-a8e9-49ef-b0fd-1278edc43ead.png)

***1.4. RECOMMENDATIONS:***
-  Focus should be primarily given on movies since it constitutes majority of the content
-  However since the number of TV-Shows added over time has increased, we can slowly ramp up the production of more shows.
-  **The content to be added should be based on the following broad factors: (We try to answer all these questions sunsequently)**
    -  What are the popular genres and ratings for the content on Netflix?
    -  Can we get really specific and find out the most loved genre and rating across Movies and TV-Shows?
    -  What are the top content producing countries?
    -  Is there any country-wise trend when it comes to the genres and ratings of the content produced?
        -  For example, Genre-A may be a popular genere globally but may not be a popular genre in Country-A. In that case, we should give less priority to produce content of Genre-A in Country-A.
        -  More specifically, we want to find out the popular genres and ratings across the Top 5 content producing countries?
        -  Draw insights from the temporal trends observed across countries
    - Comparison b/w TV Shows which ran for more than 3 seasons and those that didnt
-  **We will now try to identify the answers to the above questions individually for both Movies and TV-Shows**




### **2. What are the popular genres and ratings of the Netflix content?**

***2.1. INSIGHTS:***
-  We have clearly identified the most popular genres, ratings across both Movies and TV-Shows
-  ***Popular Movie Genres:*** 
![movies_count_byGenre](https://user-images.githubusercontent.com/108816719/215268897-3a541a80-1583-47da-98d9-9aade58c9a57.png)
-  ***Popular Movie Ratings:***
![movies_count_byRating](https://user-images.githubusercontent.com/108816719/215268907-73bb36a8-fc6d-466f-baed-aec4881ad945.png)
-  ***Popular TV-Show Genres:*** 
![shows_count_byGenre](https://user-images.githubusercontent.com/108816719/215268924-6fe106ed-f3b1-4db5-8725-d81f5c6146af.png)
-  ***Popular TV-Show Ratings:*** 
![shows_count_byRating](https://user-images.githubusercontent.com/108816719/215268938-a9d03011-3573-4bae-8a6c-e51fc3aa0c13.png)

***2.2. RECOMMENDATIONS:***
-  We can clearly see the popular genres and ratings for both Movies and TV-Shows that are present in Netflix
-  This gives us a fair idea about the kind of content that is in demand and people want to watch
-  For the subsequent content that are produced or launched on the Netflix platform, we can consciously make a plan that the content should be from the above identified popular options so that it performs well with the audience



### **3. Can we get really specific and find out the most loved genre and rating across Movies and TV-Shows?**

***3.1. INSIGHTS:***
-  Above we have seen the popular genres and rating, but what about the most loved genre and rating?
-  Sometimes the budget for content production can be limited. In such cases, we would like to know the best genre and the best rating so that we can produce the content accordingly.
-  We have tried to see the count of movies/show across the Top-5 genres and Top-5 Ratings
-  ***For Movies:***
    -  Top Genre: International Movies
    -  Top Rating: TV-MA / TV-14
![movies_count_top5RatingGenre](https://user-images.githubusercontent.com/108816719/215269082-7d7dc64d-e1ed-42ff-904f-27ccdca45801.png)
-  ***For TV-Shows:***
    -  Top Genre: International TV-Shows
    -  Top Rating: TV-MA
![shows_count_top5RatingGenre](https://user-images.githubusercontent.com/108816719/215269110-b3d4dc48-8285-48b5-8d4a-e0e251d83518.png)

***3.2. RECOMMENDATIONS:***
-  The above plots give us the count of content across genre and rating. From this data we can clearly identify the genres and ratings which are the most in demand.
-  A by-product of the above plot is that we also become aware of the those genres and rating combinations for which the content is not there and there may be scope for more such content to target a particular kind of audience
    -  This is very evident in the TV Show plot. 
    -  Some of the boxes being 0 actually make sense and has got more to do with the nature of the content 
        -  eg: Kid's TV genre has little or no shows with mature ratings
    -  However genre = comedy and rating = (TV-Y7, TV-Y, TV-PG) have fewer content and there may be scope to create more content here (especially if there are some hit TV-Shows already present under these combibnations)




## **4. What is the mean Running time / Seasons for Movies and TV-Shows respectively?**

***4.1. INSIGHTS:***
-  Again we will focus only on the content that falls in the Top-5 Genres and Top-5 Ratings across Movies and TV-Shows.
-  From the below plots, we can get an understanding about the mean running time for movies and mean seaosns for TV-Shows across different combinations of genres and ratings.
-  ***For Movies:***
![movies_meanDuration_top5RatingGenre](https://user-images.githubusercontent.com/108816719/215269265-a155f9cc-c384-41e5-bc3e-f930363c53f5.png)
-  ***For TV-Shows:***
![shows_meanSeasons_top5RatingGenre](https://user-images.githubusercontent.com/108816719/215269283-4682f1f9-56d6-489e-bd48-6c24824bc149.png)

***4.2. RECOMMENDATIONS:***
-  The above graphs can act as a coarse reference point for the duration of the contant already existing in Netflix.
-  The duration of the content is an important metric since it the audience engagement heavily depends on it
-  For Movies: The most in demand genre-rating combos are: 
    -  **International Movies + TV-MA:** *Mean running time is* ***109 mins***
    -  **International Movies + TV-14:** *Mean running time is* ***126 mins***
-  For TV-Shows: The most in demand genre-rating combos are: 
    -  **International TV-Show + TV-MA:** *Mean number of seasons is* ***1-2 Seasons***
-  Thus we can see how we can use the above data for making the content more curated




## **5. What are the top content producing countries?**

***5.1. INSIGHTS:***
-  Below are the plots showing number of Movies/TV-Shows per content producing countries
-  ***For Movies:***
![movies_count_byCountry](https://user-images.githubusercontent.com/108816719/215269346-272b1403-2179-4384-a2e5-cb0d4401ad73.png)
-  ***For TV-Shows:***
![shows_count_byCountry](https://user-images.githubusercontent.com/108816719/215269357-2c0b3346-4f0e-4521-91da-f466620007ca.png)

***5.2. RECOMMENDATIONS:***
-  We can identify the top content creating countries and do subsequent country specific analysis on the Top-5 countries for Movies and TV-Shows seperately.
-  Each country is unique and different and the content preferred will be different across the cultures.
-  We want to make curated content in those countries where the total amount of movies/shows are significant, hence this insight is critical




## **6. Country specific analysis for Movies (Top-5 countries)**

***6.1. INSIGHTS:***
-  The top-5 Movie producing countries are:
    1. US
    2. India
    3. UK
    4. Canada
    5. France

#### **What are the popular genres across countries?** 
![movies_count_byGenre_top5Country](https://user-images.githubusercontent.com/108816719/215269487-04994098-67ea-41ed-981e-fe35713a21c0.png)

#### **What are the popular ratings across countries?**  
![movies_count_byRating_top5Country](https://user-images.githubusercontent.com/108816719/215269492-5450e620-6159-4ee5-b734-a1c12e7032cc.png)

#### **What is the mean Movie running time across countries?**  
-  Movies produced in India are longer than all the other countries considered here 
![movies_meanDuration_top5Country](https://user-images.githubusercontent.com/108816719/215269532-7aecbf37-2920-4827-8e0e-a1f47bb47f96.png)

#### **How are the movies added over the years across countries?**  
-  Number of Movies produced in the US and India are showing a decline after experiencing prominent peaks
![movies_count_overTime_top5Country](https://user-images.githubusercontent.com/108816719/215269550-714e7d6e-49b8-489b-9d02-1843f1418a53.png)

***6.2. RECOMMENDATIONS:***
-  **Popular Genres**
    1. US: Dramas
    2. India: International Movie
    3. UK: Dramas
    4. Canada: Comedies
    5. France: International Movies
-  **Popular Ratings**
    1. US: TV-MA
    2. India: TV-14
    3. UK: R
    4. Canada: R
    5. France: TV-MA
-  **Decline in movies produced in prominent markets (ALARMING!!)**
    -  As seen before, Movies outnumber TV-Shows in Netflix and thus we can assume that they generate the majority of the revenue for Netflix.
    -  Even though the general trend suggests than number of movies added on Netflix has declined in the recent years, the US and India are the Top-2 countries where movies are produced.
    -  This is a cause of serious concern and we must find out what is the reason for this
        -  Is the pricing too high?
        -  Are TV-Shows taking over in these markets?
        -  Or has the quality and customer review of the movies added recently been poor?
        
        


## **7. Country specific analysis for TV-Shows (Top-5 countries)**

***7.1. INSIGHTS:***
-  The top-5 TV-Show producing countries are:
    1. US
    2. UK
    3. Japan
    4. South Korea
    5. Canada

#### **What are the popular genres across countries?**  
![shows_count_byGenre_top5Country](https://user-images.githubusercontent.com/108816719/215269719-0b82737f-46cb-477f-9976-1277aaa68b06.png)

#### **What are the popular ratings across countries?**  
![shows_count_byRating_top5Country](https://user-images.githubusercontent.com/108816719/215269737-55e5a712-c450-4ea5-a935-b1f5d85c9ff8.png)

#### **What is the mean number of seasons of TV-Shows across countries?**  
-  TV-Shows produced in Canada run for longer number of seasons than all the other countries considered here
![shows_meanSeasons_top5Country](https://user-images.githubusercontent.com/108816719/215269757-502508f0-b12d-405c-bb79-ba4622f6b97f.png)

#### **How are the TV-Shows added over the years across countries?**  
-  Number of TV-Shows produced in the US is steadily increasing  
![shows_count_overTime_top5Country](https://user-images.githubusercontent.com/108816719/215269772-2cdb1145-d77a-4b8b-8482-5854805ff336.png)

***7.2. RECOMMENDATIONS:***
-  **Popular Genres**
    1. US: TV Comedies
    2. UK: British TV Shows
    3. Japan: International TV Shows, Anime Series
    4. South Korea: International TV Shows, Korean TV Shows
    5. Canada: Kid's TV
-  **Popular Ratings**
    1. US: TV-MA
    2. UK: TV-MA
    3. Japan: TV-14
    4. South Korea: TV-14
    5. Canada: TV-MA
-  **US is a booming market for launching TV-Shows**
    -  We have seen earlier that the number of TV-Shows added on Netflix has grown over the last few years.
    -  Thus going by recent trends, the demand of TV-Shows is increasing
    -  From the data above we see that the demand in the US for TV-Shows has rapidly grown and overshadowed the other countries.
        -  This makes the US the perfect market to launch even more TV-Shows and with the information that we drew above we can make curated content so that the shows become big hits.




## **8. TV Shows which ran for more than 3 seasons vs those that didnt**

***8.1. INSIGHTS***
-  We want to understand what makes a TV Show successful.
-  The very fact that a TV show gets sanctioned for a new season is a proof of the fact that the show was well received by the audience and there is scope for airing 1 more season.
-  If we proceed with the assumption, we can segregate TV-Shows into 2 buckets
    -  Group A- Shows which ran for <= 3 season
    -  Group B- Shows which ran for > 3 seasons
- The aim of this analysis is to get some parammeters on which shows with higher number of seasons differ from those with less seasons

**Count of shows in Group-A vs Group-B:**  
![HighLowSeason_shows_count](https://user-images.githubusercontent.com/108816719/215269876-0cf18df1-2447-49e6-9974-cf1e9bef5d23.png)

**Count of shows in Group-A vs Group-B by Rating:**  
-  TV-14 and TV-MA are the ratings which form the majority when it comes to the shows with higher number of seasons
![HighLowSeason_shows_count_byRating](https://user-images.githubusercontent.com/108816719/215269907-8bd9106a-aa4e-49e8-9584-6ea817c612a6.png)

**Count of shows in Group-A vs Group-B by Genre:**
-  TV Comedies seem to be the genre which run for higher number of seasons followed by TV Dramas
![HighLowSeason_shows_count_byGenre](https://user-images.githubusercontent.com/108816719/215269919-81cde63a-7928-492b-bde1-bc93929d9eee.png)

**Temporal Trend on how the shows (of Group A and Group B) were added in Netflix over time:**  
-  We observe that in recent years more shows were added on Netflix which ran for higher number of seasons
-  Note that the data for 2021 is not for the complete year and only the first 9 months 
![HighLowSeason_shows_count_overTime](https://user-images.githubusercontent.com/108816719/215269929-e23e3246-20d3-4277-bff2-1f00edb7bc31.png)

***8.2. RECOMMENDATIONS:***
-  The fact that the demand of TV-Shows has increased over time can be explained by the fact that the number of shows with high seasons added over time has also increased
-  Thus if we do consider the shows with high seasons to be audience hits, then there is something to learn from them:
    -  We have identified the genres and ratings of these succesful shows
    -  We can launch more such shows on Netflix
    -  Even when Netflix is creating new content, this data point can be kept in mind
