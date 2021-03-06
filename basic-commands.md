# Git Commands Visualization

![Git workflow](https://cdn-media-1.freecodecamp.org/images/1*iL2J8k4ygQlg3xriKGimbQ.png)

Credits to [FreeCodeCamp for this image](https://www.freecodecamp.org/news/learn-the-basics-of-git-in-under-10-minutes-da548267cc91/). If you want more in-depth detail about Git, then click the [FreeCodeCamp link](https://www.freecodecamp.org/news/learn-the-basics-of-git-in-under-10-minutes-da548267cc91/)!

# Navigating folders through terminal

`dir`

Lists all files and folders in the current directory.

![dir command](./images/dir.png)

---

`cd ..`

This command will move you up a level (go to parent directory)

![cd .. command](./images/goto-parent.PNG)

---

`cd <path>`

Go to a child directory (basically go into the next folder within the current directory)

![cd <path> command](./images/goto-child.PNG)

# Basic Commands

`git clone <link>`

Example: `git clone git@github.com:frc2609/practice-repo.git`

Allows you to clone a repository from Github onto your computer

---

`git checkout -b <new-branch>`

Example: `git checkout -b fy-add-auto-code`

Creates a new branch based off the one you are currently on. Branch names should only have numbers, letters, and hyphens. 
Make sure branch name is descriptive! Avoid using the same branch name twice (each branch should have a unique name).

---

`git checkout <branch-name-that-already-exists>`

Example: `git checkout main`

Switches to a different branch that you already have. Alternative is to use `git switch <branch-name-that-already-exists>`.

---

`git add <filename(s)>`

Example: `git add changed-file.txt`

Adds the file to the staging area.

---

`git add .`

Same as `git add <filename(s)>`, except it adds **all** changed files to staging.

---

`git commit -m "commit message"`

Example: `git commit -m "add autonomous code"`

Commits the files from staging into the branch's commit history. Commits should be easy to follow and understand. This means that each commit shouldn't be too large. 
Ideally, a commit should have just one change, maybe a few changes if they are small and the same kind of change (like formatting the code). Just try to remember to commit small and commit often.

---

`git push`

Pushes the committed files to Github. If you are pushing a branch **for the first time**, you will need to use `git push -u origin <branch-name>`.

Example: `git push -u origin fy-add-auto-code`

After you've pushed the branch once, any subsequent pushes can just use `git push` for the same branch.

It is a good idea to push all your changes when you are done for the day. This acts as a backup for your code in case the files on your computer become corrupted. It also allows others to see the work you've done so if you made an important change that someone needs, then they will have access to it.

---

`git pull`

Pulls (gets) the newest changes from Github. Make it a habit to `git pull` on main branch before you create a new branch! If you are having trouble pulling, then switch to main branch and retry.

---

`git status`

Checks the status of the changes on your current branch. For example, if you have changed files in your branch and you run this command, it will tell you which files have changed.

---

`git merge <different-branch-that-you-want-to-merge-into-current-branch>`

Example: `git merge main`

This command takes all the changes from one branch and merges it into the current branch.

If you are working on your own branch (not main branch), and someone makes a change that you want in your branch, then do the following:

1. Have the person push their branch to Github
2. Run `git pull` on your computer
3. Run `git merge <branch-name-pushed-by-person>` NOTE: you may need to add `origin/` in front of the branch name

All the changes from that person should show up on your branch now!

# Common issues that may happen to you

#### Scenario 1) I accidentally made changes while still on the main branch! I want to create a new branch to work on but I also want to keep these changes. I did NOT use `git add` or `git commit` yet.

Run the following commands:

1. `git stash` 

This will store all the changes you made in a temporary area and will also remove the changes you made.

2. `git checkout -b <new-branch>`

This will create the new branch that you want to apply the changes to.

3. `git stash apply`

This will retrieve the changes from the temporary area and apply them to the new branch.

#### Scenario 2) I accidentally made changes while still on the main branch! I want to create a new branch to work on but I also want to keep these changes. I used `git add` but did NOT use `git commit` yet.

Run the following command:

1. `git reset` 

This will remove the files from staging (it will unstage them).

2. Run the commands from **Scenario 1)**

#### Scenario 3) I accidentally made changes while still on the main branch! I want to create a new branch to work on but I also want to keep these changes. I used `git add` and `git commit`.

Run the following command:

1. `git reset HEAD^` 

This will remove the latest commit from the commit history. It will also unstage files.

2. Run the commands from **Scenario 1)**
