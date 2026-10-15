# 提交项目

将当前项目提交并推送到远程仓库。

## 步骤

1. 运行 `git remote -v` 检查远程仓库是否已配置
2. 如果没有远程仓库，运行 `git remote add origin <仓库URL>`
3. 运行 `git add .` 暂存所有文件
4. 运行 `git commit -m "提交项目"` 创建提交
5. 运行 `git push -u origin main` 推送到远程仓库

## 注意事项

- 如果远程仓库已有内容，可能需要先 `git pull --rebase`
- 确保 `.gitignore` 已正确配置，避免提交不必要的文件
- 提交信息应简洁描述本次变更内容
