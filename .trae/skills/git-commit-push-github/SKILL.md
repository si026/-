---
name: git-commit-push-github
description: Commits all changes and pushes the entire project to the GitHub repository https://github.com/sl026/-.git. Use when the user asks to commit and push to GitHub. Do not use for pushing to Gitee.
---

# Git Commit and Push (GitHub)

## Remote Repository

- URL: `https://github.com/sl026/-.git`
- Remote name: `github`（Gitee 的 `origin` 保持不变）

## Steps

1. Check git status to see what will be committed:
   ```
   git status
   ```

2. Ensure the `github` remote exists and points to the correct URL:
   ```
   git remote get-url github
   ```
   If it errors, add it:
   ```
   git remote add github https://github.com/sl026/-.git
   ```
   If it returns a different URL, fix it:
   ```
   git remote set-url github https://github.com/sl026/-.git
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

7. Push to GitHub:
   ```
   git push -u github master
   ```

## Notes

- If HTTPS push fails due to authentication (no credential helper), switch to SSH and retry — requires the public key `~/.ssh/id_ed25519_gitee.pub` to be added to the GitHub account:
  ```
  git remote set-url github git@github.com:sl026/-.git
  git push -u github master
  ```
- Never commit secrets or sensitive files (check .gitignore).
- If push fails due to non-fast-forward, inform the user and suggest `git pull --rebase github master` first.
