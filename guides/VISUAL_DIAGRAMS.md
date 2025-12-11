# Visual Diagrams for ETL Learning System

This document describes the key diagrams to create for the repository. You can create these using:
- Draw.io (free, web-based)
- Excalidraw (free, simple)
- PowerPoint/Keynote
- Figma (free tier)
- Hand-drawn and scanned (perfectly fine!)

Save as PNG files in `assets/` folder.

---

## Diagram 1: Complete Workflow Overview

**Filename:** `assets/workflow_overview.png`

**Purpose:** Show the full ETL cycle at a glance

**Layout:** Horizontal flow, three main stages
```
┌─────────────────────────────────────────────────────────────────┐
│                    ETL LEARNING SYSTEM                           │
└─────────────────────────────────────────────────────────────────┘

┌──────────────┐      ┌──────────────┐      ┌──────────────┐
│   EXTRACT    │  →   │  TRANSFORM   │  →   │     LOAD     │
│              │      │              │      │              │
│ Raw Capture  │      │  Processing  │      │   Storage    │
└──────────────┘      └──────────────┘      └──────────────┘

MONDAY-FRIDAY          SUNDAY/MONDAY         ONGOING
                       60-90 minutes

┌──────────────┐      ┌──────────────┐      ┌──────────────┐
│              │      │              │      │              │
│  📓 A5       │      │  🔍 Scan     │      │  📚 B5       │
│  Notebook    │      │  📋 Decide   │      │  Cornell     │
│              │      │  ✏️  Refine   │      │              │
│  • Chrono    │      │  ✓ Mark      │      │  💻 Jupyter  │
│  • Symbols   │      │  📖 Update   │      │  Notebooks   │
│  • Headers   │      │  💾 Commit   │      │              │
│              │      │              │      │  📂 Docs/    │
│              │      │              │      │  Knowledge   │
│              │      │              │      │  Base        │
└──────────────┘      └──────────────┘      └──────────────┘

     Zero                 Organized            Permanent
    Friction              Workflow             Reference
```

**Design notes:**
- Use three distinct colors for each stage
- Icons: notebook, magnifying glass, book, laptop, folder
- Arrows showing flow direction
- Time estimates under each stage
- Key characteristics bulleted below each stage

---

## Diagram 2: Decision Tree (Jupyter vs Cornell)

**Filename:** `assets/decision_tree.png`

**Purpose:** Quick visual for format decisions

**Layout:** Flowchart style
```
                    ┌──────────────────┐
                    │  New Content to  │
                    │    Process?      │
                    └────────┬─────────┘
                             │
                             ↓
                    ┌──────────────────┐
                    │  School-related? │
                    └────────┬─────────┘
                             │
                ┌────────────┴─────────────┐
                │                          │
               YES                         NO
                │                          │
                ↓                          ↓
    ┌──────────────────────┐    ┌─────────────────┐
    │ Can I write code to  │    │ Process later   │
    │ demonstrate this?    │    │ (if time) or    │
    └──────────┬───────────┘    │ skip            │
               │                └─────────────────┘
               │
    ┌──────────┴──────────┐
    │                     │
   YES                   NO
    │                     │
    ↓                     ↓
┌─────────┐         ┌──────────┐
│ JUPYTER │         │ CORNELL  │
│         │         │          │
│ 💻      │         │ 📚       │
│         │         │          │
│ • Code  │         │ • Theory │
│ • SQL   │         │ • Math   │
│ • Demos │         │ • Concepts│
└─────────┘         └──────────┘

Examples:            Examples:
- Docker commands    • Docker architecture
- Python scripts     • Database normalization
- Data analysis      • Statistical theory
- ML implementation  • Algorithm comparisons
```

**Design notes:**
- Diamond shapes for decisions
- Rectangle shapes for outcomes
- Green path for "yes", orange for "no"
- Icons for Jupyter (laptop) and Cornell (book)
- Examples listed under each outcome

---

## Diagram 3: Weekly Processing Flow

**Filename:** `assets/weekly_processing.png`

**Purpose:** Detailed breakdown of Sunday/Monday session

