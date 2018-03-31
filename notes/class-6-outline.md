<!-- Reminders -->
- Code with Videos
- Web Caesar due Today

<!-- Studio Solution -->

TODO 1: 
```
import cgi
new_movie = cgi.escape(new_movie)
```

TODO 2: 
```
from flask import redirect
if new_movie.strip() == "":
    error = "Please specify the name of the movie you want to add."
    return redirect("/?error="+error)
```

TODO 3:
```
if new_movie.strip() in terrible_movies:
    error = "Trust me, you don't want to add '{}' to your Watchlist.".format(new_movie)
    return redirect("/?error="+error)
```
<!-- Summary -->
- Jinga2 Templates in Flask
- Task List App
- Template extensions
- render_template

<!-- Q&A -->

<!-- Studio Walkthough -->
```
from flask import render_template
```

```
mkdir templates
cd templates
touch base.html

<!DOCTYPE html>
<html>
    <head>
        <title>FlickList</title>
        <style>
            .error {
                color: red;
            }
        </style>
    </head>
    <body>
        <h1>
            <a href="/">FlickList</a>
        </h1>
        {% block content %}
        {% endblock %}
        
    </body>
</html>
```

```
touch edit.html


{% extends 'base.html' %}

{% block content %}

    <h2>Edit My Watchlist</h2>
    
    <form action="/add" method="post">
        <label>
            I want to add
            <input type="text" name="new-movie"/>
            to my watchlist.
        </label>
        <input type="submit" value="Add It"/>
    </form>


    
    <form action="/crossoff" method="post">
        <label>
            I want to cross off
            <select name="crossed-off-movie"/>
                {% for movie in movies %}
                    <option value="{{movie}}">{{movie}}</option>
                {% endfor %}
            </select>
            from my watchlist.
        </label>
        <input type="submit" value="Cross It Off"/>
    </form>

    {% if error %}
        <p class="error">{{error}}</p>
    {% endif %}

{% endblock %}
```

```
touch crossoff.html
{% extends 'base.html' %}

{% block content %}
    <p><strike>{{movie}}</strike> has been crossed off your Watchlist.</p>
{% endblock %}
```


FIN: They will deal with the add.html stuff in the studio.


