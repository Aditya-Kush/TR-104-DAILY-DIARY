# Date = 20 May 2025  
# INTRODUCTION TO GIT AND GITHUB

Today, I learned the basics of **Git** and **GitHub**, essential tools for version control and collaborative software development. Understanding Git and GitHub helps in managing code changes, collaborating with others, and maintaining project history efficiently.

---

## What is Git?

- Git is a **distributed version control system** that tracks changes in source code during software development.
- It allows multiple developers to work on the same project simultaneously without overwriting each other’s work.
- Git stores snapshots of your project files in a repository, enabling easy rollback, branching, and merging.

---

## What is GitHub?

- GitHub is a **web-based hosting service** for Git repositories.
- It provides a graphical interface and additional collaboration features like pull requests, issue tracking, and code reviews.
- GitHub makes it easy to share your code with others and contribute to open source projects.

---

## Basic Git Concepts

| Concept      | Description                                          |
|--------------|------------------------------------------------------|
| Repository (Repo) | A folder or storage space where your project lives, containing all files and version history. |
| Commit       | A snapshot of your files at a point in time with a message describing the changes. |
| Branch       | A parallel version of your repository to work independently on features or fixes. |
| Merge        | Combining changes from one branch into another (e.g., feature branch into main). |
| Clone        | A copy of a remote repository on your local machine. |
| Push         | Upload local commits to a remote repository. |
| Pull         | Download and integrate changes from a remote repository to your local repo. |

---

## Common Git Commands

```bash
# Configure Git username and email (once)
git config --global user.name "Your Name"
git config --global user.email "you@example.com"

# Initialize a new Git repository
git init

# Check the status of files
git status

# Stage files for commit
git add filename.txt
git add .  # add all changed files

# Commit staged files with a message
git commit -m "Add initial project files"

# Clone a remote repository
git clone https://github.com/username/repository.git

# Push changes to remote repository
git push origin main

# Pull latest changes from remote
git pull origin main

# Create a new branch
git branch new-feature

# Switch to a branch
git checkout new-feature

# Merge a branch into current branch
git merge new-feature
