## Git "Nouns"

- Repository
- Staging Area
- Commit
- HEAD
- Tag
- Branch
- Remote

---

# Git Repository

### A Git repository is tree of commit objects 

- Represented as Directed Acyclical Graph
- Stored as a  `.git` directory in your project's working directory

---

# Staging Area

### The staging area is a commit that exists in the working directory, but has not been added to the tree yet.

---

# Commit

### A Commit is a "snapshot" of your project at a point in time

---

# Commit

A commit contains the following:


- Author

- Commit date

- Tree (**Entire** state of the repo at that point in time)
 
- "Delta" between it and its parent

- Parent commit

- Commit ID (SHA-1 of the entire *commit's* contents)

---

# Committing

```bash
$ echo "this is my app" > README.txt

$ git add README.txt

$ git commit -m "Added a README to the repo"

```

---

# HEAD

### Where's your head at?

```bash
$ cat .git/HEAD
```

---

# Tags

### Lightweight pointers to commits

```bash
$ git tag my-tag-name
```

---

# Branches

### Movable, Lightweight pointers to commits

```bash
$ git branch my-branch-name
```

---

# Remote

### A reference to an external repository

