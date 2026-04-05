# Git实用拓展手册

## 文档定位

本手册聚焦 Git 相关的工具链、效率技巧和自动化实践，帮助读者从“会用 Git”进一步走向“用得顺手、用得稳定、用得节省时间”。

它不追求列出所有 Git 周边工具，而是优先覆盖个人开发和小型协作中最常见、最容易落地、最值得长期维护的一批工具与做法。

本手册与其他 Part 的关系如下：

- Part 1 负责帮助你理解 Git 概念、流程和原理
- Part 2 负责帮助你查询命令和参数
- Part 3 负责帮助你形成稳定的 Git 行为规范
- Part 4 负责帮助你选工具、提效率、做自动化和降低踩坑概率

## 使用说明

### 1. 工具选择原则

选择 Git 工具时，优先按下面的顺序判断：

1. 它是否真的解决你当前的高频问题
2. 它是否能稳定维护，不会引入比收益更高的复杂度
3. 它是否与当前团队或仓库规范兼容
4. 它是否有官方文档、官方仓库或长期可访问的公开资料

### 2. 三类常见诉求

如果你只是想更快进入状态，先按诉求选工具：

- 想减少记命令压力：优先看 GUI / IDE 工具
- 想提升终端操作效率：优先看命令行增强工具
- 想减少漏测、漏格式化、泄露敏感信息：优先看自动化与防护工具

### 3. 时效性说明

工具状态、功能边界和授权方式都可能变化。本手册只使用官方文档或官方仓库作为主要依据；涉及更细的版本差异、套餐差异和平台限制时，请以工具官网最新说明为准。

### 4. 最小工具组合建议

如果你不想一次引入太多工具，可以先按下面的最小组合开始：

- 只想把日常提交做顺：`VS Code 内置 Git` 或 `GitHub Desktop`
- 想在编辑器里更快看懂历史：`VS Code 内置 Git + GitLens`
- 想把 GitHub 协作搬到终端：`git + gh`
- 想把提交前质量兜住：`Git Hooks + pre-commit`，或在 Node.js 项目里用 `Husky`
- 想先把仓库卫生做好：`.gitignore + Git LFS（如有大文件）+ Gitleaks 或 git-secrets`

不建议一开始把 GUI、终端增强、Hook、扫描器、LFS 一次性全装上。先解决最痛的高频问题，再逐步加项，长期维护成本会低很多。

## 1. GUI 与 IDE 工具

### 1.1 选型速览

| 工具 | 类型 | 更适合谁 | 典型价值 |
|------|------|----------|----------|
| GitHub Desktop | 独立 GUI | Git 新手、GitHub 用户 | 降低提交、分支、PR 基础操作门槛 |
| Sourcetree | 独立 GUI | 想看分支图和历史的人 | 图形化查看提交、分支与冲突 |
| GitKraken | 独立 GUI | 重视可视化体验的开发者 | 更强的图形化仓库浏览和协作视图 |
| VS Code 内置 Git | IDE 内置 | 日常就在 VS Code 工作的人 | 不离开编辑器完成常见 Git 操作 |
| GitLens | VS Code 扩展 | 想在编辑器里看历史和责任归属的人 | 强化 blame、历史、提交关系和工作流可见性 |

### 1.2 GitHub Desktop

#### 是什么

GitHub Desktop 是 GitHub 官方维护的桌面 Git 客户端，重点覆盖提交、分支切换、历史查看、冲突提示和 Pull Request 基础协作流程。

#### 适合谁

- Git 初学者
- 日常主要使用 GitHub 的开发者
- 不想把大量时间花在 Git 命令记忆上的人

#### 安装方式

从 GitHub Desktop 官方下载页下载安装即可。官方文档当前说明其支持 Windows 和 macOS。

#### 优点

- 官方维护，和 GitHub 工作流贴合度高
- 提交、切分变更、查看 diff、切换分支都比较直观
- 对常见协作入口友好，适合先建立稳定习惯

#### 注意点

- 更适合常见场景，不适合作为“所有复杂 Git 场景”的唯一入口
- 对高级历史整理、复杂 rebase、批量自动化场景，终端通常更强
- GitHub Desktop 官方文档也提到它可以配合其他 Git hosting services 使用，但它的默认心智模型仍然更贴近 GitHub 工作流

