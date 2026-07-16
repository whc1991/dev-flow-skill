# dev-flow

`dev-flow` 是一个面向用户主导、串行开发场景的 Codex Skill。需求和当前开发单元明确后，通过简短指令启动编码，并将实现严格限制在当前功能点或 PR 内。

## 主要约束

- 开发前必须确认当前 Git 分支，未经确认不修改文件。
- 一次只开发一个功能点或 PR，不提前处理后续单元。
- 不创建或切换分支，不自动提交、推送或创建远程 PR。
- 不编写设计文档，不使用 `superpowers`。
- 数据库设计遵循项目规范，表、字段和码值必须具有完整中文注释。
- 可以生成 SQL 或迁移文件，但执行数据库变更前必须获得用户授权。
- 完成后只运行聚焦测试，并生成一条 `feat:` 中文提交语句。

## 安装

将仓库克隆到 Codex 的个人 Skill 目录：

```bash
mkdir -p "${CODEX_HOME:-$HOME/.codex}/skills"
git clone https://github.com/<你的用户名>/dev-flow.git "${CODEX_HOME:-$HOME/.codex}/skills/dev-flow"
```

将示例地址替换为实际 GitHub 仓库地址。安装后重新开启 Codex 会话。

## 使用

```text
$dev-flow PR4
$dev-flow 登录超时修复
```

版本号不是必填项；只有当前上下文无法唯一定位开发单元时，Codex 才会请求补充信息。
