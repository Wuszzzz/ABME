# ABME 项目结构与配置边界

## 1. 说明

当前 `abme` 重点不是实现一个完整运行时配置文件，而是先明确项目结构和配置边界。

也就是说，这里更关心：

- 哪些内容属于资源层
- 哪些内容属于调试层
- 哪些内容属于运行层

## 2. 逻辑配置结构

```yaml
resources:
  siyuan: {}

surfaces:
  abme: {}
  feishu_agents: {}

storage:
  docs: {}
  diagrams: {}
  records: {}

version: "2.0"
```

## 3. 字段语义

### resources.siyuan

- role: 资源层真源
- access_mode: `cli-first`
- profile: `siyuan`
- config_path: `/Users/Apple/.siyuan-sisyphus/config.json`
- default_write_project: `11-Agent Debug`

### surfaces.abme

- role: 本地调试工作台
- responsibilities:
  - 提示词调试
  - 工作流联调
  - 运行复盘
  - 规则升级
- permissions:
  - 读写思源核心文档
  - 修改仓库文档和规范

### surfaces.feishu_agents

- role: 前台运行层
- responsibilities:
  - 角色对话
  - 实际执行
  - 运行反馈
- permissions:
  - 优先读取规则和知识
  - 写入以运行摘要和项目反馈为主

### storage

- `docs/`：架构、规范、说明文档
- `diagrams/`：结构图、调用图
- `.agent/rules/`：项目内规则与方法约束
- `标准/siyuan/`：可复用的思源模板

## 4. 当前不再推荐的旧配置思路

下面这些思路已经不适合作为当前主叙事：

- 只读思源
- 读写滴答作为主链路
- 以 CLI MVP 为唯一目标

这些可以保留为后续自动化选项，但不再代表项目核心。
