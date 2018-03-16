<!-- Reminders -->

<!-- Studio Solution -->
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

<!-- Summary -->
- Validation
- Redirects
- HTML Escaping

<!-- Q&A -->
CREATE EXAMPLES POSSIBLY FOR SUMMARY


<!-- Studio Walkthough -->