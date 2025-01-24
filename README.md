## Omkar Prashant Karmarkar
## GitHub Repo:

### Familiarize with GIT  Important Commands

# Git Commands Cheat Sheet

## Basics

```bash

git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
###
# Check Configuration
# View the current Git configuration for your system.
git config --list
###
# Initialize Repository
# Create a new local Git repository in the current directory.
git init
###
# Clone Repository
# Copy an existing remote repository to your local system.
git clone <repository-url>
###
# Check Status
# Check the status of your working directory and see changes that haven't been staged or committed.
git status
###
# Add Files to Staging Area
# Stage specific or all files to prepare them for committing.
git add <file>   # Add a specific file
git add .        # Add all files in the current directory
###
# Commit Changes
# Save the staged changes to the repository with a commit message.
git commit -m "Commit message"
###
# View Commit History
# Display the history of commits in the current branch.
git log
###


# List Branches

# Show all branches in the repository.
# Create New Branch
# Create a new branch without switching to it.
```bash
git branch <branch-name>
```bash

# Switch to a Branch
# Move to an existing branch.
```bash
git checkout <branch-name>  # Older method
git switch <branch-name>    # Newer method
```bash

# Create and Switch to a New Branch
# Create a new branch and switch to it immediately.
```bash
git checkout -b <branch-name>  # Older method
git switch -c <branch-name>    # Newer method
```bash

# Delete Branch
# Delete a branch locally (safe deletion; will fail if unmerged changes exist).
```bash
git branch -d <branch-name>
```bash
# Force Delete Branch
# Delete a branch regardless of unmerged changes.
```bash
git branch -D <branch-name>
```bash

### Merging:
```bash 
git merge <branch_name>
## Combine the Spefied branch into the current branch
```

# Stash Changes
```bash
# Save your uncommitted changes temporarily without committing them.
git stash

# List Stashes
# View a list of all saved stashes.
git stash list

# Apply a Stash
# Apply the most recent or a specific stash without removing it.
git stash apply
###
# Apply and Drop a Stash
# Apply the most recent or a specific stash and remove it.
git stash pop
# Drop a Stash
# Delete a specific stash without applying it.
git stash drop
###
```
# Reset and Revert
```bash
## Unstage a File
# Remove a file from the staging area without deleting changes.
git reset <file>
###
# Soft Reset to a Commit
# Move HEAD to a specific commit but keep staged changes.
git reset --soft <commit-hash>
###
# Hard Reset to a Commit
# Move HEAD to a specific commit and discard all changes after it.
git reset --hard <commit-hash>
###
# Revert a Commit
# Create a new commit to undo changes from a specific commit.
git revert <commit-hash>
###

```


## Exercise:
# The Odin Project Git Basics:
##  SSH Setup
- Before Starting the task we need to configure the SSH 
	- ## Configure SSH:
		- ## Generate SSH key pair
			```bash
			ssh -keygen -t ed25519 -C "[info]"
			```
			- ## Add the Key to GitHub:
				-  After generating the key pair, add the public key to the service you want to connect over the SSH 
				- **SSH and GPG keys** section and select the **New SSH** **key** button use this section in GitHub to add the keys.
				-  To Test Connectivity use 
					 ```bash
					 ssh -T git@github.com
					```
				- Now add the Private key to the SSH Agent:
				```bash
				eval "$(shh-agent-s)"
				## add ssh key to agent
				ssh -add [path-to-private-key]
				
				
```
				- Once done we can use the SSH URL of the Repo from GitHub and  Clone it Locally.
				![[Pasted image 20250124214000.png]]
## Git Repository: 

- ## Check the Version of Git Running:
	```bash
	git --version
	```

- ## Identity:  

	-It is Good to add the username and email id  ,because every git commit uses this information.
	Also set the local default  branch to mail.
	```bash
	git config --global user.name "Omkar"
	git config --global user.email "omkar1709k@gmail.com"
	git config --global init.defaultBranch main
```

	
	- ## Creating git repo and using it
		- We  have created a Repository in GitHub using homepage name of repo is  git_test
		-  Clone the URL using SSH.
		``` bash
		git clone git@github.com:Omkar1709k/git_basics.git
		```
		- ## GIT Workflow
			- We will create a new file hello_word.txt using command 
				```bash
				touch hello_world.txt
				```
			 -To view the status and changes use:
				```bash
				git status
				```
				
				- Now add the files to the staging area
					```bash
					git add hello_world.txt
					```
					- Now we commit the changes and typing git status should show "nothing to commit"
				```bash
				git commit -m "Add hello_world.txt"
				git status
                                ```
			- Type  ```git log ``` to get the  details of the author who made the commit and date and time when commit was made.
	- ## Push your work to GitHub
		```bash
		git push 
		## or more specific 
		git push origin main
		```

