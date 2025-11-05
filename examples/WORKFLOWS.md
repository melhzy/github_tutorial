# Example Workflows

This directory contains practical examples of common Git and GitHub workflows.

## Basic Workflow Example

### Scenario: Adding a New Feature

```bash
# 1. Start from main branch
git checkout main
git pull origin main

# 2. Create feature branch
git checkout -b feature/user-login

# 3. Make changes (create/edit files)
# ... work on your feature ...

# 4. Stage and commit changes
git add .
git commit -m "Add user login functionality"

# 5. Push to GitHub
git push origin feature/user-login

# 6. Create Pull Request on GitHub
# Go to repository page and click "Compare & pull request"
```

## Collaboration Workflow

### Scenario: Working with a Team

```bash
# Developer A: Create and push feature branch
git checkout -b feature/add-api
# ... make changes ...
git add .
git commit -m "Add REST API endpoints"
git push origin feature/add-api

# Developer B: Review and test the feature
git fetch origin
git checkout feature/add-api
# ... test the feature ...
# ... provide feedback via GitHub PR comments ...

# Developer A: Address feedback
git checkout feature/add-api
# ... make changes ...
git add .
git commit -m "Address PR feedback: add error handling"
git push origin feature/add-api

# Team Lead: Merge the PR
# After approval, merge via GitHub interface or:
git checkout main
git merge feature/add-api
git push origin main
git branch -d feature/add-api
```

## Hotfix Workflow

### Scenario: Emergency Bug Fix

```bash
# 1. Create hotfix branch from main
git checkout main
git pull origin main
git checkout -b hotfix/critical-bug-fix

# 2. Fix the bug
# ... make minimal changes to fix the issue ...

# 3. Commit and push
git add .
git commit -m "Hotfix: Resolve critical authentication bug"
git push origin hotfix/critical-bug-fix

# 4. Create PR for immediate review
# Mark as high priority, request urgent review

# 5. After approval, merge to main
git checkout main
git merge hotfix/critical-bug-fix
git push origin main

# 6. Clean up
git branch -d hotfix/critical-bug-fix
git push origin --delete hotfix/critical-bug-fix
```

## Open Source Contribution Workflow

### Scenario: Contributing to a Project

```bash
# 1. Fork the repository on GitHub (click Fork button)

# 2. Clone your fork
git clone https://github.com/YOUR-USERNAME/project-name.git
cd project-name

# 3. Add upstream remote
git remote add upstream https://github.com/ORIGINAL-OWNER/project-name.git

# 4. Create a branch for your contribution
git checkout -b fix/documentation-typos

# 5. Make your changes
# ... edit files ...

# 6. Commit changes
git add .
git commit -m "Fix typos in installation documentation"

# 7. Push to your fork
git push origin fix/documentation-typos

# 8. Create Pull Request
# Go to your fork on GitHub and click "Compare & pull request"
# Fill in PR template following project guidelines

# 9. Keep your PR updated while under review
# If maintainers request changes:
# ... make changes ...
git add .
git commit -m "Address review comments"
git push origin fix/documentation-typos

# 10. Keep your fork synchronized
git fetch upstream
git checkout main
git merge upstream/main
git push origin main
```

## Handling Merge Conflicts

### Scenario: Resolving Conflicts

```bash
# 1. Attempt to merge or pull
git pull origin main
# Or: git merge feature-branch

# 2. Git reports conflicts
# CONFLICT (content): Merge conflict in file.txt

# 3. Check status to see conflicted files
git status

# 4. Open conflicted file(s) in editor
# Look for conflict markers:
<<<<<<< HEAD
Your current changes
=======
Incoming changes
>>>>>>> branch-name

# 5. Edit the file to resolve conflicts
# Remove conflict markers and keep desired changes

# 6. Stage resolved files
git add file.txt

# 7. Complete the merge
git commit -m "Resolve merge conflicts in file.txt"

# 8. Push the changes
git push origin main
```

## Multiple Commits Workflow

### Scenario: Feature with Incremental Changes

```bash
# 1. Create feature branch
git checkout -b feature/user-dashboard

# 2. First part: Create basic structure
# ... create files ...
git add .
git commit -m "Add dashboard component structure"

# 3. Second part: Add styling
# ... add CSS ...
git add styles.css
git commit -m "Add dashboard styling"

# 4. Third part: Add data fetching
# ... add API calls ...
git add api.js
git commit -m "Implement data fetching for dashboard"

# 5. Fourth part: Add tests
# ... write tests ...
git add tests/
git commit -m "Add tests for dashboard component"

# 6. Review your commits
git log --oneline

# 7. Push all commits
git push origin feature/user-dashboard

# 8. Create PR with all commits
# Each commit shows logical progression of the feature
```

## Stash Workflow

### Scenario: Switching Context Quickly

```bash
# Working on feature-A
git checkout feature-A
# ... making changes ...

# Urgent: need to fix bug on main branch
# But current changes aren't ready to commit

# 1. Stash current changes
git stash save "WIP: feature A implementation"

# 2. Switch to main and fix bug
git checkout main
# ... fix bug ...
git add .
git commit -m "Fix critical bug"
git push origin main

# 3. Return to feature branch
git checkout feature-A

# 4. Restore stashed changes
git stash pop

# 5. Continue working
# ... continue with feature A ...
```

## Rebase Workflow

### Scenario: Keep Feature Branch Updated

```bash
# 1. Working on feature branch
git checkout feature/new-api

# 2. Main branch has new commits
# Instead of merging, rebase to keep history clean

# 3. Fetch latest main
git fetch origin main

# 4. Rebase feature branch onto main
git rebase origin/main

# 5. If conflicts occur, resolve them
# ... resolve conflicts in files ...
git add .
git rebase --continue

# 6. Force push (since history was rewritten)
git push --force-with-lease origin feature/new-api

# Note: Only force push to branches you own
```

## Tag and Release Workflow

### Scenario: Creating a Release

```bash
# 1. Ensure main is up to date
git checkout main
git pull origin main

# 2. Create annotated tag
git tag -a v1.0.0 -m "Release version 1.0.0: Initial stable release"

# 3. Push tag to GitHub
git push origin v1.0.0

# 4. Create release on GitHub
# Go to repository > Releases > Draft a new release
# Select the tag, add release notes, attach binaries if needed

# For subsequent releases:
git tag -a v1.1.0 -m "Release version 1.1.0: Add user authentication"
git push origin v1.1.0
```

## Cherry-Pick Workflow

### Scenario: Apply Specific Commit to Another Branch

```bash
# 1. You made a commit on feature-A that's also needed on feature-B
git checkout feature-A
git log --oneline
# Note the commit hash of the commit you want: abc1234

# 2. Switch to feature-B
git checkout feature-B

# 3. Cherry-pick the commit
git cherry-pick abc1234

# 4. Push to remote
git push origin feature-B

# Now that commit exists on both branches
```

## Recovery Workflow

### Scenario: Recovering Deleted Branch

```bash
# 1. Accidentally deleted branch
git branch -D important-feature

# 2. Find the commit hash
git reflog
# Look for: checkout: moving from important-feature to main
# Note the commit hash

# 3. Recreate branch
git checkout -b important-feature <commit-hash>

# 4. Verify content
git log --oneline

# Branch recovered!
```

---

These workflows cover most common scenarios you'll encounter. Practice them to build confidence!
