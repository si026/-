---
name: git-commit-push-github
description: Commits all changes and pushes the entire project to the GitHub repository https://github.com/si026/-.git. Use when the user asks to commit and push to GitHub. Do not use for pushing to Gitee.
---

# Git Commit and Push (GitHub)

## Remote Repository

- URL: `https://github.com/si026/-.git`（GitHub 账号 si026）
- Remote name: `github`（Gitee 的 `origin` 保持不变）

## Steps

1. Check git status to see what will be committed:
   ```
   git status
   ```

2. Ensure the `github` remote exists and uses the SSH 443 address:
   ```
   git remote get-url github
   ```
   If it errors or differs, set it:
   ```
   git remote set-url github ssh://git@ssh.github.com:443/si026/-.git
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

7. Push to GitHub（指定密钥，走 443 端口）:
   PowerShell:
   ```
   $env:GIT_SSH_COMMAND = "ssh -i C:/Users/user/.ssh/id_ed25519_gitee"
   git push -u github master
   ```

## Notes

- 本机网络环境：HTTPS 直连 GitHub 会报 SSL 证书错误，SSH 22 端口被拒，只能走 SSH over 443（ssh.github.com）
- 认证密钥：`C:\Users\user\.ssh\id_ed25519_gitee`（该公钥已添加到 GitHub 账号 si026）
- Never commit secrets or sensitive files (check .gitignore).
- If push fails due to non-fast-forward, inform the user and suggest `git pull --rebase github master` first.

