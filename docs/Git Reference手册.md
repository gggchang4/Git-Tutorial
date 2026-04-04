# Git Reference手册

## 文档定位

本手册面向 Git 命令查询，强调准确、稳定、结构统一。重点是把常用命令整理成适合日常速查的 Reference，而不是做成冗长的百科式手册。

## 使用方式

建议每个命令统一采用以下结构：

1. 命令用途
2. 语法格式
3. 常用参数
4. 使用示例
5. 注意事项
6. 官方文档链接

## 章节规划

### 1. 本地仓库命令

- `git init`
- `git add`
- `git commit`
- `git status`
- `git log`
- `git diff`
- `git clean`
- `git mv`
- `git rm`

### 2. 远程仓库命令

- `git clone`
- `git remote`
- `git fetch`
- `git pull`
- `git push`
- `git fetch --prune`

### 3. 分支与合并命令

- `git branch`
- `git switch`
- `git checkout`
- `git merge`
- `git rebase`
- `git stash`
- `git cherry-pick`

### 4. 回滚与恢复命令

- `git reset`
- `git revert`
- `git restore`
- `git reflog`
- `git commit --amend`

### 5. 标签与发布相关命令

- `git tag`
- `git fetch --tags`
- `git push origin <tag>`
- `git tag -d <tag>`

### 6. 配置与查看类命令

- `git config`
- `git help`
- `git show`
- `git blame`

### 7. 关键词索引

- 按命令字母顺序整理最终索引
- 链接到文档内对应章节锚点

## 写作要求

- 事实性描述优先对齐 Git 官方文档
- 参数说明优先覆盖高频选项
- 同类命令的差异要讲清楚
- 危险命令必须显式写出风险

## 当前状态

- 当前为文档骨架版本
- 正文内容待按开发节奏逐步补齐
