---
name: obsidian-official-cli
description: |
  Obsidian 官方 CLI 集成（需要 Obsidian 1.12+ 和 Catalyst license）。
  支持日记、任务、标签、模板、搜索等完整功能。
  触发词：Obsidian、笔记、vault、日记、daily note
homepage: https://help.obsidian.md/cli
metadata:
  openclaw:
    emoji: "💎"
    requires:
      apps: ["Obsidian.app"]
    platform: macos
---

# Obsidian Official CLI

Obsidian 官方命令行界面集成，功能比社区版更完整。

**官方文档**: https://help.obsidian.md/cli

## 前置条件

1. **Obsidian 1.12+** (Early Access 版本)
2. **Catalyst license** (付费支持者)
3. 设置 → 通用 → 启用"命令行界面" → 注册到 PATH
4. **Obsidian 应用必须运行中**

## 安装 CLI

1. 打开 Obsidian → 设置 → 通用
2. 启用「命令行界面」
3. 点击「注册到 PATH」
4. 重启终端

验证安装：
```bash
obsidian help
```

## 快速开始

```bash
# 打开今日日记
obsidian daily

# 追加内容到日记
obsidian daily:append content="- [ ] 待办事项"

# 搜索笔记
obsidian search query="关键词"

# 创建笔记
obsidian create name="新笔记" content="# 标题\n\n内容"

# 读取文件
obsidian read file=笔记名
```

## 常用命令

### 日记 (Daily Notes)

```bash
obsidian daily                    # 打开今日日记
obsidian daily:read               # 读取日记内容
obsidian daily:append content="..." # 追加到末尾
obsidian daily:prepend content="..." # 插入到开头
```

### 文件操作

```bash
obsidian files                    # 列出所有文件
obsidian read file=笔记名          # 读取文件
obsidian create name="标题" content="内容"
obsidian create name="标题" template=模板名
obsidian append file=笔记 content="追加内容"
obsidian open file=笔记           # 在 Obsidian 中打开
obsidian move from="旧路径" to="新路径"
obsidian delete file=笔记
```

### 搜索和标签

```bash
obsidian search query="关键词"
obsidian tags counts              # 列出所有标签
obsidian tasks                    # 列出所有任务
obsidian tasks daily              # 日记中的任务
```

### 属性 (Frontmatter)

```bash
obsidian properties file=笔记
obsidian property:set file=笔记 key=status value=done
obsidian property:read file=笔记 key=status
```

### 链接

```bash
obsidian backlinks file=笔记      # 反向链接
obsidian links file=笔记          # 出链
obsidian orphans                  # 孤立笔记
```

## 多 Vault 支持

```bash
obsidian vaults                   # 列出所有 vault
obsidian vault="Work" daily       # 指定 vault
```

## 参数说明

- `file=<name>` - 按文件名匹配（像 wikilink）
- `path=<path>` - 精确路径（如 `folder/note.md`）
- `content=<text>` - 内容，`\n` 换行，`\t` 制表符
- `--copy` - 复制输出到剪贴板
- `open` - 创建后打开文件

## 与社区版 CLI 的区别

| 功能 | 官方 CLI | 社区版 (yakitrak) |
|------|---------|------------------|
| Daily Notes | ✅ | ❌ |
| Tasks | ✅ | ❌ |
| Tags | ✅ | ❌ |
| Templates | ✅ | ❌ |
| Properties | ✅ | ❌ |
| 需要 Obsidian 运行 | ✅ | ❌ |
| 需要 Catalyst | ✅ | ❌ |

## 备选方案

如果 Obsidian 未运行，可以直接编辑 .md 文件：

```bash
# Vault 就是普通文件夹
echo "# 标题" > "/path/to/vault/新笔记.md"
cat "/path/to/vault/笔记.md"
```

## 故障排除

### 命令找不到

```bash
# 检查 PATH
which obsidian

# 如果找不到，手动添加
export PATH="$PATH:/Applications/Obsidian.app/Contents/MacOS"
```

### Obsidian 未运行

CLI 需要 Obsidian 运行。第一个命令会自动启动 Obsidian。

## 注意事项

- **Early Access**: 命令语法可能变化
- **Obsidian 必须运行**: CLI 通过 IPC 通信
- **macOS 专用**: 目前仅支持 macOS
