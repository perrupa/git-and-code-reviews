# Verbs
- Communication
- Joining branches

---

# Communication

---

## The D in DVCS means distributed.
- There need not be a central repository in your Git workflow.
- Think Bittorrent vs FTP


---

##  Keeping up to date
- `git fetch` command to update all your remote references.
- You are asking each remote:
	- What branches do you have?
	- What commit is it pointing to?

---

## Keeping up to date

```
# Fetchin' ma refs
$ git fetch

remote: Counting objects: 504, done.
remote: Compressing objects: 100% (148/148), done.
remote: Total 149 (delta 111), reused 0 (delta 0)
Receiving objects: 100% (149/149), 29.75 KiB | 0 bytes/s, done.
Resolving deltas: 100% (111/111), completed with 70 local objects.
From ssh://tor-repo01.corp.achievers.com/mnt/opt/git/platform-a
   5d6fac7..e7f59b8  develop    -> origin/develop
 * [new branch]      feature/PFAPROD-14237 -> origin/feature/PFAPROD-14237
 * [new branch]      feature/yos/confirm-address -> origin/feature/yos/confirm-address
```

---

## `origin/branch-name`

The branches on external repositories are represented on your local repository in the format:

```
remotes/<remote-name>/<branch-name>

# eg:
remotes/origin/develop
remotes/github/feature/update-ui

# Double checkin' ma refs
$ git branches 
...
remotes/origin/feature/PFAPROD-14237
remotes/origin/feature/PFAPROD-2431
...
```

---

## Tracking branches

These `refs` will track the branches on the remote repos every time you run `git fetch`

```
$ git status

On branch develop
Your branch is up-to-date with 'origin/develop'.
nothing to commit, working directory clean

$ git fetch
# ...

$ git status

On branch develop
Your branch is behind 'origin/develop' by 130 commits, and can be fast-forwarded.
  (use "git pull" to update your local branch)
nothing to commit, working directory clean
```

---

# Pro-tip

```
$ git branches | grep tfa
team/tfa/develop-temp
remotes/origin/team/tfa/develop-marketplace
remotes/origin/team/tfa/develop-temp
remotes/origin/team/tfa/develop-yos
```

---

## Sending someone something

To send a branch, tag or something similar you need to "Push" your changes to that particular remote.

<br>

```bash
# Push all my tags to our origin repository 
$ git push origin --tags 

# Push my current branch to the build-script-branch on Haitham's laptop
$ git push haithams-computer build-script-branch

# Push build-script-branch to GitHub
$ git push github build-script-branch
```

