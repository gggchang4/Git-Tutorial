# Assets

该目录用于集中存放项目素材资源，避免开发过程中的图片、截图、图表源文件和临时参考资料散落在仓库根目录。

## 目录职责

建议使用方式：

- `images/`：正式配图、封面、插画等图片素材
- `screenshots/`：命令执行截图、界面截图、演示截图
- `diagrams/`：流程图源文件、结构图、草图、导图
- `references/`：外部参考图片、临时整理素材、待筛选资源

如果后续素材类型继续增加，可以在该目录下按用途继续细分子目录。

## 命名与交付约定

- 文件名统一使用小写 ASCII、短横线分隔，不在 `assets/` 下混用中文文件名、空格和随意缩写
- 平台字段统一写作 `windows`、`macos`、`linux`、`cross-platform`
- 素材类型建议统一写作 `hero`、`overview`、`flow`、`decision`、`terminal`、`ui`、`compare`
- 流程阶段建议统一写作 `setup`、`develop`、`review`、`release`、`hotfix`、`recover`
- Mermaid 或结构图源文件优先使用 `*.mmd`、`*.md` 或可维护文本源；对外展示图优先导出为 `*.svg`
- 截图统一优先使用 `*.png`；只有确实需要保真照片或复杂渐变时再使用 `*.jpg`

推荐命名模板：

```text
part{n}-{topic}-{kind}-{platform}.{ext}
readme-{topic}-{kind}.{ext}
shared-{topic}-{kind}-{platform}.{ext}
```

示例：

```text
part1-branch-flow-cross-platform.mmd
part2-log-graph-terminal-cross-platform.png
part3-release-flow-cross-platform.svg
part4-gitlens-ui-macos.png
readme-parts-overview.svg
```

## Mermaid 图示规划

图示规划遵循“正文先内嵌 Mermaid，需复用或导出时再进入 `assets/diagrams/`”的原则，避免同一套图在多处失去同步。

| 优先级 | 所属位置 | 图示主题 | 目标用途 | 推荐命名 | 当前状态 |
|------|------|------|------|------|------|
| P0 | `README.md` | 四个 Part 的职责关系图 | 仓库首页快速导览 | `readme-parts-overview.svg` | 已完成 |
| P0 | `docs/Git个人使用规范.md` | 个人 / 小团队 / 公司团队三套 SOP 主流程图 | 规范流程可视化 | `part3-personal-flow-cross-platform.mmd` 等 | 已完成正文内嵌 Mermaid |
| P1 | `docs/Git学习手册.md` | 本地提交闭环、远程同步、分支合并 / rebase、冲突解决、回滚恢复 | 帮助学习者建立阶段感 | `part1-commit-loop-flow-cross-platform.mmd` | 已完成正文内嵌 Mermaid |
| P1 | `docs/Git Reference手册.md` | `add / commit / restore / reset` 关系图、远程同步关系图 | 强化速查命令关系 | `part2-history-command-map-cross-platform.mmd` | 已完成正文内嵌 Mermaid |
| P1 | `docs/Git实用拓展手册.md` | 工具选型决策图、钩子执行链、敏感信息防护流 | 帮助选型和接入 | `part4-tooling-decision-flow-cross-platform.mmd` | 已完成首批正文内嵌 Mermaid |
| P2 | `docs/Git个人使用规范.md` | 分支策略选型图、异常分流图 | 补充 SOP 外围决策场景 | `part3-branch-strategy-decision-cross-platform.mmd` | 待规划 |

## AI 图例 Prompt 清单

为避免后续补图时每次重新组织提示词，仓库内已新增一份可直接复用的章节级 prompt 清单：

- [Illustration Prompt Pack](./references/illustration-prompt-pack.md)

建议使用方式：

- 优先复用清单中的文件名映射，保证后续素材能直接落到约定路径
- 统一复用“全局风格前缀 + 统一补充约束 + 章节 prompt + 负面提示词”的组合
- README 总览图优先 `16:9`，命令关系图优先 `4:3`，SOP / 规范看板优先 `3:2`
- 章节配图尽量保持“少文字、强结构、强关系表达”，避免做成海报式装饰图
- 若图最终需要进 README 或正文，优先产出 SVG 风格的矢量插图

## 截图和图片素材清单

截图与图片素材按“先规划、后采集、统一脱敏”的方式维护，避免后续补图时出现尺寸、主题和信息暴露不一致。

统一要求：

- 截图前先清理用户名、邮箱、仓库地址、工单号、令牌、目录中的客户或公司信息
- 同一章节内尽量保持一致的终端主题、字号和窗口宽度
- 命令截图要同时保留“输入命令 + 关键输出”，不要只截结果不截上下文
- 同一动作如果 `Windows / macOS / Linux` 行为一致，优先保留一张 `cross-platform` 示例；只有差异明显时再拆平台图
- 说明型结构图优先 SVG，终端和界面截图优先 PNG

建议优先采集的素材：

| 优先级 | 所属位置 | 素材类型 | 目标内容 | 推荐命名 | 备注 |
|------|------|------|------|------|------|
| P0 | `README.md` | 图片 | 仓库首页展示图、目录总览图 | `readme-home-overview.png` | 用于开源展示和 README 更新 |
| P1 | `docs/Git学习手册.md` | 终端截图 | `git status`、`git add`、`git commit` 前后对照 | `part1-status-terminal-cross-platform.png` | 适合新手理解状态变化 |
| P1 | `docs/Git学习手册.md` | 终端截图 | 冲突标记、解决后提交、`git reflog` 恢复 | `part1-conflict-terminal-cross-platform.png` | 要保留关键上下文 |
| P1 | `docs/Git Reference手册.md` | 终端截图 | `git log --oneline --graph`、`git remote -v`、`git stash list` | `part2-log-graph-terminal-cross-platform.png` | 用于速查配图 |
| P1 | `docs/Git个人使用规范.md` | 图片 / 截图 | PR 自检清单、分支保护示意、发布前检查清单 | `part3-pr-checklist-overview.svg` | 优先做通用示意，不依赖内部平台 |
| P1 | `docs/Git实用拓展手册.md` | UI 截图 | VS Code Source Control、GitLens、GitHub Desktop 关键界面 | `part4-gitlens-ui-macos.png` 等 | 平台差异明显时可拆分 |
| P1 | `docs/Git实用拓展手册.md` | 终端截图 | `pre-commit` 执行结果、`gitleaks` 检测输出、`git lfs track` 示例 | `part4-pre-commit-terminal-cross-platform.png` | 需要完整脱敏 |
| P2 | `assets/references/` | 参考素材 | 公开官方页面截图、图标草图、待筛选图 | `shared-reference-git-lfs-home-20260411.png` | 仅作内部整理，不直接面向正文 |
