# Decision Tree

```
START: What is this note about?

├─ Is it a TIME-BOUND goal with a deadline/end date?
│  ├─ YES → Will it be COMPLETED and ARCHIVED?
│  │  ├─ YES → PROJECT (01_PROJECTS/)
│  │  └─ NO → Reconsider - might be AREA
│  └─ NO → Continue below
│
├─ Is it an ONGOING RESPONSIBILITY you maintain regularly?
│  ├─ YES → Do you update it repeatedly over time?
│  │  ├─ YES → AREA (02_AREAS/)
│  │  │  Examples: Home Lab CMDB, Docker Containers, Health & Fitness,
│  │  │  Vehicles, 3D Printing, Firewall Rules, Personal Blog infrastructure
│  │  └─ NO → Might be RESOURCE
│  └─ NO → Continue below
│
├─ Is it SPECIFIC TO YOUR SETUP/WORKFLOW?
│  ├─ YES → Is it infrastructure or a procedure you maintain?
│  │  ├─ YES → AREA (02_AREAS/)
│  │  │  Examples: "Update Docker (My Setup)", "AdGuard DNS Config Notes",
│  │  │  "Firewall Configuration", "My Docker Update Process"
│  │  └─ NO → Continue below
│  └─ NO → Continue below
│
├─ Is it GENERIC/REUSABLE information?
│  ├─ YES → Could anyone use this?
│  │  ├─ YES → RESOURCE (03_RESOURCES/)
│  │  │  Examples: Git Cheatsheet, Docker Commands, Markdown Syntax,
│  │  │  "How to Update Docker (generic)", Raspberry Pi Setup Guide
│  │  └─ NO → Reconsider - might be AREA
│  └─ NO → Continue below
│
├─ Is it a WEB CLIPPING or EXTERNAL CONTENT?
│  ├─ YES → Did you capture it from the web?
│  │  ├─ YES → CLIPPING (05_CLIPPINGS/)
│  │  │  Examples: Article clippings, Code snippets from blogs,
│  │  │  Recipes from websites, Tutorial bookmarks
│  │  └─ NO → Reconsider - might be RESOURCE
│  └─ NO → Continue below
│
├─ Is it a DESCRIPTOR/CATEGORY/LABEL?
│  ├─ YES → Does it describe what something IS?
│  │  ├─ YES → TAG (#tag-name)
│  │  │  Examples: #docker, #automation, #homelab, #blog, #cheatsheet
│  │  └─ NO → Reconsider
│  └─ NO → Continue below
│
└─ Is it REFERENCE MATERIAL you look up?
   ├─ YES → Is it static/unchanging?
   │  ├─ YES → RESOURCE (03_RESOURCES/)
   │  │  Examples: Recipes, Guides, Comparisons, Scripts, Research notes
   │  └─ NO → Might be AREA if you maintain it
   └─ NO → Default to RESOURCE or reconsider structure
```

---

## 📁 Quick Reference Guide

### 01_PROJECTS/

**When to use:**

- ⏰ Has a deadline or target completion date
- 🎯 Specific deliverable or end goal
- 📊 Will be completed and archived
- 🔄 Temporary (not permanent)

**Examples:**

- Blog Post - Docker Security
- Job Search 2025
- Home Lab Network Upgrade
- Design Custom 3D Printed Case

**Lifecycle:** Active → Completed → Archive

---

### 02_AREAS/

**When to use:**

- 🔄 Ongoing responsibility you maintain
- 📝 Living document (updates regularly)
- 🛠️ Infrastructure/system for your life
- 📚 You reference repeatedly
- 🏠 Specific to YOUR setup/workflow

**Examples:**

- Home Lab CMDB
- Docker Containers
- Health & Fitness
- Vehicles
- 3D Printing
- Firewall Rules
- Personal Blog (infrastructure)
- Update Docker (your specific process)
- AdGuard DNS Config Notes

**Lifecycle:** Always active, continuously maintained

---

### 03_RESOURCES/

**When to use:**

- 📚 Reference material
- 🔍 Generic/reusable information
- ✅ Static (doesn't change)
- 📖 Could help anyone
- 🎯 Not specific to your setup

**Examples:**

- Git Cheatsheet
- Docker Commands Reference
- Markdown Syntax Guide
- Chocolate Bark Recipe
- How to Update Docker (generic)
- Raspberry Pi Setup Guide
- Filament Properties Reference

**Lifecycle:** Evergreen, rarely changes

---

### 04_ARCHIVE/

**When to use:**

- ✅ Project is completed
- 🏁 No longer active
- 📦 Keep for reference/history

**Examples:**

- Completed projects
- Old job searches
- Finished home lab upgrades

**Lifecycle:** Move here when done, keep indefinitely

---

### 05_CLIPPINGS/

**When to use:**

- 🌐 Captured from web
- 📰 External content
- 💾 Temporary holding area
- 🔄 May process into RESOURCES later

**Examples:**

- Article clippings
- Code snippets from blogs
- Recipes from websites
- Tutorial bookmarks
- Research from web

**Lifecycle:** Temporary → Process → Move to RESOURCES or delete

---

## 🎯 Decision Examples

### "Update Docker.md"

- Is it time-bound? **NO**
- Is it ongoing responsibility? **YES**
- Is it specific to your setup? **YES**
- Is it infrastructure you maintain? **YES**

**→ AREA** (`02_AREAS/Docker Containers/`)

---

### "Git Cheatsheet"

- Is it time-bound? **NO**
- Is it ongoing responsibility? **NO**
- Is it generic/reusable? **YES**
- Could anyone use this? **YES**

**→ RESOURCE** (`03_RESOURCES/Cheatsheets/`)

---

### "Blog Post - Docker Security"

- Is it time-bound? **YES**
- Will it be completed/archived? **YES**

**→ PROJECT** (`01_PROJECTS/`)

---

### "Chocolate Bark Recipe"

- Is it time-bound? **NO**
- Is it ongoing responsibility? **NO**
- Is it generic/reusable? **YES**
- Could anyone use this? **YES**

**→ RESOURCE** (`03_RESOURCES/Recipes/`)

---

### "3D Print Filament Inventory"

- Is it time-bound? **NO**
- Is it ongoing responsibility? **YES**
- Do you update it regularly? **YES**

**→ AREA** (`02_AREAS/3D Printing/`)

---

### "Article on Docker Best Practices"

- Is it external content? **YES**
- Did you capture from web? **YES**

**→ CLIPPING** (`05_CLIPPINGS/`)

_[Later: Process and move to RESOURCES if useful]_

---

## ❓ When in Doubt

Ask yourself:

1. Will this be completed and archived? → **PROJECT**
2. Do I maintain this regularly? → **AREA**
3. Is this generic reference material? → **RESOURCE**
4. Did I capture this from the web? → **CLIPPING**
5. Is this a label/descriptor? → **TAG**

**Default:** If unsure, lean toward **RESOURCE** (it's the safest catch-all)