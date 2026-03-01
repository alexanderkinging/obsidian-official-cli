---
name: obsidian-cli-official
description: |
  Complete official Obsidian CLI reference (v1.12+). All 115 commands documented.
  Covers files, daily notes, search, tasks, tags, properties, links, bookmarks, 
  bases, templates, history, sync, publish, themes, plugins, workspaces, and developer tools.
homepage: https://help.obsidian.md/cli
metadata:
  openclaw:
    emoji: "💎"
    requires:
      apps: ["Obsidian.app"]
    platform: macos
---

# Obsidian Official CLI - Complete Reference

**Official Obsidian CLI (v1.12+)** - Complete documentation of all 115 commands.

## About This Skill

This OpenClaw skill provides complete access to Obsidian's official CLI, enabling AI agents to automate note-taking, task management, knowledge organization, and workspace customization.

**Key capabilities:**
- 📝 Automate daily journals and meeting notes
- ✅ Manage tasks across your vault
- 🔍 Search and organize knowledge
- 🗄️ Work with Obsidian databases
- 🎨 Customize themes, plugins, and workspaces

**For complete use cases and OpenClaw integration tips, see [README.md](README.md).**

## Prerequisites

- **Obsidian 1.12+** (Early Access)
- **Catalyst license** (paid supporter)
- **macOS** system
- **Obsidian must be running** (CLI connects via IPC)

## Quick Start

### 1. Enable CLI

Settings → General → Enable CLI

### 2. Add to PATH

```bash
export PATH="$PATH:/Applications/Obsidian.app/Contents/MacOS"
```

### 3. Test

```bash
obsidian version
obsidian vault
```

## Command Syntax

```bash
obsidian <command> [options]

# Options
vault=<name>          # Target specific vault

# Notes
file=<name>           # Resolves by name (like wikilinks)
path=<path>           # Exact path (folder/note.md)
content="text"        # Quote values with spaces
\n                    # Newline in content
\t                    # Tab in content
```

## Complete Command Reference

### Basics (5 commands)

#### version
Show Obsidian version
```bash
obsidian version
```

#### help
Show all commands or help for specific command
```bash
obsidian help
obsidian help search
```

#### vault
Show vault info
```bash
obsidian vault                    # All info
obsidian vault info=name          # Just name
obsidian vault info=path          # Just path
obsidian vault info=files         # File count
obsidian vault info=folders       # Folder count
obsidian vault info=size          # Size in bytes
```

#### vaults
List known vaults
```bash
obsidian vaults                   # List all
obsidian vaults verbose           # With paths
obsidian vaults total             # Count only
```

#### reload
Reload the vault
```bash
obsidian reload
```

#### restart
Restart Obsidian app
```bash
obsidian restart
```

---

### Daily Notes (4 commands)

#### daily
Open daily note
```bash
obsidian daily
obsidian daily paneType=tab       # Open in new tab
obsidian daily paneType=split     # Open in split
obsidian daily paneType=window    # Open in new window
```

#### daily:read
Read daily note contents
```bash
obsidian daily:read
```

#### daily:append
Append to daily note
```bash
obsidian daily:append content="- [ ] Task"
obsidian daily:append content="text" inline    # No newline
obsidian daily:append content="text" open      # Open after
```

#### daily:prepend
Prepend to daily note
```bash
obsidian daily:prepend content="# Header"
obsidian daily:prepend content="text" inline
```

#### daily:path
Get daily note path
```bash
obsidian daily:path
```

---

### Files (18 commands)

#### create
Create a new file
```bash
obsidian create name="Note" content="Hello"
obsidian create name="Note" template="Travel"
obsidian create path="Work/note.md" content="text"
obsidian create name="Note" overwrite
obsidian create name="Note" open newtab
```

#### read
Read file contents
```bash
obsidian read file="Recipe"
obsidian read path="Work/notes.md"
```

#### file
Show file info
```bash
obsidian file file="Recipe"
obsidian file path="Work/notes.md"
```

#### open
Open file in Obsidian
```bash
obsidian open file="Recipe"
obsidian open file="Recipe" newtab
```

#### delete
Delete file
```bash
obsidian delete file="Old"
obsidian delete file="Old" permanent    # Skip trash
```

#### move
Move or rename file
```bash
obsidian move file="Old" to="Archive/Old.md"
```

#### rename
Rename file
```bash
obsidian rename file="Old" name="New"
```

#### append
Append to file
```bash
obsidian append file="Log" content="Entry"
obsidian append file="Log" content="text" inline
```

#### prepend
Prepend to file
```bash
obsidian prepend file="Log" content="Header"
obsidian prepend file="Log" content="text" inline
```

#### unique
Create unique note with timestamp
```bash
obsidian unique name="Meeting" content="notes"
obsidian unique name="Meeting" open paneType=tab
```

