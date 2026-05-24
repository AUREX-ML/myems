Here's a summarized version of the branching guide that you can save into a text file:

```
# Developer Guide: Setting Up Branching Strategy

## Overview
Cloned repo structure:
MYEMS/myems (upstream) -> aurex-ml/myems (origin) -> local machine

## Step 1: Verify Current Setup
```bash
git branch
git remote -v
```

## Step 2: Add Upstream Remote
```bash
git remote add upstream https://github.com/MYEMS/myems.git
git remote -v
```

## Step 3: Ensure Master is Up to Date
```bash
git checkout master
git pull origin master
```

## Step 4: Create the `develop` Branch
```bash
git checkout -b develop
git push -u origin develop
```

## Step 5: Working on a Feature
1. Start from `develop`:
    ```bash
    git checkout develop
    git pull origin develop
    ```
2. Create Feature Branch:
    ```bash
    git checkout -b feature/your-feature-name
    ```
3. Work and Commit:
    ```bash
    git add .
    git commit -m "feat: describe what you did"
    git push -u origin feature/your-feature-name
    ```

## Step 6: Merge Feature Back to `develop`
```bash
git checkout develop
git pull origin develop
git merge feature/your-feature-name
git push origin develop
```

## Step 7: Merge `develop` into `master` (Release)
```bash
git checkout master
git pull origin master
git merge develop
git push origin master
```

## Step 8: Sync Your Fork with Upstream
```bash
git fetch upstream
git checkout master
git merge upstream/master
git push origin master
git checkout develop
git merge master
git push origin develop
```

## Complete Branching Flow Summary
```
MYEMS/myems (upstream)
        |
        | git fetch upstream
        |
aurex-ml/myems (origin)
  master  <------ develop <------ feature/xyz
  (CodeQL triggers here)
```

## Commit Message Convention
- feat: add new feature
- fix: resolve a bug
- docs: update documentation
- refactor: restructure code
- test: add or update tests
- chore: maintenance tasks

## Tips
Always run `git pull origin develop` before creating a new feature branch to avoid merge conflicts!
```

Feel free to copy this text into a `.txt` file for your reference!