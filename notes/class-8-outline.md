<!-- Reminders -->

<!-- Studio Solution -->

<!-- TODO 1 -->
<>
<form action="/crossoff" method="post">
    {{ movie }}
    <input type="hidden" name="crossed-off-movie" value="{{ movie }}"/>
    <input type="submit" value="I Watched it!"/>
</form>

<!-- TODO 2-->

{% extends 'base.html' %}

{% block content %}

<h2>Movies I Have Watched:</h2>

    <ul>
        {% for movie in movies %}
            <li>
                <h3>{{movie}}</h3>
                <form action="/rating-confirmation" method="post">
                    <label>
                        My Rating:
                        <select name = "rating">
                            {% for rating in ["How was it?", "*", "**", "***", "****", "*****"] %}
                                <option>{{rating}}</option>
                            {% endfor %}
                        </select> 
                    </label>
                    <input type="hidden" name = "movie" value="{{movie}}" />
                    <input type="submit" value="Rate it!" />
                </form>
            </li>
        {% endfor%}
    </ul>

{% endblock %}

<!-- TODO 3 -->
@app.route("/ratings")
def movie_ratings():
    return render_template('ratings.html', movies = get_watched_movies())

<!-- TODO 4 -->
def get_watched_movies():
    return [ "Harry Potter", "Mars Attacks", "The Matrix"]

<!-- TODO 5 -->
{% extends 'base.html' %}
{% block content %}
    <p>You gave the <strong>{{movie}}</strong> a rating of {{rating}}.</p>
{% endblock %}

<!-- TODO 6 -->
@app.route("/rating-confirmation", methods=['POST'])
def rate_movie():
    movie = request.form['movie']
    rating = request.form['rating']
    return render_template("rating-confirmation.html", movie = movie, rating = rating)


<!-- Summary -->

<!-- Q&A -->

<!-- Studio Walkthough -->
Import sql files that hold tables
Do the last studio
<!-- STUDIO SOLN -->
SELECT title FROM movies;

SELECT title FROM movies ORDER BY year DESC;

INSERT INTO directors (first, last, country) VALUES ("Jean-Pierre", "Jeunet", "France");

SELECT director_id FROM directors WHERE first = "Jean-Pierre" AND last = "Jeunet";

INSERT INTO movies (title, year, director_id) VALUE ("Amelie", 2001, 2);

SELECT * FROM directors ORDER BY country;


SELECT directors.country FROM directors 
INNER JOIN movies 
ON movies.director_id = directors.director_id
WHERE movies.title = "Amelie";

SELECT movies.title, directors.first, directors.last FROM movies 
INNER JOIN directors
ON movies.director_id = directors.director_id
ORDER BY directors.last;