#### wordcount
Count words and characters
```bash
obsidian wordcount file="Note"
obsidian wordcount file="Note" words
obsidian wordcount file="Note" characters
```

#### random
Open random note
```bash
obsidian random
obsidian random folder="Work"
obsidian random newtab
```

#### random:read
Read random note
```bash
obsidian random:read
obsidian random:read folder="Work"
```

#### recents
List recently opened files
```bash
obsidian recents
obsidian recents total
```

#### files
List files in vault
```bash
obsidian files
obsidian files folder="Work"
obsidian files ext=md
obsidian files total
```

#### folders
List folders
```bash
obsidian folders
obsidian folders folder="Work"
obsidian folders total
```

#### folder
Show folder info
```bash
obsidian folder path="Work"
obsidian folder path="Work" info=files
obsidian folder path="Work" info=folders
obsidian folder path="Work" info=size
```

#### outline
Show headings
```bash
obsidian outline file="Note"
obsidian outline file="Note" format=md
obsidian outline file="Note" format=json
obsidian outline file="Note" total
```

---

### Search (3 commands)

#### search
Search vault
```bash
obsidian search query="meeting notes"
obsidian search query="TODO" path="Work" limit=10
obsidian search query="test" format=json
obsidian search query="Bug" case
obsidian search query="error" total
```

#### search:context
Search with matching line context
```bash
obsidian search:context query="TODO"
obsidian search:context query="error" path="Work"
obsidian search:context query="bug" case
```

#### search:open
Open search view
```bash
obsidian search:open query="TODO"
```

---

### Tasks (2 commands)

#### tasks
List tasks
```bash
obsidian tasks                    # All tasks
obsidian tasks daily              # Daily note tasks
obsidian tasks daily todo         # Incomplete
obsidian tasks daily done         # Completed
obsidian tasks file="Recipe"
obsidian tasks verbose            # With file paths
obsidian tasks total
obsidian tasks status="/"         # Custom status
```

#### task
Update task
```bash
obsidian task daily line=3 toggle
obsidian task daily line=3 done
obsidian task daily line=3 todo
obsidian task ref="Work/todo.md:5" toggle
obsidian task daily line=3 status="/"
```

---

### Tags (2 commands)

#### tags
List tags
```bash
obsidian tags file="Note"
obsidian tags total
obsidian tags counts
obsidian tags counts sort=count
obsidian tags format=json
obsidian tags active              # Active file
```

#### tag
Get tag info
```bash
obsidian tag name="project"
obsidian tag name="project" verbose
obsidian tag name="project" total
```

---

### Properties (4 commands)

#### properties
List properties
```bash
obsidian properties file="Note"
obsidian properties name="status"
obsidian properties total
obsidian properties counts
obsidian properties counts sort=count
obsidian properties format=yaml
obsidian properties format=json
obsidian properties active
```

#### property:read
Read property value
```bash
obsidian property:read name="status" file="Note"
```

#### property:set
Set property
```bash
obsidian property:set name="status" value="done" file="Note"
obsidian property:set name="due" value="2026-03-01" type=date file="Note"
```

#### property:remove
Remove property
```bash
obsidian property:remove name="status" file="Note"
```

---

### Aliases (1 command)

#### aliases
List aliases
```bash
obsidian aliases
obsidian aliases file="Note"
obsidian aliases total
obsidian aliases verbose
obsidian aliases active
```

---

### Links (5 commands)

#### links
List outgoing links
```bash
obsidian links file="Note"
obsidian links file="Note" total
```

#### backlinks
List incoming links
```bash
obsidian backlinks file="Note"
obsidian backlinks file="Note" counts
obsidian backlinks file="Note" total
obsidian backlinks file="Note" format=json
```

#### orphans
Files with no incoming links
```bash
obsidian orphans
obsidian orphans total
obsidian orphans all              # Include non-markdown
```

#### deadends
Files with no outgoing links
```bash
obsidian deadends
obsidian deadends total
obsidian deadends all
```

#### unresolved
Broken/unresolved links
```bash
obsidian unresolved
obsidian unresolved total
obsidian unresolved counts
obsidian unresolved verbose
obsidian unresolved format=json
```

---

### Bookmarks (2 commands)

#### bookmarks
List bookmarks
```bash
obsidian bookmarks
obsidian bookmarks total
obsidian bookmarks verbose
obsidian bookmarks format=json
```

#### bookmark
Add bookmark
```bash
obsidian bookmark file="note.md"
obsidian bookmark file="note.md" subpath="#heading"
obsidian bookmark folder="Work"
obsidian bookmark search="TODO"
obsidian bookmark url="https://example.com" title="Example"
```

---

### Bases (Database) (3 commands)

#### bases
List all base files
```bash
obsidian bases
```

#### base:views
List views in current base
```bash
obsidian base:views
```

