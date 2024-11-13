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