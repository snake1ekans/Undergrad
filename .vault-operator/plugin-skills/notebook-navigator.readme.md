# ![Notebook Navigator](https://github.com/johansan/notebook-navigator/blob/main/images/notebook-navigator.png?raw=true)

Read in your language: [English](https://notebooknavigator.com/docs.html) • [العربية](https://notebooknavigator.com/ar/docs.html) • [Deutsch](https://notebooknavigator.com/de/docs.html) • [Español](https://notebooknavigator.com/es/docs.html) • [فارسی](https://notebooknavigator.com/fa/docs.html) • [Français](https://notebooknavigator.com/fr/docs.html) • [Bahasa Indonesia](https://notebooknavigator.com/id/docs.html) • [Italiano](https://notebooknavigator.com/it/docs.html) • [Nederlands](https://notebooknavigator.com/nl/docs.html) • [Polski](https://notebooknavigator.com/pl/docs.html) • [Português](https://notebooknavigator.com/pt/docs.html) • [Português (Brasil)](https://notebooknavigator.com/pt-br/docs.html) • [Русский](https://notebooknavigator.com/ru/docs.html) • [ไทย](https://notebooknavigator.com/th/docs.html) • [Türkçe](https://notebooknavigator.com/tr/docs.html) • [Українська](https://notebooknavigator.com/uk/docs.html) • [Tiếng Việt](https://notebooknavigator.com/vi/docs.html) • [日本語](https://notebooknavigator.com/ja/docs.html) • [한국어](https://notebooknavigator.com/ko/docs.html) • [中文简体](https://notebooknavigator.com/zh-cn/docs.html) • [中文繁體](https://notebooknavigator.com/zh-tw/docs.html)

Turn Obsidian into a fast, customizable notes browser with folders, tags, properties and shortcuts in one view.
Visual previews. Full keyboard navigation. Dual-pane layout. Mobile optimized. Works with 100,000+ notes.

If you love using Notebook Navigator, please consider [☕️ Buying me a coffee](https://buymeacoffee.com/johansan) or [Sponsor on GitHub ❤️](https://github.com/sponsors/johansan).

Coming from another app? Read the switching guides for [Evernote](https://notebooknavigator.com/evernote/), [Apple Notes](https://notebooknavigator.com/apple-notes/), [Bear](https://notebooknavigator.com/bear/), [OneNote](https://notebooknavigator.com/onenote/) and [Day One](https://notebooknavigator.com/day-one/).

<br/>

![Obsidian Downloads](https://img.shields.io/badge/dynamic/json?logo=obsidian&color=%23483699&label=Downloads&query=%24%5B%22notebook-navigator%22%5D.downloads&url=https%3A%2F%2Fraw.githubusercontent.com%2Fobsidianmd%2Fobsidian-releases%2Fmaster%2Fcommunity-plugin-stats.json) ![Obsidian Compatibility](https://img.shields.io/badge/Obsidian-v1.11.0+-483699?logo=obsidian&style=flat-square) [![Discord](https://img.shields.io/discord/1405458145974943846?color=7289da&label=Discord&logo=discord&logoColor=white)](https://discord.gg/6eeSUvzEJr)

[![Quality checks](https://github.com/johansan/notebook-navigator/actions/workflows/ci.yml/badge.svg)](https://github.com/johansan/notebook-navigator/actions/workflows/ci.yml) [![Security scan](https://github.com/johansan/notebook-navigator/actions/workflows/codeql.yml/badge.svg)](https://github.com/johansan/notebook-navigator/actions/workflows/codeql.yml)

<br/>

<!-- DOCUMENTATION_START -->

## 1 Installation

1. **Install Obsidian** - Download and install from [obsidian.md](https://obsidian.md/)
2. **Enable community plugins** - Go to Settings → Community plugins → Turn on community plugins
3. **Install Notebook Navigator** - Click "Browse" → Search for "Notebook Navigator" → Install
4. **Install Style Settings (optional)** - For customizing colors and appearance, install [Style Settings](https://github.com/mgmeyers/obsidian-style-settings) plugin by searching for "Style Settings" in Community plugins

<br/>

## 2 Getting started

Here is the official tutorial for learning and mastering Notebook Navigator:

[![Mastering Notebook Navigator](https://raw.githubusercontent.com/johansan/notebook-navigator/main/images/youtube-thumbnail.jpg)](https://www.youtube.com/watch?v=m2maDNtho7Y)

The video has subtitles in 21 languages.

<br/>

## 3 Security and quality

Notebook Navigator is checked with [TypeScript](https://www.typescriptlang.org/), [ESLint](https://eslint.org/) with the official [Obsidian ESLint plugin](https://github.com/obsidianmd/eslint-plugin), [Prettier](https://prettier.io/), [Vitest](https://vitest.dev/) and a production build before changes are merged. The build must complete with zero errors and zero warnings.

Security checks run through [CodeQL](https://codeql.github.com/), with scan history in the [CodeQL workflow runs](https://github.com/johansan/notebook-navigator/actions/workflows/codeql.yml). Current status is shown in the badges at the top of this page.

Notebook Navigator runs locally, but some features make documented HTTP requests for updates, downloads, and remote content. See [section 11 - Network and Diagnostics Disclosure](#11-network-and-diagnostics-disclosure) for the full list.

<br/>

## Table of contents

- [4 Documentation](#4-documentation)
- [5 Keyboard shortcuts](#5-keyboard-shortcuts)
- [6 Synced and local settings](#6-synced-and-local-settings)
- [7 Search](#7-search)
- [8 Custom hotkeys](#8-custom-hotkeys)
- [9 Commands](#9-commands)
- [10 Features](#10-features)
- [11 Network and Diagnostics Disclosure](#11-network-and-diagnostics-disclosure)
- [12 Contact](#12-contact)
- [13 Questions or issues?](#13-questions-or-issues)
- [14 License](#14-license)

<br/>

## 4 Documentation

- [**API Reference**](docs/api-reference.md) - Public API documentation. Covers metadata management, navigation control and event subscriptions for JavaScript/TypeScript developers.

- [**Theming Guide**](docs/theming-guide.md) - Guide for theme developers. Includes CSS class reference, custom
  properties, and theme examples for light and dark modes.

- [**Startup Process**](docs/startup-process.md) - Plugin initialization sequence. Cold boot vs warm boot flows,
  metadata cache resolution, deferred cleanup, and content generation pipeline. Includes Mermaid diagrams.

- [**Metadata Pipeline**](docs/metadata-pipeline.md) - Cache rebuild sequence, provider pipeline stages, and completion signals. Includes Mermaid diagrams.

- [**Storage Architecture**](docs/storage-architecture.md) - Guide to storage containers (IndexedDB, Local Storage,
  Memory Cache, Settings). Data flow patterns and usage guidelines.

- [**Rendering Architecture**](docs/rendering-architecture.md) - React component hierarchy, virtual scrolling with
  TanStack Virtual, performance optimizations, and data flow.

- [**Scroll Orchestration**](docs/scroll-orchestration.md) - How the plugin ensures accurate scrolling when tree structures change (tag visibility, settings, etc.)

- [**Service Architecture**](docs/service-architecture.md) - Business logic layer: MetadataService, FileSystemOperations, ContentProviderRegistry. Dependency injection patterns and service data flow.

<br/>

## 5 Keyboard shortcuts

| Key                                 | Action                                                                                                                                                                                    |
| ----------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ↑/↓                                 | Navigate up/down in current pane                                                                                                                                                          |
| ←                                   | In navigation pane: collapse or go to parent<br>In list pane: switch to navigation pane                                                                                                   |
| →                                   | In navigation pane: expand or switch to list pane<br>In list pane: switch to editor                                                                                                       |
| Tab                                 | In navigation pane: switch to list pane<br>In list pane: switch to editor<br>In search field: switch to list pane                                                                         |
| Shift+Tab                           | In list pane: switch to navigation pane<br>In search field: switch to navigation pane                                                                                                     |
| Enter (macOS)<br>F2 (Windows/Linux) | Rename item inline in navigation pane or list pane                                                                                                                                        |
| Enter                               | In navigation pane: open folder note on Windows/Linux by default (when enabled)<br>In list pane: open selected file on all systems (when enabled)<br>In search field: switch to list pane |
| Escape                              | In search field: close search and focus list pane                                                                                                                                         |
| PageUp/PageDown                     | Scroll up/down in navigation pane and list pane                                                                                                                                           |
| Home/End                            | Jump to first/last item in current pane                                                                                                                                                   |
| Delete<br>Backspace                 | Delete selected item                                                                                                                                                                      |
| Cmd/Ctrl+A                          | Select all notes in current folder                                                                                                                                                        |
| Cmd/Ctrl+Click                      | Toggle notes selection                                                                                                                                                                    |
| Shift+Click                         | Select a range of notes                                                                                                                                                                   |
| Shift+Home/End                      | Select from current position to first/last item                                                                                                                                           |
| Shift+↑/↓                           | Extend selection up/down                                                                                                                                                                  |
| Cmd/Ctrl+↑/↓                        | Rearrange selected files up/down in manual sort mode                                                                                                                                      |

**Note:** All keyboard shortcuts can be customized. See [section 8 - Custom hotkeys](#8-custom-hotkeys) for details on adding VIM-style navigation (h,j,k,l), alternate keys, and modifier combinations.

<br/>

## 6 Synced and local settings

Many settings in Notebook Navigator display a sync toggle — a cloud icon that switches between "Enable sync" and "Disable sync". This controls where each setting is stored and whether it is shared across devices.

### 6.1 How sync works

Obsidian plugins store their configuration in `data.json`, located at `.obsidian/plugins/notebook-navigator/data.json` inside your vault folder. When you use a sync service — such as [Obsidian Sync](https://obsidian.md/sync), iCloud, GitHub, Dropbox, or Google Drive — this file is synchronized across all your devices along with the rest of your vault. Any setting saved to `data.json` will propagate to every device that syncs the vault.

<img width="606" height="48" alt="Screenshot 2026-02-18 at 22 58 05" src="https://github.com/user-attachments/assets/01d92458-1967-4008-acae-f722eee0d0a2" />

When sync is **enabled** (default) for a setting, the value is saved to `data.json` and synchronized to all devices through your sync service.

<img width="608" height="49" alt="Screenshot 2026-02-18 at 22 58 14" src="https://github.com/user-attachments/assets/f6f4c839-f8b8-42b5-be43-1cb6c78abdb3" />

<br/>

When sync is **disabled** for a setting, the value is saved to Obsidian's local storage instead. Local storage is device-specific and is not included in vault sync. The setting will have its own independent value on each device. When you disable sync for a setting, the current value is copied to local storage on the current device, and the value is removed from `data.json` to prevent it from overriding local values on other devices.

If you do not use a sync service, the sync toggle has no practical effect since `data.json` is only stored locally.

<br/>

## 7 Search

Notebook Navigator has two search modes: filter search and Omnisearch. Switch between them using the up/down arrow keys or by clicking the search icon. Combine file names, properties, tags, dates, and filters in one query (e.g., `meeting .status=active #work @thisweek`).

### 7.1 Filter search

Filters files by display name, alias, tags, properties, dates, folders, extensions, and tasks within the current folder and subfolders. Default search mode.

**File names and aliases**

- `word` - Match notes with "word" in the display name or an alias
- `word1 word2` - Require every word to match across the display name and aliases
- `-word` - Exclude notes with "word" in the display name or an alias
- `".F"` - Match text literally; a term that opens with a double quote is never interpreted as a tag, property, date, or filter (e.g., `".F"` matches names containing `.F` instead of filtering on a property)
- `-".F"` - Exclude notes with the literal text in the display name or an alias

**Tags**

- `#tag` - Include notes with tag (also matches nested tags like `#tag/subtag`)
- `#` - Include only tagged notes
- `-#tag` - Exclude notes with tag
- `-#` - Include only untagged notes
- `#tag1 #tag2` - Match both tags (implicit AND)
- `#tag1 AND #tag2` - Match both tags (explicit AND)
- `#tag1 OR #tag2` - Match either tag
- `#a OR #b AND #c` - AND has higher precedence: matches `#a`, or both `#b` and `#c`
- Cmd/Ctrl+Click a tag to add with AND. Cmd/Ctrl+Shift+Click to add with OR

**Properties**

- `.key` - Include notes with a property key that starts with `key`
- `.key=value` - Include notes where the property value contains `value`
- `."Reading Status"` - Property key with whitespace (double-quoted)
- `."Reading Status"="In Progress"` - Keys and values with whitespace must be double-quoted
- `-.key` - Exclude notes with a property key that starts with `key`
- `-.key=value` - Exclude notes where the property value contains `value`
- Cmd/Ctrl+Click a property to add with AND. Cmd/Ctrl+Shift+Click to add with OR

**Filters**

- `has:task` - Include notes with unfinished tasks
- `-has:task` - Exclude notes with unfinished tasks
- `folder:meetings` - Include notes where a folder name contains `meetings`
- `folder:/work/meetings` - Include notes only in `work/meetings` (not subfolders)
- `folder:/` - Include notes only in the vault root
- `-folder:archive` - Exclude notes where a folder name contains `archive`
- `-folder:/archive` - Exclude notes only in `archive` (not subfolders)
- `ext:md` - Include notes with extension `md` (`ext:.md` is also supported)
- `-ext:pdf` - Exclude notes with extension `pdf`
- Combine with tags, names, and dates (e.g., `folder:/work/meetings ext:md @thisweek`)

**Dates**

- `@today` - Match notes from today using the default date field
- `@yesterday`, `@last7d`, `@last30d`, `@thisweek`, `@thismonth` - Relative date ranges
- `@2026-02-07` - Match a single day (also supports `@20260207`)
- `@2026` - Match a calendar year
- `@2026-02` or `@202602` - Match a calendar month
- `@2026-W05` or `@2026W05` - Match an ISO week
- `@2026-Q2` or `@2026Q2` - Match a calendar quarter
- `@13/02/2026` - Numeric formats with separators (`@07022026` follows your locale when ambiguous)
- `@2026-02-01..2026-02-07` - Match an inclusive day range (open ends supported)
- `@c:...` or `@m:...` - Target created or modified date
- `-@...` - Exclude a date match

The default date field follows the current sort order. When sorting by name, the date field is configured in Settings → Notes → Date → When sorting by name.

**AND/OR behavior**

`AND` and `OR` operators work in tag/property-only queries (queries that contain only `#tag`, `-#tag`, `#`, `-#`, `.key`, `-.key`, `.key=value`, or `-.key=value` filters). If the query also includes names, dates, task filters, folder filters, or extension filters, `AND` and `OR` are matched as file name words instead.

- Operator query: `#work OR .status=started`
- Mixed query: `#work OR ext:md` (`OR` is matched in file names)

### 7.2 Omnisearch

Full-text search across the vault, filtered to the current folder, subfolders, or selected tags. Requires the [Omnisearch](https://github.com/scambier/obsidian-omnisearch) plugin. If Omnisearch is not installed, search falls back to filter search.

Note previews show Omnisearch result excerpts instead of the default preview text.

**Known limitations**

- **Performance** - Can be slow when searching for fewer than 3 characters in large vaults
- **Path filters** - Folder scoping is sent to Omnisearch for all folder paths except names containing `"` or `,`. Folder names with non-ASCII characters require Omnisearch 1.30.0 or later. Results are always filtered to the current view after Omnisearch returns
- **Limited results** - Omnisearch returns at most 50 results. When searching in a folder, the limit covers the folder and its subfolders, so subfolder matches count toward the limit even when `Show notes from subfolders` is disabled
- **Preview text** - Note previews are replaced with Omnisearch result excerpts, which may not show the actual search match highlight if it appears elsewhere in the file

<br/>

## 8 Custom hotkeys

Edit `.obsidian/plugins/notebook-navigator/data.json` to customize Notebook Navigator hotkeys. Open the file and locate the `keyboardShortcuts` section. Each entry maps an action to one or more key bindings:

```json
"pane:move-up": [ { "key": "ArrowUp", "modifiers": [] }, { "key": "K", "modifiers": [] } ]
```

Add multiple bindings per action to support alternate keys, like the `ArrowUp` and `K` example above. Combine modifiers in one entry by listing each value, for example `"modifiers": ["Mod", "Shift"]`. Keyboard sequences such as `gg` or `dd` are not supported. Reload Obsidian after editing the file.

### 8.1 Modifiers

| Modifier | Key                                       |
| -------- | ----------------------------------------- |
| `Mod`    | Cmd (macOS) / Ctrl (Win/Linux)            |
| `Alt`    | Alt / Option                              |
| `Shift`  | Shift                                     |
| `Ctrl`   | Control (prefer `Mod` for cross-platform) |

### 8.2 Available actions

| Action                            | Default key(s)                    |
| --------------------------------- | --------------------------------- |
| `pane:move-up`                    | ArrowUp                           |
| `pane:move-down`                  | ArrowDown                         |
| `pane:page-up`                    | PageUp                            |
| `pane:page-down`                  | PageDown                          |
| `pane:home`                       | Home                              |
| `pane:end`                        | End                               |
| `pane:rename`                     | Enter (macOS), F2 (Windows/Linux) |
| `pane:delete-selected`            | Delete, Backspace                 |
| `navigation:c

...[truncated]