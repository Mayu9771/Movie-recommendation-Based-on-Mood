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

SQLQuerie:
CREATE TABLE moods (
    mood_id INTEGER PRIMARY KEY AUTOINCREMENT,
    mood_name TEXT NOT NULL
);

CREATE TABLE movies (
    movie_id INTEGER PRIMARY KEY AUTOINCREMENT,
    title TEXT NOT NULL,
    genre TEXT,
    year INTEGER,
    mood_id INTEGER,
    FOREIGN KEY (mood_id) REFERENCES moods(mood_id)
);

INSERT INTO moods (mood_name) VALUES
('Happy'), ('Sad'), ('Romantic'), ('Action'), ('Relaxing'), ('Motivational');

INSERT INTO movies (title, genre, year, mood_id) VALUES
('Zindagi Na Milegi Dobara', 'Drama', 2011, 1),
('3 Idiots', 'Comedy', 2009, 1),
('Taare Zameen Par', 'Drama', 2007, 2),
('The Notebook', 'Romance', 2004, 3),
('Avengers: Endgame', 'Action', 2019, 4),
('Interstellar', 'Sci-Fi', 2014, 5),
('The Pursuit of Happyness', 'Biography', 2006, 6);

SELECT title, genre, year
FROM movies
JOIN moods ON movies.mood_id = moods.mood_id
WHERE moods.mood_name = 'Happy';
