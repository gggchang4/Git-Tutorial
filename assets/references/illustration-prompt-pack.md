# Illustration Prompt Pack

本文件用于沉淀仓库内各章节配图所需的 AI 图例 prompt，目标是让 README 与四个 Part 后续补图时保持统一视觉方向、统一命名和统一交付标准。

## 使用方式

- 先复制“全局风格前缀”和“负面提示词”
- 再选择对应章节的“落地版 prompt”
- 生成前根据目标用途补上比例字段，例如 `16:9`、`4:3`、`3:2`
- 如果是 SVG 风格插图，优先要求模型输出“vector illustration / clean infographic / minimal text”
- 如果是终端或工具示意图，优先强调“documentation-style / structured layout / callout labels / technical diagram”

## 全局风格前缀

```text
极简技术信息图风格，clean vector illustration, documentation-style, Git learning handbook visual, light background, high contrast, Git orange + blue + green accent colors, terminal window elements, branch graph, commit nodes, arrows, modern flat isometric composition, structured layout, SVG-friendly, no long text, no watermark, no photo, no 3D realism
```

## 统一补充约束

```text
precise hierarchy, editorial tech infographic, generous whitespace, clean callout cards, subtle shadows only, simplified UI framing, minimal labels, readable flow direction, consistent icon system, suitable for open-source documentation, export-friendly composition
```

## 可选负面提示词

```text
low detail, photorealistic, messy layout, too much text, watermark, logo clutter, blurry, dark background, fantasy style, human faces, stock photo
```

## 推荐比例

| 用途 | 推荐比例 | 说明 |
|------|------|------|
| README 总览图 / 横向流程图 | `16:9` | 适合首页、章节大图、四段式对比 |
| 命令关系图 / 技术索引图 | `4:3` | 适合文档内嵌、结构更紧凑 |
| SOP 海报 / 规范看板 | `3:2` | 适合多卡片、多阶段流程 |
| 终端示意 / 工具面板组合图 | `16:10` | 适合横向排布多个模块 |

## 落地版 Prompt 清单

### README / 总览

**文件名：** `readme-parts-overview.svg`

```text
极简技术信息图风格，clean vector illustration, documentation-style, Git learning handbook visual, light background, high contrast, Git orange + blue + green accent colors, terminal window elements, branch graph, commit nodes, arrows, modern flat isometric composition, structured layout, SVG-friendly, no long text, no watermark, no photo, no 3D realism, precise hierarchy, editorial tech infographic, generous whitespace, clean callout cards, simplified UI framing, minimal labels, readable flow direction, suitable for open-source documentation, 16:9 overview illustration, four-part handbook overview, show Part 1 learning path, Part 2 command reference, Part 3 workflow norms, Part 4 tooling and automation, connected by arrows and Git graph motifs, landing-page quality, balanced composition
```

### Part 1

**文件名：** `part1-git-setup-overview.svg`

```text
极简技术信息图风格，clean vector illustration, documentation-style, Git learning handbook visual, light background, high contrast, Git orange + blue + green accent colors, terminal window elements, branch graph, commit nodes, arrows, modern flat isometric composition, structured layout, SVG-friendly, no long text, no watermark, no photo, no 3D realism, precise hierarchy, editorial tech infographic, generous whitespace, 16:9 illustration for Git setup and installation, show developer laptop, terminal initialization, username and email config, SSH key setup, local repository, remote repository, working directory, staging area, repository relationship overview, beginner-friendly onboarding mood
```

**文件名：** `part1-local-workflow-flow.svg`

```text
极简技术信息图风格， clean vector illustration, documentation-style, Git learning handbook visual, light background, high contrast, Git orange + blue + green accent colors, terminal window elements, branch graph, commit nodes, arrows, modern flat isometric composition, structured layout, SVG-friendly, no long text, no watermark, no photo, no 3D realism, 16:9 local repository workflow diagram, show working tree, staging area, local repository, file changes flowing through edit, add, commit, status comparison, clear arrows, beginner-friendly commit loop, simple terminal panels and file cards
```

