# Movie Rating Repository

## About
This repository serves as a comprehensive platform for movie ratings from sources such as IMDb, Rotten Tomatoes, Netflix, and user-generated content. Designed for movie enthusiasts seeking a more personalized and integrated movie rating experience, it allows users to view aggregated ratings, contribute their own scores, and directly compare opinions with friends within the community.

## Methodology
- **Data Gathering:**
  - **APIs**: Ratings are collected through public APIs from IMDb, Rotten Tomatoes, and Netflix.
  - **User and Friends' Input**: Ratings are manually input by users through the web interface. Users can connect with friends to view each other's ratings.

- **Data Integration**:
  - The collected data is standardized across different sources and normalized to a 0-10 scale to ensure consistency.

- **Security**:
  - User IDs are required to access private information such as a user's personal movie ratings.

- **Updates**:
  - The database is updated monthly as new ratings and movies come in from various sources. This process includes clarifying information resources and details to maintain data transparency.

## Access
- **User Registration**: Users must create an account using their email to access personalized features.
- **Navigation**: After logging in, users can visit the dashboard to view the latest top-rated movies.
- **Friend Interaction**: Users can add friends and access their ratings through the main page, which shows both their own and their friends' movie ratings.
- **Data Retrieval**: Users can query the database for movie ratings using a search interface that supports filtering by genre, year, and director. There is also an option to download personal and friends' movie rating datasets.
- **Rating Submission**: Users can submit their ratings for any movie directly on the movie's profile page.

## Structure
- **Movie_id** (integer): Unique identifier for each movie.
- **Title** (string): Name of the movie.
- **Release Year** (integer): Year the movie was released.
- **Director** (string): Name of the movie director.
- **Genres** (string): List of movie genres.
- **IMDb_score** (integer): Movie rating from IMDb.
- **Netflix_score** (integer): Movie rating from Netflix.
- **Rotten_Tomatoes_score** (integer): Movie rating from Rotten Tomatoes.
- **Average_score** (float): Combined rating from IMDb, Netflix, and Rotten Tomatoes.
- **User_score** (float): Movie rating given by the user.
- **Friend_scores** (array of float): Ratings given by friends.
- **Average_score_friends** (float): Average of all friend scores and user's score.

## Example Usage
### Request: GET /api/movies?title=Ironman

### Response:
```json
{
  "Movie_id": 020,
  "Title": "Iron Man",
  "Release_year": 2008,
  "Director": "Jon Favreau",
  "Genres": "Action, Adventure, Sci-Fi",
  "IMDb_score": 7.6,
  "Netflix_score": 8.0,
  "Average_score": 7.95,
  "UserA_score": 8.5,
  "Friend_scores": [8.2, 7.8, 8.5],
  "Average_score_friends": 8.17
}
