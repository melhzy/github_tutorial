# Git & GitHub Quick Reference

A cheat sheet for the most commonly used Git and GitHub commands.

## Setup

```bash
# Configure user information
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"

# Check configuration
git config --list

# Get help for a command
git help <command>
```

## Repository Management

```bash
# Initialize a new repository
git init

# Clone an existing repository
git clone <url>

# Add remote repository
git remote add origin <url>

# View remotes
git remote -v

# Remove remote
git remote remove <name>
```

## Basic Workflow

```bash
# Check status
git status

# Add files to staging
git add <file>              # Specific file
git add .                   # All files in current directory
git add -A                  # All files in repository

# Commit changes
git commit -m "message"     # With message
git commit -am "message"    # Add and commit tracked files

# Push to remote
git push origin <branch>

# Pull from remote
git pull origin <branch>

# Fetch without merging
git fetch origin
```

## Branching

```bash
# List branches
git branch                  # Local branches
git branch -a              # All branches
git branch -r              # Remote branches

# Create branch
git branch <branch-name>

# Switch branch
git checkout <branch-name>

# Create and switch
git checkout -b <branch-name>

# Delete branch
git branch -d <branch-name>    # Safe delete
git branch -D <branch-name>    # Force delete

# Rename branch
git branch -m <old-name> <new-name>

# Merge branch
git merge <branch-name>
```

## Viewing History

```bash
# View commit history
git log
git log --oneline          # Compact view
git log --graph           # Graph view
git log --all --graph     # All branches graph

# View changes
git diff                   # Unstaged changes
git diff --staged         # Staged changes
git diff <branch1> <branch2>  # Between branches

# Show commit details
git show <commit-hash>
```

## Undoing Changes

```bash
# Discard changes in working directory
git checkout -- <file>
git restore <file>         # Git 2.23+

# Unstage files
git reset HEAD <file>
git restore --staged <file>  # Git 2.23+

# Undo last commit (keep changes)
git reset --soft HEAD~1

# Undo last commit (discard changes)
git reset --hard HEAD~1

# Revert a commit (creates new commit)
git revert <commit-hash>

# Amend last commit
git commit --amend
```

## Stashing

```bash
# Save changes temporarily
git stash
git stash save "message"

# List stashes
git stash list

# Apply stash
git stash apply            # Keep stash
git stash pop             # Apply and remove

# Delete stash
git stash drop
git stash clear           # All stashes
```

## Tags

```bash
# List tags
git tag

# Create tag
git tag <tag-name>
git tag -a <tag-name> -m "message"  # Annotated tag

# Push tags
git push origin <tag-name>
git push origin --tags    # All tags

# Delete tag
git tag -d <tag-name>     # Local
git push origin :refs/tags/<tag-name>  # Remote
```

## GitHub Specific

### Pull Requests via CLI (GitHub CLI required)

```bash
# Install GitHub CLI: https://cli.github.com/

# Create PR
gh pr create

# List PRs
gh pr list

# View PR
gh pr view <number>

# Checkout PR
gh pr checkout <number>

# Merge PR
gh pr merge <number>
```

### Working with Forks

```bash
# Add upstream remote
git remote add upstream <original-repo-url>

# Fetch upstream changes
git fetch upstream

# Merge upstream into local branch
git checkout main
git merge upstream/main

# Push to your fork
git push origin main
```

## Advanced Commands

```bash
# Cherry-pick a commit
git cherry-pick <commit-hash>

# Rebase
git rebase <branch>
git rebase -i HEAD~3      # Interactive rebase last 3 commits

# Clean untracked files
git clean -n              # Dry run
git clean -f              # Remove files
git clean -fd             # Remove files and directories

# Find who changed a line
git blame <file>

# Search in history
git log -S "search term"
git log --grep="pattern"
```

## Merge Conflict Resolution

```bash
# When merge conflict occurs:

# 1. Check which files have conflicts
git status

# 2. Open conflicted files and look for markers:
#    <<<<<<< HEAD
#    Your changes
#    =======
#    Their changes
#    >>>>>>> branch-name

# 3. Edit file to resolve conflicts

# 4. Mark as resolved
git add <file>

# 5. Complete merge
git commit
```

## Common Scenarios

### Starting a New Project

```bash
mkdir my-project
cd my-project
git init
echo "# My Project" > README.md
git add README.md
git commit -m "Initial commit"
git remote add origin <github-url>
git push -u origin main
```

### Contributing to Open Source

```bash
# 1. Fork repository on GitHub
# 2. Clone your fork
git clone <your-fork-url>
cd repository

# 3. Add upstream
git remote add upstream <original-repo-url>

# 4. Create branch
git checkout -b feature-branch

# 5. Make changes and commit
git add .
git commit -m "Add feature"

# 6. Push to your fork
git push origin feature-branch

# 7. Create Pull Request on GitHub
```

### Syncing Fork with Original

```bash
git fetch upstream
git checkout main
git merge upstream/main
git push origin main
```

### Fixing a Mistake

```bash
# Wrong commit message
git commit --amend -m "Correct message"

# Forgot to add a file
git add forgotten-file
git commit --amend --no-edit

# Committed to wrong branch
git checkout correct-branch
git cherry-pick <commit-hash>
git checkout wrong-branch
git reset --hard HEAD~1
```

## Git Aliases (Optional)

Add to `~/.gitconfig`:

```ini
[alias]
    st = status
    co = checkout
    br = branch
    ci = commit
    unstage = reset HEAD --
    last = log -1 HEAD
    visual = log --graph --oneline --all
    amend = commit --amend --no-edit
```

## Resources

- [Official Git Documentation](https://git-scm.com/doc)
- [GitHub Docs](https://docs.github.com)
- [Interactive Git Cheatsheet](https://ndpsoftware.com/git-cheatsheet.html)

---

**Tip**: Practice these commands regularly to build muscle memory!
