# Class 2 Outline
- Studio Solution: Not really the way this one works
- Questions before the lecture?
- HTML
- CSS
- Git
- Studio Walkthrough

----------------------------------------------------------------

<!-- Example 1 -->
- Gitbash-> cd lc101/class2/examples
- touch example1.html
- code .
- . is shorthand for the current directory
- Explain what you are doing as you work with command line.
- Have students help you write HTML template.

<!DOCTYPE html>
<html>
    <head>
    </head>
    <body>
        <h1 style="color: red;">Hello, World!</h1>
    </body>
</html>

----------------------------------------------------------------

<!-- Example 2 -->
- cd lc101/class2/examples
- touch example2.html
- code .

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

----------------------------------------------------------------

<!-- Example 3 -->
- cd lc101/class2/examples
- touch example3.html
- mkdir css (we often will organize a css dir to hold all .css files for a project)
- cd css
- touch stylesheet1.css
- code ..
- .. is short hand for our parent directory

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

-----------------------------------------------------------------

<!-- Example 4 -->
- cd lc101/class2/examples
- touch example4.html
- cd css 
- touch stylesheet2.css
- cd ..
- code .

<!DOCTYPE html>
<html>
    <head>
        <link rel="stylesheet" href="css/stylesheet2.css">
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


<!-- Git Local Example -->

cd ~
mkdir temp
cd temp
git init
touch file.py
git status
code file.py
(write a python file to square a number (write it wrong))
git status
git add .
git status
git commit -m "first commit"
python file.py
(fix error)
python file.py 
git status
git add .
git -m "fixed *2 to **2"

- All local stuff so far. 

Clone HTML-Me-Something as well and Flicklist
cd ~/lc101/class2
git clone (find my repo on github to use for branching and merging.)
git clone (find the LC repo on github to show more branching ideas.)

- Mention we will work with this stuff again later.

<!-- Example of Branching (HTML-Me-Something) -->
- Show how to create a new branch and look at what branches we have locally.
- Why we want a new "development" branch
- show it is hosted somewhere online (Mention bonus mission)

- cd html-me-something
- git branch
- git branch development (because it is hosted somewhere)
- git branch
- git checkout development

- we will work more this when merging


<!-- Example of Branching (Flicklist) -->
- Mention that this will be an important repository
- Show branches (remotely) we have (why would we want these)
- Checkout branches
- list branches

- cd flicklist-flask
- git branch (why is there only the master branch, how do we access remote branches? google it?)
- git branch -a
- git checkout walkthrough1
- git branch
- git checkout studio1
- git branch
- git branch -a

- we will use this repo and these git commands next class


<!-- Example of Merging (HTML-Me-Something) -->
- Show example of merging with a conflict using HTML-Me-Something

- cd ~/lc101/html-me-something
- start index.html
- code . (change main-title class to id and change background color)
- git status
- git add index.html
- git commit -m "changed main-title class to id"
- git status
- git add .
- git commit -m "edited main-title, body bg color"
- git status
- git merge master (nothing happens because we edited from master)
- git checkout master
- git merge development (updated, but no merge conflicts since not both were edited)

- code . (change background color)
- git status
- git add .
- git commit -m "changed main-title color"
- git checkout development 
- code . (change main-title color)
- git status
- git add .
- git commit -m "changed main-title color"
- git merge master (MERGE CONFLICTS, FIX)
- git status
- git add .
- git commit -m "used main-title color from master"
- git status
- git merge master
- git checkout master
- git merge development
- git status
- git push origin master

