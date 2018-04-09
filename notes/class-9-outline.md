<!-- Reminders -->

<!-- Studio Solution -->
1. SELECT DISTINCT country FROM directors;
2. SELECT * FROM directors WHERE country = "France";
3. SELECT MIN(date_viewed) FROM viewings;
4. SELECT COUNT(*) FROM movies INNER JOIN directors ON movies.director_id = directors.director_id WHERE directors.country = "USA";
5. SELECT movies.title FROM movies INNER JOIN directors ON directors.director_id = movies.director_id WHERE directors.first = "Akira" AND directors.last = "Kurosawa";
6. SELECT COUNT(*) FROM viewings INNER JOIN movies ON viewings.movie_id = movies.movie_id WHERE movies.title = "Talk to Me";
7. SELECT MAX(date_viewed) FROM viewings;
8. SELECT movie_id FROM viewings WHERE date_viewed = (SELECT MAX(date_viewed) FROM viewings);
9. SELECT movies.title FROM movies INNER JOIN viewings ON movies.movie_id = viewings.movie_id WHERE viewings.date_viewed = (SELECT MIN(date_viewed) FROM viewings);
10. SELECT viewers.first, viewers.last FROM viewers INNER JOIN viewings ON viewers.viewer_id = viewings.viewer_id WHERE viewings.date_viewed = (SELECT MIN(date_viewed) FROM viewings);
11. 
12. 
13. 

<!-- Summary -->

<!-- Q&A -->

<!-- Studio Walkthough -->
