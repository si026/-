---
name: git-commit-push
description: Commits all changes and pushes to the Gitee repository https://gitee.com/si-yabo1/siyabo.git. Use when the user asks to commit and push this project to Gitee. Do not use for other git operations.
---

# Git Commit and Push

## Remote Repository

- URL: `https://gitee.com/si-yabo1/siyabo.git`
- Name: `origin` (if not already set)

## Steps

1. Check git status to see what will be committed:
   ```
   git status
   ```

2. Verify the `origin` remote points to the correct URL:
   ```
   git remote get-url origin
   ```
   If it returns a different URL or errors, run:
   ```
   git remote remove origin
   git remote add origin https://gitee.com/si-yabo1/siyabo.git
   ```

3. Stage all changes:
   ```
   git add -A
   ```

4. Check staged changes:
   ```
   git status
   ```

5. Ask the user for a commit message, or generate a concise one based on the changes.

6. Commit the staged changes:
   ```
   git commit -m "<commit message>"
   ```

7. Push to the remote repository:
   ```
   git push -u origin master
   ```
   If the default branch is `main` instead of `master`, use:
   ```
   git push -u origin main
   ```

## Notes

- Never commit secrets or sensitive files (check .gitignore).
- If push fails due to non-fast-forward, inform the user and suggest pulling first (`git pull --rebase origin <branch>`).
