---
title: Intermediate GIT
author: Maxime Rio
date: February 25, 2020
---

# Today's menu

- Additional handy commands (45 min)

- **Break** (15 min)

- Branching (45 min)

- **Break** (15 min)

- Collaborative platforms (45 min)

- Bonus or **lunch** :-) 

---

# Bash memo

- `pwd`: **p**rint **w**orking **d**irectory
- `ls`: **l**i**s**t directory content
- `man`: display *man*ual (`Q` to exit pager)
- `cd`: **c**hange directory
- `mkdir`: **m**a**k**e **dir**ectory
- `nano`: text editor in the terminal (`^` is ctrl key)
- `cat`: con**cat**enate files, used to display one here

---

# Git memo

- `git config`: set username, email, default editor...
- `git init`: initialize a git repository
- `git status`: display current status (e.g. modified files)
- `git add`: record changes for next commit ("staging")
- `git commit`: save staged changes as a commit (snapshot)
- `git log`: display commit history
- `git diff`: files changes since last commit
- `git show`: display file content for a precise commit
- `git checkout`: travel between commits 
- `git remote`: configure distant repository
- `git push`: send commit to another repository
- `git pull`: get new commits from another repository
- `git clone`: retrieve a local copy of a repository

---

# Additional handy commands (45 min)

- git add/commit/push cycle

- git commit [-av] with long message

- .gitignore

- git reset

- git stash

- git revert

- gitk (and other viewers)

---

# The electrophysiology of Vegetable Language (replication)

![A pumpkin](figs/pumpkin.pdf){width=40%}

Let's write a fictitious paper to replicate *Frisch and Graben, 2007*:

- fork **github.com/jennan/vegetable_language** on Github
- clone your fork of the repository to your computer

---

# Practice `git add/commit/push`

- commit as often as possible, i.e. as often as saving documents

- add **Introduction** section to the `README.md` file
```bash
nano README.md
git add README.md
git commit
```
- add **Methods** section to the `README.md` file, and push
```bash
nano README.md
git add README.md
git commit
git push
```
- redo for **Results** and **Discussion** sections

---

# Faster/better commits with `git commit -av`

- flag `-a` (or `--all`) to automatically stage changed files
- `/!\` you still need to add new files `/!\`
- flag `-v` (or `--verbose`) to see differences in commit message

- add some content to the Introduction and commit
```bash
nano README.md
git commit -av
git log
```

---

# Ignoring things using `.gitignore` file
<!-- 5 min -->

- create a junk file and a spurious folder
```bash
nano pluto.txt~
mkdir tmp
nano tmp/more_junk_file.txt
git status
```

- create a `.gitignore` file
```bash
nano .gitignore
git add .gitignore
git commit -m "Ignore junk files"
git status
```

---

# Remove changes using `git reset`

---

# Temporary discard changes with `git stash`

---

# Undo changes with `git revert`

---

# Viewers: `gitk` and friends

---

# Branching (45 min)

- git checkout [-b]

- git push -u

- git branch

- git tag

- git merge

- feature branch workflow

---

# Collaborative platforms (45 min)

- fork and pull request
- tickets systems
- good practices (e.g. good commitizen)

---

# Bonus (probably skipped)

- git blame
- git rebase
- git subtree
- git filter-branch
- ...
