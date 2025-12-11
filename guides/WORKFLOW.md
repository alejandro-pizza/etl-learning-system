# Complete Workflow Guide

This guide walks through the entire ETL Learning System from start to finish.

---

## Weekly Cycle Overview
```
MON-FRI: Extract (Raw Capture)
    ↓
SUN/MON: Transform (Processing Session)
    ↓
ONGOING: Load (Reference & Review)
```

---

## EXTRACT: Raw Capture (During the Week)

### Setup

**Physical:**
- One A5 notebook (portable, always with you)
- Write symbols reference on inside cover

**Inside Front Cover:**
```
SYMBOLS:
- Note          □ Task          ? Question
* Important     > Code          ! Deadline

HEADER FORMAT:
[DATE] | [TYPE] | [SOURCE]

After processing: Cross out date
```

### Capturing Notes

**Every lecture, reading session, video, etc.:**

1. Write date header at top of page
2. Capture chronologically as content flows
3. Use symbols to mark different types of content
4. Don't organize - just write
5. Turn page and continue

**Example:**
```
2024-12-14 | LECTURE | MLOps - Docker Basics
───────────────────────────────────────────────
- Docker containers vs VMs
- Containers share host kernel
□ Install Docker on laptop
? How does networking work between containers
* Key command: docker run -d -p 8000:8000
> docker build -t myapp .
! Assignment due Friday - containerize ML model
```

### Rules for Raw Capture

**DO:**
- ✅ Write everything chronologically
- ✅ Use date headers consistently
- ✅ Apply symbols as you write
- ✅ Keep it messy - this is thinking space
- ✅ Mix school, tasks, thoughts freely

**DON'T:**
- ❌ Try to organize by topic
- ❌ Start new sections/pages for different subjects
- ❌ Worry about neatness
- ❌ Edit or refine while capturing
- ❌ Use multiple notebooks

---

## TRANSFORM: Processing Session (Sunday/Monday)

### Total Time: 60-90 minutes

---

### Step 1: Scan Raw Notebook (5 minutes)

**Actions:**
1. Flip through the week's raw notes
2. Use sticky tabs to mark school-related pages
3. Identify what needs processing

**Mental checklist:**
- Which topics did I cover?
- Which pages have substantial content?
- Any urgent tasks or deadlines?

**Example marking:**
- Page 12: MLOps Docker lecture ← sticky tab
- Page 15: MLOps CI/CD reading ← sticky tab  
- Page 18: Random thoughts about home organization ← skip for now
- Page 20: MDA data lakes lecture ← sticky tab

---

### Step 2: Decide Format (30 seconds per topic)

**Decision rule:**
```
Can I write code or execute this concept?
    │
    ├─ YES → Jupyter notebook (digital)
    │
    └─ NO → Cornell notebook (physical)
```

**Examples:**

| Topic | Format | Why |
|-------|--------|-----|
| Docker commands & examples | Jupyter | Executable code |
| Docker architecture theory | Cornell | Conceptual |
| Python data pipeline | Jupyter | Code examples |
| Database normalization | Cornell | Theory/diagrams |
| SQL queries | Jupyter | Executable |
| Statistics concepts | Cornell | Math/theory |

**If unsure:** Default to Jupyter

---

### Step 3A: Process to Jupyter (20-30 min per topic)

**Setup:**
```bash
cd ~/your-learning-repo
cp templates/notebook_template.ipynb courses/[course]/week-XX/YYYYMMDD_topic.ipynb
jupyter notebook courses/[course]/week-XX/YYYYMMDD_topic.ipynb
```

**Fill in template:**

1. **Header:** Topic, date, course, sources
2. **Setup:** Import libraries
3. **Key Concepts:** List main ideas (3-5)
4. **Code Examples:** One per concept with explanation
5. **Practice Problem:** Apply the concept
6. **Key Takeaways:** What you learned
7. **Questions:** What's still unclear
8. **References:** Sources used

**Tips:**
- Use `# %%` cell markers for sections
- Comment code clearly but simply
- Include output/visualizations
- Note common pitfalls
- Link to related concepts

See [Digital Notes Guide](DIGITAL_NOTES.md) for details.

---

### Step 3B: Process to Cornell (15-20 min per topic)

**In B5 refined notebook:**

**Structure:**
```
[TOPIC - Date Range]
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Cues (2.5")     |  Notes (remaining space)
                |
Key terms       |  • Detailed explanations
Questions       |  • Examples
Formulas        |  • Diagrams
                |  • Connections
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Summary (bottom 2"):
3-5 sentences synthesizing the concept
```

**Process:**
1. Title and date at top
2. Fill notes section (right) with detailed content
3. Add cues/questions (left) after reviewing notes
4. Write summary last - forces synthesis

See [Physical Notes Guide](PHYSICAL_NOTES.md) for details.

---

### Step 4: Task Sweep (5 minutes)

**Scan raw notebook for:**
- `□` Tasks that need action
- `!` Deadlines coming up

**Add to your task system:**
- To-do app
- Calendar
- Assignment tracker
- Weekly planner

---

### Step 5: Mark Processed (2 minutes)

**In raw A5 notebook:**

Go to each processed page and draw a line through the date:
```
2024-12-14 | LECTURE | MLOps - Docker  ← Cross out this line
───────────────────────────────────────────────
```

Visual indicator that you're done with this page.

---

### Step 6: Update Knowledge Base (5-10 minutes)

**Did you learn something significant?**

**Update course page:**
```bash
nano docs/courses/[CourseName].md
```

Add link to your new notebook:
```markdown
### Containerization

**Related notebooks:** 
- [Docker Basics](../../courses/mlops/week-01/20241214_docker.ipynb)
```

**Update tool reference:**
```bash
nano docs/tools/[ToolName].md
```

