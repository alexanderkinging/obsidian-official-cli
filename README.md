# Obsidian Official CLI Skill

Let your AI assistant manage Obsidian notes through the official CLI.

## What is this?

This skill enables OpenClaw to:
- 📝 Create and edit Obsidian notes
- 📅 Manage Daily Notes
- 🔍 Search note content
- 🏷️ View tags and tasks
- 📎 Create notes from templates

## Prerequisites

⚠️ **Requires Obsidian Catalyst license**

1. Obsidian 1.12 or higher (Early Access)
2. Catalyst license (paid supporter)
3. macOS system

## Installation

### 1. Enable Obsidian CLI

1. Open Obsidian
2. Settings → General → Command line interface
3. Enable and click "Register to PATH"
4. Restart terminal

### 2. Install Skill

```bash
clawhub install obsidian-catalyst-cli
```

### 3. Verify

```bash
obsidian help
```

## Usage Examples

After installation, you can talk to your AI assistant like:

- "Create a meeting notes"
- "Save this article to Obsidian"
- "Search my notes about AI"
- "Add a todo to today's daily note"
- "List all my tags"

## vs Community Version

There's another `obsidian` skill on ClawHub (by steipete) using community CLI.

| | This Skill (Official) | obsidian (Community) |
|---|---|---|
| Daily Notes | ✅ | ❌ |
| Tasks/Tags | ✅ | ❌ |
| Templates | ✅ | ❌ |
| Requires Catalyst | ✅ | ❌ |
| Requires Obsidian running | ✅ | ❌ |

If you don't have Catalyst license, use the community version.

## Documentation

- [Obsidian CLI Official Docs](https://help.obsidian.md/cli)
- [Catalyst License](https://help.obsidian.md/catalyst)

## Author

Created by OpenClaw community.

## License

MIT

---

## 中文说明

让 AI 助手通过 Obsidian 官方 CLI 管理你的笔记。

**功能**：
- 📝 创建和编辑笔记
- 📅 管理 Daily Notes（日记）
- 🔍 搜索笔记内容
- 🏷️ 查看标签和任务
- 📎 使用模板创建笔记

**前置条件**：
- Obsidian 1.12+ (Early Access)
- Catalyst license（付费支持者）
- macOS 系统

**安装**：
```bash
clawhub install obsidian-catalyst-cli
```

**文档**：https://help.obsidian.md/cli
