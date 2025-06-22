# Obsidian Vault Structure & Starter Kit

This repository provides a robust and flexible starter template for an Obsidian vault, designed to enhance visual clarity, promote deep linking, and prepare your notes for powerful database-like functionality with the upcoming Obsidian "Bases" feature.

## Table of Contents

1. [Introduction](#1-introduction "null")
2. [Core Philosophy](#2-core-philosophy "null")
3. [Vault Structure Overview](#3-vault-structure-overview "null")
    - [Folder Breakdown](#folder-breakdown "null")
4. [Key Concepts & Components](#4-key-concepts--components "null")
    - [Properties (Frontmatter)](#properties-frontmatter "null")
    - [`_Index.md` & `_Vault Map.md`](#_indexmd--_vault-mapmd "null")
    - [Tags](#tags "null")
    - [Linking](#linking "null")
    - [Obsidian Bases Preparation](#obsidian-bases-preparation "null")
5. [Getting Started](#5-getting-started "null")
6. [Customization](#6-customization "null")
7. [License](#7-license "null")

## 1. Introduction

This template provides a thoughtfully organized Obsidian vault designed for personal knowledge management (PKM). It aims to balance structured organization with the flexibility needed for organic knowledge growth, ensuring your notes are easy to find, connect, and analyze.

## 2. Core Philosophy

The structure is inspired by principles like PARA (Projects, Areas, Resources, Archives) and Zettelkasten for evergreen notes, adapted for Obsidian's unique strengths:

- **Visual Clarity:** High-level folders and consistent naming (`_Index.md`) make navigation intuitive.
    
- **Frictionless Capture:** Dedicated `Inbox` for quick notes reduces cognitive load.
    
- **Prioritize Linking:** Encourages building a rich network of interconnected ideas, leveraging Obsidian's graph view and backlinks.
    
- **Structured Data for Power:** Emphasizes consistent use of **properties (frontmatter)** to prepare for future database views with Obsidian Bases.
    
- **Scalability:** Designed to remain organized and efficient whether you have dozens or thousands of notes.
    

## 3. Vault Structure Overview

Here's the top-level folder structure provided in this repository:

```
Vault Root/
|------ 00 Meta/
|      |------ _Index.md           (Vault Operations & Management)
|      |------ _Vault Map.md       (Overall Vault Navigator)
|      |------ Templates/          (All note templates)
|      |      |------ Daily Note Template.md
|      |      |------ Project Brief Template.md
|      |      |------ Area Note Template.md
|      |      |------ Article Template.md
|      |      |------ Book Note Template.md
|      |      |------ Permanent Note Template.md
|      |------ Attachments/        (General vault-level attachments)
|      |------ Inbox/              (Quick capture for unprocessed notes)
|
|------ 01 Projects/
|      |------ _Index.md           (Dashboard for all projects)
|      |------ Project A/          (Example project folder)
|      |      |------ Project A Overview.md
|      |
|------ 02 Areas/
|      |------ _Index.md           (Dashboard for all ongoing responsibilities)
|      |------ Learning/
|      |      |------ _Index.md      (Learning Hub)
|      |------ Personal/
|      |      |------ _Index.md      (Personal Hub)
|
|------ 03 Resources/
|      |------ _Index.md           (Dashboard for curated knowledge)
|      |------ Articles/
|      |      |------ _Index.md      (Articles Hub)
|      |------ Books/
|      |      |------ _Index.md      (Books Hub)
|      |------ Permanent Notes/
|      |      |------ _Index.md      (Zettelkasten/Evergreen Notes Hub)
|
|------ Daily Notes/
|      |------ _Index.md           (Daily Notes Hub)
|      |------ 2025-06-19 Daily.md (Example daily note)
|
|------ 99 Archive/
|      |------ _Index.md           (Archive Overview)
```

### Folder Breakdown

- **`00 Meta/`**: The "operating system" of your vault. Contains notes about your vault's structure, templates, general attachments, and an inbox for quick captures.
    
- **`01 Projects/`**: For discrete, goal-oriented endeavors with a defined start and end. Each project gets its own sub-folder.
    
- **`02 Areas/`**: For ongoing responsibilities, roles, and continuous learning that don't have a definitive end date (e.g., Health, Finances, specific learning paths). Each area typically has its own sub-folder.
    
- **`03 Resources/`**: Your curated library of information – articles, books, permanent/evergreen notes (your Zettelkasten), software tips, etc. These are generally stable and less frequently updated than project or area notes.
    
- **`Daily Notes/`**: A dedicated folder for your daily notes/journals, providing a chronological log of your activity and thoughts.

## 4. Key Concepts & Components

### Properties (Frontmatter)

At the core of this structure's power, especially for future Bases integration, is the consistent use of **properties** (also known as YAML frontmatter or metadata). These are `key: value` pairs placed at the very top of your Markdown notes, enclosed by `---`.

**Example:**

```
---
status: Active
project_type: Client Work
due_date: 2025-07-15
tags: project, client/acmecorp
---
# My Project Note
```

**Why:** Bases will read these properties to create dynamic tables, filters, and groups of your notes, transforming them into powerful databases. All templates provided include example properties.

### `_Index.md` & `_Vault Map.md`

These notes serve as navigational dashboards:

- **`_Vault Map.md` (in `00 Meta/`)**: Your highest-level overview and navigation hub for the _entire_ vault. It outlines the overall structure and links to the main section indexes.
- **`_Index.md` (in each major folder and sub-folder)**: The entry point and summary dashboard for its respective section. The `_` prefix ensures it always sorts to the very top of its folder, providing immediate context and navigation.

### Tags

Tags (`#tag`) are used for orthogonal classification, cutting across your folder structure. They complement folders by adding another dimension for connecting related notes (e.g., `#meeting`, `#actionable`, `#person/JohnDoe`).

### Linking

The foundation of Obsidian is interlinking. This structure encourages proactive linking between notes using `[[Note Name]]` to build a dense, interconnected web of knowledge.

### Obsidian Bases Preparation

This vault structure is designed with Obsidian's upcoming "Bases" feature in mind:

- **Consistent Properties:** By defining and using properties in your templates from day one, your notes will be ready to be queried and displayed in Bases views.
- **Logical Grouping:** The clear folder structure (e.g., all projects in `01 Projects/`) makes it easy to define the "source" for a Base (e.g., "all notes in the `01 Projects/` folder").
- **Dynamic Dashboards:** Your `_Index.md` files are ready to be replaced with embedded Bases views that automatically update with relevant information (e.g., a table of all active projects, or a list of articles to read).
    

## 5. Getting Started

1. **Clone or Download:** Get the contents of this repository.
2. **Create a New Vault:** In Obsidian, choose "Open another vault" -> "Create new vault" and select an empty folder.
3. **Copy Files:** Copy all the folders and `.md` files from this repository into your new Obsidian vault folder.
4. **Explore:** Open your vault in Obsidian. Start by exploring `00 Meta/_Vault Map.md` to get an overview.
5. **Use Templates:** When creating new notes, use the templates from `00 Meta/Templates/` to ensure consistency and proper property usage. The Templater plugin can automate this for you.
6. **Daily Workflow:** Make your `Daily Notes/_Index.md` or your daily note itself (`YYYY-MM-DD Daily.md`) a starting point for your day. Use `00 Meta/Inbox/` for quick capture.

## 6. Customization

This is a starter template. Feel free to:

- Adjust folder names to better suit your personal terminology.
- Modify the templates to include properties and sections most relevant to _your_ workflow.
- Add more sub-folders within `01 Projects`, `02 Areas`, and `03 Resources` as your vault grows.
- Experiment with Obsidian themes and community plugins that align with this structure.

## 7. License

This project is licensed under the MIT License - see the `LICENSE` file for details.