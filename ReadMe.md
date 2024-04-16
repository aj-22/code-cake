# Steps

1. Create an empty repository
```sh
git init code-cake -b main
```

2. Initial Commit
Create a file ReadMe.md
```sh
git add .
git commit -m "Initial Commit"
```

3. Set up Remote
Got to Github.com
Create a Repo with name `code-cake`
Copy its link `https://github.com/aj-22/code-cake.git`
```sh
git remote add origin https://github.com/aj-22/code-cake.git
```

4. Push local changes to Remote
```sh
git push origin main
```

5. Create Dev, QA and Prod Branches
```sh
git checkout -b dev
git checkout -b qa
git checkout -b prod
```

6. Push branches to Origin for Tracking
```sh
git push -u origin prod
git push --set-upstream qa
git push -u origin dev
```

7. Pull file from GitHub.com into Local
Create `dummy.py` in GitHub.com in the dev branch
```sh
git checkout dev
git pull
```

8. Push changes from Local to GitHub.com
```sh
git checkout dev
git add .
git commit -m "Updated Readme.md"
git push remote origin 
```

Realize that if you make changes after adding, the new changes will not be committed with `git commit`.
New changes need to be staged again.

9. Add new changes and commit
```sh
git add .
git commit -m "Added the changes that were missed"
```

10. Create feature branch and raise a PR to merge it to dev
```sh
git checkout -b feature-1a
# Add feature.py to local repo
git add .
git commit -m "Added feature"
git push origin feature-1a
```
Create a Pull Request in Github.com to merge feature-1a to dev. Delete the branch from remote.

Delete the branch from local.
```sh
git branch -d feature-1a
```
Commit this change in ReadMe.md locally and push it to remote.
```sh
git add .
git commit -m "Updated ReadMe.md"
git push origin dev
```

# Hands-on with cherry-pick

1. Create Feature Branch 1b
```sh
git status # Check if on dev
git pull origin dev # Sync with Origin
git checkout -b feature-1b
```
Add multiple random commits to `feature.py` file.
Note down the commit number after committing.
For example,
commit-1 = `acfb640`
commit-2 = ``
commit-3 = ``