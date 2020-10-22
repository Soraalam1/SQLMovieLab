## Create a database.

```
-- CREATE DATABASE movies2;

-- USE movies2;

```

## Add Movies to the movies table using an insert statement:

```
-- CREATE TABLE movies (
-- MOVIEID INT NOT NULL PRIMARY KEY,
-- Title VARCHAR(30) NOT NULL DEFAULT '',
-- Runtime INT NOT NULL DEFAULT 0,
-- Genre VARCHAR(30) NOT NULL DEFAULT '',
-- IMDB_Score DECIMAL(2,1) NOT NULL DEFAULT 0.0,
-- Rating VARCHAR(30) NOT NULL DEFAULT ''
-- );


-- DESCRIBE movies;


-- INSERT INTO movies VALUES
-- (1, 'Howard the Duck', 110, 'Sci-Fi', 4.6, 'PG'),
-- (2, 'Lavalantula', 83, 'Horror', 4.7, 'TV-14'),
-- (3, 'Starship Troopers', 129, 'Sci-Fi', 7.2, 'PG-13'),
-- (4, 'Waltz with Bashir', 90, 'Documentary', 8.0, 'R'),
-- (5, 'Spaceballs', 96, 'Comedy', 7.1, 'PG'),
-- (6, 'Monsters Inc.', 92, 'Animation', 8.1, 'G'),
-- (7, 'Dragon Ball Z: Battle of Gods', 85, 'Animation', 7.2, 'TV-PG'),
-- (8, 'Boruto: Naruto the Movie', 95, 'Animation', 7.9, 'PG')

-- SELECT * FROM movies;
```

## Create a query to find all movies in the Sci-Fi genre.
```
-- SELECT * FROM movies
-- WHERE genre = 'Sci-Fi';
```

## Create a query to find all films that scored at least a 6.5 on IMDB
```
-- SELECT * FROM movies
-- WHERE IMDB_Score >= 6.5;
```

## For parents who have young kids, but who don't want to sit through long children's movies, create a query to find all of the movies rated G or PG that are less than 100 minutes long.

```
-- SELECT * FROM movies
-- WHERE Rating = 'G' OR Rating = 'PG' AND Runtime < 100;
```

## Create a query to show the average runtimes of movies scoring below a 7.5 on imdb, grouped by their respective genres.
```
-- SELECT * FROM movies
-- WHERE  IMDB_Score < 7.5 GROUP BY Genre;
```

## There's been a data entry mistake; Starship Troopers is actually rated R, not PG-13. Create a query that finds the movie by its title and changes its rating to R.
```
-- UPDATE movies
-- SET Rating = 'R'
-- WHERE MOVIEID = 3;


-- SELECT * FROM movies;
```
## Show the ID number and rating of all of the Horror and Documentary movies in the database. Do this in only one query.
```
-- SELECT MOVIEID, Rating FROM movies
-- WHERE Genre = 'Horror' OR Genre = 'Documentary';
```

## This time let's find the average, maximum, and minimum IMDB score for movies of each rating.
```
-- SELECT Rating, AVG(IMDB_Score), MAX(IMDB_Score), MIN(IMDB_Score) FROM movies
-- GROUP BY Rating;
```
## That last query isn't very informative for ratings that only have 1 entry. Use a HAVING COUNT(*) > 1 clause to only show ratings with multiple movies showing.
```
-- SELECT Rating, AVG(IMDB_Score), MAX(IMDB_Score), MIN(IMDB_Score) FROM movies
-- GROUP BY Rating
-- HAVING COUNT(*) > 1;
```

## Bonus Query 1: Change the Naruto and Dragon Ball movie in the list genre from 'Animation' to 'Anime'.
```
-- UPDATE movies
-- SET Genre = 'Anime'
-- WHERE MOVIEID > 6;

-- SELECT * FROM movies;
```

## Bonus Query 2: Show all movies with a rating that contains TV, such as TV-14 and TV-PG
```
-- SELECT * FROM movies
-- WHERE Rating LIKE 'TV-%';
```

## Bonus Query 3: Find the average IMDB Score of movies rated PG, INCLUDING a movie rated TV-PG, don't include PG-13.
```
-- SELECT AVG(IMDB_Score) FROM movies
-- WHERE Rating LIKE '%PG';
```