**Layout:** Vertical checklist with time estimates
```
┌──────────────────────────────────────────────────────┐
│        WEEKLY PROCESSING SESSION                     │
│        Sunday/Monday: 60-90 minutes                  │
└──────────────────────────────────────────────────────┘

┌──────────────────────────────────────────────────────┐
│ 1. SCAN RAW NOTEBOOK                     [5 min]     │
├──────────────────────────────────────────────────────┤
│ • Flip through week's pages                          │
│ • Mark school-related with sticky tabs               │
│ • Mental note of topics                              │
└──────────────────────────────────────────────────────┘
                        ↓
┌──────────────────────────────────────────────────────┐
│ 2. DECIDE FORMAT                        [~30 sec ea] │
├──────────────────────────────────────────────────────┤
│ For each topic:                                      │
│ Can I code it? → Jupyter                            │
│ Concepts only? → Cornell                            │
└──────────────────────────────────────────────────────┘
                        ↓
┌──────────────────────────────────────────────────────┐
│ 3. PROCESS NOTES                        [50-70 min]  │
├──────────────────────────────────────────────────────┤
│                                                      │
│  ┌─────────────────┐    ┌──────────────────┐       │
│  │ JUPYTER PATH    │    │ CORNELL PATH     │       │
│  ├─────────────────┤    ├──────────────────┤       │
│  │ 1. Copy template│    │ 1. Draw sections │       │
│  │ 2. Fill header  │    │ 2. Fill notes    │       │
│  │ 3. Add examples │    │ 3. Add cues      │       │
│  │ 4. Test code    │    │ 4. Write summary │       │
│  │ 5. Write summary│    │                  │       │
│  └─────────────────┘    └──────────────────┘       │
│                                                      │
└──────────────────────────────────────────────────────┘
                        ↓
┌──────────────────────────────────────────────────────┐
│ 4. TASK SWEEP                           [5 min]      │
├──────────────────────────────────────────────────────┤
│ • Scan for □ (tasks) and ! (deadlines)              │
│ • Add to task system                                 │
└──────────────────────────────────────────────────────┘
                        ↓
┌──────────────────────────────────────────────────────┐
│ 5. MARK PROCESSED                       [2 min]      │
├──────────────────────────────────────────────────────┤
│ • Cross out dates in raw notebook                    │
│ • Visual confirmation of completion                  │
└──────────────────────────────────────────────────────┘
                        ↓
┌──────────────────────────────────────────────────────┐
│ 6. UPDATE KNOWLEDGE BASE               [5-10 min]    │
├──────────────────────────────────────────────────────┤
│ • Link notebooks from course pages                   │
│ • Update tool references                             │
│ • Add resources                                      │
└──────────────────────────────────────────────────────┘
                        ↓
┌──────────────────────────────────────────────────────┐
│ 7. COMMIT & PUSH                        [3 min]      │
├──────────────────────────────────────────────────────┤
│ git add .                                            │
│ git commit -m "Week X: topics"                       │
│ git push origin main                                 │
└──────────────────────────────────────────────────────┘
                        ↓
┌──────────────────────────────────────────────────────┐
│              ✓ WEEK COMPLETE                         │
└──────────────────────────────────────────────────────┘
```

**Design notes:**
- Boxes with time estimates in brackets
- Arrows showing sequential flow
- Two parallel paths for Jupyter/Cornell
- Different colors for different step types
- Checkmark at completion

---

## Diagram 4: Repository Structure

**Filename:** `assets/repo_structure.png`

**Purpose:** Visual map of folder organization

**Layout:** Tree diagram
```
📦 ds-masters-portfolio/
│
├── 📚 courses/
│   ├── 📁 mlops/
│   │   ├── 📁 week-01/
│   │   │   ├── 📓 20241214_docker_basics.ipynb
│   │   │   └── 📓 20241216_docker_compose.ipynb
│   │   ├── 📁 week-02/
│   │   └── 📄 README.md
│   │
│   ├── 📁 modern-data-architectures/
│   │   ├── 📁 week-01/
│   │   └── 📄 README.md
│   │
│   └── 📁 [previous courses]/
│       └── 📁 backfill/
│
├── 🎯 projects/
│   ├── 📁 project-01-name/
│   └── 📁 project-02-name/
│
├── 🏋️ exercises/
│   ├── 📁 practice/
│   ├── 📁 leetcode/
│   └── 📁 kaggle/
│
├── 📖 docs/              ← Knowledge Base
│   ├── 📄 README.md
│   ├── 📁 courses/
│   │   ├── 📄 MLOps.md
│   │   └── 📄 Modern-Data-Architectures.md
│   ├── 📁 topics/
│   │   └── 📄 Data-Engineering.md
│   └── 📁 tools/
│       ├── 📄 Docker.md
│       └── 📄 Git-GitHub.md
│
├── 📝 templates/
│   ├── 📓 notebook_template.ipynb
│   └── 📋 weekly_processing_checklist.md
│
└── 📚 resources/
    ├── 📁 papers/
    ├── 📁 articles/
    └── 📁 books/
```

