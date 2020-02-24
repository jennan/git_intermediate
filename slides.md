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

- git revert

- git stash

- gitk (and other viewers)

---

# The electrophysiology of Vegetable Language (replication)

![A pumpkin](figs/pumpkin.pdf){width=40%}

Let's write a fictitious paper to replicate *Frisch and Graben, 2007*:

- fork **github.com/jennan/vegetable_language** on Github
- clone your fork of the repository to your computer

---

# Practice `git add/commit/push`

Commit as often as possible, i.e. as often as saving documents.

- add **Introduction** section to the `README.md` file
```bash
nano README.md
git add README.md
git commit -m "add intro section title"
```
- add **Methods** section to the `README.md` file, and push
```bash
nano README.md
git add README.md
git commit -m "add methods section title"
git push
```

---

# Faster/better commits with `git commit -av`


- useful optional flags for the `git commit` command

    - flag `-a` (or `--all`) to automatically stage changed files
    - `/!\` you still need to manually add new files `/!\`
    - flag `-v` (or `--verbose`) to see differences in commit message

- add **Results** section
```bash
nano README.md
git commit -av
git status
```

- add **Discussion** section
```bash
nano README.md
git commit -am "add discussion section"
git status
git log
```

---

# Ignoring things using `.gitignore` file

- create a junk file and a spurious folder
```bash
nano README.md~
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

**Note:** local vs. user's `.gitignore` files

---

# Remove changes using `git reset`

- make some changes to `README.md` and stage (no commit)
```bash
nano README.md
git add README.md
git status
```

- unstage changes using `git reset`
```bash
git reset README.md
git status
git diff
```

- remove all changes (to all file) using `git reset --hard`
```bash
git reset --hard
git status
git diff
```

**Note:** remember `git checkout` to remove changes for one file

---

# Undo changes with `git revert`

- create a new commit to undo a previous commit

- remove `README.md` and commit
```bash
rm README.md
git commit -am "remove README.md"
ls -la
```

- recover the file by undoing the last commit
```bash
git revert HEAD
ls -la
git log
```

**Note:** useful if changes already pushed

---

# Temporary discard changes with `git stash`

- make some changes to `README.md` (no commit)
```bash
nano README.md  # add a bit of context in the intro
git status
cat README.md
```

- aaarg, boss wants to see last clean version, use `git stash`!
```bash
git stash
cat README.md
```

- back to work, recover changes and commit
```bash
git stash pop
cat README.md
git commit -av
```

**Note:** `git stash list` and `git stash drop`

---

# Viewers: `gitk` and friends

- `gitk` is available everywhere

- other graphical/cli clients: gitg, kraken, sourcetree, tig...

- I personally use them to look at commits and files history.

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

Convention for commit messages:

- short first line (max ~80 characters) to describe changes
- blank line
- paragraph to give more context, details...

---

# Bonus (probably skipped)

- git blame
- git rebase
- git cherry-pick
- git subtree
- git filter-branch
- ...
