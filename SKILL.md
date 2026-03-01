---
name: obsidian-official-cli
description: |
  Official Obsidian CLI integration (requires Obsidian 1.12+ and Catalyst license).
  Full support for Daily Notes, Tasks, Tags, Templates, and more.
homepage: https://help.obsidian.md/cli
metadata:
  openclaw:
    emoji: "💎"
    requires:
      apps: ["Obsidian.app"]
    platform: macos
---

# Obsidian Official CLI

Official Obsidian command-line interface integration with full feature support.

**Official Docs**: https://help.obsidian.md/cli

## Prerequisites

1. **Obsidian 1.12+** (Early Access version)
2. **Catalyst license** (paid supporter)
3. Settings → General → Enable "Command line interface" → Register to PATH
4. **Obsidian app must be running**

## Install CLI

1. Open Obsidian → Settings → General
2. Enable "Command line interface"
3. Click "Register to PATH"
4. Restart terminal

Verify installation:
```bash
obsidian help
```

## Quick Start

```bash
# Open today's daily note
obsidian daily

# Append to daily note
obsidian daily:append content="- [ ] Task"

# Search notes
obsidian search query="keyword"

# Create note
obsidian create name="New Note" content="# Title\n\nContent"

# Read file
obsidian read file=NoteName
```

## Common Commands

### Daily Notes

```bash
obsidian daily                    # Open today's daily note
obsidian daily:read               # Read daily note content
obsidian daily:append content="..." # Append to end
obsidian daily:prepend content="..." # Insert at beginning
```

### File Operations

```bash
obsidian files                    # List all files
obsidian read file=NoteName       # Read file
obsidian create name="Title" content="Content"
obsidian create name="Title" template=TemplateName
obsidian append file=Note content="Append content"
obsidian open file=Note           # Open in Obsidian
obsidian move from="old/path" to="new/path"
obsidian delete file=Note
```

### Search and Tags

```bash
obsidian search query="keyword"
obsidian tags counts              # List all tags
obsidian tasks                    # List all tasks
obsidian tasks daily              # Tasks in daily note
```

### Properties (Frontmatter)

```bash
obsidian properties file=Note
obsidian property:set file=Note key=status value=done
obsidian property:read file=Note key=status
```

### Links

```bash
obsidian backlinks file=Note      # Backlinks
obsidian links file=Note          # Outgoing links
obsidian orphans                  # Orphaned notes
```

## Multi-Vault Support

```bash
obsidian vaults                   # List all vaults
obsidian vault="Work" daily       # Target specific vault
```

## Parameters

- `file=<name>` - Match by filename (like wikilinks)
- `path=<path>` - Exact path (e.g., `folder/note.md`)
- `content=<text>` - Content, use `\n` for newline, `\t` for tab
- `--copy` - Copy output to clipboard
- `open` - Open file after creation

## vs Community CLI

| Feature | Official CLI | Community (yakitrak) |
|---------|-------------|---------------------|
| Daily Notes | ✅ | ❌ |
| Tasks | ✅ | ❌ |
| Tags | ✅ | ❌ |
| Templates | ✅ | ❌ |
| Requires Obsidian running | ✅ | ❌ |
| Requires Catalyst | ✅ | ❌ |

## Alternative: Direct File Editing

If Obsidian is not running, you can directly edit .md files:

```bash
# Vault is just a folder
echo "# Title" > "/path/to/vault/NewNote.md"
cat "/path/to/vault/Note.md"
```

## Troubleshooting

### Command not found

```bash
# Check PATH
which obsidian

# If not found, manually add
export PATH="$PATH:/Applications/Obsidian.app/Contents/MacOS"
```

### Obsidian not running

CLI requires Obsidian to be running. The first command will auto-launch Obsidian.

## Notes

- **Early Access**: Command syntax may change
- **Obsidian must be running**: CLI communicates via IPC
- **macOS only**: Currently supports macOS only

---

## 中文说明

完整的 Obsidian 官方 CLI 集成，支持日记、任务、标签、模板等功能。

**前置条件**：
- Obsidian 1.12+ (Early Access)
- Catalyst license（付费支持者）
- macOS 系统

**安装**：设置 → 通用 → 启用"命令行界面" → 注册到 PATH

**文档**：https://help.obsidian.md/cli
