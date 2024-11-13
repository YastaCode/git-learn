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