#### base:query
Query base
```bash
obsidian base:query file="MyBase"
obsidian base:query file="MyBase" format=json
obsidian base:query file="MyBase" format=csv
obsidian base:query file="MyBase" view="View Name"
```

#### base:create
Create item in base
```bash
obsidian base:create name="New Item"
obsidian base:create name="Item" content="text" open
```

---

### Templates (3 commands)

#### templates
List templates
```bash
obsidian templates
obsidian templates total
```

#### template:read
Read template
```bash
obsidian template:read name="Daily"
obsidian template:read name="Daily" resolve
obsidian template:read name="Daily" resolve title="My Note"
```

#### template:insert
Insert template
```bash
obsidian template:insert name="Daily"
```

---

### Commands & Hotkeys (4 commands)

#### commands
List command IDs
```bash
obsidian commands
obsidian commands filter="editor"
```

#### command
Execute command
```bash
obsidian command id="app:open-settings"
```

#### hotkeys
List hotkeys
```bash
obsidian hotkeys
obsidian hotkeys all
obsidian hotkeys total
obsidian hotkeys verbose
```

#### hotkey
Get hotkey for command
```bash
obsidian hotkey id="app:open-settings"
obsidian hotkey id="app:open-settings" verbose
```

---

### Tabs & Workspaces (7 commands)

#### tabs
List open tabs
```bash
obsidian tabs
obsidian tabs ids
```

#### tab:open
Open new tab
```bash
obsidian tab:open
obsidian tab:open file="Work/note.md"
obsidian tab:open group=2
```

#### workspace
Show workspace tree
```bash
obsidian workspace
obsidian workspace ids
```

#### workspaces
List saved workspaces
```bash
obsidian workspaces
obsidian workspaces total
```

#### workspace:save
Save current layout
```bash
obsidian workspace:save name="coding"
```

#### workspace:load
Load workspace
```bash
obsidian workspace:load name="coding"
```

#### workspace:delete
Delete workspace
```bash
obsidian workspace:delete name="old"
```

---

### History & Diff (6 commands)

#### history
List file history
```bash
obsidian history file="Note"
```

#### history:list
List files with history
```bash
obsidian history:list
```

#### history:read
Read history version
```bash
obsidian history:read file="Note"
obsidian history:read file="Note" version=3
```

#### history:restore
Restore version
```bash
obsidian history:restore file="Note" version=3
```

#### history:open
Open file recovery UI
```bash
obsidian history:open file="Note"
```

#### diff
Diff versions
```bash
obsidian diff file="Note"
obsidian diff file="Note" from=1 to=3
obsidian diff file="Note" filter=local
obsidian diff file="Note" filter=sync
```

---

### Sync (7 commands)

#### sync:status
Show sync status
```bash
obsidian sync:status
```

#### sync
Pause/resume sync
```bash
obsidian sync on
obsidian sync off
```

#### sync:history
Sync version history
```bash
obsidian sync:history file="Note"
obsidian sync:history file="Note" total
```

#### sync:read
Read sync version
```bash
obsidian sync:read file="Note" version=2
```

#### sync:restore
Restore sync version
```bash
obsidian sync:restore file="Note" version=2
```

#### sync:deleted
List deleted files
```bash
obsidian sync:deleted
obsidian sync:deleted total
```

#### sync:open
Open sync history UI
```bash
obsidian sync:open file="Note"
```

---

### Publish (6 commands)

⚠️ **Requires Obsidian Publish subscription** ($8/month or $96/year)

These commands only work if you have an active Obsidian Publish subscription.

#### publish:site
Show publish site info
```bash
obsidian publish:site             # Show slug and URL
```

#### publish:list
List published files
```bash
obsidian publish:list
obsidian publish:list total       # Count only
```

#### publish:status
List publish changes
```bash
obsidian publish:status           # All changes
obsidian publish:status total     # Count only
obsidian publish:status new       # New files only
obsidian publish:status changed   # Changed files only
obsidian publish:status deleted   # Deleted files only
```

#### publish:add
Publish a file or all changed files
```bash
obsidian publish:add              # Publish active file
obsidian publish:add file="Note"  # Publish specific file
obsidian publish:add path="Work/note.md"
obsidian publish:add changed      # Publish all changed files
```

#### publish:remove
Unpublish a file
```bash
obsidian publish:remove           # Unpublish active file
obsidian publish:remove file="Note"
obsidian publish:remove path="Work/note.md"
```

#### publish:open
Open file on published site
```bash
obsidian publish:open             # Open active file
obsidian publish:open file="Note"
obsidian publish:open path="Work/note.md"
```

---

### Themes & CSS (7 commands)

#### theme
Show active theme
```bash
obsidian theme
obsidian theme name="Minimal"
```

#### themes
List themes
```bash
obsidian themes
obsidian themes versions
```

