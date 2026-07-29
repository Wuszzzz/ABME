# Wxpub CLI

## 作用

`wxpub` 是公众号文章从 Markdown/模板到草稿箱的本地编译与连接器 CLI。它是对外输出的执行工具，不替代 ABME 对内容和发布权的判断。

## 已验证能力

- 检查、校验、渲染和预览文章。
- 管理主题、授权样式和模板组。
- 查询公众号连接状态。
- 创建、更新、读取和列出草稿；查询发布状态。

## 推荐流程

```bash
wxpub inspect <article-directory> --json
wxpub validate <article-directory> --json
wxpub preview <article-directory> --json
wxpub wechat status --json
wxpub wechat draft create <article-directory> --json
```

更新已存在草稿：

```bash
wxpub wechat draft update <media-id> <article-directory> --json
```

## 发布边界

- 文章正文、标题、封面和模板先经人工确认，再创建或更新草稿。
- 创建或更新草稿不等于发布。
- `draft publish` 是单独的外部动作，只在所有者明确批准后运行。
- 公众号凭据、授权资源、本机配置和草稿 ID 均属于私有运行数据，不进入本仓库。
