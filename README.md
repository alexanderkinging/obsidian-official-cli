# Obsidian Official CLI Skill

Complete reference for the official Obsidian CLI (v1.12+). All 110 commands documented.

## What is this?

This skill enables OpenClaw to use **all official Obsidian CLI features**:
- 📝 Files (create, read, edit, delete, move, rename)
- 📅 Daily Notes (open, read, append, prepend)
- 🔍 Search (full-text, context, case-sensitive)
- ✅ Tasks (list, toggle, filter by status)
- 🏷️ Tags (list, count, filter)
- 📋 Properties (read, set, remove)
- 🔗 Links (backlinks, orphans, deadends, unresolved)
- 🔖 Bookmarks (files, folders, searches, URLs)
- 🗄️ Bases (database views, query, create)
- 📄 Templates (list, read, insert, resolve)
- 🕐 History (versions, diff, restore)
- ☁️ Sync (status, history, restore)
- 🎨 Themes (install, switch, uninstall)
- 🔌 Plugins (install, enable, disable, reload)
- 🪟 Workspaces (save, load, delete)
- 🛠️ Developer Tools (devtools, eval, screenshot, console)

## Prerequisites

- **Obsidian 1.12+** (Early Access)
- **Catalyst license** (paid supporter - $25 one-time)
- **macOS** system
- **Obsidian must be running** (CLI connects via IPC)

## Installation

### 1. Get Catalyst License

Visit https://obsidian.md/pricing and purchase Catalyst ($25 one-time).

### 2. Install Skill

```bash
clawhub install obsidian-catalyst-cli
```

### 3. Enable CLI in Obsidian

Settings → General → Enable CLI

### 4. Add to PATH

```bash
echo 'export PATH="$PATH:/Applications/Obsidian.app/Contents/MacOS"' >> ~/.zprofile
source ~/.zprofile
```

### 5. Test

```bash
obsidian version
obsidian vault
```

## Quick Examples

```bash
# Daily notes
obsidian daily
obsidian daily:append content="- [ ] Task"

# Files
obsidian create name="Note" content="Hello"
obsidian read file="Recipe"
obsidian search query="meeting"

# Tasks
obsidian tasks daily todo
obsidian task daily line=3 toggle

# Tags & Properties
obsidian tags counts sort=count
obsidian property:set name="status" value="done" file="Note"

# Bookmarks
obsidian bookmark file="important.md"
obsidian bookmarks

# Bases (Database)
obsidian bases
obsidian base:query file="MyBase" format=json

# History
obsidian history file="Note"
obsidian history:restore file="Note" version=3

# Plugins
obsidian plugins filter=community
obsidian plugin:install id="dataview" enable

# Developer
obsidian devtools
obsidian eval code="app.vault.getFiles().length"
```

## Complete Documentation

See [SKILL.md](SKILL.md) for all 110 commands with full parameter documentation.

## Official vs Community CLI

| Feature | Official CLI | Community CLI (yakitrak) |
|---------|--------------|--------------------------|
| **Daily Notes** | ✅ Full support | ❌ Manual file editing |
| **Tasks** | ✅ Toggle, filter | ❌ Manual editing |
| **Tags** | ✅ Count, sort | ❌ Manual parsing |
| **Properties** | ✅ Read, set, remove | ❌ Manual YAML |
| **Bookmarks** | ✅ Full support | ❌ Not available |
| **Bases** | ✅ Query, create | ❌ Not available |
| **History** | ✅ Versions, restore | ❌ Not available |
| **Sync** | ✅ Control, history | ❌ Not available |
| **Plugins** | ✅ Install, manage | ❌ Not available |
| **Developer Tools** | ✅ DevTools, eval | ❌ Not available |
| **Requires Obsidian running** | ✅ Yes (IPC) | ❌ No |
| **Requires Catalyst** | ✅ Yes ($25) | ❌ No |

## Troubleshooting

### "Cannot connect to Obsidian"
- Ensure Obsidian is running
- Enable CLI in Settings → General → Enable CLI

### "Command not found: obsidian"
```bash
# Add to PATH
export PATH="$PATH:/Applications/Obsidian.app/Contents/MacOS"

# Or use full path
/Applications/Obsidian.app/Contents/MacOS/obsidian version
```

### "File not found"
- Use `file=<name>` for wikilink-style resolution (no path, no .md)
- Use `path=<path>` for exact paths (include folder and .md)

### Multi-vault
```bash
# Target specific vault (must be FIRST parameter)
obsidian vault="Work" daily
obsidian vault="Notes" search query="test"
```

## Alternative: Direct File Editing

If you don't have Catalyst license, you can still work with Obsidian vaults by editing files directly:

```bash
# Read note
cat ~/Documents/Obsidian\ Vault/note.md

# Append to daily note
echo "- [ ] Task" >> ~/Documents/Obsidian\ Vault/Daily/2026-03-01.md

# Search
grep -r "keyword" ~/Documents/Obsidian\ Vault/
```

But you'll miss: tasks toggle, properties, bookmarks, bases, history, sync, plugins, etc.

## Resources

- **Official Docs**: https://help.obsidian.md/cli
- **Catalyst License**: https://obsidian.md/pricing
- **GitHub**: https://github.com/alexanderkinging/obsidian-official-cli
- **ClawHub**: https://clawhub.ai/obsidian-catalyst-cli

---

## 中文说明

### 这是什么？

完整的 Obsidian 官方 CLI 文档（110 个命令），包括：
- 文件操作、日记、搜索、任务、标签
- 书签、数据库、模板、历史记录
- 同步、发布、主题、插件、工作区
- 开发者工具

### 前置条件

- Obsidian 1.12+ (Early Access)
- Catalyst 许可证（$25 一次性付费）
- macOS 系统
- Obsidian 必须运行中

### 安装

```bash
clawhub install obsidian-catalyst-cli
```

### 配置

1. 设置 → 通用 → 启用 CLI
2. 添加到 PATH：`export PATH="$PATH:/Applications/Obsidian.app/Contents/MacOS"`
3. 测试：`obsidian version`

### 快速示例

```bash
# 日记
obsidian daily
obsidian daily:append content="- [ ] 任务"

# 文件
obsidian create name="笔记" content="内容"
obsidian read file="食谱"

# 搜索
obsidian search query="会议"

# 任务
obsidian tasks daily todo
obsidian task daily line=3 toggle

# 书签
obsidian bookmark file="重要.md"

# 数据库
obsidian base:query file="数据库" format=json

# 历史记录
obsidian history file="笔记"
obsidian history:restore file="笔记" version=3
```

详细文档见 [SKILL.md](SKILL.md)。
