--- 
- Keep track changes that we make to code
- Version Control tool
- Command line tool
- Synchronizes code between different people (Repositories)
- Test changes to the code without losing the original (Branch)
- Revert old versions of code
--- 

**We need store our get code!** 

## What is GitHub?

Is a website that store Git repositories

(Repository : Folder that hold a whole bunch of code and files related to our code)

## Git Basic Commands

### Git clone

Take a repository form the internet and download it to our computer

~~~
git clone <url>
~~~

### Git add

I want add a file as one to track the next time I save or the next time I make a commit 

~~~
git add <filename>
~~~

### Git commit

I would like to take a snapshot of the current state of the repository keeping track of the file that I've added using git add 

~~~
git commit -m <message>

// <message> : Known as a commit message, is a description of what changes you've made in this most recent commit
~~~

### Git status

Tell us what is currently happening inside of my repository

~~~
git status
~~~

### Git push 

Whatever changes that I've made, when I run git push, those changes get pushed up to GitHub

~~~
git push
~~~

Or push the changes to some remote server

### Git add-commit all in one!

Useful as we need to keep track all of the changes saved in the files for the next commit

~~~
git commit -am <message>

// -am : means git commit all of the files that have been changed
~~~

Combine the git add step and git commit step into just a single step for all of the files that I've change and then I'll provide a message 

### Git pull

Take the changes that currently exist on GitHub and go ahead and pull the most recent changes down 

~~~
git pull
~~~

## Merge conflicts 

~~~
// Posible output for git pull command
>> git pull
remote: Enumerating objects: 5, done.
remote: Counting objects: 100% (5/5), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 1), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (3/3), 669 bytes | 26.00 KiB/s, done.
From https://github.com/dabog01/sampleRepo
   9d03c3b..6f13fb7  main       -> origin/main
Auto-merging hello.html
CONFLICT (content): Merge conflict in hello.html
Automatic merge failed; fix conflicts and then commit the result.
~~~

**The resulting file after a merge conflict will look something like this **

~~~
<!DOCTYPE hmtl>
<html lang="en">
    <head>
        <title>Hello!</title>
    </head>
    <body>
<<<<<<< HEAD
        <h1>Welcome to my web page!!</h1>
=======
        <h1 style="color: blue">Welcome to my web page!</h1>
>>>>>>> 6f13fb7c155dfd0b120a2748df3608f76696ea37
        <h2>Second heading</h2>
        Hello, World! :)
    </body>
</html>
~~~


**Play with it to come up with a useful solution. Human intuition is cool! :p**

**NOTE : After this... git add and git commit the resulting code!!!**

### Git log 

Is useful if need keep track of all your the commit that have been made

~~~
get log
~~~

### Get reset

Will take the current state of the repository and reverted back to an older state of the repository

~~~
get reset --hard <commit>

get reset --hard origin/master 
~~~

## Branching

Is a Git's way of working on diferent parts of the repository at the same time

![[Pasted image 20230607162414.png]]

**NOTE : The head is switchable between branches**

### Git branching commands

#### Git branch

~~~
git branch
~~~

Tell me what branch I'm currently on and what branches exists in my repository 

#### Git checkout 

##### Create a new branch

~~~
git checkout -b <branch_name>
~~~

##### Move between branches

~~~
git checkout <branch_name>
~~~

#### Git merge

~~~
git merge <branch_name>
~~~

## Features

### Forking (Bifurcación)

Forking a GitHub repository mean making your own copy of the original repository

==Useful Example : Bootstrap GitHub Repository==

### GitHub Pages

GitHub Pages website for free

https://github.com/new

Repository Name : username.github.io

**Play with it and create your website!! :p**


