<!-- Reminders -->

<!-- Studio Solution -->

<!-- TODO -->
ADD IN THE COMMAND LINE NOTES
<!-- TODO -->

line 25: movie_list = ["The Big Lebowski", "Princess Mononoke", "The Princess Bride", "Star Wars", "Begin Again"]

line 2: import random

line 27: return "The Big Lebowski" ----> return random.choice(movie_list)

line 11: todays_movie = get_random_movie()
line 17: change movie to todays_movie

line 12: tomorrows_movie = get_random_movie()

Update last TODO

questions?


<!-- Summary -->


<!-- TODO -->

CREATE EXAMPLES POSSIBLY FOR SUMMARY
NOTES FOR STUDIO WALKTHROUGH

<!-- TODO --> Talk more about git and version controol?

<!-- Studio Walkthrough -->
- GO TO LAUNCHCODES PAGE AND READ WHAT WE WILL DO

<!-- TODO -->
ADD IN THE COMMAND LINE NOTES
<!-- TODO -->


- add page_header and page_footer for organization purposes:

page_header = """
<!DOCTYPE html>
<html>
    <head>
        <title>FlickList</title>
    </head>
    <body>
        <h1>FlickList</h1>
"""

page_footer = """
    </body>
</html>
"""


- add_form to display on index page
add_form = """
    <form action="/add" method="post">=
            I want to add
            <input type="text" name="new-movie"/>
            to my watchlist.=
        <input type="submit" value="Add It"/>
    </form>
"""
- So far we have changed the HTML but we can't actually process the form

- RUN CODE AND CHECK.

- /add route

line 1: from flask import request to make requests

@app.route("/add", methods=['POST'])
def add_movie():
    new_movie = request.form['new-movie']

    # build response content
    sentence = "<strong>{}</strong> has been added to your Watchlist!"
    sentence = sentence.format(new_movie)
    content = page_header + "<p>" + sentence + "</p>" + page_footer

    return content

@app.route("/")
def index():
    edit_header = "<h2>Edit My Watchlist</h2>"

    # build the response string
    content = page_header + edit_header + add_form + page_footer

    return content


app.run()
