<!-- title({titleCase: true, postfix: " Plugin"}) -->

# Yanki Obsidian Plugin

<!-- /title -->

![Yanki Obsidian Banner](./assets/banner.gif)

<!-- badges({ githubRelease: true, npm: false, obsidianDownloads: true }) -->

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/license/mit)
[![CI](https://github.com/kitschpatrol/yanki-obsidian/actions/workflows/ci.yml/badge.svg)](https://github.com/kitschpatrol/yanki-obsidian/actions/workflows/ci.yml)
[![GitHub Release](https://img.shields.io/github/v/release/kitschpatrol/yanki-obsidian?label=Release)](https://github.com/kitschpatrol/yanki-obsidian/releases/latest)
[![Obsidian Downloads](https://img.shields.io/badge/dynamic/json?logo=obsidian&color=%23A88BFA&label=Downloads&query=%24%5B%22yanki%22%5D.downloads&url=https%3A%2F%2Fraw.githubusercontent.com%2Fobsidianmd%2Fobsidian-releases%2Fmaster%2Fcommunity-plugin-stats.json)](https://community.obsidian.md/plugins/yanki)

<!-- /badges -->

<!-- short-description -->

**Obsidian plugin to sync flashcards from a folder in your vault to Anki. Pure Markdown syntax. No fuss.**

<!-- /short-description -->

<!-- toc({ depth: 2 }) -->

## Table of contents

- [Overview](#overview)
- [Quick start](#quick-start)
- [Features](#features)
- [Markdown note types](#markdown-note-types)
- [Usage](#usage)
- [FAQ](#faq)
- [Privacy and security](#privacy-and-security)
- [Background](#background)
- [Maintainers](#maintainers)
- [Acknowledgments](#acknowledgments)
- [Contributing](#contributing)
- [License](#license)

<!-- /toc -->

## Overview

Yanki is a plugin for Obsidian that syncs a folder (or folders) of notes from your vault to Anki.

The primary novelty of its approach is in how Markdown is translated into Anki notes, and how folders are translated into Anki decks according to a few simple rules:

- **One** Obsidian note maps to **one** Anki note.

- The **structure** of the Markdown in your Obsidian notes determines the **types** of Anki notes they become. No extra syntax or Anki-specific markup is required — just pure Markdown.

  This also means that your flashcard notes remain nice and legible in Obsidian, and you don't have to deal with the cognitive switch of ` ```fenced``` ` regions and Anki's rather noisy templating syntax.

- The **parent folder** of your notes in your Obsidian vault determines their **deck name** in Anki, with any intermediate hierarchies created as needed.

## Quick start

1. **Prerequisites**

- The [Obsidian desktop application](https://obsidian.md/download), with both the app and **installer version** at 1.9.12+. Yanki is tested on Windows, macOS, and Linux.
- The [Anki desktop application](https://apps.ankiweb.net), version 26.08+. (Linux users should install from the Anki Website, [issues have been reported](#my-obsidian-vault-links-arent-opening-on-linux) with Flatpak distributions.)
- The [AnkiConnect](https://ankiweb.net/shared/info/2055492159) add-on, version 26.10.14.0 or newer.

  To install the AnkiConnect add-on, open the Anki desktop application and select _Tools → Add-ons_ from the menu, click _Get Add-ons..._, and then enter the code `2055492159` in the field to get AnkiConnect.

  AnkiConnect may ask for your permission in the Anki application to connect to Obsidian on the first sync.

  If you encounter trouble with AnkiConnect, please see [the manual configuration procedure](#ive-installed-ankiconnect-but-am-still-getting-connection-errors).

  _Anki versions back to 2.1.55 and AnkiConnect versions back to 24.6.17.0 should work, but please upgrade both to the latest before [reporting a Yanki Obsidian issue on GitHub](https://github.com/kitschpatrol/yanki-obsidian/issues)._

2. **Plugin installation**

   Search for `yanki` in Obsidian's community plugins browser, then click "Install". Or, install it from [the Obsidian website](https://community.obsidian.md/plugins/yanki).

3. **Setup**

   Enable the plugin, and go to its settings tab to select which folders of notes you'd like to sync to Anki. See the section [Markdown note types](#markdown-note-types) on how to format your notes to create different types of Anki cards.

4. **Sync**

   Initiate a sync from Obsidian to Anki using the `Yanki: Sync flashcard notes to Anki` command. You can also trigger a sync manually via the button in the Yanki settings tab.

5. **Study**

   Pop over to the Anki app, and you should see the Obsidian notes from your selected folders organized into decks in Anki that match your vault's folder hierarchy.

## Features

### One Obsidian note = one Anki note

Avoid the complexity of mixing and matching multi-note and single-note syntaxes. One note in Obsidian always yields one Anki note.

### Vault folder hierarchy = Anki deck hierarchy

Yanki uses your Obsidian note's parent folder name as the deck name. Complex folder hierarchies are also supported — Anki decks will be created and nested as needed to match the structure of your vault.

### Embrace Anki's default note types

More note types, more problems.

Yanki _only_ supports turning Markdown into the "Basic", "Basic (and reversed card with extra)", "Basic (type in the answer)", and "Cloze" note types that ship as defaults in the Anki App.

### Infer Anki note type from Markdown structure

Since the number of supported note types is small, the type of Anki note to create from a given Obsidian note can be inferred from a few simple rules about the structure of the Markdown.

For example, a Basic note is any Markdown file with a `---` thematic break splitting the front and back of the card:

```md
I'm the front of the card.

---

I'm the back of the card.
```

That's it, no extra metadata or Anki-specific markup is required. You're free to use additional Markdown syntax to style the note to your liking.

The structural cues for all four supported note types are described [later in this document](#markdown-note-types).

### Tag support

The values in the `tags` array of your note's properties will be added as tags in Anki. This gives nice interoperability with Obsidian's tag system, which also recognizes the frontmatter `tags` array.

Detecting Obsidian `#tags` in the document body is not currently supported, but plugins like Victor Tao's [Obsidian Linter](https://github.com/platers/obsidian-linter) can automate tag migration from the document body to frontmatter, where Yanki (and thus Anki) can see them.

### Support for Obsidian WikiLinks

Easily jump back to source notes in Obsidian while studying in the Anki desktop application.

The Yanki plugin detects your vault's name, and automatically turns any internal `[[WikiLinks]]` in your notes into deep `obsidian://` protocol links, which you can click through in Anki to get back to the source in Obsidian.

### Fancy Markdown

An extended palette of Markdown syntax is available out of the box, mirroring (almost) all the features supported by Obsidian:

- [GitHub Flavored Markdown](https://github.github.com/gfm/), including `| tables |`, `~~strike-through~~`, `- [x] task lists`, and auto-links.
- Syntax highlighting via [Shiki](https://shiki.style).
- GitHub-style [Alerts](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax#alerts).
- The aforementioned [WikiLinks](https://github.com/Python-Markdown/markdown/blob/master/docs/extensions/wikilinks.md).
- [LaTeX formatted mathematical expressions](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/writing-mathematical-expressions) via Anki's built-in [MathJax](https://www.mathjax.org) rendering support.
- The [`==highlights==`](https://github.com/ipikuka/remark-flexible-markers) syntax.
- Compact [furigana](https://en.wikipedia.org/wiki/Furigana) / [Ruby](https://en.wikipedia.org/wiki/Ruby_character) syntax specified by [DenDen Markdown](https://conv.denshochan.com/markdown#ruby), for example: `{東京|とうきょう}` renders as `<ruby>東京<rp>(</rp><rt>とうきょう</rt><rp>)</rp></ruby>`. This matches support in Obsidian provided by the [Markdown Furigana](https://github.com/steven-kraft/obsidian-markdown-furigana) plugin.
- Obsidian's [block links](https://obsidian.md/help/links#Link+to+a+block+in+a+note), e.g. `[[Some Note#^37066d]]`
- Obsidian's [heading links](https://obsidian.md/help/links#Link+to+a+heading+in+a+note), e.g. `[[Some Note#Heading]]`

### Intelligent syncing

Your local Obsidian Markdown notes are the single point of truth for what will end up in Anki, but Yanki knows to leave your other Anki notes alone.

When you edit a local Obsidian note, Yanki makes every effort to update rather than recreate it in the Anki database so that review progress is preserved.

When you _do_ want to delete something, it's as simple as deleting it from Obsidian, and it will be removed from the Anki database on the next sync. Protections are in place to prevent deleting Anki notes that weren't initially created by Yanki.

If you use [AnkiWeb](https://ankiweb.net/) to sync your notes to the cloud, Yanki will also trigger this next step in the sync, automating the flow from Markdown → Anki → AnkiWeb in one shot. (Configurable via a [setting](#push-to-ankiweb).)

### Existing notes are untouched

Yanki tags the notes it's in charge of with a hidden field, so it will never touch your existing Anki notes. Yanki also creates and manages the note types it needs in Anki, so your existing note types and customizations remain untouched.

### Note name management

The "one Obsidian note = one Anki note" premise can make for a lot of individual note files, and thinking up and renaming notes as their content is revised can be tedious. So, if you want, Yanki can manage the names of your note files based on their content.

Yanki looks inside each note, and extracts either the text of the "prompt" (e.g. the front of the card in most cases), or the "response" (e.g. the back of the card in most cases) to use as the filename. Truncation, deduplication, and sanitization are all taken care of.

Edge cases are carefully managed to ensure that there's always _some kind_ of best-effort semantically valuable file name assigned.

### Media asset sync

Yanki can sync images, videos, and audio files embedded in your Obsidian notes to Anki's media asset management system. At your option, it can sync local assets, or assets linked via URL, or both, or none.

Yanki automatically manages change detection when you revise assets, and also manages clean-up of synced media assets in Anki when you delete either entire notes or embedded assets in Obsidian.

Both wiki-style `![[something.png]]` and `![markdown](style.png)` asset embedding syntaxes are supported.

## Markdown note types

Yanki automatically infers the _type_ of Note you'd like to create in Anki based on the presence or absence of certain elements in your Markdown.

The rules were designed with Markdown's semantic precedents and visual nature in mind, and are based on the note types that are included as defaults in a fresh installation of Anki. Yanki creates and manages the required note types automatically. Do not create or edit them manually.

The most minimal examples to "trigger" different note types are shown below, but the implementation can handle additional weirdness and will generally do the right thing if it encounters elements that might indicate conflicting note types.

There's no such thing as an invalid note: In the absence of enough Markdown syntax to differentiate your intended note type, Yanki will resort to creating a Basic note with all content on the front, and nothing on the back. This preserves the guarantee that all notes in selected flashcard folders will be synced to Anki one way or another.

You're free to use additional Markdown in your notes to style and structure the front and back of your flashcard notes.

The four supported note types are described below. See the [Yanki Demo Vault](https://github.com/kitschpatrol/yanki-obsidian/tree/main/examples/Yanki%20Demo%20Vault) for additional examples.

### Basic

A **basic** card is created from any file with a `---`:

```md
This is the front of the card

---

This is the back of the card
```

### Basic (and reversed card with extra)

Doubling up the `---` identifies the note as being **reversible** (and will result in the generation of two cards in Anki).

_Mnemonic: Twice the `---` for twice the cards._

```md
Sometimes the answer is the question

---

---

Sometimes the question is the answer
```

Yanki deviates slightly from the default Anki reversed card note type by supporting adding optional "extra" content that will appear on the back of both generated cards:

```md
Sometimes the answer is the question

---

---

Sometimes the question is the answer

---

This will appear on the back of both generated cards
```

### Basic (type in the answer)

If the last statement in the Markdown file is `_emphasized like this_`, it becomes the type-in-the-answer text in Anki.

<em>Mnemonic: The syntax resembles a `_blank to be filled in_`.</em>

```md
Jazz isn't dead

_It just smells funny_
```

### Cloze

Text that is `~~struck through~~` with the [somewhat esoteric double-tilde syntax](https://github.github.com/gfm/#strikethrough-extension-) will be hidden in the card as a _cloze_ deletion:

_Mnemonic: The `~~strike through~~` implies redaction._

```md
All will be ~~revealed~~.
```

Multiple clozes are supported, which will create additional cards. You can add a `---` to include back-of-card information as well. Hints are also supported, and are indicated by giving the hint text `_emphasis_` at the end of the cloze strike-through:

```md
~~All~~ will be ~~revealed _here's a hint_~~.

---

Additional revelations on the back of the card.
```

#### Advanced cloze numbering

By default, clozes are numbered incrementally. For example, the Markdown:

```md
~~All~~ will be ~~revealed _here's a hint_~~.
```

Is turned into the following Anki markup:

```text
{{c1::All}} will be {{c2::revealed::<em>here's a hint</em>}}
```

In [rare cases](https://github.com/kitschpatrol/yanki-obsidian/issues/4), you might want to take control over cloze numbering — perhaps you want to reveal multiple clozes simultaneously on a single card, or group certain clozes together on a particularly cloze-heavy note.

To support this, Yanki offers some optional extra syntax. A leading one- or two-digit number at the front of your clozed content will be interpreted as the cloze number:

For example:

```md
~~1 All~~ will be ~~1 revealed _here's a hint_~~.
```

Yields the following Anki markup:

```text
{{c1::All}} will be {{c1::revealed::<em>here's a hint</em>}}
```

The difference is subtle, but note the matching `{{c1`s. This markup yields a single card where both `All` and `revealed` are revealed simultaneously.

_Note: While you can encloze images, math equations, and other inline-styled syntax, clozing over multiple lines or block elements is not currently supported._

_Note: If you delete one of several clozes from an existing note, previous cards associated with the now-missing cloze will linger in Anki's database. While studying, you may see the message "No cloze found on card. Please either add a cloze deletion, or use the Empty Cards tool." In these cases, you must run the "Tools → Empty Cards..." command from Anki desktop application menu bar._

_Warning: If you delete one of several implicitly numbered clozes (e.g. `~~hidden~~`) from a note, then study progress will "move" from one cloze to another. For example, if you have three clozes in a note, but then delete the second cloze and sync to Anki, then what was previously the "third" cloze becomes the new "second" cloze, inheriting study progress associated with the now-deleted second cloze. If you plan on editing your cloze notes heavily after the fact, consider using explicit numbering syntax (e.g. `~~1 hidden~~`) instead._

## Usage

### Commands

The Yanki plugin provides a single command, which works as advertised:

**`Yanki: Sync flashcard notes to Anki`**

### Settings

#### Anki flashcard folders

##### Watched folder list

> [!CAUTION]
>
> Use care when editing or deleting folders from this list, since notes from the removed folders will be deleted from Anki (along with their review statistics) on the next sync.

Yanki will sync notes in the vault folders specified here to Anki.

Anki decks will be created automatically to match the hierarchy of your Obsidian folders.

Selecting multiple folders from different parts of your vault is fine, they'll just end up in different Anki decks.

Folder syncing is always recursive: You can add a top-level folder to the watched folder list, and all sub-folders will be synced as well under eponymous deck names.

In addition to adding / removing entries from settings, you can also add or remove folders from the watched folder list via /context menus in the Obsidian File explorer side bar. (The "Add to Yanki" and "Remove from Yanki" entries.)

The way that folders and flashcard notes are mapped to Anki decks is somewhat nuanced to accommodate the case of syncing the root folder of a vault.

In general: **Decks are created, as needed, _if there is a note in a given part of the folder hierarchy_.**

For example, syncing `/Flashcards` with this folder structure:

```plaintext
📂 Flashcards
└── 📂 Subdeck
   ├── 📝 Note A.md
   └── 📝 Note B.md
```

Will yield the following deck in Anki, because `/Flashcards` does not contain multiple items:

```plaintext
Subdeck
```

If you add a second folder to `/Flashcards` in Obsidian, you still won't get a `Flashcards` deck in Anki since it doesn't contain any notes directly, for example:

```plaintext
📁 Flashcards
├── 📁 Subdeck
│  ├── 📝 Note 1.md
│  └── 📝 Note 2.md
└── 📁 Subdeck B
   ├── 📝 Note 1.md
   └── 📝 Note 2.md
```

Yields the following decks in Anki:

```plaintext
Subdeck
Subdeck B
```

If you then add a _note_ to the root of `/Flashcards` in Obsidian:

```plaintext
📁 Flashcards
├── 📝 Note 1.md
├── 📁 Subdeck
│  ├── 📝 Note 1.md
│  └── 📝 Note 2.md
└── 📁 Subdeck B
   ├── 📝 Note 1.md
   └── 📝 Note 2.md
```

Then you'll get the full hierarchy in Anki:

```plaintext
Flashcards
Flashcards::Subdeck
Flashcards::Subdeck B
```

The idea here is that you can sync a folder of folders in Obsidian, without necessarily including top-level folder as a deck. (For example in my personal use of Yanki, I have an `/Anki` folder in the root of my Obsidian vault with many subfolders that I sync, but I don't want all of my synced cards to be inside an `Anki` deck.)

> [!TIP]
>
> If you really want to put multiple decks in a noteless parent deck, you can add a note in the parent deck's folder in Obsidian, and then suspend the card in Anki after the next sync.
>
> _Thank you to user [mzietzke](https://github.com/mzietzke) for this suggestion._

##### Ignore folder notes

When enabled, notes matching the name of their parent folder will not be synced. This is useful if you use the [folder notes](https://github.com/LostPaul/obsidian-folder-notes) plugin to keep a top-level note per folder.

_Default: Enabled_

#### Sync settings

##### Push to AnkiWeb

There are (potentially) three places your note data lives:

1. The Obsidian application — Markdown notes, the single source of truth.
2. The Anki application — The local database of notes.
3. AnkiWeb — Anki's first-party note syncing service, which brings your notes to the browser and the Anki mobile app.

"Syncing" in Yanki is focused on going from 1 → 2, but when the "Push to AnkiWeb" option is enabled, Yanki will ask the Anki Desktop application to take care of syncing from 2 → 3. (Basically the equivalent of pushing the "Sync" button in the Anki Desktop app.)

This happens on a best-effort basis, since Yanki doesn't get any feedback on whether syncing forward to AnkiWeb worked or not, so your mileage may vary.

_Default: Enabled_

##### Sync media assets

Copy an

...[truncated]