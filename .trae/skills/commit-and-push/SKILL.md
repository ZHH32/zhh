---
name: commit-and-push
description: 提交并推送当前项目到远程 Git 仓库。当用户要求提交项目、提交代码、推送或 push 时使用。不用于仅查看 git 状态或修改代码。
---

## What I do

1. 确认 Gitee 远程仓库已配置
2. 查看状态和最近提交
3. 暂存所有项目文件
4. 用简洁的描述创建提交
5. 推送到 Gitee 远程仓库

## Workflow

### 1. 检查/配置远程

```powershell
$git = "D:\下载\Git\cmd\git.exe"
& $git -C d:\webpage\111 remote -v
# 如果没有 origin，则添加：
& $git -C d:\webpage\111 remote add origin https://gitee.com/zhang-huaihao/zhh_html.git
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

### 5. 推送

```powershell
& $git -C d:\webpage\111 push -u origin main
```

## Notes

- 本机 git 不在 PATH 中，必须用完整路径 `D:\下载\Git\cmd\git.exe` 调用
- PowerShell 不支持 heredoc，多行提交信息用反引号 n 换行
- 远程已有新内容时先 `& $git -C d:\webpage\111 pull --rebase` 再推送
- 只要求提交、没要求推送时，跳过第 5 步并说明领先远程几个提交
