# My Obsidian Vault Structure

## Overview

This vault uses a **hybrid PARA + tagging system** designed for low-friction capture and powerful querying. The goal: capture quickly, organize automatically, find easily.

---

## Folder Structure

Vault/
├── 01_PROJECTS/              # Active work with deadlines
├── 02_AREAS/                 # Ongoing responsibilities maintained over time
├── 03_RESOURCES/             # Reference material and static content
├── 04_ARCHIVE/               # Completed projects
└── _HOME/                    # Entry point
├── Dashboard.md          # Your main navigation hub
└── Dashboard.base        # Database views of your vault


### 01_PROJECTS/
**Active work with deadlines and deliverables.**
- Create a folder for each project
- Move to ARCHIVE when complete
- Examples:
  - `Blog Post - Docker Security Best Practices/`
  - `Home Lab Network Upgrade/`
  - `Automate Backup System/`

### 02_AREAS/
**Ongoing responsibilities you maintain and update regularly.**
- These are living documents that evolve over time
- You return to them repeatedly to add/modify content
- Examples:
  - `Home Lab CMDB/` - Your network inventory (grows as you add devices)
  - `Firewall Rules/` - Network security rules (updated as your network changes)
  - `Docker Containers/` - Deployed containers and configs (maintained as you deploy)
  - `Personal Blog/` - Blog infrastructure and metadata (ongoing responsibility)

### 03_RESOURCES/
**Reference material, guides, cheatsheets, and static content.**
Organize by type or domain:
- `Guides/` - Step-by-step instructions (Raspberry Pi setup, etc.)
- `Cheatsheets/` - Quick reference (Git, Docker, Nmap, Markdown)
- `Comparisons/` - SaaS/product evaluations
- `Scripts/` - Reusable code snippets
- `Research/` - Research notes and findings

### 04_ARCHIVE/
**Completed projects.**
- Move finished projects here
- Keep for reference/history
- Minimal maintenance

### _HOME/
**Your vault entry point.**
- Contains `Dashboard.md` - your main navigation hub
- Contains `Dashboard.base` - database views of your vault
- Open `Dashboard.md` first when you start working

---

## Frontmatter Template

Every new note automatically gets this template:

```yaml
---
type: [project|area|resource|note]
status: [active|on-hold|completed|reference]
tags: []
created: <date auto-filled>
updated: <date auto-filled>
---
```

**Fields Explained**
- **type**: What category does this belong to?
	- ⁠project - Active work
	- ⁠area - Ongoing responsibility
	- ⁠resource - Reference material
	- ⁠note - General note
- **status**: Current state?
	- ⁠active - Currently working on it
	- ⁠on-hold - Paused, not working on it now
	- ⁠completed - Finished
	- ⁠reference - Static reference material
- **tags**: Domain/category tags (see below)

**Tagging System**

**Domain Tags (Pick 1-3 per note)**

**Infrastructure & Homelab:**
- ⁠#homelab - General homelab stuff, Raspberry Pi tasks
- ⁠#docker - Docker containers, compose files, Docker-specific
- ⁠#networking - Firewall rules, network CMDB, network configuration
- ⁠#automation - Automation tools, workflows, scripts

**Technical Reference:**
- ⁠#cheatsheet - Quick reference (Git, Docker, Nmap, Markdown)

- ⁠#guide - Step-by-step instructions and how-tos

**Content & Projects:**
- ⁠#blog - Blog posts and writing
- ⁠#project-idea - Project ideas to explore
- ⁠#comparison - SaaS/product comparisons

**Optional:**
- ⁠#learning - If actively studying something new
- ⁠#research - If still investigating
- ⁠#home-maintenance - House repairs and maintenance (if needed)

**Tagging Rules**
1. **Use 1-3 tags per note** - More than that means you're overthinking it
- **Use multiple tags when relevant** - A note can have multiple domains
- Example: "n8n Docker Deployment" → ⁠#docker + ⁠#automation
- **Be consistent** - Use the same tag name every time (all lowercase, hyphens for multi-word)
- **Don't create new tags lightly** - Use the list above first


**Tagging Examples**

