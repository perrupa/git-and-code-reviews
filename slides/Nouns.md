## Git "Nouns"

- Concepts / Objects
	- Working Tree
	- Repositories
	- Staging Area / Index
	- Commits
- Refs 
	- HEAD
	- Tags
	- Branches
	- Remotes

---

# Working Tree

The __Working Tree__ refers to the current state of the files and subfolders in your project 

---

# Git Repository

- A _Directed, Acyclical Graph_ (DAG) of commit objects
- Stored as a  `.git` directory in your project's working directory

```
# Created by
git init
```

---

# "Staging Area"
<br>

###The Index is your next proposed commit. 
<br>
You can compose your next commit by adding blob and tree objects to the index.

---

# Commit
<br>
A "snapshot" of your project at a point in time, along with the info on how we got there.


---

# Commit

A commit contains the following:

- Author

- Commit date

- Tree Object

	- A list of blob and tree objects 

- Parent commit

- Commit ID (SHA-1 of the entire commit's contents)

---

# Committing

<br>

```bash
# Change the working tree
$ touch README.txt
$ echo "this is my app" > README.txt

# Stage the changes to the index (Staging Area)
$ git add README.txt

# Craft the index into a commit
$ git commit -m "Added a README to the repo"

```
