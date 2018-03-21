<!-- Reminders -->

<!-- Studio Solution -->
cd ~/lc101/flicklist
git checkout studio2

1. Add a crossoff form. Line 40

crossoff_form = """
    <form action="/crossoff" method="post">
        <label for="crossed-off-movie">
            I want to cross off
            <input type="text" id="crossed-off-movie" name="crossed-off-movie"/>
            from my watchlist.
        </label>
        <input type="submit" value="Cross It Off"/>
    </form>
"""


in index function: content = page_header + edit_header + add_form + "<br/>" +crossoff_form + page_footer

RUN CODE.

2. Handle the form submission. 

line 56: @app.route("/crossoff", methods =['POST'])
line 59:    sentence = "<strike>{}</strike> has been crossed off your Watchlist"
            content = page_header + "<p>" + sentence.format(crossed_off_movie) + "</p>" + page_footer
            return content

3. Use a dropdown instead of an input text field. 

crossoff_form = """
    <form action="/crossoff" method="post">
        <label for="crossed-off-movie">
            I want to cross off
            <select id="crossed-off-movie" name="crossed-off-movie">
                <option>Begin Again</option>
                <option>Big Fish</option>
                <option>Pulp Fiction</option>
            </select>
            from my watchlist.
        </label>
        <input type="submit" value="Cross It Off"/>
    </form>
"""



<!-- TODO -->
1. Put Validate Time code on my machine
2. Put Hello _____ on my Machine.

<!-- Summary -->
- Validation
- Redirects
- HTML Escaping

<!-- Q&A -->


<!-- Studio Walkthough -->
READ THE STUDIO WALKTHROUGH
ADD SOME (At least two) TODOS IN THE CODE


1. Write a function where we can fetch the user's watchlist.
    - Rather than hardcode, we will dynamically do this.
        - write the function hardcoding a return list

<!-- CODE --> 
def get_current_watchlist():
    # returns user's current watchlist--hard coded for now
    return [ "Star Wars", "Minions", "Freaky Friday", "My Favorite Martian" ]
<!-- CODE -->
    - Use the str.format method
        - write loop to hardcode the options for the select piece
        - rewrite the crossoff_form list and use str.format with the last piece
<!-- CODE -->
crossoff_options = ""
for movie in get_current_watchlist():
    crossoff_options += '<option value="{0}">{0}</option>'.format(movie)

crossoff_form = """
    <form action="/crossoff" method="post">
        <label>
            I want to cross off
            <select name="crossed-off-movie"/>
                {0}
            </select>
            from my watchlist.
        </label>
        <input type="submit" value="Cross It Off"/>
    </form>
""".format(crossoff_options)

<!-- CODE -->
2. Add some validation on crossoff route
    - make sure movie is on list first (if movie not in....)
    - else redirect to the home page with query error message. Note spaces are not allowed in URLs
        - (if movie not in.... create error)
        - return redirect("/?error={}".format(error))

<!-- CODE -->
if crossed_off_movie not in get_current_watchlist():
    # the user tried to cross off a movie that isn't in their list,
    # so we redirect back to the front page and tell them what went wrong
    error = "'{0}' is not in your Watchlist, so you can't cross it off!".format(crossed_off_movie)

    # redirect to homepage, and include error as a query parameter in the URL
    return redirect("/?error=" + error)
<!-- CODE -->   
    
    - display error message
        - edit index route to include errors

<!-- CODE -->
error = request.args.get("error")
if error:
    error_esc = cgi.escape(error, quote=True)
    error_element = '<p class="error">' + error_esc + '</p>'
else:
    error_element = ''

# combine all the pieces to build the content of our response
main_content = edit_header + add_form + crossoff_form + error_element

 <!-- CODE -->   
    

3. Why is this necessary? Doesn't the Drop Down prevent this from happening? Nope, because we can edit HTML uysing Dev tools. 
