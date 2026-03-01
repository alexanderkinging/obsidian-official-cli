# Obsidian Official CLI Skill

让 AI 助手通过 Obsidian 官方 CLI 管理你的笔记。

## 这是什么？

这个 skill 让 OpenClaw 能够：
- 📝 创建和编辑 Obsidian 笔记
- 📅 管理 Daily Notes（日记）
- 🔍 搜索笔记内容
- 🏷️ 查看标签和任务
- 📎 使用模板创建笔记

## 前置条件

⚠️ **需要 Obsidian Catalyst license**

1. Obsidian 1.12 或更高版本（Early Access）
2. Catalyst license（付费支持者）
3. macOS 系统

## 安装步骤

### 1. 启用 Obsidian CLI

1. 打开 Obsidian
2. 设置 → 通用 → 命令行界面
3. 启用并点击「注册到 PATH」
4. 重启终端

### 2. 安装 Skill

```bash
clawhub install obsidian-official-cli
```

### 3. 验证

```bash
obsidian help
```

## 使用示例

安装后，你可以这样和 AI 助手对话：

- "帮我创建一个会议记录笔记"
- "把这篇文章保存到 Obsidian"
- "搜索我笔记里关于 AI 的内容"
- "在今天的日记里添加一个待办事项"
- "列出我所有的标签"

## 与社区版的区别

ClawHub 上还有一个 `obsidian` skill（by steipete），使用的是社区版 CLI。

| | 本 Skill (官方 CLI) | obsidian (社区版) |
|---|---|---|
| Daily Notes | ✅ | ❌ |
| Tasks/Tags | ✅ | ❌ |
| Templates | ✅ | ❌ |
| 需要 Catalyst | ✅ | ❌ |
| 需要 Obsidian 运行 | ✅ | ❌ |

如果你没有 Catalyst license，请使用社区版。

## 文档

- [Obsidian CLI 官方文档](https://help.obsidian.md/cli)
- [Catalyst License](https://help.obsidian.md/catalyst)

## 作者

由 OpenClaw 社区创建。

## License

MIT
