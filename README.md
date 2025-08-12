# Mood-Based Movie Recommendation (SQLite)

A simple SQLite database project that recommends movies based on mood.  
Movies are tagged with moods like *Happy, **Sad, **Romantic, **Action, **Relaxing, and **Motivational*.  
Run SQL queries to get personalized movie suggestions.

## How to Use
1. Open the database in your terminal:
   ```bash
   sqlite3 mood_movies.db

   Run a query:
   SELECT title, genre, year
FROM movies
JOIN moods ON movies.mood_id = moods.mood_id
WHERE moods.mood_name = 'Happy';
