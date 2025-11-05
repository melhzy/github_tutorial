# GitHub Tutorial

A comprehensive guide to Git and GitHub for beginners and intermediate users.

## Table of Contents
- [Introduction](#introduction)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Getting Started with Git](#getting-started-with-git)
- [GitHub Basics](#github-basics)
- [Working with Repositories](#working-with-repositories)
- [Branching and Merging](#branching-and-merging)
- [Collaboration Workflow](#collaboration-workflow)
- [GitHub Features](#github-features)
- [Best Practices](#best-practices)
- [Common Commands Reference](#common-commands-reference)
- [Troubleshooting](#troubleshooting)
- [Additional Resources](#additional-resources)

## Introduction

### What is Git?
Git is a distributed version control system that tracks changes in your code over time. It allows multiple developers to work on the same project simultaneously without conflicts.

### What is GitHub?
GitHub is a web-based platform that hosts Git repositories. It provides collaboration features, issue tracking, pull requests, and many other tools for software development.

### Why Use Git and GitHub?
- **Version Control**: Track every change made to your code
- **Collaboration**: Work with others seamlessly
- **Backup**: Keep your code safe in the cloud
- **Open Source**: Contribute to and learn from millions of projects
- **Portfolio**: Showcase your work to potential employers

## Prerequisites

- Basic understanding of command line/terminal
- A text editor (VS Code, Sublime Text, Atom, etc.)
- Internet connection

## Installation

### Installing Git

#### Windows
1. Download Git from [git-scm.com](https://git-scm.com/download/win)
2. Run the installer with default settings
3. Verify installation: Open Command Prompt and type `git --version`

#### macOS
```bash
# Using Homebrew
brew install git

# Or download from git-scm.com
```

#### Linux (Ubuntu/Debian)
```bash
sudo apt-get update
sudo apt-get install git
```

### Verify Installation
```bash
git --version
```

### Creating a GitHub Account
1. Go to [github.com](https://github.com)
2. Click "Sign up"
3. Follow the registration process
4. Verify your email address

## Getting Started with Git

### Initial Configuration
Set up your identity (required for commits):

```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

View your configuration:
```bash
git config --list
```

### Basic Git Concepts

- **Repository (Repo)**: A project folder tracked by Git
- **Commit**: A snapshot of your project at a specific point in time
- **Branch**: An independent line of development
- **Remote**: A version of your repository hosted on the internet
- **Clone**: A local copy of a remote repository

## GitHub Basics

### Creating Your First Repository on GitHub

1. Log in to GitHub
2. Click the "+" icon in the top right corner
3. Select "New repository"
4. Fill in:
   - **Repository name**: Choose a descriptive name
   - **Description**: Optional but recommended
   - **Public/Private**: Choose visibility
   - **Initialize with README**: Check this for a starter file
5. Click "Create repository"

### Cloning a Repository

To download a repository to your local machine:

```bash
# Clone via HTTPS
git clone https://github.com/username/repository-name.git

# Clone via SSH (requires SSH key setup)
git clone git@github.com:username/repository-name.git
```

Navigate into the cloned directory:
```bash
cd repository-name
```

## Working with Repositories

### Creating a Local Repository

```bash
# Create a new directory
mkdir my-project
cd my-project

# Initialize Git
git init
```

### Adding Files

```bash
# Create a new file
echo "# My Project" > README.md

# Check status
git status

# Add file to staging area
git add README.md

# Add all files
git add .
```

### Committing Changes

```bash
# Commit with a message
git commit -m "Initial commit: Add README"

# View commit history
git log
```

### Connecting to GitHub

```bash
# Add remote repository
git remote add origin https://github.com/username/repository-name.git

# Verify remote
git remote -v

# Push to GitHub
git push -u origin main
```

## Branching and Merging

### Understanding Branches

Branches allow you to develop features isolated from the main codebase.

### Creating and Switching Branches

```bash
# Create a new branch
git branch feature-branch

# Switch to the branch
git checkout feature-branch

# Create and switch in one command
git checkout -b feature-branch

# List all branches
git branch
```

### Making Changes on a Branch

```bash
# Make changes to files
echo "New feature" > feature.txt

# Stage and commit
git add feature.txt
git commit -m "Add new feature"
```

### Merging Branches

```bash
# Switch to main branch
git checkout main

# Merge feature branch into main
git merge feature-branch

# Delete branch after merging
git branch -d feature-branch
```

### Pushing Branches to GitHub

```bash
# Push branch to remote
git push origin feature-branch
```

## Collaboration Workflow

### Forking a Repository

1. Navigate to the repository on GitHub
2. Click the "Fork" button in the top right
3. This creates a copy under your account

### Creating a Pull Request

1. Make changes in your fork or branch
2. Push changes to GitHub
3. Go to the repository on GitHub
4. Click "Pull requests" tab
5. Click "New pull request"
6. Select branches to compare
7. Click "Create pull request"
8. Add title and description
9. Submit the pull request

### Keeping Your Fork Updated

```bash
# Add original repo as upstream
git remote add upstream https://github.com/original-owner/repository.git

# Fetch changes from upstream
git fetch upstream

# Merge upstream changes
git merge upstream/main
```

## GitHub Features

### Issues
- Track bugs, enhancements, and tasks
- Assign to team members
- Label for organization
- Link to pull requests

### GitHub Actions
- Automate workflows (CI/CD)
- Run tests automatically
- Deploy applications

### GitHub Pages
- Host static websites directly from repositories
- Great for project documentation and portfolios

### Wiki
- Create comprehensive documentation
- Collaborate on documentation

### Projects
- Organize and prioritize work
- Kanban-style boards
- Track progress

## Best Practices

### Commit Messages
```bash
# Good commit messages
git commit -m "Fix: Resolve login authentication bug"
git commit -m "Feature: Add user profile page"
git commit -m "Docs: Update installation instructions"

# Bad commit messages (avoid these)
git commit -m "fixed stuff"
git commit -m "changes"
```

### Commit Message Conventions
- Use present tense: "Add feature" not "Added feature"
- Keep first line under 50 characters
- Provide details in the body if needed
- Reference issue numbers when applicable

### Branch Naming
```bash
# Good branch names
feature/user-authentication
bugfix/login-error
hotfix/security-patch
docs/update-readme

# Avoid
branch1
new-branch
test
```

### .gitignore File

Create a `.gitignore` file to exclude files from version control:

```bash
# Node.js
node_modules/
npm-debug.log

# Python
__pycache__/
*.pyc
*.pyo
venv/

# IDEs
.vscode/
.idea/
*.swp

# OS
.DS_Store
Thumbs.db

# Secrets
.env
*.key
```

### Pull Request Best Practices
- Keep changes focused and small
- Write clear descriptions
- Reference related issues
- Request reviews from team members
- Respond to feedback promptly
- Keep the PR updated with main branch

## Common Commands Reference

### Basic Commands
```bash
git init                    # Initialize a new repository
git clone [url]            # Clone a repository
git status                 # Check status of files
git add [file]             # Stage a file
git add .                  # Stage all changes
git commit -m "[message]"  # Commit staged changes
git push                   # Push commits to remote
git pull                   # Fetch and merge changes
```

### Branching Commands
```bash
git branch                 # List branches
git branch [name]          # Create a branch
git checkout [branch]      # Switch branches
git checkout -b [branch]   # Create and switch to branch
git merge [branch]         # Merge branch into current
git branch -d [branch]     # Delete a branch
```

### Remote Commands
```bash
git remote add [name] [url]  # Add a remote
git remote -v                # List remotes
git fetch [remote]           # Fetch changes
git pull [remote] [branch]   # Pull changes
git push [remote] [branch]   # Push changes
```

### Inspection Commands
```bash
git log                    # View commit history
git log --oneline          # Condensed commit history
git diff                   # Show unstaged changes
git diff --staged          # Show staged changes
git show [commit]          # Show commit details
```

### Undoing Changes
```bash
git checkout -- [file]     # Discard changes to file
git reset HEAD [file]      # Unstage a file
git reset --soft HEAD~1    # Undo last commit, keep changes
git reset --hard HEAD~1    # Undo last commit, discard changes
git revert [commit]        # Create new commit that undoes changes
```

## Troubleshooting

### Common Issues and Solutions

#### Authentication Issues
```bash
# Use personal access token instead of password
# Generate token at: Settings > Developer settings > Personal access tokens
```

#### Merge Conflicts
```bash
# When conflicts occur:
1. Open the conflicted file
2. Look for conflict markers: <<<<<<<, =======, >>>>>>>
3. Edit the file to resolve conflicts
4. Remove conflict markers
5. Stage the resolved file: git add [file]
6. Complete the merge: git commit
```

#### Accidentally Committed Large Files
```bash
# Remove file from Git history
git rm --cached [large-file]
git commit -m "Remove large file"
git push
```

#### Wrong Commit Message
```bash
# Change the last commit message
git commit --amend -m "New commit message"
git push --force  # Use with caution!
```

#### Pushed to Wrong Branch
```bash
# Create a new branch from current position
git branch [correct-branch]
# Reset current branch
git reset --hard HEAD~1
# Checkout correct branch
git checkout [correct-branch]
```

## Additional Resources

### Official Documentation
- [Git Documentation](https://git-scm.com/doc)
- [GitHub Docs](https://docs.github.com)
- [GitHub Learning Lab](https://lab.github.com)

### Interactive Tutorials
- [Learn Git Branching](https://learngitbranching.js.org)
- [GitHub Skills](https://skills.github.com)
- [Git Immersion](http://gitimmersion.com)

### Cheat Sheets
- [GitHub Git Cheat Sheet](https://education.github.com/git-cheat-sheet-education.pdf)
- [Atlassian Git Cheat Sheet](https://www.atlassian.com/git/tutorials/atlassian-git-cheatsheet)

### Books
- Pro Git (free online): https://git-scm.com/book/en/v2
- GitHub for Dummies

### Video Tutorials
- [Git & GitHub Crash Course on YouTube](https://www.youtube.com/results?search_query=git+github+tutorial)
- [GitHub Training & Guides](https://www.youtube.com/githubguides)

## Contributing

Found an error or want to improve this tutorial? Contributions are welcome!

1. Fork this repository
2. Create a feature branch (`git checkout -b improve-tutorial`)
3. Commit your changes (`git commit -m "Improve section on branching"`)
4. Push to the branch (`git push origin improve-tutorial`)
5. Create a Pull Request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Git community for excellent documentation
- GitHub for providing an amazing platform
- All contributors to this tutorial

---

**Happy Coding! 🚀**

Remember: The best way to learn Git and GitHub is by using them. Don't be afraid to experiment and make mistakes—that's how you learn!