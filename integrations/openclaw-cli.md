# OpenClaw CLI

## 作用

`openclaw` 是 ABME 的 agent 运行与运维入口：管理 agent、workspace、skills、会话、网关和配置。日常运行中的工具调用由 OpenClaw 承接；CLI 用于诊断、初始化和明确授权的维护操作。

## 使用边界

- 先读取当前状态和配置，再修改；不要用整份配置覆盖局部设置。
- 网关重启、配置变更和外部发送属于有影响操作，需要明确授权和变更审阅。
- agent workspace 保存私有工作状态；公开仓库只同步可复用的工程版本。
- 可复用的 skill、agent 规则和集成接入方式发生变更时，按 `docs/public-sync.md` 同步。
