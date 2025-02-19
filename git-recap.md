# GitHub/Git Command Cheat Sheet

## 1. Configuration & Setup

git config --global user.name "Your Name"          # Set global username 

git config --global user.email "your@email.com"    # Set global email

git config --global --edit                         # Edit global config file

git config --list                                  # List current configurations

git config credential.helper cache                 # Cache credentials (15min default)

## 2. Basic Workflow

git init                                           # Initialize new repository

git clone <repo-url>                               # Clone a repository

git status                                         # Show working tree status

git add <file>                                     # Add specific file

git add .                                          # Add all changes

git commit -m "message"                            # Commit with message

git commit --amend                                 # Modify last commit

git rm <file>                                      # Remove file from tracking

git mv <old> <new>                                 # Rename/move file

## 3. Branch Management

git branch                                         # List local branches

git branch -a                                      # List all branches (local + remote)

git branch <name>                                  # Create new branch

git checkout <branch>                              # Switch branches

git checkout -b <new-branch>                       # Create and switch to new branch

git switch <branch>                                # Newer way to switch branches

git merge <branch>                                 # Merge branch into current

git branch -d <branch>                             # Delete local branch

git push origin --delete <branch>                  # Delete remote branch

git branch --unset-upstream                        # Remove track from branch


## 4. Remote Management

git remote -v                                      # List remote repositories

git remote add <name> <url>                        # Add new remote

git fetch <remote>                                 # Download objects from remote

git pull                                           # Fetch + merge (default: origin/main)

git pull --rebase                                  # Fetch + rebase instead of merge

git push -u origin <branch>                        # Push & set upstream

git push --force-with-lease                        # Safer force push

## 5. Stashing Changes

git stash                                         # Stash working directory

git stash save "message"                          # Stash with message

git stash list                                    # List stashed changes

git stash pop                                     # Apply and remove most recent stash

git stash apply                                   # Apply without removing from stash

git stash drop                                    # Delete most recent stash

git stash branch <name>                           # Create branch from stash

## 6. Undoing Changes

git reset --soft HEAD^                            # Undo commit but keep changes staged

git reset --mixed HEAD^                           # Undo commit, unstage changes (default)

git reset --hard HEAD^                            # Discard commit and changes (careful!)

git revert <commit>                               # Create undo commit

git checkout -- <file>                            # Discard uncommitted file changes

git restore <file>                                # Newer way to discard changes

git clean -fd                                     # Remove untracked files/directories

## 7. Viewing History & Diffs

git log --oneline                                 # Compact commit history

git log --graph --decorate --all                  # Visual branch history

git diff                                          # Unstaged changes

git diff --staged                                 # Staged changes

git diff <commit1> <commit2>                      # Compare two commits

git show <commit>                                 # Show commit details

git blame <file>                                  # Show file changes by author

## 8. Advanced Tools

git rebase <branch>                               # Reapply commits on another branch

git cherry-pick <commit>                          # Apply specific commit

git bisect                                        # Binary search for bugs

git reflog                                        # Show reference history (recovery tool)

git worktree add ../new-dir                       # Manage multiple working trees

git submodule update --init                       # Initialize submodules

## 9. Collaboration

git fetch --prune                                 # Remove deleted remote branches locally

git request-pull origin/main <feature-branch>     # Generate pull request summary

git tag v1.0                                      # Create lightweight tag

git tag -a v1.0 -m "Version 1.0"                  # Create annotated tag

## 10. Patch Management

git diff > changes.patch                          # Generate patch file

git apply changes.patch                           # Apply patch file

git format-patch HEAD~2                           # Generate email-ready patches

## 11. Hooks (in .git/hooks/)

pre-commit     # Run before commit

post-merge     # After merge completes

pre-push       # Before pushing to remote

## Tips & Tricks

# Shortcut aliases (add to .gitconfig)

[alias]

    co = checkout

    br = branch

    ci = commit

    st = status

    lol = log --graph --oneline --decorate
    
    unstage = reset HEAD --