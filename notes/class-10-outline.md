<!-- Reminders -->

<!-- Studio Solution -->
line 7: change password

Run code to see current functionality.

line 16: ratings = db.Column(db.String(5))

line 42:

line 63: 
    movie.rating = rating
    db.session.add(movie)
    db.session.commit()

    return render_template('rating-confirmation.html', movie=movie)


ratings.html
    <option {% if movie.rating == rating %} selected {% endif %}>{{ rating }}</option>


<!-- Summary -->

<!-- Q&A -->

<!-- Studio Walkthough -->
git checkout stuff 

<!-- TODO 0 -->
Add a User Class

    
    class User(db.Model):
        id = db.Column(db.Integer, primary_key=True)
        email = db.Column(db.String(120), unique=True)
        password = db.Column(db.String(120))
    
        def __init__(self, email, password):
            self.email = email
            self.password = password
    
        def __repr__(self):
            return '<User %r>' % self.email


<!-- TODO 1 -->
New Routes and methods: register and logout

    @app.route("/register", methods = ["GET", "POST"])
    def register():
        if request.method = "POST":
            email = request.form["email"]
            password = request.form["password"]
            if not is_email(email):
                flash(email + "does not seem like an email address")
                return redirect("/")

            user = User(email = email, password = password)
            db.session.add(user)
            db.session.commit()
            session["user"] = user.email
            return redirect("/")
        else:
            return render_template("register.html")


+@app.route("/logout", methods=['POST'])
+def logout():
+    del session['user']
+    return redirect("/")

## Need to write an is_email function

+def is_email(string):
+    # for our purposes, an email string has an '@' followed by a '.'
+    # there is an embedded language called 'regular expression' that would crun            ch this implementation down
+    # to a one-liner, but we'll keep it simple:
+    atsign_index = string.find('@')
+    atsign_present = atsign_index >= 0
+    if not atsign_present:
+        return False
+    else:
+        domain_dot_index = string.find('.', atsign_index)
+        domain_dot_present = domain_dot_index >= 0
+        return domain_dot_present


<!-- TODO 2 -->
    register template

    {% extends "base.html" %}
    {% block content %}

    <h2>Register New Account</h2>
    <form action="/register" method="post">
        <label>Email: <input type="text"  name="email"/></label>
        <label>New Password: <input type="password" name="password" /></label>
        <label>Verify Password: <input type="password"  name="verify"/></label>
        <input type="submit" value="Register"/>
    </form>

    {% endblock %}

<!-- TODO 3 -->
    base template to display email OR login/register links

    @@ -9,10 +9,30 @@
         </style>
     </head>
     <body>
+        <div style='float: right'>
+          {% if 'user' in session %}
+            {{ session['user'] }}
+            <form action="/logout" method="post">
+              <input type="submit" value="Log Out" />
+            </form>
+          {% else %}
+            <a href="login">login</a> | <a href="register">register</a>
+          {% endif %}
+        </div>
         <h1>
             <a href="/">FlickList</a>
         </h1>

+        


<!-- TODO 4 -->
    @app.before request thing

    @app.before_request
    def require_login():
        if not ('user' in session or request.endpoint = "register"):
            return redirect("/register")


<!-- TODO 5 -->
    base.html with flash messages

    {% with messages = get_flashed_messages() %}
+          {% if messages %}
+            <ul class=flashes>
+              {% for message in messages %}
+              <li>{{ message }}</li>
+              {% endfor %}
+            </ul>
+          {% endif %}
+        {% endwith %}
+
         {% block content %}
         {% endblock %}
