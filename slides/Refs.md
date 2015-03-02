# References 

- Commit IDs
- Head
- Tags
- Branches

---

# What is a `ref`?

A `ref` is simply a pointer to a commit. 

---

# Commit IDs

A SHA-1 hash of the commit's comments. You can use a shortened version of the full hash 

eg: `47083fed3f66dcce6f022adb75288eee20a928ed` could be referred to by simply `47083fed`
```
$ git show 47083fed3f66dcce6f022adb75288eee20a928ed
47083fed3f66dcce6f022adb75288eee20a928ed Fixed bug #512...

$ git show 47083fed
47083fed3f66dcce6f022adb75288eee20a928ed Fixed bug #512...
```

---

## Where's your `head` at?

The `HEAD` is your currently checked `ref`.

```
$ git checkout master
Switched to branch 'master'
```


---

# Detached Head?

If your `HEAD` is not pointing to a branch, it is in a "Detached State"

If you create additional commits and then checkout another branch, they may be lost.

---

## Tags
<br>
#### Lightweight pointer to a commit

```bash
$ git tag my-tag-name
```

---

## "Don't try and change me"
<br>
Tags cannot be moved. They can only be created or deleted.

---


# Branches
<br>
Movable, Lightweight pointers to commits
<br>
```bash
$ git branch my-branch-name
```

---

## Branches sway in my `HEAD`
<br>
When a new commit is created, `HEAD` will advance the checked out `branch` to point to the newly created commit.

---

#### Quick demo

---

# Remotes

Remote repositories can be referred to by URL or by a `remote` reference

```
git remote add github https://github.com/user/repo.git
git remote add achievers https://brm.repo12-01.achievers.com/pfa.git
```

---

```
$ git remote -v
github	https://10.100.40.253/chrism/develop.git (fetch)
github	https://10.100.40.253/chrism/develop.git (push)
origin	ssh://tor-repo01.corp.achievers.com/mnt/opt/git/platform-a (fetch)
origin	ssh://tor-repo01.corp.achievers.com/mnt/opt/git/platform-a (push)
```
