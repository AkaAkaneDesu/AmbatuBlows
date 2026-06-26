# 🔄 Workspace Handoff & Session Portability Guide

> [!IMPORTANT]
> **To the Next AI Agent:** Read this document immediately to load the user's workspace context, active tasks, design rules, and project directories.

---

## 🤖 Instructions for the Next Agent

Welcome! You are pair programming with the user in the workspace `c:/AntiGravity Stuff (No delete pls T-T)`. Before writing any code or initiating plans, please align with the following:

1. **Active Task**: Continue working on the **Frontier AI Model Poster Series** in the [AI_Models_Catalogue](file:///c:/AntiGravity%20Stuff%20%28No%20delete%20pls%20T-T%29/AI_Models_Catalogue) directory.
2. **Coding Style Rules**: You must adhere to the **Ponytail (lazy senior dev mode)** rules located in [.agents/AGENTS.md](file:///c:/AntiGravity%20Stuff%20%28No%20delete%20pls%20T-T%29/.agents/AGENTS.md). 
   - No unnecessary abstractions, boilerplate, or extra dependencies.
   - Boring over clever. Minimum code that works.
   - Use standard libraries and existing features first.
   - Comment intentional simplifications with a `ponytail:` comment.
3. **Custom Skills & Tools**: The workspace uses custom skills. Check [.agents/skills.json](file:///c:/AntiGravity%20Stuff%20%28No%20delete%20pls%20T-T%29/.agents/skills.json) for registration paths (e.g. `../.skills` and `../claude-code-best-practice/.claude/skills`).

---

## 📂 Workspace Project Map

Use these links to navigate the major projects in the workspace:

### 🌟 Active Project: AI Models Catalogue
* **Purpose**: A4-format multi-model poster series showcasing six frontier AI models with premium, brand-specific CSS layouts and SVGs.
* **Key Files**:
  * [AI_Models_Catalogue/index.html](file:///c:/AntiGravity%20Stuff%20%28No%20delete%20pls%20T-T%29/AI_Models_Catalogue/index.html) (Main interface & structure)
  * [AI_Models_Catalogue/poster.css](file:///c:/AntiGravity%20Stuff%20%28No%20delete%20pls%20T-T%29/AI_Models_Catalogue/poster.css) (Consolidated layout styling)
  * [AI_Models_Catalogue/brand-spec poster.md](file:///c:/AntiGravity%20Stuff%20%28No%20delete%20pls%20T-T%29/AI_Models_Catalogue/brand-spec%20poster.md) (Design system, OKLCH palette tokens, & specs)

### 📁 Other Workspace Directories
* [Self Project 1](file:///c:/AntiGravity%20Stuff%20%28No%20delete%20pls%20T-T%29/Self%20Project%201) - Main dev files.
* [Needy_Girl_Portfolio](file:///c:/AntiGravity%20Stuff%20%28No%20delete%20pls%20T-T%29/Needy_Girl_Portfolio) - Portfolio designs & layouts.
* [NGO Messanger](file:///c:/AntiGravity%20Stuff%20%28No%20delete%20pls%20T-T%29/NGO%20Messanger) - Messaging & communication system.
* [Sentry_Turret](file:///c:/AntiGravity%20Stuff%20%28No%20delete%20pls%20T-T%29/Sentry_Turret) - Turret logic / config workspace.
* [Gemnastik](file:///c:/AntiGravity%20Stuff%20%28No%20delete%20pls%20T-T%29/Gemnastik) - Core codebase files.
* [Antigravity Dashboard.md](file:///c:/AntiGravity%20Stuff%20%28No%20delete%20pls%20T-T%29/Antigravity%20Dashboard.md) - Summary Obsidian dashboard connecting the notes.

---

## ⚙️ How to Migrate Sessions & History (For the User)

When you change Windows accounts, your local terminal shell sessions, past chat history transcripts, MCP configuration, and plugins do not automatically carry over. To move all of them to your new account, follow these steps:

### 1. Locate the App Data Folder on the Current Account
Open File Explorer (or PowerShell) and navigate to the Antigravity configuration directory:
* **Path**: `C:\Users\PANDU-PC\.gemini\antigravity-ide`

This folder contains:
* `brain/` - Holds all your conversations and agent memory.
  * **Current Conversation ID**: `05843637-7d81-4511-a74a-5bb420e00d91`
  * Logs are located at: `brain/05843637-7d81-4511-a74a-5bb420e00d91/.system_generated/logs/transcript.jsonl`
* `mcp/` - Your Model Context Protocol (MCP) server configurations (e.g. `figma-local`).
* `config/` - Custom settings, keys, and global plugins.

### 2. Copy the Data to the New Windows Account
1. Copy the entire `antigravity-ide` folder to a shared directory (e.g., an external drive, or `C:\Users\Public`).
2. Log in to your new Windows account.
3. Move the folder to the equivalent location in the new user's directory:
   * **Target Path**: `C:\Users\<NEW_USERNAME>\.gemini\antigravity-ide`

### 3. Open the Workspace and Resume
1. Open your terminal or IDE in the workspace directory `c:\AntiGravity Stuff (No delete pls T-T)`.
2. Start your AI assistant.
3. Prompt it with:
   > *"Read [handoff.md](file:///c:/AntiGravity%20Stuff%20%28No%20delete%20pls%20T-T%29/handoff.md) to resume our project context and rules."*
4. The agent will read this file, immediately understand your workspace setup, adopt the Ponytail senior developer mode rules, and be ready to help you edit the active project files.
