---
name: github-push
description: 提交整个项目并推送到 GitHub 仓库 https://github.com/ZHH32/zhh.git。当用户要求提交 GitHub、上传 GitHub、push 到 github 时使用。不用于推送到 Gitee，也不用于仅查看 git 状态或修改代码。
---

## What I do

1. 确认 GitHub 远程仓库已配置
2. 查看状态和最近提交
3. 暂存所有项目文件
4. 用简洁的描述创建提交
5. 推送到 GitHub 远程仓库

## Workflow

### 1. 检查/配置远程

```powershell
$git = "D:\下载\Git\cmd\git.exe"
& $git -C d:\webpage\111 remote -v
# 如果没有名为 github 的远程，则添加：
& $git -C d:\webpage\111 remote add github https://github.com/ZHH32/zhh.git
```

### 2. 查看状态

```powershell
& $git -C d:\webpage\111 status --short
& $git -C d:\webpage\111 log --oneline -3 2>$null
```

### 3. 暂存所有文件

```powershell
& $git -C d:\webpage\111 add -A
```

### 4. 创建提交

```powershell
& $git -C d:\webpage\111 commit -m "简洁描述本次变更"
```

### 5. 推送到 GitHub

```powershell
& $git -C d:\webpage\111 push -u github main
```

## Notes

- 本仓库 origin 指向 Gitee，GitHub 使用独立远程名 `github`，推送目标永远是 `github` 而不是 `origin`
- 本机 git 不在 PATH 中，必须用完整路径 `D:\下载\Git\cmd\git.exe` 调用
- PowerShell 不支持 heredoc，多行提交信息用反引号 n 换行
- 首次推送或推送时弹出登录窗口，需要用户完成 GitHub 认证（浏览器登录或 Personal Access Token）
- GitHub 远程已有新内容时先 `& $git -C d:\webpage\111 pull github main --rebase` 再推送
- 只要求提交、没要求推送时，跳过第 5 步并说明领先远程几个提交
