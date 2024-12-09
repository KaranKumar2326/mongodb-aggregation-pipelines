

---

# MongoDB Aggregation Pipeline Queries

This project contains the solutions to MongoDB aggregation pipeline tasks as part of the Backend Intern Hiring Task. The queries are designed to retrieve and transform data from MongoDB collections using various aggregation operators and stages.

## Tasks Overview

This repository includes five JSON files, each containing an aggregation pipeline solution to the following tasks:

1. **Find the title of the movie along with all comments associated with it.**
2. **Count the number of comments for each movie and include the movie title and the count.**
3. **Find the top 5 movies with the highest average IMDb rating, including the title, IMDb rating, and the total number of comments.**
4. **Get a list of all unique cast members across all movies and count how many movies each cast member appeared in.**
5. **Find movies released before 1950 that have an average IMDb rating of 7.0 or higher, and include the title, IMDb rating, release year, genres, and the first 2 comments for each movie.**

## Folder Structure

```
mongodb-aggregation-pipelines/
│
├── 1.json               # Query for Task 1 - Title and Comments for each Movie
├── 2.json               # Query for Task 2 - Count of Comments per Movie
├── 3.json               # Query for Task 3 - Top 5 Movies with Highest IMDb Rating
├── 4.json               # Query for Task 4 - Unique Cast Members and Movie Count
├── 5.json               # Query for Task 5 - Movies Released Before 1950 with Rating >= 7
└── README.md            # Project Overview, Instructions, and Approach
```

## How to Use

1. **Clone the repository**:
   ```
   https://github.com/KaranKumar2326/mongodb-aggregation-pipelines.git
   ```
   
2. **Set up MongoDB Atlas**:
   - Create a free-tier **M0 MongoDB cluster** on [MongoDB Atlas](https://www.mongodb.com/cloud/atlas).
   - Load the `mflix` dataset into your MongoDB Atlas cluster. You can find this dataset in the Atlas Data Import section or use the sample dataset provided by MongoDB.

3. **Run the Queries**:
   - Execute the aggregation pipeline queries provided in the `.json` files.
   - You can run these queries using MongoDB Compass, Mongo Shell, or any MongoDB client that supports aggregation pipelines.
   
   Example of running the query in MongoDB Compass:
   - Navigate to your cluster and select the `mflix` database.
   - Open the "Aggregations" tab and load one of the `.json` files into the pipeline interface.
   - Run the query and verify the results.

4. **Review the Output**:
   - Each query returns a structured output based on the task description. For example, Task 1 returns the title of the movie along with its associated comments.

## Approach

The following stages were used in the aggregation queries:

1. **$lookup**:
   - To join the `movies` collection with the `comments` collection, allowing us to retrieve movie comments for each movie.
   
2. **$project**:
   - To shape the output and include only relevant fields such as the movie title, comments, IMDb rating, and comment count.

3. **$addFields**:
   - To calculate additional fields, such as the comment count for each movie.

4. **$sort**:
   - To sort the movies based on IMDb rating in descending order.

5. **$limit**:
   - To restrict the results to the top 5 movies or the first 2 comments when required.

## MongoDB Atlas Setup Instructions

To ensure the queries work correctly, follow these setup steps:

1. Create a free-tier M0 MongoDB cluster on [MongoDB Atlas](https://www.mongodb.com/cloud/atlas).
2. Load the `mflix` sample dataset into your cluster by following the instructions in the [MongoDB Atlas documentation](https://docs.atlas.mongodb.com/).
3. Ensure that the `comments` collection is linked to the `movies` collection via the `movie_id` field in `comments`.

## Testing the Queries

After loading the data, you can test the queries:

1. **Run the aggregation pipeline queries** in MongoDB Compass or using Mongo Shell.
2. **Verify the output** to check that it matches the expected schema for each task.


---

