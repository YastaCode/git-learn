## Git Install
Download git for free from the following website: [https://git-scm.com/](https://git-scm.com/)
## Using Git with Command Line
The first thing we need to do, is to check if Git is properly installed:
```bash
% git --version
git version 2.39.5 (Apple Git-154)
```
## Configure Git
This is important for version control systems, as each Git commit uses this information:
```bash
% git config --global user.name "name-user"
% git config --global user.email "email-user"
```
## Creating Git Folder
Now let's create a new folder for our project:
```bash
% mkdir myProject
% cd myProject
```
## Initialize Git
Once you have navigated to the correct folder, you can initialize Git on that folder:
```bash
% git init
Initialized empty Git repository in /Users/user/myProject/.git/
```
## Git Adding New Files
For this example, I am going to use a simple HTML file like this:
```bash
% touch index.html
% ls
index.html
% git status
On branch master

No commits yet

Untracked files:
  (use "git add ..." to include in what will be committed)
    index.html

nothing added to commit but untracked files present (use "git add" to track)
```
## Git Staging Environment
For now, we are done working with index.html> So we can add in to the Staging Environment:
```bash
% git add index.html
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached ..." to unstage)
    new file: index.html
``` 
## Git Add More than One File
A README.md file that describes the repository (recommended for all repositories):
A basic external style sheet style.css:
```bash
% touch README.md
% touch myStyle.css
% git add --all
% git status
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached ..." to unstage)
        new file:   README.md
        new file:   style.css
        new file:   index.html
```
**Note**: The shorthand command for git add --all is git add -A
## Git Commit
When you commit, we should **always** include a **message**
```bash
% git commit -m "First release of Hello World!"
[master (root-commit) 221ec6e] First release of Hello World!
 3 files changed, 26 insertions(+)
 create mode 100644 README.md
 create mode 100644 bluestyle.css
 create mode 100644 index.html
 ```
 The Staging Environment has been committed to our repo, with the message:
"First release of Hello World!"
## Git Commit without Stage
Let's add a small update to index.html
```bash
% git commit --short
M index.html
```
**Note** Short status flags are:
* ?? - Untracked files
*  A - Files added to stage
*  M - Modified files
*  D - Deleted files

We see the file we expected is modified. So let's commit it directly:
```bash
% git commit -a -m"Updated index.html with a new line" 
[master 09f4acd] Updated index.html with a new line
 1 file changed, 1 insertion(+)
```
## Git Commit Log
To view the history of commits for a repository, you can use **log** command.
```bash
% git log
commit 09f4acd3f8836b7f6fc44ad9e012f82faf861803 (HEAD -> master)
Author: w3schools-test 
Date:   Fri Mar 26 09:35:54 2021 +0100

    Updated index.html with a new line

commit 221ec6e10aeedbfd02b85264087cd9adc18e4b26
Author: w3schools-test 
Date:   Fri Mar 26 09:13:07 2021 +0100

    First release of Hello World!
```
## Git Help
If you are having trouble remembering commands or options for commands, you can use Git help.

 Let's go over the different commands.
 * % [git command --help](https://www.w3schools.com/git/git_help.asp?remote=github#:~:text=Git%20%2Dhelp%20See%20Options%20for%20a%20Specific%20Command)
 * % [git help --all](https://www.w3schools.com/git/git_help.asp?remote=github#:~:text=Git%20help%20%2D%2Dall%20See%20All%20Possible%20Commands)

 **Note**: If you find yourself stuck in the list view, SHIFT + G to jump the end of the list, then q to exit the view.

 ## Git Branch
 In Git, a branch is a new/separate version of the main repository.

 We are working in our local repository, and we do not want to disturb or possibly wreck the main project.

So we create a new **branch**:
```bash
% git branch hello-world-images
```
Let's confirm that we have created a new **branch**:
```bash
% git branch
  hello-world-images
* master
```
**checkout** is the command used to check out a **branch**. Moving us from the current **branch**, to the one specified at the end **of the command:
```bash
% git checkout hello-world-images
Switched to branch 'hello-world-images'

% git branch
* hello-world-images
  master
```
Now we have moved our current workspace from the master branch, to the new **branch**
```bash
% git status
On branch hello-world-images
Changes not staged for commit:
  (use "git add ..." to update what will be committed)
  (use "git restore ..." to discard changes in working directory)
        modified:   index.html

Untracked files:
  (use "git add ..." to include in what will be committed)
        img_hello_world.jpg

no changes added to commit (use "git add" and/or "git commit -a")
```
So we need to add both files to the Staging Environment for this **branch**:
```bash
% git add --all
```
Using --all instead of individual filenames will **Stage** all changed (new, modified, and deleted) files.
Check the status of the branch:
```bash
% git status
On branch hello-world-images
Changes to be committed:
  (use "git restore --staged ..." to unstage)
    new file: img_hello_world.jpg
    modified: index.html
```
We are happy with our changes. So we will commit them to the branch:
```bash
% git commit -m "Added image to Hello World"
[hello-world-images 0312c55] Added image to Hello World
2 files changed, 1 insertion(+)
create mode 100644 img_hello_world.jpg
```
Now we have a new branch, that is different from the master branch.

**Note**: Using the -b option on checkout will create a new branch, and move to it, if it does not exist
## Switching Between Branches
We can see the new file img_hello_world.jpg, and if we open the html file, we can see the code has been altered. All is as it should be.

Now, let's see what happens when we change branch to master
```bash
% git checkout main
```
The new image is not a part of this branch. List the files in the current directory again:
```bash
% ls 
README.md  style.css  index.html'
```
## Emergency Branch
So we create a new branch to deal with the emergency:
```bash
% git checkout -b emergency-fix
Switched to a new branch 'emergency-fix'
```
We have made changes in this file, and we need to get those changes to the master branch.
```bash
% git status
On branch emergency-fix
Changes not staged for commit:
  (use "git add ..." to update what will be committed)
  (use "git restore ..." to discard changes in working directory)
        modified:   index.html

no changes added to commit (use "git add" and/or "git commit -a")
```
stage the file, and commit:
```bash
% git add index.html
% git commit -m "updated index.html with emergency fix"
[emergency-fix dfa79db] updated index.html with emergency fix
 1 file changed, 1 insertion(+), 1 deletion(-)
 ```
 ## Merge Branches
 First, we need to change to the master branch:
 ```bash
% git checkout master
Switched to branch 'master'
```
Now we merge the current branch (master) with emergency-fix:
```bash
% git merge emergency-fix
Updating 09f4acd..dfa79db
Fast-forward
 index.html | 2 +-
 1 file changed, 1 insertion(+), 1 deletion(-)
 ```
 As master and emergency-fix are essentially the same now, we can delete emergency-fix, as it is no longer needed:
 ```bash
 % git branch -d emergency-fix
Deleted branch emergency-fix (was dfa79db).
```
## Merge Conflict
```bash
% git checkout hello-world-images
Switched to branch 'hello-world-images'
```
Now, we are done with our work here and can stage and commit for this branch:

```bash
% git add --all
git commit -m "added new image"
[hello-world-images 1f1584e] added new image
 2 files changed, 1 insertion(+)
 create mode 100644 img_hello_git.jpg
 ```
 We see that index.html has been changed in both branches. Now we are ready to merge hello-world-images into master. But what will happen to the changes we recently made in master?
 ```bash
 % git checkout master
git merge hello-world-images
Auto-merging index.html
CONFLICT (content): Merge conflict in index.html
Automatic merge failed; fix conflicts and then commit the result.
```
he merge failed, as there is conflict between the versions for index.html. Let us check the status:
```bash
% git status
On branch master
You have unmerged paths.
  (fix conflicts and run "git commit")
  (use "git merge --abort" to abort the merge)

Changes to be committed:
        new file:   img_hello_git.jpg
        new file:   img_hello_world.jpg

Unmerged paths:
  (use "git add ..." to mark resolution)
        both modified:   index.htm
```
So we need to fix that conflict. Open the file in our editor:
```html
<!DOCTYPE html>
<html>
<head>
<title>Hello World!</title>
<link rel="stylesheet" href="bluestyle.css">
</head>
<body>

<h1>Hello world!</h1>
<div><img src="img_hello_world.jpg" alt="Hello World from Space" style="width:100%;max-width:960px"></div>
<p>This is the first file in my new Git Repo.</p>
<<<<<<< HEAD
<p>This line is here to show how merging works.</p>
=======
<p>A new line in our file!</p>
<div><img src="img_hello_git.jpg" alt="Hello Git" style="width:100%;max-width:640px"></div>
>>>>>>> hello-world-images

</body>
</html>
```
We can see the differences between the versions and edit it like we want:
```html
<!DOCTYPE html>
<html>
<head>
<title>Hello World!</title>
<link rel="stylesheet" href="bluestyle.css">
</head>
<body>

<h1>Hello world!</h1>
<div><img src="img_hello_world.jpg" alt="Hello World from Space" style="width:100%;max-width:960px"></div>
<p>This is the first file in my new Git Repo.</p>
<p>This line is here to show how merging works.</p>
<div><img src="img_hello_git.jpg" alt="Hello Git" style="width:100%;max-width:640px"></div>

</body>
</html>
```
Now we can stage index.html and check the status:
```bash
% git add index.html
git status
On branch master
All conflicts fixed but you are still merging.
  (use "git commit" to conclude merge)

Changes to be committed:
        new file:   img_hello_git.jpg
        new file:   img_hello_world.jpg
        modified:   index.html
```
The conflict has been fixed, and we can use commit to conclude the merge:
```bash
% git commit -m "merged with hello-world-images after fixing conflicts"
[master e0b6038] merged with hello-world-images after fixing conflicts
```
And delete the hello-world-images branch:
```bash
% git branch -d hello-world-images
Deleted branch hello-world-images (was 1f1584e).
```
Now you have a better understanding of how branches and merging works. Time to start working with a remote repository!