Add new commands or patterns you learned.

**Add resources:**
- Link to useful article
- Reference to documentation
- Video tutorial you found

See [Knowledge Base Guide](KNOWLEDGE_BASE.md) for details.

---

### Step 7: Commit & Push (3 minutes)
```bash
cd ~/your-learning-repo

# Check what changed
git status

# Add everything
git add .

# Commit with descriptive message
git commit -m "Week X: [Main topics covered]"

# Push to GitHub
git push origin main
```

**Commit message format:**
- `Week 1: Docker basics - containers and images`
- `Week 2: CI/CD pipelines with GitHub Actions`
- `Backfill: Statistics - Hypothesis testing`

See [Git Workflow Guide](GIT_WORKFLOW.md) for details.

---

## LOAD: Reference & Review (Ongoing)

### Using Your Refined Notes

**Physical Cornell notebook:**
- Review weekly before exams
- Cover right side, quiz yourself from cues
- Re-read summaries for quick refresher

**Digital Jupyter notebooks:**
- Search for code examples when coding
- Copy/paste proven patterns
- Review before similar assignments
- Run cells to refresh understanding

**Knowledge base (docs/):**
- Quick reference for concepts
- Find resources when diving deeper
- Link sharing with study groups
- Portfolio for job applications

---

## Time Investment

### Per Week:
- **Capture:** No extra time (you're already in lectures/reading)
- **Processing:** 60-90 minutes
- **Review:** 10-20 minutes (ongoing as needed)

### Return on Investment:
- Better retention from spaced repetition
- Organized reference materials
- Reduced study time before exams
- Professional portfolio for jobs
- Less anxiety about scattered notes

---

## Complete Workflow Diagram
```
MONDAY-FRIDAY (Extract)
┌─────────────────────────────────────┐
│   RAW CAPTURE (A5 Notebook)         │
│   • Lectures                         │
│   • Readings                         │
│   • Videos                           │
│   Chronological, minimal structure   │
└──────────────┬──────────────────────┘
               │
               │ Week accumulates...
               │
SUNDAY/MONDAY  ↓
┌─────────────────────────────────────┐
│   1. SCAN (5 min)                   │
│   □ Mark school pages with tabs     │
└──────────────┬──────────────────────┘
               ↓
┌─────────────────────────────────────┐
│   2. DECIDE (30 sec each)           │
│   Can I code it?                    │
│   YES → Jupyter | NO → Cornell      │
└──────────────┬──────────────────────┘
               │
        ┌──────┴──────┐
        ↓             ↓
┌─────────────┐  ┌──────────────┐
│  3A. JUPYTER│  │ 3B. CORNELL  │
│  (20-30 min)│  │ (15-20 min)  │
│  • Template │  │ • Cues column│
│  • Examples │  │ • Notes      │
│  • Practice │  │ • Summary    │
└──────┬──────┘  └──────┬───────┘
       │                │
       └────────┬───────┘
                ↓
┌─────────────────────────────────────┐
│   4. TASK SWEEP (5 min)             │
│   □ Scan for □ and !                │
└──────────────┬──────────────────────┘
               ↓
┌─────────────────────────────────────┐
│   5. MARK PROCESSED (2 min)         │
│   Cross out dates in raw notebook   │
└──────────────┬──────────────────────┘
               ↓
┌─────────────────────────────────────┐
│   6. UPDATE KNOWLEDGE BASE (5-10min)│
│   • Course pages                    │
│   • Tool references                 │
│   • Resources                       │
└──────────────┬──────────────────────┘
               ↓
┌─────────────────────────────────────┐
│   7. COMMIT & PUSH (3 min)          │
│   git add .                         │
│   git commit -m "Week X: topics"    │
│   git push origin main              │
└─────────────────────────────────────┘
               ↓
        ┌──────┴──────┐
        ↓             ↓
┌──────────────┐  ┌──────────────┐
│ B5 CORNELL   │  │ JUPYTER      │
│ Physical ref │  │ Digital code │
│              │  │              │
│ + DOCS/      │  │ + GITHUB     │
│ Knowledge    │  │ Portfolio    │
└──────────────┘  └──────────────┘
```

---

## Troubleshooting

### "I don't have 90 minutes on Sunday"

**Split the session:**
- Sunday: 45 min - Process most urgent/recent
- Monday: 45 min - Finish remaining topics

**Or prioritize:**
- Always: School notes for current courses
- Sometimes: Previous courses (backfill)
- Rarely: Non-school content

### "I forgot to use symbols while capturing"

**That's okay!**
- Start using them next session
- Or add them during processing
- The system adapts to you

### "I can't decide Jupyter vs Cornell"

**Default to Jupyter**
- Can always print to PDF later if needed
- Searchable and shareable
- Easier to update

### "My raw notes are illegible"

**That's normal!**
- Raw capture is for you during capture
- Illegible parts remind you to write clearer
- Processing while it's fresh solves this

### "What if I miss a week?"

**No problem:**
- System degrades gracefully
- Prioritize most recent/important notes
- Older notes = lower priority (or skip)
- Don't try to catch up on everything
- Resume weekly processing next week

**Better to process:**
- 3 pages perfectly than
- 15 pages poorly

---

## Next Steps

1. Read [Physical Notes Guide](PHYSICAL_NOTES.md)
2. Read [Digital Notes Guide](DIGITAL_NOTES.md)
3. Read [Knowledge Base Guide](KNOWLEDGE_BASE.md)
4. Read [Git Workflow Guide](GIT_WORKFLOW.md)
5. Read [ADHD Strategies](ADHD_STRATEGIES.md) if applicable
6. Set up your first processing session
7. Try with one week of notes
8. Adjust based on what works

---

*The system should serve you, not the other way around. Adapt as needed!*
