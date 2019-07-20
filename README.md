# GIT_Tutorials
GIT DVCS - Basics
GIT Tutorial by https://www.youtube.com/watch?v=dnGeRjP8oxw

DVCS - GIT is most famous among all

GIT is a VCS used for Source Code management in software development

1.Creating Repository
2.Making Changes
3.Parallel development
4.Syncing Repositories

mkdir mydevops
cd mydevops
echo "Hello world" > file1.txt
echo "Hello two" > file2.txt

These two files are in Local FileSystem and not tracked by GIT so inorder to convert them into GIT file system then we can run the following

git init 

git status

untracked files are file1 and file2

to add these files

git add file1.txt file2.txt 
or
git add .

git status

now we are in staging area, so to add these files from local file system into GIT file system then do commit

git commit -m "Initial commit"

git status

shows working tree clean

echo "File3" > file3.txt
modify file2.txt

git status
says
file3.txt untracked
file3.txt modified


================ Syncing Repositories

Inorder to make these codes avail to the world we need to create github repo

Create an account and a repo in GitHub.com 

Now we can push our changes to the remote repository

git remote add origin "Url of Git"


git remote add origin "https://github.com/svenugopal/myrepo.git"

git push origin master
username:
password:

git add file2.txt

git status

git commit -m "modified file2"

now the changes are completed in my local repository but not in the remote repository

git push origin master

now the files are pushed even to the remote repository

git add .

git commit -m "adding 3.txt"

git push origin master

===

How this repo can be used again by someone else 


git clone "https://github.com/svenugopal/myrepo.git"

echo "file 4" > file4.txt

now another person just added file4.txt

git add .

git commit -m "Adding file 4"

git push origin master
username:
password:

=======================================
How to get the files remote repo files to my local repository

git pull origin master 

now I can get file4.txt to my local repository

echo "this is file5" > file5.txt

git add .

git commit -m "adding file5"

git push origin master
username:
password:

if user b logs in then do git pull

=======================================
difference between git clone and git pull

git pull - update the files in your local repo

git clone - copy whole repo to your local system
====================Parallel development =======

To create a branch
git branch <name of the branch>
git branch feature1
git branch feature2

To delete a branch
git branch -D <name of the branch>

To switch to the new branch
git checkout <name of branch>

To know in which branch you are in now
git branch

If I create a file in feature1 branch then if I go to master branch, the new file added in feature1 branch will not be available unless you push the files from feature1 branch and raise a pull request to master branch , finally merge it with master branch

git checkout master 

------
git checkout feature1

git status 
says 
working tree clean

git push origin feature1

=======================================
git log

helps to see the history of a repository

it shows the logs of the current branch which I have switched.

the moment I create a branch then all commits in a master branch will also be a part of feature branch

=======================================
Git STASH

stash helps to save your work without committing the code

In the middle of your work, if u want to save your work switch branches (to master branch) but do not want to save your work to git repository then "git stash" command will help to serve your purpose.

if want to stash your untracked files  as well, then type "git stash -u"

Once you are back to your feature branch and want to retrieve working, type in 
"git stash pop"

=======================================
To revert it to the previous commit id 

git revert <commit-id>

=======================================