**文件名：** `part1-remote-sync-flow.svg`

```text
极简技术信息图风格， clean vector illustration, documentation-style, Git learning handbook visual, light background, high contrast, Git orange + blue + green accent colors, terminal window elements, branch graph, commit nodes, arrows, modern flat isometric composition, structured layout, SVG-friendly, no long text, no watermark, no photo, no 3D realism, 16:9 remote collaboration flow, show local repository and GitHub remote repository, fetch, pull, push paths, origin and main relationship, ahead and behind indicators, sync checkpoints, emphasize collaboration entry point and safe synchronization
```

**文件名：** `part1-branch-collaboration-flow.svg`

```text
极简技术信息图风格， clean vector illustration, documentation-style, Git learning handbook visual, light background, high contrast, Git orange + blue + green accent colors, terminal window elements, branch graph, commit nodes, arrows, modern flat isometric composition, structured layout, SVG-friendly, no long text, no watermark, no photo, no 3D realism, 16:9 branch management infographic, parallel main develop and feature branches, branch creation switching merge and rebase comparison, clean Git graph structure, collaboration rhythm, multiple timelines with clear merge points
```

**文件名：** `part1-recover-decision-map.svg`

```text
极简技术信息图风格， clean vector illustration, documentation-style, Git learning handbook visual, light background, high contrast, Git orange + blue + green accent colors, terminal window elements, branch graph, commit nodes, arrows, modern flat isometric composition, structured layout, SVG-friendly, no long text, no watermark, no photo, no 3D realism, 4:3 recovery decision map, compare git reset, restore, revert, reflog, show working tree staging area history timeline, safe recovery concept, visual distinction between file restore commit rollback and history recovery
```

**文件名：** `part1-conflict-resolution-flow.svg`

```text
极简技术信息图风格， clean vector illustration, documentation-style, Git learning handbook visual, light background, high contrast, Git orange + blue + green accent colors, terminal window elements, branch graph, commit nodes, arrows, modern flat isometric composition, structured layout, SVG-friendly, no long text, no watermark, no photo, no 3D realism, 16:9 merge conflict resolution diagram, two branches edit same file then conflict, conflict markers, side-by-side code window, terminal warning, manual resolution, retest and commit, emphasize diagnosis and resolution flow
```

**文件名：** `part1-release-tag-overview.svg`

```text
极简技术信息图风格， clean vector illustration, documentation-style, Git learning handbook visual, light background, high contrast, Git orange + blue + green accent colors, terminal window elements, branch graph, commit nodes, arrows, modern flat isometric composition, structured layout, SVG-friendly, no long text, no watermark, no photo, no 3D realism, 16:9 release and tag overview, commit graph with version milestones v1.0.0 v1.1.0 v2.0.0, tag markers, release checkpoints, snapshot concept, simple timeline with highlighted version nodes
```

**文件名：** `part1-git-internals-overview.svg`

```text
极简技术信息图风格， clean vector illustration, documentation-style, Git learning handbook visual, light background, high contrast, Git orange + blue + green accent colors, terminal window elements, branch graph, commit nodes, arrows, modern flat isometric composition, structured layout, SVG-friendly, no long text, no watermark, no photo, no 3D realism, 4:3 Git internals architecture diagram, show blob tree commit HEAD branch pointers and references, object model visualization, clean technical structure, emphasize pointer movement and repository internals
```

**文件名：** `part1-troubleshooting-overview.svg`

```text
极简技术信息图风格， clean vector illustration, documentation-style, Git learning handbook visual, light background, high contrast, Git orange + blue + green accent colors, terminal window elements, branch graph, commit nodes, arrows, modern flat isometric composition, structured layout, SVG-friendly, no long text, no watermark, no photo, no 3D realism, 16:9 troubleshooting dashboard, show detached HEAD, push rejected, merge conflict, wrong branch, untracked files, issue cards connected to diagnosis path, summary board for common Git problems
```

