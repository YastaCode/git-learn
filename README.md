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