# 思源接入规范

## 1. 原则

- 思源访问默认走 `siyuan-sisyphus` CLI
- 默认 profile：`siyuan`
- 配置文件：`/Users/Apple/.siyuan-sisyphus/config.json`
- 只有 CLI 无法覆盖时，才允许退回到更底层 API

## 2. 角色定位

思源是资源层，不是临时缓存。

当前服务两个调用层：

- `abme` 调试工作台
- 飞书角色 agent 运行层

## 3. ABME 的思源权限

`abme` 默认拥有最高读写权限，用于：

- 读取规则和上下文
- 创建调试项目和调试记录
- 升级稳定规则
- 整理知识结构

默认写入优先级：

1. `11-Agent Debug`
2. `00-Core`
3. `01-Profile`
4. `20-Knowledge`
5. `50-Outputs`

## 4. 飞书角色 Agent 的思源权限

飞书角色 agent 不应独立维护一套知识库。

默认规则：

- 以读取为主
- 写入以运行摘要、项目反馈、复盘记录为主
- 不直接把聊天内容塞进 `00-Core`

## 5. 推荐命令

读取与检索：

```bash
siyuan-sisyphus notebook list
siyuan-sisyphus search fulltext --query "关键词" --json
siyuan-sisyphus document list-tree --notebook <notebook-id> --path / --json
siyuan-sisyphus document lookup --notebook <notebook-id> --hpath "/路径"
```

创建与更新：

```bash
siyuan-sisyphus document create --notebook <id> --path "/目标路径" --markdown "# 标题"
siyuan-sisyphus block append --parent-id <id> --data-type markdown --data "- 新内容"
siyuan-sisyphus block update --id <block-id> --data-type markdown --data "更新内容"
```

## 6. 调试工程写入规则

当内容属于以下情况时，默认写到 `Agent 调试工程`：

- 提示词调试过程
- 工作流联调过程
- 飞书层异常和复盘
- 待确认的改动结论

只有在结论已经稳定之后，才升级到规则层或知识层。
