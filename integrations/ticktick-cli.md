# TickTick CLI

## 作用

`ticktick` 是 ABME 的任务执行接口。它不保存长期认知和项目判断；它把已经明确的行动、提醒、检查清单和状态变成可跟踪任务。

## 已验证能力

- OAuth 登录与本机令牌存储。
- 创建、查询、更新、完成、移动和删除任务。
- 管理项目、项目组、看板列、标签、习惯和专注记录。

## 常用流程

```bash
ticktick auth status
ticktick project list
ticktick task create --help
ticktick task filter --help
ticktick task complete <project-id> <task-id>
```

先用 `--help` 查看当前 CLI 版本的字段，再创建任务；不要把真实项目 ID、任务标题、个人日程或访问令牌写入公开文档。

## 与思源的分工

- 思源：目标、上下文、判断、项目材料、复盘与稳定结论。
- TickTick：下一步动作、截止时间、提醒、执行状态和检查清单。
- 回写：任务完成或阻塞后，把结果、证据和新的判断回写到对应的思源资产，而不是只留在任务工具里。