### Part 2

**文件名：** `part2-local-command-map.svg`

```text
极简技术信息图风格， clean vector illustration, documentation-style, Git learning handbook visual, light background, high contrast, Git orange + blue + green accent colors, terminal window elements, branch graph, commit nodes, arrows, modern flat isometric composition, structured layout, SVG-friendly, no long text, no watermark, no photo, no 3D realism, 4:3 command map infographic, local repository commands git init add commit status diff log rm mv, command relationships centered on modify stage commit inspect workflow, fast-reference style
```

**文件名：** `part2-remote-command-map.svg`

```text
极简技术信息图风格， clean vector illustration, documentation-style, Git learning handbook visual, light background, high contrast, Git orange + blue + green accent colors, terminal window elements, branch graph, commit nodes, arrows, modern flat isometric composition, structured layout, SVG-friendly, no long text, no watermark, no photo, no 3D realism, 4:3 remote command map, git clone remote fetch pull push fetch prune, local versus remote synchronization routes, clear node grouping, fast lookup layout for documentation
```

**文件名：** `part2-branch-merge-command-map.svg`

```text
极简技术信息图风格， clean vector illustration, documentation-style, Git learning handbook visual, light background, high contrast, Git orange + blue + green accent colors, terminal window elements, branch graph, commit nodes, arrows, modern flat isometric composition, structured layout, SVG-friendly, no long text, no watermark, no photo, no 3D realism, 4:3 branch and merge command map, git branch switch checkout merge rebase stash cherry-pick, semantic differences between commands, flow-oriented Git graph with categorized callouts
```

**文件名：** `part2-recovery-command-map.svg`

```text
极简技术信息图风格， clean vector illustration, documentation-style, Git learning handbook visual, light background, high contrast, Git orange + blue + green accent colors, terminal window elements, branch graph, commit nodes, arrows, modern flat isometric composition, structured layout, SVG-friendly, no long text, no watermark, no photo, no 3D realism, 4:3 recovery cheat sheet, git reset revert restore reflog commit amend, decision map showing impact on working tree staging area and history, regret medicine map for Git users
```

**文件名：** `part2-tag-release-command-map.svg`

```text
极简技术信息图风格， clean vector illustration, documentation-style, Git learning handbook visual, light background, high contrast, Git orange + blue + green accent colors, terminal window elements, branch graph, commit nodes, arrows, modern flat isometric composition, structured layout, SVG-friendly, no long text, no watermark, no photo, no 3D realism, 4:3 tag and release command map, git tag fetch tags push origin tag delete tag, release milestone flow, emphasize tag as version marker in publishing workflow
```

**文件名：** `part2-inspect-config-command-map.svg`

```text
极简技术信息图风格， clean vector illustration, documentation-style, Git learning handbook visual, light background, high contrast, Git orange + blue + green accent colors, terminal window elements, branch graph, commit nodes, arrows, modern flat isometric composition, structured layout, SVG-friendly, no long text, no watermark, no photo, no 3D realism, 4:3 inspection tools index, git config show blame help, grouped as inspect configuration inspect history inspect ownership and documentation lookup, utility index poster
```

### Part 3

**文件名：** `part3-branch-policy-overview.svg`

```text
极简技术信息图风格， clean vector illustration, documentation-style, Git learning handbook visual, light background, high contrast, Git orange + blue + green accent colors, terminal window elements, branch graph, commit nodes, arrows, modern flat isometric composition, structured layout, SVG-friendly, no long text, no watermark, no photo, no 3D realism, 3:2 branch policy poster, main develop feature release hotfix with clear responsibilities and lifecycle boundaries, handbook-style governance board, strong hierarchy and readable role distinction
```