| Note                                   | Tags                      |
| -------------------------------------- | ------------------------- |
| "Install Pihole on Raspberry Pi"       | ⁠#homelab ⁠#guide         |
| "Docker Compose Cheatsheet"            | ⁠#docker ⁠#cheatsheet     |
| "Firewall Rules - Q4 2025"             | ⁠#networking              |
| "Blog: Docker Security Best Practices" | ⁠#blog                    |
| "Comparing Wireguard vs Tailscale"     | ⁠#networking ⁠#comparison |
| "n8n Docker Deployment"                | ⁠#docker ⁠#automation     |
| "Home Network CMDB"                    | ⁠#homelab ⁠#networking    |
| "Git Cheatsheet"                       | ⁠#cheatsheet              |
**Obsidian Bases (Your Database Views)**
**Bases** let you create database-like views of your notes. Instead of manually querying, you get interactive tables that filter and organize your content.

**What is a Base?**
A ⁠.base file is like a database view. It reads your notes' frontmatter (type, status, tags) and displays them in organized tables. You can:
- **Filter** by status, type, tags
- **Sort** by date, name, status
- **Group** by domain or project
- **Search** across all notes at once

**Using Bases in This Vault**
Your main base is ⁠_HOME/Dashboard.base. It contains multiple **views**:
- **Active Projects** - All notes with ⁠status: active and ⁠type: project
- **Docker & Containers** - All notes tagged ⁠#docker
- **Networking** - All notes tagged ⁠#networking
- **Automation** - All notes tagged ⁠#automation
- **Homelab** - All notes tagged ⁠#homelab
- **Cheatsheets** - All notes tagged ⁠#cheatsheet
- **Guides** - All notes tagged ⁠#guide
- **Blog Posts** - All notes tagged ⁠#blog
- **Comparisons** - All notes tagged ⁠#comparison
- **Project Ideas** - All notes tagged ⁠#project-idea
- **All Active Items** - Everything with ⁠status: active

**How to Use Bases**
1. **Open Dashboard.md** - Your entry point
- **Embedded base views** - See your organized notes
- **Click a note** - Jump directly to it
- **Update frontmatter** - Changes appear in base automatically

**Creating/Editing Bases**
To create or modify your base:
1. **Command Palette** → "Create a base"
- **Select source folder** (your vault root)
- **Create views** for each domain/filter you want
- **Save as** ⁠Dashboard.base in ⁠_HOME/

To embed in Dashboard.md:
```
![[Dashboard.base#Active Projects]]
![[Dashboard.base#Docker & Containers]]
![[Dashboard.base#All Active Items]]
```

**Dashboard (Your Entry Point)**
Open ⁠_HOME/Dashboard.md when you start working. It embeds your base views showing:
- **Active Projects** - What you're currently working on
- **Infrastructure & Homelab** - Organized by domain (Docker, Networking, Automation, Homelab)
- **Technical Reference** - Cheatsheets and guides
- **Content & Writing** - Blog posts and comparisons
- **Ideas & Exploration** - Project ideas
- **All Active Items** - Everything you're actively working on
The base automatically updates as you modify note frontmatter.
---
**Workflow**
**Capturing a New Note**
1. **Create new note** → Template auto-fills
2. **Fill in:**
	- ⁠type: (project/area/resource/note)
	- ⁠status: (active/on-hold/completed/reference)
	- ⁠tags: (1-3 relevant tags from the list)
3. **Done** - Note appears in base views automatically

**Finding a Note**
1. **Open Dashboard.md** (⁠_HOME/Dashboard.md)
2. **Browse the embedded base views**
3. **Click a note** to jump to it

Or use Obsidian's search:
- Search by tag: ⁠tag:#docker
- Search by status: ⁠status:active
- Search by text: normal search

**Maintaining Your Vault**
- **Update status** when things change (active → completed)
- **Move projects to ARCHIVE** when done
- **Update AREA notes** as your infrastructure/blog/etc. evolves
- **Changes appear in base automatically** - No manual updates needed
---
**AREA vs TAG: When to Use Each**

**Use an AREA (02_AREAS folder) when:**
1. **It's an ongoing responsibility** - Something you maintain/update regularly over time
	- Examples: Home Lab CMDB, Firewall Rules, Docker Containers, Personal Blog
	- Test: "Will I come back to this repeatedly and add/update it?"
- **It has multiple related notes** - You'll create several notes that belong together
	- Example: Home Lab CMDB might have sub-notes for each device, network segments, etc.
	- Test: "Will this become a collection of related documents?"
- **It's a reference system** - A living document that evolves
	- Example: Your CMDB grows as you add devices; Firewall Rules change as your network evolves
	- Test: "Does this need to be maintained and updated over time?"
- **It's a core responsibility** - Part of your regular workflow/life
	- Example: Your personal blog, home lab infrastructure
	- Test: "Is this something I'm responsible for managing?"

