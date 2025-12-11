# ETL Learning System

> A comprehensive note-taking and knowledge management system designed for graduate students, particularly those with ADHD. Based on the Extract-Transform-Load (ETL) data pipeline metaphor.

## 🎯 Philosophy

This system addresses common challenges in graduate education:
- **Information overload** during lectures and readings
- **Scattered notes** that are never reviewed
- **Decision paralysis** about where to write things
- **Inconsistency** in note-taking methods
- **Poor retention** of material

**Solution:** A streamlined, three-stage workflow that separates capture from processing, minimizes decisions, and creates both physical and digital reference materials.

---

## 📚 System Overview
```
EXTRACT (Capture)          TRANSFORM (Process)         LOAD (Store)
─────────────────          ───────────────────         ────────────
Raw notebook      →        Weekly sessions      →      Refined notes
- Chronological            • 60-90 minutes             • Cornell method
- Minimal structure        • Format decisions          • Jupyter notebooks
- Zero friction            • Refinement                • Knowledge base
```

### The Three Stages

**1. EXTRACT (During the Week)**
- Capture everything in one A5 notebook chronologically
- Use simple symbols: `• □ ? * > !`
- Date header format: `[DATE] | [TYPE] | [SOURCE]`
- No organization, no decisions - just write

**2. TRANSFORM (Sunday/Monday)**
- 60-90 minute weekly processing session
- Scan raw notes, mark pages with sticky tabs
- Decide: Code-heavy? → Jupyter. Conceptual? → Cornell.
- Process notes using templates

**3. LOAD (Storage)**
- **Physical:** B5 Cornell notebook for concepts/theory
- **Digital:** Jupyter notebooks for code/examples
- **Knowledge base:** Markdown docs with course summaries

---

## 🚀 Quick Start

### Prerequisites
- One A5 notebook (raw capture)
- One B5 notebook (refined notes)
- GitHub account
- Jupyter installed (`pip install jupyter`)

### Setup Steps

1. **Clone this repository:**
```bash
   git clone https://github.com/[username]/etl-learning-system.git
```

2. **Copy templates to your learning repo:**
```bash
   cp -r templates/ ~/your-learning-repo/
```

3. **Read the guides:**
   - [Complete Workflow Guide](guides/WORKFLOW.md)
   - [Physical Note-Taking Guide](guides/PHYSICAL_NOTES.md)
   - [Digital Note-Taking Guide](guides/DIGITAL_NOTES.md)
   - [Knowledge Base Setup](guides/KNOWLEDGE_BASE.md)

4. **Print the weekly checklist:**
   - [Weekly Processing Checklist](templates/checklists/weekly_processing.md)

---

## 📁 Repository Structure
```
etl-learning-system/
├── templates/
│   ├── notebook/
│   │   └── notebook_template.ipynb          # Jupyter notebook template
│   ├── physical/
│   │   ├── cornell_template.md              # Cornell method guide
│   │   └── raw_capture_symbols.md           # Symbol reference
│   └── checklists/
│       ├── weekly_processing.md             # Weekly routine checklist
│       └── setup_checklist.md               # Initial setup checklist
├── guides/
│   ├── WORKFLOW.md                          # Complete workflow guide
│   ├── PHYSICAL_NOTES.md                    # Raw capture & Cornell method
│   ├── DIGITAL_NOTES.md                     # Jupyter notebook guide
│   ├── KNOWLEDGE_BASE.md                    # Docs structure guide
│   ├── GIT_WORKFLOW.md                      # Version control guide
│   └── ADHD_STRATEGIES.md                   # ADHD-specific tips
├── examples/
│   ├── sample_raw_notes.jpg                 # Photo of raw capture
│   ├── sample_cornell_notes.jpg             # Photo of Cornell notes
│   ├── sample_notebook.ipynb                # Example Jupyter notebook
│   └── sample_knowledge_base/               # Example docs structure
└── assets/
    ├── workflow_diagram.png                 # Visual workflow
    └── decision_tree.png                    # Format decision tree
```

---

## 🎓 Who This Is For

- Graduate students managing multiple courses
- People with ADHD who struggle with organization
- Anyone overwhelmed by scattered notes
- Students who want to retain more information
- Technical students who need both code and concept notes

---

## 💡 Key Features

### For ADHD Brains
- **Single capture point** - no decisions about "which notebook"
- **Simple symbols** - consistent, minimal choices
- **Chronological only** - no complex categorization
- **Processing ritual** - structured weekly session
- **Visual completion** - cross out processed pages

### For Learning
- **Writing by hand** - better retention during capture
- **Spaced repetition** - weekly processing reinforces learning
- **Multiple formats** - concepts in Cornell, code in Jupyter
- **Knowledge base** - searchable reference for future use
- **Version control** - track your learning over time

### For Technical Content
- **Jupyter templates** - structured code documentation
- **Git integration** - professional portfolio building
- **Markdown docs** - cross-referenced knowledge base
- **Tool references** - quick lookup for Docker, Git, etc.

---

## 📖 Documentation

### Guides
- [**Complete Workflow**](guides/WORKFLOW.md) - Start here for full system overview
- [**Physical Notes**](guides/PHYSICAL_NOTES.md) - Raw capture & Cornell method
- [**Digital Notes**](guides/DIGITAL_NOTES.md) - Jupyter notebooks & templates
- [**Knowledge Base**](guides/KNOWLEDGE_BASE.md) - Documentation structure
- [**Git Workflow**](guides/GIT_WORKFLOW.md) - Version control for learning
- [**ADHD Strategies**](guides/ADHD_STRATEGIES.md) - Managing decision paralysis

### Templates
- [Jupyter Notebook Template](templates/notebook/notebook_template.ipynb)
- [Cornell Method Template](templates/physical/cornell_template.md)
- [Raw Capture Symbols](templates/physical/raw_capture_symbols.md)
- [Weekly Processing Checklist](templates/checklists/weekly_processing.md)

---

## 🛠️ Customization

This system is designed to be adapted. Common modifications:

**Symbols:** Adjust the symbol set to your needs
**Timing:** Process on different days if Sunday/Monday doesn't work
**Tools:** Use VS Code instead of Jupyter, Obsidian instead of markdown
**Scope:** Start with just school notes, expand to all areas later

---

## 🤝 Contributing

Have improvements or adaptations? Contributions welcome!

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/improvement`)
3. Commit your changes
4. Push and create a Pull Request

---

## 📝 License

MIT License - feel free to use and adapt for your own learning journey.

---

## 🙏 Acknowledgments

This system combines proven note-taking methods:
- **Cornell Method** (Walter Pauk, 1940s)
- **Bullet Journal** (Ryder Carroll, 2013) - simplified symbols
- **ETL Pipeline** (Data engineering metaphor)
- **Zettelkasten principles** (Niklas Luhmann)

Designed specifically for graduate students with ADHD, tested in a Data Science Masters program.

---

## 📧 Questions?

Open an issue or start a discussion. Happy to help you adapt this system!

---

*"The best note-taking system is the one you'll actually use."*