#### theme:set
Set active theme
```bash
obsidian theme:set name="Minimal"
obsidian theme:set name=""        # Default theme
```

#### theme:install
Install theme
```bash
obsidian theme:install name="Minimal"
obsidian theme:install name="Minimal" enable
```

#### theme:uninstall
Uninstall theme
```bash
obsidian theme:uninstall name="Minimal"
```

#### snippets
List CSS snippets
```bash
obsidian snippets
```

#### snippets:enabled
List enabled snippets
```bash
obsidian snippets:enabled
```

#### snippet:enable
Enable snippet
```bash
obsidian snippet:enable name="custom"
```

#### snippet:disable
Disable snippet
```bash
obsidian snippet:disable name="custom"
```

---

### Plugins (9 commands)

#### plugins
List plugins
```bash
obsidian plugins
obsidian plugins filter=core
obsidian plugins filter=community
obsidian plugins versions
```

#### plugins:enabled
List enabled plugins
```bash
obsidian plugins:enabled
obsidian plugins:enabled filter=community versions
```

#### plugins:restrict
Restricted mode
```bash
obsidian plugins:restrict
obsidian plugins:restrict on
obsidian plugins:restrict off
```

#### plugin
Get plugin info
```bash
obsidian plugin id="dataview"
```

#### plugin:enable
Enable plugin
```bash
obsidian plugin:enable id="dataview"
obsidian plugin:enable id="dataview" filter=community
```

#### plugin:disable
Disable plugin
```bash
obsidian plugin:disable id="dataview"
```

#### plugin:install
Install plugin
```bash
obsidian plugin:install id="dataview"
obsidian plugin:install id="dataview" enable
```

#### plugin:uninstall
Uninstall plugin
```bash
obsidian plugin:uninstall id="dataview"
```

#### plugin:reload
Reload plugin (dev)
```bash
obsidian plugin:reload id="my-plugin"
```

---

### Developer Tools (10 commands)

#### devtools
Toggle Electron DevTools
```bash
obsidian devtools
```

#### eval
Execute JavaScript
```bash
obsidian eval code="app.vault.getFiles().length"
obsidian eval code="console.log('hello')"
```

#### dev:screenshot
Take screenshot
```bash
obsidian dev:screenshot path="screenshot.png"
```

#### dev:console
Show console messages
```bash
obsidian dev:console
obsidian dev:console clear
obsidian dev:console limit=100
obsidian dev:console level=error
```

#### dev:errors
Show errors
```bash
obsidian dev:errors
obsidian dev:errors clear
```

#### dev:css
Inspect CSS
```bash
obsidian dev:css selector=".workspace"
obsidian dev:css selector=".workspace" prop="background"
```

#### dev:dom
Query DOM
```bash
obsidian dev:dom selector=".workspace"
obsidian dev:dom selector=".workspace" total
obsidian dev:dom selector=".workspace" text
obsidian dev:dom selector=".workspace" attr="class"
```

#### dev:cdp
Chrome DevTools Protocol
```bash
obsidian dev:cdp method="Page.getLayoutMetrics"
obsidian dev:cdp method="Runtime.evaluate" params='{"expression":"1+1"}'
```

#### dev:debug
Attach/detach debugger
```bash
obsidian dev:debug on
obsidian dev:debug off
```

#### dev:mobile
Mobile emulation
```bash
obsidian dev:mobile on
obsidian dev:mobile off
```

#### web
Open URL in web viewer
```bash
obsidian web url="https://example.com"
obsidian web url="https://example.com" newtab
```

---

## Multi-Vault Usage

Target specific vault:
```bash
obsidian vault="Notes" daily
obsidian vault="Work" search query="test"
```

**Note**: `vault=<name>` must be the FIRST parameter.

---

## Troubleshooting

### "Cannot connect"
- Ensure Obsidian is running
- Enable CLI in Settings → General

### "Command not found"
- Add to PATH: `export PATH="$PATH:/Applications/Obsidian.app/Contents/MacOS"`
- Or use full path: `/Applications/Obsidian.app/Contents/MacOS/obsidian`

### File not found
- Use `file=<name>` for wikilink-style resolution
- Use `path=<path>` for exact paths

---

## 中文说明

### 前置条件
- Obsidian 1.12+ (Early Access)
- Catalyst 许可证（付费支持者）
- macOS 系统
- Obsidian 必须运行中

### 快速开始
1. 设置 → 通用 → 启用 CLI
2. 添加到 PATH：`export PATH="$PATH:/Applications/Obsidian.app/Contents/MacOS"`
3. 测试：`obsidian version`

### 完整功能
- 110 个官方命令
- 文件操作、日记、搜索、任务、标签
- 书签、数据库、模板、历史记录
- 同步、发布、主题、插件
- 工作区、开发者工具

详细用法见上方英文文档。
