# Excalidraw

【English | [简体中文](./docs/zh-cn/README.md)】

👉👉👉 Check out and contribute to the new [Obsidian-Excalidraw Community Wiki](https://community.sketch-your-mind.com/Wiki)

The Obsidian-Excalidraw plugin integrates [Excalidraw](https://excalidraw.com/), a feature rich sketching tool, into Obsidian. You can store and edit Excalidraw files in your vault, you can embed drawings into your documents, and you can link to documents and other drawings to/and from Excalidraw. For a showcase of Excalidraw features watch the videos below.

![Excalidraw Screenshot](https://github.com/user-attachments/assets/dde1df97-c6ae-491c-b546-65ec2d625326)

Excalidraw for Obsidian keeps evolving; it is extremely feature‑rich and can feel intimidating at first. The Video Walkthrough below should ease that initial overwhelm. For a comprehensive, searchable knowledge base covering features, settings, scripting, workflows, and visual thinking methods, explore the public [NotebookLM workbook](https://notebooklm.google.com/notebook/42d76a2f-c11d-4002-9286-1683c43d0ab0) (a must‑have learning resource). 

<a href="https://community.sketch-your-mind.com/ee"><img src="https://github.com/zsviczian/obsidian-excalidraw-plugin/blob/master/images/logo-EE.png?raw=true" width="150"></a>

[**Excalidraw Essentials**](https://community.sketch-your-mind.com/ee) is a free course to get started with Excalidraw.

<a href="https://community.sketch-your-mind.com/sym"><img src="https://github.com/zsviczian/obsidian-excalidraw-plugin/blob/master/images/sym-cover.jpg?raw=true" width="150"></a>

If you are curious about the Visual PKM philosophy behind the plugin, consider my book [Sketch Your Mind](https://community.sketch-your-mind.com/sym) and the [Visual Thinking Workshops](https://community.sketch-your-mind.com/vtw). To learn about all the different options available and how they fit together, check out the [Welcome to the Sketch Your Mind Ecosystem](https://community.sketch-your-mind.com/t/welcome-to-the-sketch-your-mind-ecosystem/375) introduction page. Finally, keep the [Excalidraw Plugin Wiki](https://community.sketch-your-mind.com/Wiki) and the [NotebookLM workbook](https://notebooklm.google.com/notebook/42d76a2f-c11d-4002-9286-1683c43d0ab0) at hand, those are essential companions.

## Disclaimer / Disclosure: Plugin Access and Privileges

I treat privacy as a top priority. Apart from the few technical limitations outlined below, Excalidraw is 100% local and runs without network access. Most of the findings published on sites such as [obsidianpluginaudit.com](https://obsidianpluginaudit.com/), [plugin.observer](https://plugin.observer/), and [community.obsidian.md/plugins](https://community.obsidian.md/plugins) can be misleading without proper context.

Obsidian is fundamentally a locally executed web application. Automated code scanners apply the same vulnerability rules used for public-facing websites, even though the risk model inside a local Obsidian vault is very different. For example, patterns such as `innerHTML` or `outerHTML` manipulation are considered problematic on public websites because they can expose visitors to malicious third-party content. In a local-first application such as Obsidian, these risks are significantly different in nature and impact.

Excalidraw for Obsidian is a large and feature-rich tool with many integrations and performance optimizations. Below, I explain how the most common findings reported by these scanners are actually used within the plugin.

When evaluating these findings, please keep the following in mind:

1. Obsidian.md currently does not provide plugin developers with proper mechanisms for deploying local assets such as fonts, auxiliary packages, or official APIs for certain features like Obsidian Publish or PDF generation. As a result, plugin developers sometimes need to rely on workaround solutions such as IPC calls or dynamic code execution (`eval`) to deliver functionality users expect.

2. Excalidraw for Obsidian is not maintained by a company or engineering team. It is a one-person hobby project and an open-source contribution developed alongside a full-time job. If you would like to support continued development and improved code quality, the best way is through financial support via [Ko-fi](https://ko-fi.com/zsolt). Open-source software is not truly “free.” The cost is usually paid in developer time, personal energy, or by supporters who help sustain the project. I will continue striving to improve the codebase, but expectations around enterprise-grade engineering standards for a free community contribution can easily become unrealistic and unsustainable without corresponding support structures.

3. In general, I recommend using the minimum number of plugins necessary for your workflow. Personally, I use around 10–15 plugins and disable plugins when not actively needed. This is not because I distrust plugin safety, but because most Obsidian plugins are hobby-driven community projects, and I believe users should maintain realistic expectations regarding maintenance, complexity, and long-term support.

<details><summary><h3>Detailed Findings</h3></summary>

- **Plugin might make requests to external domains:**
  - To see the complete list of URLs referenced in the code, either used as links, images, or in API calls, open the Obsidian Developer Console (CTRL+SHIFT+i or CMD+OPT+i) and run `ExcalidrawAutomate.printURLsInCodebase()`
  - The plugin works fully offline and locally by default.
  - If you configure API keys for AI features and explicitly use those features, the corresponding AI providers are contacted.
  - The Taskbone OCR service requires a separate API key and explicit user opt-in in plugin settings.
  - Iframely is optionally used to resolve reader-friendly webpage titles when dragging website links into Excalidraw. This feature is disabled by default.
  - The Ko-fi support button, when enabled, downloads its image asset from `cdn.ko-fi.com`.
  - The CJK font package exceeds 12 MB in size. To avoid significantly increasing plugin startup time and bundle size, these fonts are downloaded from GitHub only when required.

- **`requestUrl` and `fetch` calls:**
  - Used for AI integrations and Taskbone OCR functionality.
  - Excalidraw supports embedding images from external sources (local URIs and public URLs). `requestUrl` is used to retrieve those images when needed.
  - The Excalidraw Script Library accesses GitHub to download scripts only when the user explicitly chooses to install them.

- **Excalidraw accesses files in your vault:**
  - To detect legacy `.excalidraw` files and support conversion workflows.
  - To search for and load custom fonts stored inside the vault.
  - To populate file picker dialogs such as “Insert any file.”

- **Clipboard access:**
  - Allows users to copy and paste Excalidraw scenes between Obsidian and excalidraw.com.
  - Allows users to copy links to scene elements and paste them into markdown documents as embeds.

- **Local Storage:**
  - Excalidraw stores image caches locally to improve loading performance for large and complex scenes.
  - Mermaid text-to-diagram chat history is stored locally.
  - Backup versions of drawings are stored locally to support crash recovery.

- **Dynamic Code Execution:**
  - Excalidraw dynamically loads user-created scripts and scripts installed from the Script Library.
  - Excalidraw also dynamically loads parts of the Excalidraw React component and supporting packages. This improves startup performance and supports functionality such as desktop popout windows.

- **Electron remote module privilege IPC bridge calls:**
  - Used to access Electron’s built-in PDF generation capabilities so users can export drawings as PDFs.
  - This avoids bundling additional large PDF libraries, reducing plugin size and improving performance.
  - The process also enables Electron’s native file-save dialog when exporting PDFs.

- **Document-level keyboard listener:**
  - Comes from the core excalidraw.com component to support keyboard shortcuts and interactions.

- **Direct Node.js file system access allowing access outside the vault:**
  - Used exclusively to support embedding images located outside the Obsidian vault into Excalidraw scenes.

</details>

## Video Walkthrough
<a href="https://youtu.be/P_Q6avJGoWI" target="_blank"><img src="https://github.com/zsviczian/obsidian-excalidraw-plugin/assets/14358394/da34bb33-7610-45e6-b36f-cb7a02a9141b" width="300"/></a>
<a href="https://youtu.be/o0exK-xFP3k" target="_blank"><img src="https://user-images.githubusercontent.com/14358394/156931370-aa4d88de-c4a8-46cc-aeb2-dc09aa0bea39.jpg" width="300"/></a> 
<a href="https://youtu.be/QKnQgSjJVuc" target="_blank"><img src="https://raw.githubusercontent.com/zsviczian/obsidian-excalidraw-plugin/master/images/thumbnail-getting-started.jpg" width="300"/></a>

### Here's my complete catalog of videos:
<a href="https://community.sketch-your-mind.com/t/a-visual-catalogue-of-all-my-youtube-videos/701"><img width="380" alt="image" src="https://github.com/zsviczian/obsidian-excalidraw-plugin/blob/master/images/catalogue.jpg?raw=true"></a>
<br>

<details><summary>10 Part (slightly outdated) Video Walkthrough</summary>
<a href="https://youtu.be/sY4FoflGaiM" target="_blank"><img src="https://user-images.githubusercontent.com/14358394/125160304-7f211180-e17c-11eb-8363-c52723de1ffd.jpg" width="100" style="vertical-align: middle;"/>&nbsp;&nbsp;1  Getting Started</a><br>
<a href="https://youtu.be/Iy_oVTq12Gw" target="_blank"><img src="https://user-images.githubusercontent.com/14358394/125160312-8a743d00-e17c-11eb-9fa2-490ef4cbd59e.jpg" width="100" style="vertical-align: middle;"/>&nbsp;&nbsp;2  Basic shapes and features</a><br>
<a href="https://youtu.be/QOL1KF7-kdc" target="_blank"><img src="https://user-images.githubusercontent.com/14358394/125160323-96f89580-e17c-11eb-9bce-8eb1067a51bb.jpg" width="100" style="vertical-align: middle;"/>&nbsp;&nbsp;3  Grouping elements</a><br>
<a href="https://youtu.be/aSgcbfspvfo" target="_blank"><img src="https://user-images.githubusercontent.com/14358394/125160332-9f50d080-e17c-11eb-98e9-fec60fe147d9.jpg" width="100" style="vertical-align: middle;"/>&nbsp;&nbsp;4  The stencil-library</a><br>
<a href="https://youtu.be/MaJ5jJwBRWs" target="_blank"><img src="https://user-images.githubusercontent.com/14358394/125160341-a546b180-e17c-11eb-9de8-d87fdc844c9c.jpg" width="100" style="vertical-align: middle;"/>&nbsp;&nbsp;5  Embedding</a><br>
<a href="https://youtu.be/MXzeCOEExNo" target="_blank"><img src="https://user-images.githubusercontent.com/14358394/125160346-aa0b6580-e17c-11eb-930b-4024807040d1.jpg" width="100" style="vertical-align: middle;"/>&nbsp;&nbsp;6  Links</a><br>
<a href="https://youtu.be/R0IAg0s-wQE" target="_blank"><img src="https://user-images.githubusercontent.com/14358394/125160354-b2fc3700-e17c-11eb-81af-9e71e461f6dd.jpg" width="100" style="vertical-align: middle;"/>&nbsp;&nbsp;7  Markdown</a><br>
<a href="https://youtu.be/ibdS7ykwpW4" target="_blank"><img src="https://user-images.githubusercontent.com/14358394/125160360-b8f21800-e17c-11eb-8bd8-79d4e3f6e92d.jpg" width="100" style="vertical-align: middle;"/>&nbsp;&nbsp;8  Templates</a><br>
<a href="https://youtu.be/VRZVujfVab0" target="_blank"><img src="https://user-images.githubusercontent.com/14358394/125160367-bdb6cc00-e17c-11eb-92f1-6f59faea85fd.jpg" width="100" style="vertical-align: middle;"/>&nbsp;&nbsp;9  Excalidraw Automate</a><br>
<a href="https://youtu.be/D1iBYo1_jjc" target="_blank"><img src="https://user-images.githubusercontent.com/14358394/125160374-c3141680-e17c-11eb-8cc2-dfaffd903d15.jpg" width="100" style="vertical-align: middle;"/>&nbsp;&nbsp;10  Miscellaneous</a><br>
</details>
<details><summary>Embedding stuff into Excalidraw</summary>
<a href="https://www.youtube.com/watch?v=_c_0zpBJ4Xc&" target="_blank"><img src="https://user-images.githubusercontent.com/14358394/138607067-ccb62f92-48a4-4880-ac6e-68c1bf86ac2c.png" width="100" style="vertical-align: middle;"/>&nbsp;&nbsp;Image Elements</a><br>
<a href="https://youtu.be/r08wk-58DPk" target="_blank"><img src="https://user-images.githubusercontent.com/14358394/143732412-1c65227e-4381-406d-847a-b001ab3506ca.jpg" width="100" style="vertical-align: middle;"/>&nbsp;&nbsp;LaTex Demo</a><br>
<a href="https://youtu.be/tsecSfnTMow" target="_blank"><img src="https://user-images.githubusercontent.com/14358394/143732440-90bfa029-8615-462e-ada3-c903d71a82c9.jpg" width="100" style="vertical-align: middle;"/>&nbsp;&nbsp;Markdown embeds</a><br>
<a href="https://youtu.be/K6qZkTz8GHs" target="_blank"><img src="https://user-images.githubusercontent.com/143783906-15cee494-c6d5-4495-a2ca-74634e4e7355.jpg" width="100" style="vertical-align: middle;"/>&nbsp;&nbsp;Markdown embeds advanced features</a><br>
<a href="https://youtu.be/Etskjw7a5zo" target="_blank"><img src="https://user-images.githubusercontent.com/14358394/156931461-0979b821-315a-41dd-86f1-31d169b7c127.jpg" width="100" style="vertical-align: middle;"/>&nbsp;&nbsp;Link to Elements, Vertical text alignment, Markdown Styling</a><br>
</details>
<details><summary>The Script Engine Store - Excalidraw Automation</summary>
<a href="https://youtu.be/hePJcObHIso" target="_blank"><img src="https://user-images.githubusercontent.com/14358394/145684531-8d9c2992-59ac-4ebc-804a-4cce1777ded2.jpg" width="100" style="vertical-align: middle;"/>&nbsp;&nbsp;Introducing the Script Engine</a><br>
<a href="https://youtu.be/lzYdOQ6z8F0" target="_blank"><img src="https://user-images.githubusercontent.com/14358394/147889174-6c306d0d-2d29-46cc-a53f-3f0013cf14de.jpg" width="100" style="vertical-align: middle;"/>&nbsp;&nbsp;Script Engine Store</a><br>
</details>
<details><summary>Working with colors</summary>
<a href="https://youtu.be/6PLGHBH9VZ4" target="_blank"><img src="https://user-images.githubusercontent.com/14358394/194773147-5418a0ab-6be5-4eb0-a8e4-d6af21b1b483.png" width="100" style="vertical-align: middle;"/>&nbsp;&nbsp;Colors - Excalidraw Basics (Custom)</a><br>
<a href="https://youtu.be/epYNx2FSf2w" target="_blank"><img src="https://user-images.githubusercontent.com/14358394/194773211-9e871be7-0795-4dc7-947e-c6c275e690d0.png" width="100" style="vertical-align: middle;"/>&nbsp;&nbsp;Excalidraw color palettes (Custom)</a><br>
<a href="https://youtu.be/Amhlv6r9WvM" target="_blank"><img src="https://user-images.githubusercontent.com/14358394/194773268-400cfb1b-6bde-45e0-9e4b-91bbaa461cf0.png" width="100" style="vertical-align: middle;"/>&nbsp;&nbsp;"Artistic" Color Gradients</a><br>
<a href="https://youtu.be/r9oB1SlK1GU" target="_blank"><img src="https://user-images.githubusercontent.com/14358394/194773527-ef35c8b9-1a6d-4415-9c7e-b667fb17535d.png" width="100" style="vertical-align: middle;"/>&nbsp;&nbsp;Simple rules for beautiful sketches</a><br>
<a href="https://youtu.be/7gJDwNgQ6NU" target="_blank"><img src="https://user-images.githubusercontent.com/14358394/195988535-a133a9b9-d094-45ba-ba64-c994b9a1e0ef.png" width="100" style="vertical-align: middle;"/>&nbsp;&nbsp;ColorMaster Scripting</a><br>
</details>
<details><summary>Links and block references</summary>
<a href="https://youtu.be/qiKuqMcNWgU" target="_blank"><img src="https://user-images.githubusercontent.com/14358394/171635214-30533c45-94fa-436e-83a9-b2ec99f190e2.jpg" width="100" style="vertical-align: middle;"/>&nbsp;&nbsp;6 strategies for linking your visual thoughts v4</a><br>
<a href="https://youtu.be/yZQoJg2RCKI" target="_blank"><img src="https://user-images.githubusercontent.com/14358394/185791706-3d9983ab-7cb1-4b27-a016-30c039d84e34.jpg" width="100" style="vertical-align: middle;"/>&nbsp;&nbsp;Block reference parts of images</a><br>
<a href="https://youtu.be/Etskjw7a5zo" target="_blank"><img src="https://user-images.githubusercontent.com/14358394/156931461-0979b821-315a-41dd-86f1-31d169b7c127.jpg" width="100" style="vertical-align: middle;"/>&nbsp;&nbsp;Link to Elements, Vertical text alignment, Markdown Styling</a><br>
<a href="https://youtu.be/2Y8OhkGiTHg" target="_blank"><img src="https://user-images.githubusercontent.com/14358394/152585752-7eb0371f-0bab-40f6-a194-3b48e5811735.jpg" width="100" style="vertical-align: middle;"/>&nbsp;&nbsp;How to guide for the Excalidraw-native hyperlinks</a><br>
</details>
<details><summary>Powertools</summary>
<a href="https://youtu.be/NOuddK6xrr8" target="_blank"><img src="https://user-images.githubusercontent.com/14358394/147283367-e5689385-ea51-4983-81a3-04d810d39f62.jpg" width="100" style="vertical-align: middle;"/>&nbsp;&nbsp;Sticky Notes (word wrapping)</a><br>
<a href="https://youtu.be/eKFmrSQhFA4" target="_blank"><img src="https://user-images.githubusercontent.com/14358394/149659524-2a4e0a24-40c9-4e66-a6b1-c92f3b88ecd5.jpg" width="100" style="vertical-align: middle;"/>&nbsp;&nbsp;Fourth Font</a><br>
<a href="https://youtu.be/vlC1-iBvIfo" target="_blank"><img src="https://user-images.githubusercontent.com/14358394/199207784-8bbe14e0-7d10-47d7-971d-20dce8dbd659.png" width="100" style="vertical-align: middle;"/>&nbsp;&nbsp;SVG import</a><br>
<a href="https://youtu.be/7gu4ETx7zro" target="_blank"><img src="https://user-images.githubusercontent.com/14358394/202916770-28f2fa64-1ba2-4b40-a7fe-d721b42634f7.png" width="100" style="vertical-align: middle;"/>&nbsp;&nbsp;OCR</a><br>
<a href="https://youtu.be/U2LkBRBk4LY" target="_blank"><img src="https://user-images.githubusercontent.com/14358394/159369910-6371f08d-b5fa-454d-9c6c-948f7e7a7d26.jpg" width="100" style="vertical-align: middle;"/>&nbsp;&nbsp;Bind/unbind text from container, Frontmatter tags to customize export</a><br>
<a href="https://youtu.be/uZz5MgzWXiM" target="_blank"><img src="https://user-images.githubusercontent.com/14358394/211054371-8872e01a-77d6-4afc-a0c2-86a55410a8d3.png" width="100" style="vertical-align: middle;"/>&nbsp;&nbsp;Custom pen support</a><br>
</details>
<details><summary>Quality of life improvements</summary>
<a href="https://youtu.be/qbPIAZguJeo" target="_blank"><img src="https://user-images.githubusercontent.com/14358394/151705333-54e9ffd2-0bd7-4d02-b99e-0bd4e4708d4d.jpg" width="100" style="vertical-align: middle;"/>&nbsp;&nbsp;Mobile Support</a><br>
<a href="https://youtu.be/2v9TZmQNO8c" target="_blank"><img src="https://user-images.githubusercontent.com/14358394/153676009-6f86b2d7-c248-49a2-b802-be21c6999e4f.jpg" width="100" style="vertical-align: middle;"/>&nbsp;&nbsp;Tray-mode and Customizable Color Palette</a><br>
<a href="https://youtu.be/xHPGWR3m0c8" target="_blank"><img src="https://user-images.githubusercontent.com/14358394/154821232-a404b6cf-72fb-4ce4-9d53-619132dce491.jpg" width="100" style="vertical-align: middle;"/>&nbsp;&nbsp;Compressed JSON and improved save/sync support</a><br>
<a href="https://youtu.be/gMIKXyhS-dM" target="_blank"><img src="https://user-images.githubusercontent.com/14358394/156931428-b2269fd9-87bd-43ab-8558-5572f40dff93.jpg" width="100" style="vertical-align: middle;"/>&nbsp;&nbsp;The Obsidian Tools Panel</a><br>
<a href="https://youtu.be/4N6efq1DtH0" target="_blank"><img src="https://user-images.githubusercontent.com/14358394/158008902-12c6a851-237e-4edd-a631-d48e81c904b2.jpg" width="100" style="vertical-align: middle;"/>&nbsp;&nbsp;Eraser, left-handed mode, improved filename configuration</a><br>
</details>

### Beta testing
The plugin follows a monthly release schedule. If you want to receive more frequent updates with new features (e.g. shiny new stuff available on excalidraw.com, but not yet in Obsidian) and minor bug fixes, then [join the beta community](https://community.sketch-your-mind.com/t/about-the-beta-releases-category/329).

[![Thumbnail - 20240803 Excalidraw Release Approach (Custom)](https://github.com/user-attachments/assets/ab40648c-f73f-4bda-a416-52839f918f2a)](https://youtu.be/2poSS-Z91lY)

[![Excal

...[truncated]