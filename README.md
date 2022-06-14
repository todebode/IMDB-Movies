# IMDb Movies

### Tijesunimi Odebode

## Business Problem

I was hired to analyze data on movies to determine what makes a movie successful, and then provide recommendations to the stakeholder on how to make a successful movie. To get this done, I would have to retrieve relevant movie data from a subset of IMDb’s (Internet Movie Database) dataset, extract financial data from TMDB’s (The Movie Database) API, create a MySQL database and then use hypothesis testing to answer some questions about what makes a movie successful.

### Part 1 - Loading and Preprocessing IMDb data

In this part of the project, I loaded data on movies retrieved from a subset of IMDb's (Internet Movie Database) dataset. I also carried out some preprocessing steps on the data, including filtering out unnecessary data. Finally, the filtered tables were saved as gzip-compressed csv files. The following are the specifications for filtering given by the stakeholder:

•	Exclude any movie with missing values for genre or runtime

•	Include only full-length movies (titleType = "movie")

•	Include only fictional movies (not from documentary genre)

•	Include only movies that were released 2000 - 2021 (include 2000 and 2021)

•	Include only movies that were released in the United States

### Data Source:

Overview/Data Dictionary: IMDb

Downloads page: https://datasets.imdbws.com

Based on previous research by the stakeholder, they want me to focus on the following files from the IMDb downloads link above:

•	title.basics.tsv.gz

•	title.ratings.tsv.gz

•	title.akas.tsv.gz

### Part 2a - Extract from TMDB

Considering there is no financial information in the IMDb data that was loaded in Part 1 of the project, financial information was extracted from The Movie Database (TMDB) in this part of the project. The stakeholder specifically wants me to extract the budget, revenue and MPAA rating (e.g. G/PG/PG-13/R etc.). The MPAA rating is also called ‘certification.’ Extracting the financial information is important to analyze which movies are successful. I have extracted financial information for pre-COVID pandemic years 2010 – 2019 using TMDB’s API.

### Data Source:

I was able to sign up for an API key using the following link: https://www.themoviedb.org/ 

### Part 2b - Exploratory Data Analysis

In this part, l have performed some exploratory data analysis to show the following:

a. How many movies had at least some valid financial information (values > 0 for budget OR revenue)?

Note: I excluded any movies with 0's for budget AND revenue from the remaining visualizations.

b. How many movies are there in each of the certification categories (G/PG/PG-13/R etc.)?

c. What is the average revenue per certification category?

d. What is the average budget per certification category?

Bar charts showing the number of movies with valid financial information, number of movies by certification categories, average revenue per certification category and average budget per certification category are shown in Figure 1, Figure 2, Figure 3 and Figure 4 below.

**Figure 1:** Bar chart of the number of movies with valid financial information

![image](https://user-images.githubusercontent.com/97941938/173638842-43949783-4f65-4bad-8f26-76fa0b88c889.png)

**Figure 2:** Bar chart of the number of movies by certification categories

![image](https://user-images.githubusercontent.com/97941938/173639755-2b1e33bf-227e-40d1-b6ba-2c93ca8feb71.png)

**Figure 3:** Bar chart of the average revenue per certification category

![image](https://user-images.githubusercontent.com/97941938/173639829-2869e8d6-fff3-44ea-b879-31765444a280.png)

**Figure 4:** Bar chart of the average budget per certification category

![image](https://user-images.githubusercontent.com/97941938/173639877-6fe4fecd-8920-4bab-9c2a-1413fc19daa3.png)

<ins>Findings</ins> 

- In Figure 1, 7835 movies had valid financial information (values > 0 for budget OR revenue). This was a lot less than movies without valid financial information. There were 29052 movies without valid financial information

- In Figure 2, The 'R' certification category had 1640 movies and that was the highest number of movies of all certification categories

- From Figure 3, we can see that the 'PG' category had the highest average revenue

- From Figure 4, we can see that the PG' category had the highest average budget



### Part 3 - Creating a Database

In this part of the project, I applied an ETL (extract, transform, load) process on the previously saved movie data, and then created a new MySQL database for the data. Finally, I exported the database to a .sql file using MySQL Workbench.

### Part 4 - Hypothesis Testing

In this part of the project, I used hypothesis testing to answer 3 questions about what makes a movie successful. The following are the questions that were answered:

a. Does the MPAA rating of a movie (G/PG/PG-13/R etc.) affect how much revenue the movie generates?

b. Do some movie genres earn more revenue than others?

c. Are some genres higher rated than others?
