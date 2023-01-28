# Git Tutorial
Git is a version control tool. In layterms, this means that you take a snapshot of your repository. The idea is that you can go back to a set snapshot ('commit'), when you require an older version (perhaps a new version is not working for some reason). 

This also provides a way to collaborate and contribute. A repository is hosted at a central place (github in this case), which everyone can copy ('clone') to their local computers. You can then locally work on some part of it and contribute it back ('push') to the central place ('remote'). You can also initialize a repository on a local machine and then push it to start a new repository. 

Here's a brief list of the terminology mentioned:

## Terminology
* Clone: Copy. Git clone means that you are just copying a repository.
* Commit: Saving a snapshot of the repository with the changes that you made.
* Push: Sending the changes you made (commits) upstream to the central location.
* Pull: Receiving the changes in the main repo to your local copy.
* Branch: 

## Workflow
Before you begin working with git, you should configure your git environment.

Right after installing git, run the following two commands in your terminal:
```
git config --global user.email "you@example.com"
git config --global user.name "Your Name"
```
Now, any time you contribute to the repository by committing (taking a snap shot) to it, git will have the information about who made a commit. For more information, refer to the article [here](https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup).

Once you have done that, you should go ahead and clone a repo to your computer. For example, to clone this particular repo,
go to the top page of this repo and look for the green button (upper right) that says clone. Get the https link. In this case the link is: https://github.com/kanavsetia/q-res.git. `cd` to the location on your computer that you would like to clone the repo to locally. Run the following command and the git repo will be copied to that location on your computer as a new directory.
```
git clone https://github.com/kanavsetia/q-res.git
```
Now, you can open files locally and make edits on your own computer. Before you commit your changes, it always helps to see what has ben changed since the last commit.  
Use the following command to see such changes:
```
git status
```
This will tell you about files that have been modified since last commit. Git gives you freedom to choose which changes you want to commit, so not everything you modified needs to go in the commit. You can manually add ('stage') the changes that you want to commit using
```
git add 'filename'
```
If you want to add ('stage') all the files in a directory for the next commit, use `git add *`. After staging, you can commit the changes with
```
git commit -m 'Type your message about the commit here'
```
The `-m` option lets you specify the message in the command line itself. If you just do `git commit`, then git opens up the default editor for you to type your message. You can also do the `git add` and `git commit` is a single step:
```
git commit -m -a "message here"
```
This adds all the modified files and commits. With this a snapshot of your changes has been made. Now if you want to send these changes to the central location, you can run the following command:
```
git push origin master
```
where 'origin' is the name of the host and 'master' is the branch name. 

There is so much more that you can do with git, so we will list some commands here along with little info about what they do.
It may feel like a lot to learn but with regular usage it will all make sense.


## Important Commands
A brief note on command structures. All the commands start with `git`, followed by the `command`. You can also have options and arguments in addition. Options have the structure `-x` where x is a letter that depends on the command you are using. All the different options available for a given command can be displayed by using the help command of the `-h` option (see below). Depending on the command, you may or may not need to provide an option or argument. It always helps to just look at the help page to know more about the arguments that are required and the different option flags present for the command.

Below are some useful commands:
```
git help "command"
```
This pulls up the help page for that particular command and opens up the pdf for it.
```
git "command" -h
```
Displays help inline.
```
git clone 'repository link' 
```
Clones the repo to your local machine as a directory just under the current directory.
```
git help tutorial
```
Pulls up the git tutorial page from git bash.
```
git checkout 'branchname'
```
Checks out (puts you in) a new branch.
```
git diff 'file1'/'branch1' 'file2'/'branch2'
```
Compares the difference between two files or branches.
```
git config --global core.autocrlf true
```
Editing files in two different environments can lead to erratic behvaior due to different new line characters. Git may think all the files have been modified, so use this command to avoid this problem.
```
git rm --cached
```
Remove files from the staging area.
```
git reset --hard head
```
Removes changes that have been made in the working directory but have not yet been commited.

## Important pages from the git-scm book
There are pages which are more useful to your daily use than others. We would like to present the ones that we found most useful:
- 2.3 [Git Basics](https://git-scm.com/book/en/v2/Git-Basics-Recording-Changes-to-the-Repository) Essentially the extended version of this tutorial.
- 2.5 [Remotes](https://git-scm.com/book/en/v2/Git-Basics-Working-with-Remotes) This contains lot of info about working with remotes.
