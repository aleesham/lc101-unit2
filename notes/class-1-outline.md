# Class 1 Outline
- About Me (Set Clear Boundaries)
- About this Section 
- About the Web
- HTML
- Git Basics
- Studio Walkthrough


# About Me (Intro Slide)
- Aleesha, TF for Unit 1. I went through LC CodeCamp last summer. It was sweet. If you ever want to chat about it, you can hit me up on Slack.
- MY ROLE HAS CHANGED in LC101 AND I AM STARTING A JOB. I will NOT be answering questions like I did last unit. You have individual TF groups now. Your TFs should be your second resource behind trying to answer your own question. 


# About Unit 2 (Intro Slide)
- You are expected to finish class Prep before each class. I will not lecture on absolutely everything, but key points will be discussed. Questions and participation during lecture are encouraged. You should not be coding tpp much during lecture really, unless it is something quick (like today when we talk about Git)
- You SHOULD be coding with the prep videos. Pause when necessary. It makes assignments way more approachable.
- Class will be run as follows: Studio answer, lecture, studio walkthrough, studio.



# Questions Slide
- Questions before we begin the lecture?
- If you have not downloaded firefox, do it now so it is ready to go by the end of the lecture. 

# About the Web, HTML
- I will not talk about this. You are expected to read this stuff. If you have questions, google is your friend. Or ask your TF. 

# Git Basics (Slideshow)

# (Introduction Slide)

Git, GitBash, and github are all different things, but they are all related. Git is a VCS which we will talk about in detail. GitBash is a Unix shell/terminal that Windows users will use in this course, we often run `git` commands here. github is a website that allows us to store files remotely. We will talk (or you will read) about this in detail later as well. 

# (What is VCS?)
We will be using git in this class, although we haven't yet unless you are working ahead. (Different from GitBash!)

# (Why use a VCS? Slide 1)

# (Why use a VCS? Slide 2)

# (VCS Visualization Slide)
This is one way you can visualize a VCS. You have your master branch (in this case Development). Then you may want to work on one thing and your coworker will work on another. You create branches (component A and B) so your changes aren't affecting one anothers. Then you merge back to the master. If you have merge issues (your VCS will tell you if you do), you deal with yours then. When component B merges, we do the same. 

# (How do you use a VCS?)
- mkdir temp, git init
- we will talk about remote repos in more detail later
- touch temp.py
- git add .
- git commit -m "initial commit"

# (What is commiting?)
- add (stage) vs commit (committing)
- write some easy code (with a bug) (for loop accumulation sum)
- git add temp.py
- git commit -m "began code"
- fix code
- git add temp.py
- git commit -m "fixed itertion code to add correctly"
- git log

# (Local Repo vs Remote Repo)
- git clone <url for remote repo>
- now you have a local version of a remote repo 
- you need this to work on project, push it to correct branch to correct remote repo
- you get more familiar with it as you work with it more.

# (Using Git as your VCS)
- We have already installed git.
- Here are some which I have shown.
- If you haven't yet, DEFINITELY WATCH THE VIDEOS (Prep Work)
# END OF SLIDES

## DO A git TUTORIAL QUICKLY?
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

## Studio Walkthrough
Open firefox
Go to NYtimes
open dev tools using hamburger>web dev>inspector
open dev tools using shift+ctrl+i
Inspector: highlight over html to see what html elements goes with what on page
Top left: Cursor button to highlight the pic to do the reverse
Actually edit something: Title and picture

href: http://www.akc.org/content/entertainment/articles/cute-puppies
picture: https://img-aws.ehowcdn.com/600x600p/photos.demandstudios.com/getty/article/154/20/87788187.jpg


View source vs inspector



# (TF Slide)
- Introduce the TFs