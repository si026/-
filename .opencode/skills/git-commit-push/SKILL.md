---
name: git-commit-push
description: Use when the user asks to commit and push the current project to the Gitee repository. Commits all changes and pushes to https://gitee.com/si-yabo1/siyabo.git
---

# Git Commit and Push

Use this skill when the user asks to commit and push the current project.

## Remote Repository

- URL: `https://gitee.com/si-yabo1/siyabo.git`
- Name: `origin` (if not already set)

## Steps

1. Check git status to see what will be committed:
   ```
   git status
   ```

2. If `origin` remote is not set to the correct URL, set it:
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
