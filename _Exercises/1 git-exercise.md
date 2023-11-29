# Week 1 Git Exercise

Open up Git BASH (on Windows) or your terminal (on Mac/Linux). Make sure that you are in the folder where you want your repository to be on your computer. With Git BASH, you can do this easily by finding the place you want on your file explorer then right-clicking and choosing "Git Bash Here". You can always use the `cd` command to move around to the folder/directory that you want to be in.

1. **Clone your team's repository.** What is cloning? This means that you're creating a copy of the contents of the repository on your own computer that is linked to the remote version (the one that you're looking at on GitLab).
``` sh
git clone https://github.com/220620-java/team-YOURTEAMNAME.git
```
2. This will create a folder named `team-YOURTEAMNAME` in the location where you ran the command. Go into that folder to get started. Don't forget that you can use the tab key to easily autocomplete your command.
``` sh
cd ./team-YOURTEAMNAME/
# or just
cd team-YOURTEAMNAME
```
3. **When you first clone the repository, you are on the default branch (`main`). Before you make any changes, create your own branch.** What does this mean? When you create a branch, you are creating a copy of the branch you're currently on. This copy allows you to make changes as much as you want without needing to worry about messing up code on the branch that you copied from. This is important because the main branch should typically be the final version of code that is safe and ready to go, so you want to keep your changes on a separate branch until they are fully tested and/or reviewed.
``` sh
git checkout -b your-branch-name
# note - the "-b" flag creates a new branch if the specified name isn't already a branch on this repository.
# "git checkout branch-name" by itself will just switch to an already existing branch.
```
4. Now you are on your own branch and you can start editing files safely. However, if other people have changed things between you doing step 2 and now, you might not have the most up-to-date version of the files from the `main` branch. **You should always be sure to pull the most recent changes before you start editing files so that you can avoid conflicts.** What are conflicts? Merge conflicts arise when you pull code from the remote repository, and there is some kind of conflict with your local copy - maybe you changed a line somewhere, but somebody else changed it in a different way and already pushed it to the repository. We'll talk about how to fix merge conflicts soon.
``` sh
git pull origin main
# "origin" is in reference to the remote copy of the repository (rather than your local copy).
```
5. After you're sure that you've pulled the most up-to-date version of the `main` branch, you can start editing. **Open up the about-us.txt file and add a sentence about yourself.** You can go into your file explorer to open up the file in your text editor of choice, or just use a command to open it from the terminal/BASH. If your team hasn't made the file yet, you'll need to do that first, of course. You can do this from your file explorer or by using the first command below.
``` sh
# creating the file if necessary
touch about-us.txt
# some options for opening the file from the text editor
vim about-us.txt
nano about-us.txt
code about-us.txt
```
6. Now that you've added your changes and saved the file, let's start putting those changes on the remote copy of your branch so that it's not just on your computer all alone. **First, we need to add changes to the current commit** (we'll talk about commits in the next step). Added changes are called "staged" files, i.e. they are in "staging".
``` sh
git add about-us.txt
# add everything by using "git add ."
# add multiple specific files by using "git add file-name-1.txt file-name-2.java" with spaces between file names.
```
7. **Once all of your changes are added, you can commit.** What does this mean? A commit is a way of keeping track of a group of changes. It's good to commit related changes together, because with Git, you can do things like look back at a previous commit or even revert back to a specific one if you've messed up. This is one of the ways that Git can be used to managing versions of files and code bases, so you can think of a commit kind of like a "version" of a particular branch.
``` sh
git commit -m "message describing the changes you made"
# the "-m" flag is necessary, as it allows you to write your commit message.
# in quotes are your commit message, which should be clear and concise so that others know what changes you made.
```
8. **After making commits, you need to push your code to the remote repository.** This is when you send your changes from your computer (local) to the remote repository (the one on GitLab) so that everybody is able to see them and use them. Generally you should be pushing to the same branch that you're working on. Note, you may be asked for your Git credentials here - use the `git config` commands that it gives you to set that up if needed.
``` sh
git push origin your-branch-name
```
9. **Now you can go to GitLab and make a merge request to `main`.** Making a merge request is simply submitting a request to merge your branch with another branch. Often this will be merging it back to whatever branch it originally branched off of (in this case, we branched off the main branch, so we are merging the changes back into that branch).
    1. Go to the repository on GitLab and find "Merge requests" on the sidebar.
    2. Click on the "New merge request" button.
    3. Set the source branch to your branch. This is the "source" because it's where the new code is that you're adding.
    4. Make sure the target branch is set to `main`. This is the target of the merge - where the new code is going to.
    5. Click "Compare branches and continue".
    6. Name the merge request whatever you'd like (ideally describing the changes you'd made).
    7. Be sure to uncheck "Delete source branch when merge request is accepted" if it's checked so that your branch doesn't get deleted (you'll continue using it during training).
    8. Click "Create merge request".
10. **Now, let the trainer know that you made your merge request** so that they can approve it and the next person can add their updates!

## What if I ran into merge conflicts?

When you run into merge conflicts, your terminal/BASH will give you a message saying `CONFLICT` and it will tell you which files have conflicts. The first thing that you need to do is open those files in the editor of your choice. I recommend Visual Studio Code for resolving merge conflicts as it can make it easier. Once you've opened the files, you'll find which parts of the code have conflicts because they look something like this:
```Java
<<<<<<< HEAD
// the changes that you made
=======
// the changes that someone else made
>>>>>>>
```
In a basic editor, you simply need to remove the "weird" lines (the ones with `<`, `>`, or `=` signs) and modify the contents in between so that they reflect the change you want. When working on a team, it's usually helpful to consult others when you do this so that you don't delete/change code that you weren't supposed to.

In Visual Studio Code (and other editors), it will make this process a little bit easier by giving you options above the conflict to accept the changes you've made (current changes), the incoming changes, both, or to compare and choose what you want and don't want. This is really handy, especially when you're dealing with a lot of merge conflicts (maybe after some major changes).

After you've done this, you'll need to `add` and `commit` your fix before you can continue with whatever you were trying to do.

However, there are *many* situations where you can simply avoid getting merge conflicts by:
- **always pulling before you make changes**, 
- **pushing often as you make changes**, and of course, 
- **communicating with your team about what changes are being made to which files.**

## Other Resources

- [Quick, informal article about Git](https://www.freecodecamp.org/news/learn-the-basics-of-git-in-under-10-minutes-da548267cc91/)
- [Deeper dive about branching and merging](https://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging)
- [Git Cheatsheet by GitLab](https://about.gitlab.com/images/press/git-cheat-sheet.pdf)
- [Git Cheatsheet by GitHub](https://education.github.com/git-cheat-sheet-education.pdf)
    - note that GitLab and GitHub are essentially just two separate Git tools, but Git exists on its own, so these cheatsheets are not really all that different - you might just find one easier to read/use than another which is why I provide both.