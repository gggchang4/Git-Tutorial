# Git学习手册

## 文档定位

本手册面向 Git 学习路径，重点解决“从入门到进阶如何建立完整认知”的问题。内容会覆盖基础命令、远程协作、分支管理、回滚恢复、冲突处理和底层原理。

## 目标读者

- 刚开始系统学习 Git 的开发者
- 已会基础命令，但缺少知识结构的人
- 希望把 Git 用法和原理真正串起来的读者

## 章节规划

### 1. Git 简介与安装配置

- Git 是什么
- Git 与 SVN 的区别
- Git 安装
- 基础配置

### 2. 本地仓库核心操作

- `git init`
- `git add`
- `git commit`
- `git status`
- `git log`
- `git diff`

### 3. 远程仓库基础交互

- `git clone`
- `git remote`
- `git pull`
- `git push`
- SSH 基础配置

### 4. 分支管理与协作

- `git branch`
- `git switch`
- `git checkout`
- `git merge`
- `git rebase`
- `git stash`

### 5. 回滚、撤销与恢复

- `git reset`
- `git revert`
- `git restore`
- `git commit --amend`

### 6. 冲突解决

- 冲突产生原因
- 冲突查看
- 冲突解决流程
- 减少冲突的方法

### 7. 标签与版本标记

- `git tag`
- 标签的使用场景

### 8. Git 原理

- 工作区、暂存区、本地仓库
- blob、tree、commit、tag
- 快照模型
- 分支指针
- 分布式原理

### 9. 常见问题排查

- 基础报错
- 远程同步问题
- 回滚与恢复问题
- 分支与冲突问题

## 写作要求

- 每个核心知识点尽量包含“专业讲解 + 通俗解读 + 示例 + 图示 + 参考链接”
- 命令示例优先使用高频、可复现的场景
- 图示优先使用 Mermaid
- 涉及风险命令时必须标注注意事项

## 当前状态

- 当前为文档骨架版本
- 正文内容待按开发节奏逐步补齐
