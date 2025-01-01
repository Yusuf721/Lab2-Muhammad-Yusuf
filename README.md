# Git Operations Guide

This document provides a comprehensive guide to essential Git operations, including pulling updates, managing branches, tags, and understanding rebase.

## Understanding the `git pull` Command

The `git pull` command is a vital tool in Git, allowing developers to synchronize their local repositories with updates from a remote repository. It combines two key operations:

1. **Fetch**: Retrieves the latest changes from the remote repository.
2. **Merge**: Incorporates those changes into the current branch of the local repository.

By performing both steps in one command, `git pull` ensures your local copy is aligned with the latest contributions.

---

## Commands for the Pull Operation

### Fetching Changes
To manually download updates from a remote repository:
```bash
git fetch <remote-name>
```
By default, the remote name is `origin`. This command downloads the updates without merging them.

### Merging Changes
To apply fetched changes to your current branch:
```bash
git merge <branch-name>
```
This integrates the updates from the remote branch into your local branch.

### Pulling Changes (Fetch + Merge)
The `git pull` command combines fetching and merging in one step:
```bash
git pull <remote-name> <branch-name>
```
For example:
```bash
git pull origin main
```
This fetches and merges updates from the `main` branch of the `origin` remote repository.

---

## Example Workflow
1. Switch to the branch you want to update:
   ```bash
   git checkout <branch-name>
   ```
2. Pull the latest changes:
   ```bash
   git pull origin <branch-name>
   ```
   Replace `<branch-name>` with the appropriate branch name, such as `main` or `dev`.

---

## Removing Branches

### Deleting a Branch Locally
To delete a branch from your local repository:
```bash
git branch -d <branch-name>
```
If the branch has not been merged, force deletion with:
```bash
git branch -D <branch-name>
```

### Deleting a Branch Remotely
To delete a branch from a remote repository:
```bash
git push <remote-name> --delete <branch-name>
```
For example:
```bash
git push origin --delete feature-branch
```

---

## Managing Tags in Git

### Listing Tags Locally
To view all tags in your local repository:
```bash
git tag
```

### Deleting a Tag Locally
To remove a tag from your local repository:
```bash
git tag -d <tag-name>
```
For example:
```bash
git tag -d v1.0
```

### Deleting a Tag Remotely
To delete a tag from a remote repository:
```bash
git push <remote-name> --delete <tag-name>
```
For example:
```bash
git push origin --delete v1.0
```
Alternatively, push an empty reference to the tag:
```bash
git push origin :refs/tags/<tag-name>
```

---

## Understanding Git Rebase

The `git rebase` command integrates changes from one branch into another by moving the base of the branch to a new starting point. Unlike `git merge`, which creates a merge commit, `git rebase` rewrites the commit history to create a linear history.

### Difference Between Rebase and Merge

- **Rebase**: Creates a clean, linear commit history by rewriting logs.
- **Merge**: Combines changes while retaining the branch history.



### Example
![How Merge and Rebase Work](./mergeVsRebase.png)

### Benefits of Rebase
- Produces a clean, linear commit history.
- Simplifies the process of reviewing changes.

---

## Adding an Image

Include images in your documentation for clarity. Example:

![Together, We Rise](./google.jpg)