**Design notes:**
- Tree structure with folder icons
- Different icons for different file types
- Indentation showing hierarchy
- Annotations on key folders
- Color coding by purpose

---

## Diagram 5: Symbol Reference Card

**Filename:** `assets/symbol_reference.png`

**Purpose:** Quick reference for raw capture symbols

**Layout:** Grid/table format
```
┌─────────────────────────────────────────────────────┐
│           RAW CAPTURE SYMBOLS                       │
├──────┬──────────────────────────────────────────────┤
│  •   │ NOTE / OBSERVATION                           │
│      │ Default for most content                     │
│      │ Example: • Docker uses containers            │
├──────┼──────────────────────────────────────────────┤
│  □   │ TASK / ACTION ITEM                           │
│      │ Something you need to do                     │
│      │ Example: □ Install Docker                    │
├──────┼──────────────────────────────────────────────┤
│  ?   │ QUESTION / UNCLEAR                           │
│      │ Didn't understand, need to research          │
│      │ Example: ? How does port mapping work?       │
├──────┼──────────────────────────────────────────────┤
│  *   │ IMPORTANT / EXAM RELEVANT                    │
│      │ Key concept, professor emphasized            │
│      │ Example: * Three pipeline stages             │
├──────┼──────────────────────────────────────────────┤
│  >   │ CODE / EXAMPLE                               │
│      │ Technical commands or code                   │
│      │ Example: > docker run -d                     │
├──────┼──────────────────────────────────────────────┤
│  !   │ DEADLINE / TIME-SENSITIVE                    │
│      │ Due dates, exams, appointments               │
│      │ Example: ! Assignment due Friday             │
└──────┴──────────────────────────────────────────────┘

HEADER FORMAT:
┌────────────────────────────────────────────────────┐
│ [DATE] | [TYPE] | [SOURCE]                         │
│                                                    │
│ Example:                                           │
│ 2024-12-14 | LECTURE | MLOps - Docker             │
└────────────────────────────────────────────────────┘
```

**Design notes:**
- Clean table format
- Large, clear symbols
- Real example for each
- Header format shown separately
- Printable size (could be 8.5x11)

---

## Diagram 6: Cornell Method Template

**Filename:** `assets/cornell_template.png`

**Purpose:** Visual guide for Cornell note structure

**Layout:** Labeled diagram
```
┌────────────────────────────────────────────────────────┐
│  TOPIC - Date Range                                    │
│  (Course name and time period covered)                 │
├──────────────┬─────────────────────────────────────────┤
│              │                                         │
│  CUES        │  NOTES                                  │
│  (2.5")      │  (Remaining space)                      │
│              │                                         │
│  Key terms   │  • Detailed explanations                │
│  Questions   │  • Examples from lecture                │
│  Formulas    │  • Connections between ideas            │
│              │  • Diagrams and visuals                 │
│              │  • Important facts and concepts         │
│              │                                         │
│  [Add these  │  [Fill this section FIRST]             │
│   SECOND]    │  [During processing session]            │
│              │                                         │
│              │                                         │
│              │                                         │
│              │                                         │
│              │                                         │
│              │                                         │
├──────────────┴─────────────────────────────────────────┤
│  SUMMARY (2" at bottom)                                │
│                                                        │
│  [Write this LAST]                                     │
│  3-5 sentences synthesizing the key concepts           │
│  Focus on "what" and "why it matters"                  │
│                                                        │
└────────────────────────────────────────────────────────┘

USAGE:
1. Fill NOTES section first (right side)
2. Add CUES after reviewing (left side)
3. Write SUMMARY last (bottom)

REVIEW:
- Cover notes, quiz yourself from cues
- Read summaries for quick refresh
```

