git_quickstart
==============

A quick intro to git commands (work-in-progress)

**Basic commit workflow:**

```
git status
git add .
git commit -m "Commit Message."
git push
```

**Making a change to a remote repo:**

"Fork" the repo so that you get: 

> https://host.com/[MY_USERNAME]/[REPO_NAME]

Then:

> git clone  https://host.com/[MY_USERNAME]/[REPO_NAME].git

**Branching:**

Create:

> git checkout -b branch_name

Switch:

> git checkout branch_1

Delete:

> git checkout -d branch_name

**Fetching remote branch:**

If you are trying to "checkout" a new remote branch (that exists only on the remote,
but not locally), here's what you'll need:

```
git fetch origin
git checkout --track origin/<remote_branch_name>
```

**Remote_master/Remote_fork/Local syncing:**

```
git remote add upstream https://host.com/[ORIGINAL_REPO]/[REPO_NAME].git
git fetch upstream (1)
git merge upstream/master (2)
```

Or (1 + 2):

> git pull upstream/master

**Merging:**

```
git checkout branch_name
git merge branch_1
```

Branch_1 merges with branch_name.

**Undo:**

```
git reflog
# you will see a list of every thing you've done in git, across all branches!
# each one has an index HEAD@{index}
# find the one before you broke everything
git reset HEAD@{index}
# magic time machine
```

**Small Edit after commit:**

```
# make your change
git add . # or add individual files
git commit --amend
# follow prompts to change or keep the commit message
# now your last commit contains that change!
```

**Change last commit message:**

```
git commit --amend
# follow prompts to change the commit message
```

**Committed to master but should have been on new branch**

```
# create a new branch from the current state of master
git branch some-new-branch-name
# remove the commit from the master branch
git reset HEAD~ --hard
git checkout some-new-branch-name
# your commit lives in this branch now :)
```

**Committed to wrong branch:**

```
# undo the last commit, but leave the changes available
git reset HEAD~ --soft
git stash
# move to the correct branch
git checkout name-of-the-correct-branch
git stash pop
git add . # or add individual files
git commit -m "your message here"
# now your changes are on the correct branch
```

or

```
git checkout name-of-the-correct-branch
# grab the last commit to master
git cherry-pick master
# delete it from master
git checkout master
git reset HEAD~ --hard
```

**Diff of staged files:**

> git diff --staged

