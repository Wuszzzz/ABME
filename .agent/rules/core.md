---
alwaysApply: true
---
# 回答尽量是中文回答

# 规范
## 流程图设计规范参考

## 思源笔记接入规范
- 思源笔记相关读取、检索、创建、更新，默认通过 `siyuan-sisyphus` CLI 执行，不默认依赖 MCP。
- 默认使用当前已初始化的 profile：`siyuan`。
- 默认配置路径：`/Users/Apple/.siyuan-sisyphus/config.json`。
- 常用读取命令优先使用：
  - `siyuan-sisyphus notebook list`
  - `siyuan-sisyphus search fulltext --query "<关键词>" --json`
  - `siyuan-sisyphus document list-tree --notebook <notebook-id> --json`
- 常用写入命令优先使用：
  - `siyuan-sisyphus document create --notebook <id> --path "<path>" --markdown "<content>"`
  - `siyuan-sisyphus block append --parent-id <id> --data-type markdown --data "<content>"`
  - `siyuan-sisyphus block update --id <id> --data-type markdown --data "<content>"`
- 只有在 `siyuan-sisyphus` CLI 无法覆盖目标操作时，才允许退回到其他接入方式。
- 涉及时间时，优先直接用本机北京时间，不再依赖思源时间 MCP。

# 做事方法
## 我们每次交流，你需要深度了解我的目的，我要是实现的效果，然后再一起考虑解决方案

## 项目定位
- `abme` 是 agent 调试工作台，不是一个先做 MVP 的终端产品原型。
- 思源是资源层和知识真源，飞书中的各角色 agent 是运行层。
- 当任务涉及提示词调试、工作流联调、运行复盘时，默认把结果沉淀到思源 `11-Agent Debug`，稳定后再升级到 `00-Core`、`01-Profile` 或 `20-Knowledge`。

## 人格与调教
- `J.A.R.V.I.S.` 与各主合伙人不应只有职责边界，还应有稳定人格特征、表达风格、判断偏好与升级边界。
- 人格不是文学设定，而是可执行行为约束。至少要明确：`定位`、`气质`、`判断方式`、`沟通风格`、`禁做事项`、`可调参数`。
- 所有人格调整都必须可被记录和复盘。调试中的人格变化先进思源 `11-Agent Debug`，稳定后再升级到思源 `00-Core`。
- 如果用户要求“赋予灵魂”或“可以被调教”，默认落到“人格参数化 + 调试记录 + 升级规则”三件事，而不是只改几句提示词修辞。

## 会话记录
- `abme` 仓库允许保留结构化会话纪要，但不保存无整理原始聊天流水。
- 默认记录位置是仓库内 `docs/session-notes/`，用于保存：会话背景、关键决策、争议点、已落地动作、下一步。
- 同步到思源时，调试性内容优先进入 `11-Agent Debug`；稳定结论再进入 `00-Core`、`01-Profile`、`20-Knowledge`。

## GitHub 同步
- `abme` 仓库应保持随时可初始化为 git 仓库并推送到 GitHub 的状态。
- 进入 GitHub 的内容应以可复用规则、结构文档、模板和方法为主，不提交明显敏感或无整理临时数据。
- 当用户要求“持续更新 GitHub 项目”时，默认理解为：本地修改应可被提交、追踪、回滚和推送，而不是只在本地堆文档。
