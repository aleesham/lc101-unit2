<!-- Studio Solution -->

<!-- TODO 1 --> MAke User and Movies relate
    Line 29:
        owner_id = db.Column(db.Integer, db.ForeignKey('user.id'))

    Line 31, 34:
        def __init__(self, name, owner):
            self.owner = owner

    Line 16: 
        movies = db.relationship("Movie", backref = "owner")

    Lines 48-52:
    def get_current_watchlist(current_owner_id):
        return Movie.query.filter_by(watched=False, owner_id = current_owner_id).all()

    def get_watched_movies(current_owner_id):
        return Movie.query.filter_by(watched=True, owner_id = current_owner_id).all()

    Line 169:
        movie = Movie(new_movie_name, session['user'])


<!-- TODO 2 --> Refector Code
################################################################################
    Step 1:
        command line: touch models.py
        command line: app.py
################################################################################
    Step 2: Move the following into app
        from flask import Flask
        from flask_sqlalchemy import SQLAlchemy

        app = Flask(__name__)
        app.config['DEBUG'] = True      # displays runtime errors in the browser, too
        app.config['SQLALCHEMY_DATABASE_URI'] = 'mysql+pymysql://flicklist:MyNewPass@localhost:8889/flicklist'
        app.config['SQLALCHEMY_ECHO'] = True

        db = SQLAlchemy(app)
################################################################################
    Step 3: Move the following into models.py
        from app import db

        class User(db.Model):
            id = db.Column(db.Integer, primary_key=True)
            email = db.Column(db.String(120), unique=True)
            password = db.Column(db.String(120))
            
            def __init__(self, email, password):
                self.email = email
                self.password = password

            def __repr__(self):
                return '<User %r>' % self.email

        class Movie(db.Model):
            id = db.Column(db.Integer, primary_key=True)
            name = db.Column(db.String(120))
            watched = db.Column(db.Boolean)
            rating = db.Column(db.String(20))
            owner_id = db.Column(db.Integer, db.ForeignKey('user.id'))

            def __init__(self, name, owner):
                self.name = name
                self.watched = False
                self.owner = owner

            def __repr__(self):
                return '<Movie %r>' % self.name
################################################################################
    Step 4: Refector main.py
        line 1: 
            Delete "Flask" from the imports
        lines 2 and 3:            
            from models import User, Movie
            from app import app, db`


