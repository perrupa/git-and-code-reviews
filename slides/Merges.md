# Joining Branches

---

### Let's talk about merging

```bash
# Update my remotes
$ git fetch

# Where are we at?
$ git status
On branch develop
Your branch is behind 'origin/develop' by 2 commits, and can be fast-forwarded.
  (use "git pull" to update your local branch)
nothing to commit, working directory clean

# merge the remote changes from origin/develop to my local develop branch
$ git merge origin/develop
git merge origin/develop
Updating c218be4..e7f59b8
Fast-forward
 src/system/application/controllers/admin/reports/basic_p2p_given.php | 6 +++---
 1 file changed, 3 insertions(+), 3 deletions(-)
```

---

## Fast Forward Merge

Your branch is sometimes behind your merge candidate. Meaning it is an ancestor of the candidate. 

<br>

Then you can simply fast-forward your branch to the candidate's commit.

---

## Merge Commits

When your branches have diverged, a merge commit becomes necesarry.

![alt text](./images/merge-commit.png)

---

# Merge Commits
## Good or bad?

---

## Is it relevant?

Where you actually merging two branches?

Or where you just trying to keep up to date with an origin branch?

---

# Yeah....
```
| | | | | | | | | | | | | * | |   7525c7f - (3 hours ago) Merge remote-tracking branch 'origin/feature/standardized_approvals' into feature/standardized_approvals_PRODEV-1213 - (Someone Anonymous)
| | | | | | | | | | | | | |\ \ \
| | | | | | | | | | | | | | * \ \   f582837 - (3 hours ago) Merge branch 'feature/standardized_approvals' of ssh://tor-repo01/mnt/opt/git/platform-a into feature/standardized_approvals - (Someone Anonymous)
| | | | | | | | | | | | | | |\ \ \
| | | | | | | | | | | | | | * | | | af185c6 - (3 hours ago) NO-JIRA Fixing a helper class and its function definition. - (Someone Anonymous)
| | | | | | | | | | | | | * | | | |   f91ad63 - (3 hours ago) Merge branch 'feature/standardized_approvals_PRODEV-1213' of ssh://tor-repo01/mnt/opt/git/platform-a into feature/standardized_approvals_PRODEV-1213 - (Someone Anonymous)
| | | | | | | | | | | | | |\ \ \ \ \
| | | | | | | | | | | | | * | | | | | e123c2d - (3 hours ago) NO-JIRA Getting only the first filter till we implement filter strategy. - (Someone Anonymous)
| | | | | | | | | | | | | * | | | | | 0eec300 - (34 hours ago) NO-JIRA Throwing some error messages when mandatory fields are not provided. - (Someone Anonymous)
| | | | | | | | | | | | | | | | | | | * 86bb88c - (2 hours ago) NO-JIRA: Fix Modal closing issue - Joel Langlois (origin/feature/marketplace/rule_builder)
| | | | | | | | | | | | | | | | | | | *   09673c9 - (3 hours ago) Merge branch 'develop' into feature/marketplace/rule_builder - Joel Langlois
```

---

## Who's been here before?

```
$ git commit -m "Awesome Commit"
# Finished!
$ git status
	On branch develop
	Your branch is ahead of 'origin/develop' by 1 commit.
	  (use "git push" to publish your local commits)
	nothing to commit, working directory clean
	# Awesome! I'll just fetch and push!
$ git fetch
	# waiting for any updates...
$ git status
	On branch develop
	Your branch and 'origin/develop' have diverged,
	and have 1 and 2 different commits each, respectively.
	  (use "git pull" to merge the remote branch into yours)
	nothing to commit, working directory clean
# uh oh, this is going to get messy...
```

---

## We have a few options:

- Merge the branch into ours 
- "rebase" our local commit(s)

---

# Merge 
- create a merge commit ("merge origin/master into master")
- push our commit along with a merge commit

```
$ git lg | cat

*   fb10b1f - Merge branch 'master' into new-branch (3 months ago) <Chris Marlow>
|\
| * d688c6c - Added a readme (3 months ago) <Chris Marlow>
* | 79fc050 - added a Gruntfile. (3 months ago) <Chris Marlow>
|/
* ef2c0d0 - Made a small change to app.js (3 months ago) <Chris Marlow>
* 490bcd0 - Added my js app file (3 months ago) <Chris Marlow>
* 05e5406 - Added package.json (3 months ago) <Chris Marlow>%
```

---

# Rebase
- rebase our branch on the merge candidate
- push our newly created commit (no merge commit)

```
* d688c6c - Added a readme (3 months ago) <Chris Marlow>
* c6dc5aa - added a Gruntfile. (3 months ago) <Chris Marlow>
* ef2c0d0 - Made a small change to app.js (3 months ago) <Chris Marlow>
* 490bcd0 - Added my js app file (3 months ago) <Chris Marlow>
* 05e5406 - Added package.json (3 months ago) <Chris Marlow>%
```

---

# How to rebase

###It's not too scary

---

## Let's Diverge and try

```
# create a new branch
(master) $ git branch new-branch
(master) $ git commit --allow-emtpy -m "commit on master"
(master) $ git checkout new-branch
(master) $ git commit --allow-emtpy -m "commit on new-branch"
```

---

# Resolving Conflicts

Conflict resolution when rebasing can be scary and or confusing. But once you get used to it, it is pretty painless (as far as conflicts go).