**Design notes:**
- Actual proportions shown
- Annotations for each section
- Order of completion indicated
- Usage instructions included
- Review tips at bottom

---

## Diagram 7: ADHD-Friendly Features

**Filename:** `assets/adhd_features.png`

**Purpose:** Highlight system features that help with ADHD

**Layout:** Icon-based feature grid
```
┌────────────────────────────────────────────────────────────┐
│         WHY THIS SYSTEM WORKS FOR ADHD BRAINS             │
└────────────────────────────────────────────────────────────┘

┌──────────────────┐  ┌──────────────────┐  ┌──────────────────┐
│  📓 ONE NOTEBOOK │  │  ⏱️ MINIMAL CHOICES│  │  ✅ VISUAL DONE  │
├──────────────────┤  ├──────────────────┤  ├──────────────────┤
│ No decisions     │  │ Same symbols     │  │ Cross out dates  │
│ about "which     │  │ Same header      │  │ See progress     │
│ notebook?"       │  │ Default: write   │  │ Completed pages  │
│                  │  │ on next line     │  │ trigger dopamine │
└──────────────────┘  └──────────────────┘  └──────────────────┘

┌──────────────────┐  ┌──────────────────┐  ┌──────────────────┐
│  🔄 RITUAL       │  │  ⏲️ TIME BOXING   │  │  📋 CHECKLIST    │
├──────────────────┤  ├──────────────────┤  ├──────────────────┤
│ Same day/time    │  │ 60-90 min max    │  │ External         │
│ Same location    │  │ Not "until done" │  │ structure        │
│ Same workflow    │  │ Timer creates    │  │ No working       │
│ Reduces friction │  │ urgency          │  │ memory load      │
└──────────────────┘  └──────────────────┘  └──────────────────┘

┌──────────────────┐  ┌──────────────────┐  ┌──────────────────┐
│  🎯 SINGLE FOCUS │  │  📊 CLEAR STEPS  │  │  🏆 COMPLETION   │
├──────────────────┤  ├──────────────────┤  ├──────────────────┤
│ One page at a    │  │ 1. Scan          │  │ Filled notebooks │
│ time during      │  │ 2. Decide        │  │ = tangible proof │
│ processing       │  │ 3. Process       │  │ of work done     │
│ No multitasking  │  │ 4. Commit        │  │ Visible wins     │
└──────────────────┘  └──────────────────┘  └──────────────────┘
```

**Design notes:**
- Grid layout with icons
- One feature per box
- Brief explanation under each
- Consistent icon style
- Encouraging, positive tone

---

## How to Create These

### Option 1: Draw.io (Recommended)
1. Go to https://app.diagrams.net/
2. Start with blank diagram
3. Use shapes library on left
4. Export as PNG (File → Export as → PNG)

### Option 2: Excalidraw (Simple & Fast)
1. Go to https://excalidraw.com/
2. Hand-drawn style (friendly, approachable)
3. Export as PNG

### Option 3: PowerPoint/Keynote
1. Create slides with shapes and text
2. Export as images
3. Simple and works offline

### Option 4: Hand-Drawn
1. Draw on paper with markers
2. Take photo or scan
3. Clean up in any photo editor
4. Authentic and personal

### Tips for All Methods
- **Keep it simple** - Don't over-design
- **High contrast** - Easy to read
- **Consistent colors** - Same meaning = same color
- **Large text** - Readable on phone screens
- **Icons/emojis** - Visual interest and clarity

---

## Adding Diagrams to Repository
```bash
cd ~/etl-learning-system

# Create assets folder if needed
mkdir -p assets

# Add your PNG files
cp ~/Downloads/workflow_overview.png assets/
cp ~/Downloads/decision_tree.png assets/
# etc.

# Update README to show diagrams
nano README.md
# Add: ![Workflow Overview](assets/workflow_overview.png)

# Commit
git add assets/
git commit -m "Add visual diagrams"
git push
```

### In Markdown
```markdown
## Workflow Overview

![ETL Workflow](assets/workflow_overview.png)

The system follows three stages...
```

GitHub will render images automatically!

---

These diagrams will make the system immediately understandable to visual learners and provide quick reference materials.
