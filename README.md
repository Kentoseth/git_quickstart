git_quickstart
==============

A quick intro to git commands (work-in-progress)

**Basic commit workflow:**

> git status
> git add .
> git commit -m "Commit Message."
> git push

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

**Remote_master/Remote_fork/Local syncing:**

> git remote add upstream https://host.com/[ORIGINAL_REPO]/[REPO_NAME].git
> git fetch upstream (1)
> git merge upstream/master (2)

Or (1 +2):

> git pull upstream/master

**Merging:**

> git checkout branch_name
> git merge branch_1

Branch_1 merges with branch_name.

