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

Pushes the committed files to Github. If you are pushing a branch, you will need to use `git push -u origin <branch-name>`.

Example: `git push -u origin fy-add-auto-code`

It is a good idea to push all your changes when you are done for the day. This acts as a backup for your code in case the files on your computer become corrupted. It also allows others to see the work you've done so if you made an important change that someone needs, then they will have access to it.

---

`git pull`

Pulls (gets) the newest changes from Github. You should only use this command if you are on **main** branch. 
Make it a habit to `git pull` on main branch before you create a new branch!

---

`git status`

Checks the status of the changes on your current branch. For example, if you have changed files in your branch and you run this command, it will tell you which files have changed.

---

`git merge <branch-that-you-want-to-merge-into-current-branch>`

Example: `git merge main`

This command won't be used often, but it's good to know. If you are working on your own branch (not main branch), and someone makes a change that you want in your branch, then do the following:

1. Have the person push their branch to Github and open a pull request
2. Have a mentor review the pull request and wait for the mentor to approve/merge the PR into the main branch
3. On your computer, switch to main branch and run `git pull` to get the latest changes
4. Switch back to the branch you were previously on and run `git merge main`

All the changes from that person should show up o your branch now!

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