#### 官方链接

- <https://desktop.github.com/>
- <https://docs.github.com/desktop>

### 1.3 Sourcetree

#### 是什么

Sourcetree 是 Atlassian 提供的 Git 图形客户端，常用于可视化查看分支、提交历史、stash、tag 和合并关系。

#### 适合谁

- 习惯先看图再操作的人
- 经常需要观察分支图、回看提交关系的人

#### 安装方式

从 Sourcetree 官方站点下载安装即可，具体系统要求和账号接入方式以 Atlassian 官方支持文档为准。

#### 优点

- 图形化历史和分支视图比较直观
- 对“我现在在哪条分支”“这次合并是怎么来的”这类问题很有帮助

#### 注意点

- 图形界面容易让人忽视底层命令含义，建议仍保留 Part 1 / Part 2 的基础认知
- 不同账号、不同远程地址配置时，要注意凭据管理和协议统一

#### 官方链接

- <https://www.sourcetreeapp.com/>
- <https://support.atlassian.com/sourcetree/>

### 1.4 GitKraken

#### 是什么

GitKraken 是面向 Git 工作流的图形客户端，强调提交图、分支图、仓库导航和协作可视化。

#### 适合谁

- 重视视觉化工作流的人
- 希望更方便地浏览复杂分支关系的人

#### 安装方式

从 GitKraken 官方下载页安装。具体授权方案、可用能力和平台支持请以官方帮助文档为准。

#### 优点

- 提交关系图、分支图和仓库状态的表达较强
- 适合在复杂仓库里快速建立上下文

#### 注意点

- 具体功能边界和授权方式可能会变化，使用前先看官方说明
- 不要因为图形工具“看起来方便”，就忽略了公共历史改写、强推等操作的风险

#### 官方链接

- <https://www.gitkraken.com/git-client>
- <https://help.gitkraken.com/>

### 1.5 VS Code 内置 Git

#### 是什么

VS Code 自带 Source Control 视图，可以直接完成常见 Git 操作，例如查看修改、stage / unstage、commit、branch、sync 和 conflict resolution 入口。

#### 适合谁

- 主要开发环境就是 VS Code 的开发者
- 希望尽量不切出编辑器的人

#### 安装方式

安装 VS Code 后即可直接使用内置 Source Control 视图，无需额外安装 Git 客户端扩展。

#### 优点

- 零额外安装成本
- 日常提交、看 diff、解决简单冲突都够用
- 与编辑器上下文天然联动

#### 注意点

- 内置功能适合高频基础操作，不代表可以替代所有终端命令
- 如果你对历史排查、作者归属、提交关系追溯要求更高，可以再配合 GitLens

#### 官方链接

- <https://code.visualstudio.com/docs/sourcecontrol/overview>

### 1.6 GitLens

这里将你提到的 `gitlen` 视为 `GitLens`。

#### 是什么

GitLens 是 GitKraken 团队维护的 VS Code 扩展，用来增强 VS Code 中的 Git 可见性。它的核心价值不是“代替 Git”，而是把 blame、提交历史、作者归属、行级修改来源、分支和提交关系更直接地展示在编辑器里。

#### 适合谁

- 日常主力工具是 VS Code 的开发者
- 经常会问“这段代码是谁改的”“为什么这样改”“这个文件最近怎么演变的”的人
- 想在不离开编辑器的前提下加强历史追踪能力的人

#### 安装方式

可直接从 VS Code Marketplace 安装 GitLens 扩展，也可以通过扩展面板搜索 `GitLens` 安装。

#### 优点

- 强化文件级、行级、提交级历史可见性
- 对排查回归问题、理解陌生代码、定位责任上下文很有帮助
- 与 VS Code 内置 Git 互补，而不是重复造一个客户端

#### 注意点

- GitLens 不是独立 Git 客户端，复杂历史操作仍然建议结合 Git 原生命令
- 某些高级能力可能受不同版本或授权方式影响，使用前先看官方说明
- 适合“理解上下文”，不适合让人因此忽略基础 Git 命令学习

#### 推荐场景

- 查看某一行最后一次是谁改的
- 追踪某个文件的提交演变
- 在 review 或排障时快速回看某次提交改动

#### 官方链接

