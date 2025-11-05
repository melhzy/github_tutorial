# Git and GitHub Glossary

A comprehensive list of terms and concepts you'll encounter when using Git and GitHub.

## A

**Add**: Stage changes for the next commit using `git add`.

## B

**Branch**: An independent line of development. The default branch is usually called `main` or `master`.

**Branch Protection**: GitHub feature that enforces rules on branches (e.g., requiring reviews before merging).

## C

**Cherry-pick**: Apply a specific commit from one branch to another using `git cherry-pick`.

**Clone**: Create a local copy of a remote repository using `git clone`.

**Commit**: A snapshot of your repository at a specific point in time. Created with `git commit`.

**Commit Hash (SHA)**: A unique identifier for each commit (e.g., `a1b2c3d4`).

**Commit Message**: Description of changes made in a commit.

**Conflict**: Occurs when Git cannot automatically merge changes from different branches.

**Contributors**: People who have contributed code or other changes to a repository.

## D

**Detached HEAD**: State where HEAD points to a specific commit rather than a branch.

**Diff**: Shows differences between commits, branches, or working directory using `git diff`.

**Distributed Version Control**: System where every user has a complete copy of the repository.

## F

**Fetch**: Download changes from remote repository without merging them using `git fetch`.

**Fork**: Create a personal copy of someone else's repository on GitHub.

## G

**Git**: Distributed version control system created by Linus Torvalds.

**GitHub**: Web-based hosting service for Git repositories with collaboration features.

**GitHub Actions**: CI/CD platform integrated with GitHub for automation.

**GitHub Pages**: Service to host static websites directly from GitHub repositories.

**.gitignore**: File specifying which files Git should ignore.

## H

**HEAD**: Reference to the current commit or branch you're on.

**HEAD~1**: Reference to the parent of HEAD (one commit before current).

**Hotfix**: Quick fix for a critical bug, usually branched from and merged back to production.

## I

**Init**: Initialize a new Git repository using `git init`.

**Issue**: GitHub's way of tracking bugs, enhancements, tasks, and questions.

## L

**Local Repository**: Git repository on your computer.

**Log**: View commit history using `git log`.

## M

**Main/Master**: Default branch name in a repository.

**Merge**: Combine changes from different branches using `git merge`.

**Merge Conflict**: Situation where Git cannot automatically merge changes.

**Merge Commit**: Commit that combines changes from two or more branches.

**Milestone**: GitHub feature to group related issues and pull requests.

## O

**Origin**: Default name for the primary remote repository.

**Orphan Branch**: Branch with no parent commits.

## P

**Pull**: Fetch and merge changes from remote repository using `git pull`.

**Pull Request (PR)**: GitHub feature to propose changes and request code review before merging.

**Push**: Upload local commits to remote repository using `git push`.

## R

**Rebase**: Reapply commits on top of another branch using `git rebase`.

**Ref**: Reference to a commit (branch, tag, or HEAD).

**Reflog**: Log of where HEAD and branches have pointed in the past.

**Remote**: Version of repository hosted on the internet or network.

**Repository (Repo)**: Project folder tracked by Git, containing all files and history.

**Reset**: Move HEAD to a different commit, optionally changing working directory.

**Revert**: Create a new commit that undoes changes from a previous commit.

**Review**: Process of examining code changes before merging.

## S

**SHA**: Secure Hash Algorithm - used to generate unique commit identifiers.

**Stage/Staging Area**: Place where changes are prepared before committing.

**Stash**: Temporarily save changes without committing using `git stash`.

**Status**: Check state of working directory and staging area using `git status`.

**Submodule**: Repository embedded within another repository.

## T

**Tag**: Named reference to a specific commit, often used for releases.

**Tracking Branch**: Local branch that has a direct relationship to a remote branch.

**Tree**: Git's internal representation of a directory.

## U

**Untracked Files**: Files in working directory not yet added to Git.

**Upstream**: Original repository that your fork is based on.

**Upstream Branch**: Remote branch that local branch tracks.

## W

**Working Directory/Tree**: Files you're currently working on (not staged or committed).

**Workflow**: Agreed-upon process for using Git and GitHub in a team.

## Common Command Patterns

### Commit Reference Shortcuts

- `HEAD`: Current commit
- `HEAD~1` or `HEAD~`: Previous commit
- `HEAD~2`: Two commits ago
- `HEAD^`: Parent of HEAD (same as HEAD~1)
- `HEAD^^`: Grandparent of HEAD
- `<branch>@{yesterday}`: Where branch was yesterday
- `<commit-hash>`: Specific commit by its SHA

### Git States

1. **Untracked**: File not yet added to Git
2. **Unmodified**: File tracked but unchanged since last commit
3. **Modified**: File changed but not staged
4. **Staged**: File ready to be committed
5. **Committed**: File changes saved to repository

### Repository Types

- **Bare Repository**: Repository without working directory (used on servers)
- **Non-bare Repository**: Normal repository with working directory

## GitHub-Specific Terms

**Actions**: Automated workflows for CI/CD and other tasks.

**Blame View**: Shows who last modified each line of a file.

**Code Owners**: People automatically requested for review on specific files.

**Deploy Keys**: SSH keys for read-only or read-write access to a single repository.

**Gist**: Quick way to share code snippets or files.

**Organization**: Shared account for multiple users to collaborate on projects.

**Projects**: Kanban-style boards for organizing work.

**Releases**: Packaged versions of software with release notes.

**Repository Insights**: Analytics about contributors, commits, and activity.

**Security Advisory**: Report of security vulnerability in a repository.

**Sponsors**: GitHub program for financial support of developers.

**Teams**: Groups of organization members with specific permissions.

**Watch**: Subscribe to notifications for a repository.

**Wiki**: Documentation space for projects.

## Symbols and Shortcuts

- `.`: Current directory
- `..`: Parent directory
- `~`: Home directory
- `*`: Wildcard (matches multiple files)
- `HEAD`: Current commit
- `origin`: Default remote name
- `upstream`: Common name for original repository in forks

## File States in Git Status

- **Untracked**: `??` - New file not tracked by Git
- **Modified**: `M` - Changed file
- **Added**: `A` - Newly staged file
- **Deleted**: `D` - Deleted file
- **Renamed**: `R` - Renamed file
- **Copied**: `C` - Copied file
- **Unmerged**: `U` - File with merge conflicts

## Merge Strategies

- **Fast-forward**: Simply move branch pointer forward (no merge commit)
- **Recursive**: Default merge strategy for two branches
- **Ours**: Keep our changes in conflict
- **Theirs**: Keep their changes in conflict
- **Squash**: Combine all commits into one

## Common Acronyms

- **CI/CD**: Continuous Integration/Continuous Deployment
- **CLI**: Command Line Interface
- **DVCS**: Distributed Version Control System
- **GUI**: Graphical User Interface
- **PR**: Pull Request
- **SHA**: Secure Hash Algorithm
- **SSH**: Secure Shell
- **UI**: User Interface
- **VCS**: Version Control System
- **WIP**: Work In Progress

---

**Pro Tip**: Don't try to memorize all terms at once. Learn them as you encounter them in practice!
