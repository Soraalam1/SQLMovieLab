-- CREATE DATABASE movies2;

-- USE movies2;

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

-- SELECT * FROM movies
-- WHERE genre = 'Sci-Fi';

-- SELECT * FROM movies
-- WHERE IMDB_Score >= 6.5;

-- SELECT * FROM movies
-- WHERE Rating = 'G' OR Rating = 'PG' AND Runtime < 100;

-- SELECT * FROM movies
-- WHERE  IMDB_Score < 7.5 GROUP BY Genre;

-- UPDATE movies
-- SET Rating = 'R'
-- WHERE MOVIEID = 3;

-- SELECT * FROM movies;

-- SELECT MOVIEID, Rating FROM movies
-- WHERE Genre = 'Horror' OR Genre = 'Documentary';

-- SELECT AVG(IMDB_Score), MAX(IMDB_Score), MIN(IMDB_Score) FROM movies
-- GROUP BY Rating;

-- SELECT AVG(IMDB_Score), MAX(IMDB_Score), MIN(IMDB_Score) FROM movies
-- GROUP BY Rating
-- HAVING COUNT(*) > 1;