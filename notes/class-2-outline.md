# Class 2 Outline
- Studio Solution: Not really the way this one works
- Questions before the lecture?
- HTML
- CSS
- Git
- Studio Walkthrough

# Reminders Slide
- Reminder: I will not be here next class period because I will be out of town for work. 


# Questions Slide?

# Introduction Slide
- I will not talk much about HTML.
- I will talk about CSS in depth.
- I will talk about Git branching and merging which are both important for our studio.

# What is CSS?
- You should have read about this.
- The rules between tags versus tags with classes vs tags with ids. We will talk about this later

# Elements have default syles
- Nothing to add here really. 

# Changing an Elements Style
- Using styles (pre-defined)

# Use style attribute of an element
- Show example of changing elements inline
- Avoid this

<!--Example:-->
# Example example1.html
<!DOCTYPE html>
<html>
    <head>
    </head>
    <body>
        <h1 style="color: red;">Hello, World!</h1>
    </body>
</html>

<!-- end example -->

# Where to put your CSS
- Style HTML tag (Provide example: (CODE THIS IN FRONT OF THEM))
- .css file (CODE AND CREATE IN FRONT OF THEM)

<!--Examples:-->
# Example example2.html, example3.html, stylesheet.css

<!--example2.html-->

<!DOCTYPE html>
<html>
    <head>
        <style type="text/css">
	        p {
		        color: red;
            }
        </style>
    </head>
    <body>
        <p>Hello, World!</p>
    </body>
</html>

<!--example3.html and stylesheet.css-->

<!DOCTYPE html>
<html>
    <head>
        <link rel="stylesheet" href="css/stylesheet1.css">
    </head>
    <body>
        <p>Hello, World!</p>
    </body>
</html>
p {
    color: red
}

<!-- end examples -->

# CSS Selectors
- element is the default to the browser

# Class Selector
- show examples of this on slide and in VS Code

# ID Selector
- show examples of this on slide and in VS Code

<!--Examples:-->
# Example example4.html, stylesheet2.css


<!--example4.html and stylesheet2.css-->

<!DOCTYPE html>
<html>
    <head>
        <link rel="stylesheet" href="css/stylesheet.css">
    </head>
    <body>
        <h1 id="main-page-title" class="section-title">Hello, World!</h1>
        <p class="content">This is some stuff.</p>
        <hr/>
        <h2 class="section-title">Hello, USA!</h2>
        <p class="content">This is more stuff.</p>        
    </body>
</html>

h1 {
    color: blue
}

.content {
    text-align: center;
    font-weight: bold;
}

.section-title {
    color: brown;
    font-size: 20px;
    text-align: center;
}

#main-page-title {
    font-size: 40px;
    color: red;
}


<!-- end examples -->


<!--TODO-->

# Branching in Git
- show examples of branching 
- Use Unit-1 Stuff 
- Use HTML-Me-Something to create a new branch, change something in CSS and HTML that will affect the merge, add and commit files separately.

# Merging in Git
- Show example of merging with a conflict using HTML-Me-Something

# Studio Walkthough
- We will work in pairs to create a story one sentence at a time. 
- Why GitHub (remote repositories) are important.
- I won't do any coding/initializing here as the directions are outlined very well. 
- Please find a partner in your groups. 
- If you have an odd number, have one person pair with another group with an odd number of people, or with a TF. 


