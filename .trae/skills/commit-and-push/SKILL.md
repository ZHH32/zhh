---
name: commit-and-push
description: 提交并推送当前项目到远程 Git 仓库。当用户要求提交项目、提交代码、推送或 push 时使用。不用于仅查看 git 状态或修改代码。
---

# 提交项目

将当前项目提交并推送到远程仓库。

## 环境要点

- 本机 git 不在 PATH 中，必须用完整路径调用，例如：
  `& "D:\下载\Git\cmd\git.exe" -C d:\webpage\111 status`
- Shell 是 PowerShell：不支持 `<<'EOF'` heredoc；多行提交信息用反引号 n 换行，
  如 `-m "标题`n`n正文"`（正文行尾接 Co-Authored-By 说明）
- 分支为 main，已关联 origin/main

## 步骤

1. 运行 `git status` 和 `git diff` 确认本次变更内容
2. 运行 `git remote -v` 检查远程仓库是否已配置
3. 如果没有远程仓库，运行 `git remote add origin 仓库URL`
4. 运行 `git add .` 暂存所有文件（提交前确认没有敏感文件或不该入库的内容）
5. 运行 `git commit -m "..."` 创建提交，提交信息简洁描述本次变更内容
6. 运行 `git push -u origin main` 推送到远程仓库（首次之后可只用 `git push`）

## 注意事项

- 如果远程仓库已有新内容，先 `git pull --rebase` 再推送
- 确保 `.gitignore` 已正确配置，避免提交不必要的文件
- 用户只要求提交、没要求推送时，跳过第 6 步并在结果中说明领先远程几个提交
