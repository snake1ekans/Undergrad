---
id: omnisearch
name: Omnisearch
source: vault-native
plugin-type: community
status: enabled
class: PARTIAL
description: "A search engine that just works."
has-settings: true
commands:
  - id: "omnisearch:show-modal"
    name: "Omnisearch: Vault search"
  - id: "omnisearch:show-modal-infile"
    name: "Omnisearch: In-file search"
---

# Omnisearch

**Description:** A search engine that just works.
**Status:** Enabled
**Plugin ID:** omnisearch

## Available Commands

Available command IDs (use execute_command for Obsidian-native commands):
- `omnisearch:show-modal` -- Omnisearch: Vault search
- `omnisearch:show-modal-infile` -- Omnisearch: In-file search

## Plugin API

This plugin exposes a JavaScript API. Use call_plugin_api to call these methods:
- `hasOwnProperty` -- call via call_plugin_api("omnisearch", "hasOwnProperty", [args])
- `isPrototypeOf` -- call via call_plugin_api("omnisearch", "isPrototypeOf", [args])
- `propertyIsEnumerable` -- call via call_plugin_api("omnisearch", "propertyIsEnumerable", [args])
- `toString` -- call via call_plugin_api("omnisearch", "toString", [args])
- `valueOf` -- call via call_plugin_api("omnisearch", "valueOf", [args])
- `toLocaleString` -- call via call_plugin_api("omnisearch", "toLocaleString", [args])

Note: Dynamically discovered methods require user approval for each call unless marked as safe in settings.

## Configuration File

Settings path: `.obsidian/plugins/omnisearch/data.json`

To configure this plugin programmatically:
1. Read the config: read_file(".obsidian/plugins/omnisearch/data.json")
2. Understand the settings structure and modify values as needed
3. Write changes: write_file(".obsidian/plugins/omnisearch/data.json", updatedJSON)

Do NOT ask the user to open Settings UI. Modify data.json directly.

## Current Configuration

These are the plugin's current settings (sensitive values redacted):

```
useCache: true
hideExcluded: false
recencyBoost: 0
ignoreDiacritics: true
ignoreArabicDiacritics: false
indexFilesWithoutExtension: false
PDFIndexing: false
officeIndexing: false
imagesIndexing: false
aiImageIndexing: false
unsupportedFilesIndexing: default
splitCamelCase: false
vimLikeNavigationShortcut: false
ribbonIcon: true
showExcerpt: true
maxEmbeds: 5
renderLineReturnInExcerpts: true
showCreateButton: false
highlight: true
showPreviousQueryResults: true
simpleSearch: false
tokenizeUrls: false
fuzziness: 1
weightBasename: 10
weightDirectory: 7
weightH1: 6
weightH2: 5
weightH3: 4
weightUnmarkedTags: 2
httpApiEnabled: false
httpApiPort: 51361
httpApiNotice: true
welcomeMessage: 1.21.0
verboseLogging: false
DANGER_forceSaveCache: false
```

For full settings, read: `.obsidian/plugins/omnisearch/data.json`

## Documentation

For detailed plugin documentation (commands, options, dependencies):
read_file(".vault-operator/plugin-skills/omnisearch.readme.md")

## Usage

When the user asks for functionality related to Omnisearch:
1. Read the plugin documentation (.readme.md) to understand capabilities and dependencies
2. Read the config file (.obsidian/plugins/omnisearch/data.json). If it does not exist, that is normal -- create it with the required settings
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
