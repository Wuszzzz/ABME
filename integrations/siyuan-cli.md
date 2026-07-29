# SiYuan CLI

## 作用

`siyuan-sisyphus` 是 ABME 连接思源知识库的命令行接口。思源承担长期认知资产、项目材料和稳定规则；CLI 让 agent 能够检索、创建和回写这些资产。

## 已验证能力

- 列出笔记本、文档树和标签。
- 全文检索与结构化 JSON 输出。
- 创建文档、追加块、更新块。
- 管理资源、属性视图和闪卡等思源对象。

## 常用流程

```bash
siyuan-sisyphus notebook list --json
siyuan-sisyphus search fulltext --query "关键词" --page-size 10 --json
siyuan-sisyphus document create --notebook <notebook-id> --path "/项目/标题" --markdown "# 标题"
siyuan-sisyphus block append --parent-id <block-id> --data-type markdown --data "- 新结论"
```

## 使用边界

- 先检索既有材料，再创建或更新，避免重建已有结论。
- 调试过程优先进入调试区；稳定结论再升级到规则或知识区。
- 认证令牌只保存在本机私有配置、环境变量或受管凭据中；示例与仓库不提交令牌。
- 当 CLI 无法覆盖操作时，才退回到受控 API 或其他接入方式。