**Use a TAG when:**
1. **It's a characteristic or category** - Describes what something IS, not a place it LIVES
	- Examples: ⁠#docker, ⁠#automation, ⁠#cheatsheet
	- Test: "Is this a descriptor/label rather than a container?"
- **It crosses multiple areas** - The same note might belong to different contexts
	- Example: "n8n Docker Deployment" is both ⁠#docker AND ⁠#automation
	- Test: "Could this note be relevant from multiple angles?"
- **It's optional metadata** - Helpful for filtering but not essential to the note's location
	- Examples: ⁠#learning, ⁠#comparison, ⁠#guide
	- Test: "Would I filter by this, or is it just extra context?"
- **It's a type/format** - Describes HOW the information is structured
	- Examples: ⁠#cheatsheet, ⁠#guide, ⁠#comparison
	- Test: "Is this about the format/structure of the content?"

**Decision Tree**
```
Does this thing need to be maintained/updated over time?
├─ YES → Is it an ongoing responsibility?
│  ├─ YES → Make it an AREA (02_AREAS/Your Area Name/)
│  └─ NO → Could be a tag or resource
└─ NO → Is it a descriptor/category?
   ├─ YES → Make it a TAG (#tag-name)
   └─ NO → Make it a RESOURCE (03_RESOURCES/)
```

**Examples from Your Vault**

| Item                               | Decision       | Why                                                                 |
| ---------------------------------- | -------------- | ------------------------------------------------------------------- |
| Home Lab CMDB                      | AREA           | Ongoing responsibility, multiple related notes, grows over time     |
| Firewall Rules                     | AREA           | Maintained regularly, core responsibility, evolves                  |
| Docker Containers                  | AREA           | You manage these, add/update regularly                              |
| Personal Blog                      | AREA           | Ongoing responsibility, multiple posts, you maintain it             |
| Git Cheatsheet                     | TAG + RESOURCE | It's a reference type (⁠#cheatsheet), not something you maintain    |
| n8n deployment guide               | TAG + RESOURCE | Describes what it is (⁠#docker, ⁠#automation), not a responsibility |
| Project Ideas                      | TAG + RESOURCE | A collection, but not something you "maintain" like CMDB            |
| Comparison: Wireguard vs Tailscale | TAG + RESOURCE | A reference document (⁠#comparison), not ongoing                    |
| Raspberry Pi Setup Guide           | TAG + RESOURCE | A guide (⁠#guide), reference material                               |


**Tips & Best Practices**

✅ **DO**
- **Capture quickly** - Don't overthink tags/type when capturing
- **Use the template** - Let it auto-fill, just add tags
- **Update status regularly** - This keeps your base views accurate
- **Review Dashboard.md weekly** - See what's active, what's done
- **Archive completed projects** - Keeps root folders clean
- **Check base views** - They update automatically as you change frontmatter

❌ **DON'T**
- **Create new tags constantly** - Stick to the list above
- **Over-tag notes** - 1-3 tags is plenty
- **Leave notes in root** - Everything goes in a folder
- **Forget to update status** - This breaks the base filtering
- **Maintain tags inconsistently** - Use lowercase, hyphens, same names
- **Manually update base** - It's automatic, just update frontmatter
---
**Plugins Required**
- **Obsidian Bases** - Built-in (no installation needed)
- **Templater** (optional) - For auto-filling frontmatter on note creation
---
**Getting Started**
1. Create the folder structure above
2. Set up the frontmatter template in Obsidian
3. Create a base file (⁠Dashboard.base) with views for each domain
4. Create ⁠_HOME/Dashboard.md and embed your base views
5. w Start capturing notes - the base will organize itself
---
**Your system is:**
1. **PARA-inspired folder structure** (Projects, Areas, Resources, Archive)
	- But simplified: you only use the core folders, not strict PARA rules
2. **Tag-based filtering** (like Kepano's system)
	- But with low friction: only 1-3 tags, no forced metadata
	- Solves the "I forgot to tag" problem
3. **Folder-based navigation** (like FranklyFuzzy's system)
	- But organized: prevents root clutter
	- Solves the "lazy filing" problem
4. **Database views** (Obsidian Bases)
	- Gives you the querying power you wanted from Kepano
	- But makes it visible/usable (your main complaint about .base files)

**Your system is: PARA folder structure + lightweight tagging + Obsidian Bases = low-friction capture with powerful querying**