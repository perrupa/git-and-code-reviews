// Notes to myself to help organize the presentation

# Intro

# Objects

Git Repository
	`git init`
Staging Area
	add readme
	`git add`
Commit
	`git commit`
	edit readme
	add another file
	commit

# Identifiers

Commit ID
	explain sha-1
	`git show`
	HEAD~1 syntax
HEAD
	`git checkout`
	get detached
	jump around
Tags
	`git tag`
Branches
	`git branch`

# Network Communication

Remote
	`git remote`
Origin branches
	`git fetch`
Pushing branches
	`git push <remote (defaults to origin)> <refs to update (tags, branches, etc..)`
	Updates remote refs using local refs, while sending objects necessary to complete the given refs.
Upstream branch
	`git status`
	git push's default destination

## Actions
- commit
	- amend
- fetch
- branch
	- `git branch -a | grep "feature/grunt"`
- merge
	- fast forward ( --no-ff )
	- merge commit
- rebase
- don't use pull
	- if you have to, use `git pull --rebase`

## Code Reviews
- 