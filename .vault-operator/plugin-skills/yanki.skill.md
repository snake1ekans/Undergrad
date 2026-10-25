---
id: yanki
name: Yanki
source: vault-native
plugin-type: community
status: enabled
class: PARTIAL
description: "Sync flashcards from a folder in your vault to Anki. Pure Markdown syntax. No fuss."
has-settings: true
commands:
  - id: "yanki:sync"
    name: "Yanki: Sync flashcard notes to Anki"
---

# Yanki

**Description:** Sync flashcards from a folder in your vault to Anki. Pure Markdown syntax. No fuss.
**Status:** Enabled
**Plugin ID:** yanki

## Available Commands

Available command IDs (use execute_command for Obsidian-native commands):
- `yanki:sync` -- Yanki: Sync flashcard notes to Anki

## Configuration File

Settings path: `.obsidian/plugins/yanki/data.json`

To configure this plugin programmatically:
1. Read the config: read_file(".obsidian/plugins/yanki/data.json")
2. Understand the settings structure and modify values as needed
3. Write changes: write_file(".obsidian/plugins/yanki/data.json", updatedJSON)

Do NOT ask the user to open Settings UI. Modify data.json directly.

## Current Configuration

These are the plugin's current settings (sensitive values redacted):

```
ankiConnect:
  host: http://localhost
  port: 8765
ignoreFolderNotes: true
manageFilenames:
  autoRenameDebounceIntervalMs: 300
  autoRenameTrigger: off
  maxLength: 60
  mode: prompt
namespace: Yanki Obsidian - Vault ID 59fea8e3ae482668
showAdvancedSettings: false
stats:
  sync:
    auto: 0
    duration: 0
    errors: 0
    invalid: 0
    manual: 0
    notes:
      ankiUnreachable: 0
      created: 0
      deleted: 0
      matched: 0
      unchanged: 0
      updated: 0
sync:
  autoSyncDebounceIntervalMs: 4000
  autoSyncEnabled: false
  mediaMode: local
  pushToAnkiWeb: true
verboseNotices: false
```

For full settings, read: `.obsidian/plugins/yanki/data.json`

## Documentation

For detailed plugin documentation (commands, options, dependencies):
read_file(".vault-operator/plugin-skills/yanki.readme.md")

## Usage

When the user asks for functionality related to Yanki:
1. Read the plugin documentation (.readme.md) to understand capabilities and dependencies
2. Read the config file (.obsidian/plugins/yanki/data.json). If it does not exist, that is normal -- create it with the required settings
3. Configure the plugin by writing data.json with the values needed for the task
4. Execute the task using the appropriate tool:
   - For Obsidian-native commands (including file export): use execute_command
   - For CLI-based conversion needing Pandoc/LaTeX: use execute_recipe
   - For data queries: use call_plugin_api
5. If a command opens a UI dialog, tell the user what to click.

CRITICAL RULES:
- Prefer native Obsidian commands over external tools when both can accomplish the task.
- NEVER create fake output files. If the user asks for a PDF/DOCX/image export, use execute_recipe -- do NOT write content to a .pdf file yourself.
- If a dependency is missing (e.g. Pandoc), tell the user what to install.
IMPORTANT: After reading this file, ALWAYS take action or respond. Never end silently.
