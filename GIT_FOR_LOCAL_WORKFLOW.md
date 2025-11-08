# Git and GitHub Commands for Local PR Workflow

This documentation provides **Git and GitHub commands** used in creating, managing, and debugging **Pull Requests (PRs)** from a **local environment**.  
Each of the **10 aspects** includes **5 essential commands** that cover different parts of the workflow.

---

## 1. Repository Setup & Initialization

| Command | Purpose / Notes |
|----------|-----------------|
| `git init` | Initialize a new local Git repository. |
| `git remote add origin <url>` | Connect local repo to a GitHub remote. |
| `git clone <repo_url>` | Clone an existing remote repository. |
| `git remote -v` | List configured remote repositories. |
| `git fetch origin` | Fetch latest branches and updates without merging. |

---

## 2. Branch Management

| Command | Purpose / Notes |
|----------|-----------------|
| `git branch` | List all branches in your local repository. |
| `git branch <new_branch>` | Create a new local branch. |
| `git checkout <branch_name>` | Switch to an existing branch. |
| `git checkout -b <branch_name>` | Create and switch to a new branch. |
| `git branch -d <branch_name>` | Delete a local branch after merge. |

---

## 3. Staging & Committing Changes

| Command | Purpose / Notes |
|----------|-----------------|
| `git status` | Show modified and untracked files. |
| `git add <file>` | Stage a specific file for commit. |
| `git add .` | Stage all modified/untracked files. |
| `git commit -m "message"` | Commit staged changes with a message. |
| `git restore --staged <file>` | Unstage a file accidentally added. |

---

## 4. Syncing with Remote Repository

| Command | Purpose / Notes |
|----------|-----------------|
| `git pull origin main` | Pull latest changes from remote `main`. |
| `git fetch --all` | Fetch all branches and tags from origin. |
| `git merge origin/main` | Merge fetched main branch into current branch. |
| `git rebase origin/main` | Rebase current branch on latest main branch. |
| `git push origin <branch>` | Push local branch changes to GitHub. |

---

## 5. Creating and Managing Pull Requests (PRs)

| Command | Purpose / Notes |
|----------|-----------------|
| `gh pr create --fill` | Create a PR using commit messages and default template. |
| `gh pr create --base main --head <branch>` | Create PR from local branch to main. |
| `gh pr view --web` | Open PR page in browser. |
| `gh pr list` | List all open PRs for the repo. |
| `gh pr status` | Show PRs associated with the current branch. |

---

## 6. Reviewing & Updating Pull Requests

| Command | Purpose / Notes |
|----------|-----------------|
| `gh pr checkout <PR_number>` | Fetch and switch to a PR branch locally. |
| `gh pr diff <PR_number>` | View differences for a specific PR. |
| `gh pr comment <PR_number> --body "Looks good"` | Add a comment to a PR. |
| `gh pr merge <PR_number> --merge` | Merge a PR with a merge commit. |
| `gh pr close <PR_number>` | Close a PR without merging. |

---

## 7. Handling Merge Conflicts

| Command | Purpose / Notes |
|----------|-----------------|
| `git merge main` | Merge `main` into current branch (may cause conflicts). |
| `git status` | See files with merge conflicts. |
| `git diff` | View differences between conflicting versions. |
| `git mergetool` | Launch merge resolution tool. |
| `git add <file> && git commit` | Mark conflicts as resolved and commit. |

---

## 8. Rebasing & Cleaning History

| Command | Purpose / Notes |
|----------|-----------------|
| `git rebase -i HEAD~3` | Interactive rebase last 3 commits. |
| `git commit --amend` | Edit the last commit message or content. |
| `git rebase --continue` | Continue rebase after conflict resolution. |
| `git rebase --abort` | Abort rebase and restore branch. |
| `git reset --soft HEAD~1` | Undo last commit, keep changes staged. |

---

## 9. Tagging, Versioning & Releases

| Command | Purpose / Notes |
|----------|-----------------|
| `git tag -a v1.0 -m "First release"` | Create an annotated tag. |
| `git tag` | List all tags in repository. |
| `git push origin v1.0` | Push a specific tag to GitHub. |
| `gh release create v1.0 --notes "Initial release"` | Create a GitHub release. |
| `gh release view v1.0` | View details of a release. |

---

## 10. Debugging, Logs & Cleanup

| Command | Purpose / Notes |
|----------|-----------------|
| `git log --oneline --graph --decorate` | Visualize commit history. |
| `git show <commit_hash>` | Show details of a specific commit. |
| `git reflog` | View recent actions and branch history. |
| `git clean -fd` | Remove untracked files and folders. |
| `git fsck --full` | Check repository for errors or corruption. |

---