**文件名：** `part3-commit-guideline-overview.svg`

```text
极简技术信息图风格， clean vector illustration, documentation-style, Git learning handbook visual, light background, high contrast, Git orange + blue + green accent colors, terminal window elements, branch graph, commit nodes, arrows, modern flat isometric composition, structured layout, SVG-friendly, no long text, no watermark, no photo, no 3D realism, 3:2 commit guideline poster, structured commit message, one change per commit, inspect diff before commit, terminal panel with checklist cards, show good commit habits
```

**文件名：** `part3-solo-workflow-map.svg`

```text
极简技术信息图风格， clean vector illustration, documentation-style, Git learning handbook visual, light background, high contrast, Git orange + blue + green accent colors, terminal window elements, branch graph, commit nodes, arrows, modern flat isometric composition, structured layout, SVG-friendly, no long text, no watermark, no photo, no 3D realism, 16:9 solo developer Git workflow map, create branch from main or develop, code, commit, self-check, merge, release, closed-loop structure, personal productivity diagram
```

**文件名：** `part3-personal-sop-board.svg`

```text
极简技术信息图风格， clean vector illustration, documentation-style, Git learning handbook visual, light background, high contrast, Git orange + blue + green accent colors, terminal window elements, branch graph, commit nodes, arrows, modern flat isometric composition, structured layout, SVG-friendly, no long text, no watermark, no photo, no 3D realism, 3:2 personal development SOP board, phased cards for initialization daily development sync release hotfix, clear stage gates inputs outputs and checks, clean procedural poster
```

**文件名：** `part3-small-team-sop-board.svg`

```text
极简技术信息图风格， clean vector illustration, documentation-style, Git learning handbook visual, light background, high contrast, Git orange + blue + green accent colors, terminal window elements, branch graph, commit nodes, arrows, modern flat isometric composition, structured layout, SVG-friendly, no long text, no watermark, no photo, no 3D realism, 3:2 small team SOP board for 2 to 5 developers, task branch PR review merge regression verification, collaboration rhythm and responsibility boundaries, quality gate focused workflow
```

**文件名：** `part3-company-team-sop-board.svg`

```text
极简技术信息图风格， clean vector illustration, documentation-style, Git learning handbook visual, light background, high contrast, Git orange + blue + green accent colors, terminal window elements, branch graph, commit nodes, arrows, modern flat isometric composition, structured layout, SVG-friendly, no long text, no watermark, no photo, no 3D realism, 16:9 enterprise delivery workflow, requirement intake task branch development self-test code review CI release rollback plan, structured software delivery pipeline, formal company-grade process diagram
```

**文件名：** `part3-conflict-policy-flow.svg`

```text
极简技术信息图风格， clean vector illustration, documentation-style, Git learning handbook visual, light background, high contrast, Git orange + blue + green accent colors, terminal window elements, branch graph, commit nodes, arrows, modern flat isometric composition, structured layout, SVG-friendly, no long text, no watermark, no photo, no 3D realism, 16:9 conflict handling policy diagram, prevention detection resolution verification submit, emphasize sync first resolve second validate third, handbook-style standard process
```

**文件名：** `part3-supporting-policy-panel.svg`

```text
极简技术信息图风格， clean vector illustration, documentation-style, Git learning handbook visual, light background, high contrast, Git orange + blue + green accent colors, terminal window elements, branch graph, commit nodes, arrows, modern flat isometric composition, structured layout, SVG-friendly, no long text, no watermark, no photo, no 3D realism, 3:2 supporting policy ecosystem panel, show gitignore tag strategy release conventions repository layout sensitive data boundaries, policy dashboard with modular cards
```

**文件名：** `part3-lightweight-collab-flow.svg`

