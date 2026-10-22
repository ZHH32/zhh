---
name: commit-and-push
description: Commit all changes and push the project to the Gitee remote repository at https://gitee.com/zhang-huaihao/zhh_html.git. Use when the user asks to submit, commit, push, or upload the project.
metadata:
  opencode/slash: "false"
  opencode/autoinvoke: "false"
---

## What I do

1. Ensure the Gitee remote is configured
2. Check status and recent commits
3. Stage all project files
4. Create a commit with a descriptive message
5. Push to the Gitee remote repository

## Workflow

### 1. Check/Configure Remote

```powershell
$git = "D:\下载\Git\cmd\git.exe"
& $git -C d:\webpage\111 remote -v
# 如果没有 origin，则添加：
& $git -C d:\webpage\111 remote add origin https://gitee.com/zhang-huaihao/zhh_html.git
```

### 2. Check Status

```powershell
& $git -C d:\webpage\111 status --short
& $git -C d:\webpage\111 log --oneline -3 2>$null
```

### 3. Stage All Files

```powershell
& $git -C d:\webpage\111 add -A
```

### 4. Commit

```powershell
& $git -C d:\webpage\111 commit -m "简洁描述本次变更"
```

### 5. Push

```powershell
& $git -C d:\webpage\111 push -u origin main
```

## Notes

- 本机 git 不在 PATH 中，必须用完整路径 `D:\下载\Git\cmd\git.exe` 调用
- PowerShell 不支持 heredoc，多行提交信息用反引号 n 换行
- 远程已有新内容时先 `& $git -C d:\webpage\111 pull --rebase` 再推送
- 只要求提交、没要求推送时，跳过第 5 步
