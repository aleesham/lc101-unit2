<!-- Reminders -->

<!-- Studio Solution -->
1. add-confirmation.html

    {% extends 'base.html' %}

    {% block content %}
    <p><strong>{{movie}}</strong> has been added to your Watchlist.</p> 
    {% endblock %}

2. render_template('add-confirmation.html', movie = movie)

    return render_template('add-confirmation.html', movie = new_movie)

3. Modify the edit.html file to display the watchlist in an unordered list with bullets in front of each movie.
    (This is above the forms)

    <hr />
    
    <h2>My Watchlist</h2>
    <ul>
    {% for movie in watchlist %}
        <li>{{movie}}</li>
    {% endfor %}
    </ul>




4. Change get_current_watchlist to return []. This simulates a user with an empty watchlist. Now, modify edit.html to make sense in such a situation:

    def get_current_watchlist():
    # returns user's current watchlist--hard coded for now
    return []

    1. Hide the <h2>My Watchlist</h2> and its unordered list. 
    2. Hide the crossoff form, since there are no movies to cross off.
    
    Wrap both with {% if watchlist|length == 0 %} ... {% endif %}


<!-- Summary -->

<!-- Q&A -->

<!-- Studio Walkthough -->
```
CREATE TABLE movies (
    movie_id INTEGER PRIMARY KEY AUTO_INCREMENT,
    title VARCHAR(120),
    year INTEGER,
    director VARCHAR(120)
);


INSERT INTO movies (title, year, director) VALUES ("Star Wars: The Last Jedi", 2017, "Rian Johnson");
INSERT INTO movies (title, year, director) VALUES ("Crossroads", 1986, "Walter Hill");
INSERT INTO movies (title, year, director) VALUES ("Crossroads", 2002, "Tamra Davis");
INSERT INTO movies (title, year, director) VALUES ("Begin Again", 2014, "John Carney");


CREATE TABLE directors (
    director_id INTEGER PRIMARY KEY AUTO_INCREMENT,
    first VARCHAR(120),
    last VARCHAR(120),
    country VARCHAR(120)
);

INSERT INTO directors (first, last, country) VALUES ("Walter", "Hill", "USA");
INSERT INTO directors (first, last, country) VALUES ("Rian", "Johnson", "USA");
INSERT INTO directors (first, last, country) VALUES ("Tamra", "Davis", "USA");
INSERT INTO directors (first, last, country) VALUES ("John", "Carney", "Ireland");

DROP TABLE movies;

CREATE TABLE movies (
    movie_id INTEGER PRIMARY KEY AUTO_INCREMENT,
    title VARCHAR(120),
    year INTEGER,
    director_id INTEGER,
    FOREIGN KEY (director_id) REFERENCES directors(director_id)
);
```