```text
极简技术信息图风格， clean vector illustration, documentation-style, Git learning handbook visual, light background, high contrast, Git orange + blue + green accent colors, terminal window elements, branch graph, commit nodes, arrows, modern flat isometric composition, structured layout, SVG-friendly, no long text, no watermark, no photo, no 3D realism, 16:9 lightweight collaboration flow, issue to branch to commit to PR to review to merge, low-cost but disciplined team workflow, clear and minimal collaboration diagram
```

### Part 4

**文件名：** `part4-gui-tooling-overview.svg`

```text
极简技术信息图风格， clean vector illustration, documentation-style, Git learning handbook visual, light background, high contrast, Git orange + blue + green accent colors, terminal window elements, branch graph, commit nodes, arrows, modern flat isometric composition, structured layout, SVG-friendly, no long text, no watermark, no photo, no 3D realism, 16:10 GUI and IDE tooling overview, show GitHub Desktop Sourcetree GitKraken VS Code Source Control GitLens as clean framed interface panels, emphasize visual Git history and status management
```

**文件名：** `part4-cli-enhancement-overview.svg`

```text
极简技术信息图风格， clean vector illustration, documentation-style, Git learning handbook visual, light background, high contrast, Git orange + blue + green accent colors, terminal window elements, branch graph, commit nodes, arrows, modern flat isometric composition, structured layout, SVG-friendly, no long text, no watermark, no photo, no 3D realism, 16:10 CLI productivity overview, show git alias gh and lazygit, terminal panels with shortcuts PR operations branch switching quick history inspection, productivity-focused command line dashboard
```

**文件名：** `part4-automation-chain-overview.svg`

```text
极简技术信息图风格， clean vector illustration, documentation-style, Git learning handbook visual, light background, high contrast, Git orange + blue + green accent colors, terminal window elements, branch graph, commit nodes, arrows, modern flat isometric composition, structured layout, SVG-friendly, no long text, no watermark, no photo, no 3D realism, 16:9 automation chain diagram, hooks pre-commit husky CI checks from file save to commit to pipeline, automated quality gate concept, structured step-by-step validation flow
```

**文件名：** `part4-lfs-secrets-security-overview.svg`

```text
极简技术信息图风格， clean vector illustration, documentation-style, Git learning handbook visual, light background, high contrast, Git orange + blue + green accent colors, terminal window elements, branch graph, commit nodes, arrows, modern flat isometric composition, structured layout, SVG-friendly, no long text, no watermark, no photo, no 3D realism, 16:9 security and large-file protection infographic, show Git LFS git-secrets gitleaks, file size risk secret leakage risk pre-commit scanning and policy shields, clean documentation security board
```

**文件名：** `part4-high-frequency-tips-overview.svg`

```text
极简技术信息图风格， clean vector illustration, documentation-style, Git learning handbook visual, light background, high contrast, Git orange + blue + green accent colors, terminal window elements, branch graph, commit nodes, arrows, modern flat isometric composition, structured layout, SVG-friendly, no long text, no watermark, no photo, no 3D realism, 16:10 high-frequency Git tips board, git status git log graph git diff cached prune stale remotes quick inspect recent commits, cheat sheet style technical illustration
```

**文件名：** `part4-resource-map-overview.svg`

```text
极简技术信息图风格， clean vector illustration, documentation-style, Git learning handbook visual, light background, high contrast, Git orange + blue + green accent colors, terminal window elements, branch graph, commit nodes, arrows, modern flat isometric composition, structured layout, SVG-friendly, no long text, no watermark, no photo, no 3D realism, 16:9 resource network map, official docs graphical tools CLI tools workflow norms learning paths connected as knowledge network, chapter-ending navigation illustration
```

## 建议交付顺序

1. 先生成 `readme-parts-overview.svg` 与 Part 1 的 3 张基础总览图，优先增强首页和学习入口。
2. 再生成 Part 3 的 SOP 看板类插图，补强项目的“规范感”和“可执行感”。
3. 最后补齐 Part 2 命令地图和 Part 4 工具图，形成完整的图文资产闭环。
