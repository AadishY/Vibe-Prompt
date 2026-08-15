# 🤖 AI Agent Instructions (`agent.md`)

This document guides AI coding assistants (Antigravity, Cursor, Claude, Copilot, ChatGPT) on how to maintain, extend, and add new prompts to this repository.

---

## 🎯 Repository Purpose

**Vibe Coding Prompts** is a curated, high-quality collection of complete prompt blueprints for building aesthetic, viral web applications. Each prompt entry contains:
1. **The Visual / Artwork Prompt** (Image generation prompt for Midjourney, ChatGPT, Flux, Recraft).
2. **The Full Code Generation Prompt** (Next.js, Vite, React, Tailwind CSS prompt for Claude, Cursor, v0, etc.).
3. **Reference Links** (Live site links and original source documentation).
4. **Visual UI Previews** (Screenshots showing the design aesthetics and features).

---

## 🏗️ Repository Structure Standard

```text
Prompt/
├── README.md                                  # Main showcase index & gallery table
├── agent.md                                   # This instruction file for AI agents
├── .gitignore                                 # Git ignore file (excludes desktop.ini, etc.)
└── <site-type-or-prompt-name>/                # Individual prompt directory (lowercase or human-readable)
    ├── README.md                              # Complete prompt blueprint, terms, and guide
    ├── preview.png                            # Primary UI screenshot (16:9 recommended)
    └── [additional-screenshots].png           # Secondary UI previews or showcase cards
```

---

## 📋 Standard Workflow for Adding a New Prompt

When the user requests: *"Add a new prompt for [Site Type / URL]"*, execute the following 5 steps:

### Step 1: Ingest and Extract Content
- Fetch live site content or documentation links provided by the user (Notion, Runable, tweets, GitHub repos, blog posts).
- Extract:
  - **Site Title & Concept**
  - **Live URL(s)** (e.g. `https://playlist.runable.site/`)
  - **Source Guide URL(s)**
  - **Full Artwork Prompt** (with all placeholder parameters like `[SETTING]`, `[ERA]`, `[PALETTE]`)
  - **Full Code Prompt** (with full tech stack, layout specs, state management, animations, gotchas)
  - **Prerequisites & Tooling** (e.g. Node versions, CLI tools like `yt-dlp`)

### Step 2: Handle Images & Assets
- If screenshots or image files are in the root directory:
  - Move/rename the primary UI preview to `<site-folder>/preview.png`.
  - Move/rename any secondary preview images to `<site-folder>/<descriptive-name>.png`.
- Ensure all relative image paths in markdown use `./preview.png`.
- Clean up any stray root-level screenshots or temporary files.

### Step 3: Create the Subfolder `README.md`
Inside `<site-folder>/README.md`, follow this exact template:

```markdown
# [Emoji] [Site Title / Concept]

> **Example Live Site:** [https://example.com/](https://example.com/)  
> **Original Source Guide:** [Source Name](https://source-link.com)

---

## 📸 Preview

![Preview Title](./preview.png)

---

## ⚠️ Read This First — Terms of Use
[Include any copyright, legal, or API policy disclaimers if applicable]

---

## 🛠️ Before You Start
[Asset dimensions table, tooling requirements like Node / yt-dlp, and key tips]

---

## 🎨 1. The Artwork Prompt (Paste into ChatGPT / Midjourney)
[Fill-in variables block + Complete locked art style prompt]

---

## 💻 2. The Code Generation Prompt (Paste into Claude / Cursor / ChatGPT)
[Complete copy-pasteable prompt with Stack, Architecture, UI Specs, and Gotchas]
```

### Step 4: Update the Root `README.md` Gallery Table
Add a new row to the table under `## 📚 Prompt Gallery & Index` in `Prompt/README.md`:

```markdown
| [Category] | **[Site Concept]** | <img src="./[folder-name]/preview.png" width="220" alt="Preview"/> | [📁 View Prompt](./[folder-name]/) | [🔗 Live Demo]([URL]) |
```

### Step 5: Git Cleanliness & Sanity Check
- Verify that OS junk files (`desktop.ini`, `Thumbs.db`) are NOT present or tracked.
- Ensure all markdown links (`file:///...` or relative `./...`) are valid and work properly.
- Commit all additions with a clean, standard git commit message:
  `feat: add [site-name] prompt and visual assets`

---

## 🚫 Rules & Anti-Patterns for AI Agents
- ❌ **Never truncate prompts:** Always preserve the entire prompt text, parameters, and gotchas.
- ❌ **Never leave images loose in root:** Always move images into their respective subfolder.
- ❌ **Never forget the root index:** Always update the root `README.md` table when a new prompt is added.
- ❌ **Never commit OS junk:** Ensure `desktop.ini` and temporary cache files are excluded.
