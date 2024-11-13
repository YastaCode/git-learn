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