- <https://gitlens.amod.io/>
- <https://help.gitkraken.com/gitlens/gitlens-home/>
- <https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens>

## 2. 命令行增强工具

### 2.1 使用原则

命令行增强工具的目标不是“让终端更花哨”，而是减少重复输入、缩短高频路径、把常见协作动作固化下来。

### 2.2 Git alias

#### 是什么

Git alias 是 Git 原生支持的命令别名机制，适合把高频但较长的命令封装成更短的入口。

#### 适合谁

- 已经有稳定 Git 操作习惯的人
- 想压缩高频命令输入成本的人

#### 适合固化的高频 alias

```bash
git config --global alias.st "status -sb"
git config --global alias.lg "log --oneline --graph --decorate --all"
git config --global alias.last "log -1 HEAD --stat"
git config --global alias.unstage "restore --staged --"
```

#### 优点

- 无额外依赖
- 可移植性高
- 很适合把个人高频动作沉淀成习惯

#### 注意点

- alias 要少而稳，不要把几乎不用的命令也强行起别名
- 团队共享脚本时，尽量仍给出原始命令，避免别人必须理解你的私人 alias

#### 官方链接

- <https://git-scm.com/book/en/v2/Git-Basics-Git-Aliases>
- <https://git-scm.com/docs/git-config>

### 2.3 GitHub CLI (`gh`)

#### 是什么

GitHub CLI 是 GitHub 官方命令行工具，用来在终端里处理仓库、Issue、PR、Release 等 GitHub 相关工作流。

#### 适合谁

- 终端党
- 经常需要打开 PR、查看 PR、checkout PR、处理 issue 的 GitHub 用户

#### 安装方式

按 GitHub CLI 官方安装说明使用对应平台的包管理器或安装包安装。首次使用前建议先执行 `gh auth login` 完成认证。

#### 常见价值

- 在终端里创建和查看 PR
- 快速 checkout 某个 PR 分支
- 在本地 Git 操作之外补足 GitHub 平台动作

#### 高频入口

```bash
gh pr create
gh pr view --web
gh pr checkout 123
```

适用环境：Bash / Git Bash / PowerShell

#### 注意点

- 它解决的是 GitHub 平台协作，不是取代 `git`
- 如果仓库不在 GitHub 上，收益会明显降低

#### 官方链接

- <https://cli.github.com/>
- <https://cli.github.com/manual/>

### 2.4 Lazygit

#### 是什么

Lazygit 是开源的终端 UI 工具，用来在终端里图形化管理 Git 状态、提交、stash、branch 和历史。

#### 适合谁

- 喜欢终端，但又想要比纯命令更直观的交互
- 想减少频繁输入长命令的人

#### 优点

- 保留终端环境
- 对高频动作切换较快
- 适合作为 GUI 和纯命令之间的折中方案

#### 注意点

- 它是效率工具，不是基础认知的替代品
- 涉及公共历史改写、强推、复杂 rebase 时，仍应明确自己正在做什么

#### 官方链接

- <https://github.com/jesseduffield/lazygit>

## 3. 自动化工具与脚本

### 3.1 Git Hooks

#### 是什么

Git Hooks 是 Git 原生支持的脚本钩子机制，可以在 `pre-commit`、`commit-msg`、`pre-push` 等时机执行自动检查。

#### 适合解决的问题

- 漏格式化
- 漏测试
- 提交信息不符合规范
- 推送前缺少关键验证

#### 常见落点

- `pre-commit`：格式化、lint、快速测试
- `commit-msg`：提交信息结构校验
- `pre-push`：更重一点的测试或检查

#### 注意点

- 本地 Hook 适合挡住高频低级错误，但不要塞进过重的检查，避免拖垮体验
- 团队项目里要区分“本地快检查”和“CI 最终兜底检查”

#### 官方链接

- <https://git-scm.com/book/en/v2/Customizing-Git-Git-Hooks>

### 3.2 pre-commit

#### 是什么

`pre-commit` 是一个通用 Hook 管理工具，用来统一管理和分发各类 pre-commit 检查。

#### 适合谁

- 想把格式化、lint、基础安全检查统一到提交前入口的人
- 多语言仓库维护者

#### 安装方式

按官方文档安装 `pre-commit` 后，在仓库根目录执行 `pre-commit install` 即可把它接入 Git Hooks。

