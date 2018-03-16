# Class 4 Outline
- Studio Solution
- Review Q&A Style
- Studio Walkthrough

# Reminders Slide
- YOU SHOULD BE CODING WITH THE VIDEOS
- WEB CAESAR. START IT.

# OBJECTIVES
- Create an HTML form using `<form>`
- Create input elements with common types: text, submit, password, email, checkbox, radio
- Use the name attribute of form inputs to name request  parameters
- Create handlers in Flask for GET and POST request types
- Use the value attribute to specify the data value that is sent to the server upon form submission
- Decribe the differences between GET and POST and what each request type should be used for
- WE WILL NOT TALK ABOUT HTTP STATUS CODES in detail
- Explain why we receive a 405 Error when submitting a form to a handler with a decorator like @app.route('/')
- Use str.format() to create strings from template strings and data values.

# Studio Solution

line 25: movie_list = ["The Big Lebowski", "Princess Mononoke", "The Princess Bride", "Star Wars", "Begin Again"]

line 2: import random

line 27: return "The Big Lebowski" ----> return random.choice(movie_list)

line 11: todays_movie = get_random_movie()
line 17: change movie to todays_movie

line 12: tomorrows_movie = get_random_movie()
Update last TODO



# Questions Slide?

# Review Slide

# Studio Walkthough