#### 优点

- 社区生态成熟
- 配置集中
- 很适合放入仓库长期维护

#### 注意点

- 不要把运行时间过长的任务都塞到提交前
- 对个人仓库和小团队仓库来说，先保证“少而稳”的检查，再逐步加项

#### 官方链接

- <https://pre-commit.com/>

### 3.3 Husky

#### 是什么

Husky 是 JavaScript / Node.js 生态里常见的 Git Hook 管理工具，常与 lint-staged、commitlint 等工具组合使用。

#### 适合谁

- 前端仓库
- Node.js / JavaScript / TypeScript 项目

#### 安装方式

按 Husky 官方文档通过 `npm`、`pnpm`、`yarn` 或 `bun` 安装，再用 `husky init` 完成基础初始化。

#### 常见用途

- 在 `pre-commit` 运行格式化和 lint
- 在 `commit-msg` 校验提交信息

#### 注意点

- 更偏向 JS 生态，不适合作为所有语言项目的默认方案
- 如果仓库不是 Node.js 生态，`pre-commit` 往往更通用

#### 官方链接

- <https://typicode.github.io/husky/>

### 3.4 自动化落地建议

对个人项目和小型协作，推荐按下面顺序引入自动化：

1. 先建立最小 `pre-commit` 或 Husky 检查
2. 再补提交信息校验
3. 最后再考虑更重的推送前检查

建议优先自动化的检查：

- 代码格式化
- lint
- 快速单元测试
- 提交信息格式校验
- 简单敏感信息扫描

### 3.5 Hook 与 CI 的边界

这一点很重要：

- 本地 Hook 更适合做快速反馈，例如格式化、lint、轻量测试和提交信息校验
- CI 更适合做更重、更完整、更统一的兜底检查

不要把所有检查都塞进本地 Hook，也不要把本地 Hook 省掉后完全指望 CI。更稳妥的做法通常是：

- 本地先挡住高频低级错误
- CI 再做更完整的最终校验

这也和 Part 3 的“提交前先自检，再进入共享历史”的原则是一致的。

## 4. 大文件与敏感信息防护

### 4.1 Git LFS

#### 是什么

Git LFS 是 Git Large File Storage，用来把大文件用指针方式纳入 Git 工作流，而不是直接把大体积二进制内容塞进普通 Git 对象历史。

#### 适合谁

- 需要管理模型文件、设计资源、媒体文件或大型二进制产物的人

#### 安装方式

按 Git LFS 官方说明安装后，在本机执行一次 `git lfs install`，再按文件类型决定是否纳入 LFS 跟踪。

#### 优点

- 减少普通 Git 历史被大文件拖垮
- 更适合管理持续演化的大型二进制资源

#### 注意点

- 不是所有大文件都应该进 Git；有些产物更适合交给制品仓库或对象存储
- 一旦历史里已经塞进大量大文件，再切到 LFS，治理成本会更高

#### 官方链接

- <https://git-lfs.com/>
- <https://github.com/git-lfs/git-lfs>

### 4.2 git-secrets

#### 是什么

`git-secrets` 是 AWS Labs 开源的工具，用来防止把常见敏感信息提交进 Git 仓库。

#### 适合谁

- 需要提前拦截密钥、令牌、凭据类误提交的人

#### 安装方式

按官方仓库说明安装后，再把检测规则和 Hook 入口接到你的仓库流程里。

#### 优点

- 目标明确
- 很适合和 Hook 组合

#### 注意点

- 它不是“装了就万无一失”的安全方案
- 规则库需要按项目场景持续维护

#### 官方链接

- <https://github.com/awslabs/git-secrets>

### 4.3 Gitleaks

#### 是什么

Gitleaks 是一个用于检测 Git 仓库、提交和文件中敏感信息泄露的工具。

#### 适合谁

- 想在提交前、本地扫描或 CI 中做密钥泄露检查的人

#### 安装方式

按官方文档或官方仓库安装后，可先从本地扫描开始，再视需要接入 CI。

#### 优点

- 既可本地使用，也适合接入 CI
- 适合对仓库历史和当前内容做扫描

#### 注意点

- 扫描规则需要结合项目实际调整
- 误报和漏报都可能存在，不能替代凭据管理制度

#### 官方链接

- <https://github.com/gitleaks/gitleaks>
- <https://gitleaks.io/>

### 4.4 环境变量与安全边界

在个人项目里，真正高频且最值得长期坚持的安全习惯通常是下面这些：

- `.env`、`.env.local`、证书、私钥默认不提交
- 先用 `.gitignore` 建立边界，再用检测工具兜底
- 真正敏感的生产凭据不放进示例配置
- 一旦误提交，先旋转凭据，再处理历史

不要把“已经接了扫描工具”理解成可以放松敏感信息管理。

## 5. 高频技巧

### 5.1 让 `git status` 成为第一排障入口

遇到 Git 问题时，优先先看：

```bash
git status -sb
```

它常常能最快回答这些问题：

- 当前在哪条分支
- 工作区是否干净
- 有没有 staged 但未提交的内容
- 是否落后于远程
- 当前是否处于 merge / rebase / cherry-pick 之中

### 5.2 用图形化日志快速建立上下文

```bash
git log --oneline --graph --decorate --all
```

适用环境：Bash / Git Bash / PowerShell

适合排查：

- 分支是从哪里分出来的
- 某次合并是怎么发生的
- 当前仓库的历史结构是否符合预期

### 5.3 用 `git diff --cached` 代替“盲提交”

```bash
git diff --cached
```

在提交前看一眼暂存区 diff，能大幅减少这几类问题：

- 顺手把无关改动也提了
- 漏加文件
- 临时调试代码忘删
- 敏感信息误带入提交

### 5.4 删除已合并分支前先选安全动作

```bash
git branch -d feature/auth-login
```

适用环境：Bash / Git Bash / PowerShell

建议默认优先使用更安全的删除方式，而不是一上来就强制删除。

### 5.5 远程分支同步后清理无效引用

```bash
git fetch --prune
```

适用环境：Bash / Git Bash / PowerShell

这类动作有两个实际收益：

- 远程分支列表更干净
- 减少“分支早删了但本地还挂着引用”的混乱感

### 5.6 `cherry-pick` 适合拿单个修复，不适合替代正常合并

`cherry-pick` 很适合这些场景：

- 把某个热修复补回开发分支
- 把一个独立且明确的修复迁移到另一个维护分支

但不要把它当成长期协作的主路径。频繁 `cherry-pick` 容易让历史关系越来越难读。

## 6. 扩展资源

### 6.1 官方资料优先

- [Git Documentation](https://git-scm.com/doc)
- [Pro Git](https://git-scm.com/book)
- [Learn Git Branching](https://learngitbranching.js.org/)

### 6.2 工具官方资料

- [GitHub Desktop Docs](https://docs.github.com/desktop)
- [Sourcetree Support](https://support.atlassian.com/sourcetree/)
- [GitKraken Help](https://help.gitkraken.com/)
- [VS Code Source Control Docs](https://code.visualstudio.com/docs/sourcecontrol/overview)
- [GitLens Docs](https://help.gitkraken.com/gitlens/gitlens-home/)
- [GitHub CLI Manual](https://cli.github.com/manual/)
- [pre-commit Docs](https://pre-commit.com/)
- [Husky Docs](https://typicode.github.io/husky/)
- [Git LFS](https://git-lfs.com/)
- [git-secrets](https://github.com/awslabs/git-secrets)
- [Gitleaks](https://gitleaks.io/)

### 6.3 阅读建议

如果你刚开始补齐 Part 4，建议按下面顺序阅读：

1. 先看 GUI / IDE 工具，选一套高频入口
2. 再看命令行增强工具，缩短高频操作路径
3. 接着看自动化和敏感信息防护，建立长期可维护的底线
4. 最后把高频技巧固化成自己的日常工作流

### 6.4 与其他 Part 的联动

- 如果你正在补 Git 基础认知，优先回到 Part 1
- 如果你看到这里的某个命令但不熟悉参数，优先回到 Part 2
- 如果你准备把 Hook、提交前检查、敏感信息边界固化成团队习惯，优先结合 Part 3 一起看

## 当前状态

- 当前已完成 Part 4 全量初稿
- 当前已纳入 GitLens，并将其作为 VS Code 场景下的重要增强工具
- 后续重点转向跨文档术语统一、工具取舍复审和来源持续校验
