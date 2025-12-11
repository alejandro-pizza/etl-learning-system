# Digital Notes Guide

Complete guide for Jupyter notebooks and digital knowledge management.

---

## Why Jupyter Notebooks?

### For Data Science Students

**Perfect for:**
- ✅ Code examples with explanations
- ✅ Reproducible demonstrations
- ✅ Combining code, output, and documentation
- ✅ Interactive learning (run cells, see results)
- ✅ Sharing code with proper context

**Benefits over plain .py files:**
- Markdown cells for explanations
- Output saved with code (no need to re-run)
- Natural teaching/learning format
- Portfolio-ready (renders nicely on GitHub)

### Integration with Physical Notes
```
Cornell Notebook        Jupyter Notebook
(Concepts)              (Implementation)
──────────────────      ────────────────────
What is algorithm?  →   Code implementing it
Theory/math         →   Working examples
Comparisons         →   Performance tests
When to use?        →   Use case demos
```

**Cross-reference them:**
- In Cornell: "See [notebook name] for code example"
- In Jupyter: "For theory, see Cornell notes page X"

---

## When to Use Jupyter (vs Cornell)

### Decision Rule
```
Can I write executable code to demonstrate this?
    │
    ├─ YES → Jupyter notebook
    │
    └─ NO → Cornell notebook
```

### Jupyter Examples

✅ **Docker commands and examples**
```python
# Demonstrates: Docker container lifecycle

# Pull and run container
!docker run hello-world

# Build custom image
!docker build -t my-app .

# Run with port mapping
!docker run -d -p 8000:8000 my-app
```

✅ **Python data manipulation**
```python
import pandas as pd

# Load data
df = pd.read_csv('data.csv')

# Transform
df_clean = df.dropna().reset_index()

# Demonstrate result
df_clean.head()
```

✅ **SQL queries**
```python
import sqlite3

conn = sqlite3.connect('database.db')

query = """
SELECT customer_id, SUM(amount) as total
FROM orders
GROUP BY customer_id
HAVING total > 1000
"""

pd.read_sql(query, conn)
```

✅ **Machine learning workflow**
```python
from sklearn.model_selection import train_test_split
from sklearn.ensemble import RandomForestClassifier

# Split data
X_train, X_test, y_train, y_test = train_test_split(X, y)

# Train model
model = RandomForestClassifier()
model.fit(X_train, y_train)

# Evaluate
print(f"Accuracy: {model.score(X_test, y_test)}")
```

### Cornell Examples

❌ **Architectural concepts** (can't execute Docker philosophy)
❌ **Database normalization theory** (can't run "3rd normal form")
❌ **Statistical concepts** (formulas yes, but explaining theory no)
❌ **Comparison analysis** (X vs Y requires prose, not code)
❌ **Design patterns** (code examples would go in Jupyter, but pattern theory in Cornell)

---

## Notebook Template Structure

### Template Sections

Your template has 8 sections. Here's why each matters:
```python
"""
1. TOPIC/METADATA
   → What, when, where
"""

# %% 2. Setup and Imports
# → Get environment ready

# %% 3. Key Concepts
"""
→ What you'll learn (summary)
"""

# %% 4-6. Code Examples (Concepts 1, 2, 3...)
# → Demonstrations with explanations

# %% 7. Practice Problem
"""
→ Apply what you learned
"""

# %% 8. Key Takeaways
"""
→ Synthesis and reflection
"""

# %% 9. Questions & Next Steps
"""
→ What's still unclear, what to explore
"""

# %% 10. References
"""
→ Sources and resources
"""
```

### Section-by-Section Guide

#### 1. Metadata Header
```python
"""
TOPIC: Docker Basics - Containers and Images
WEEK/DATE: Week 1 (Dec 9-14, 2024)
COURSE: MLOps
SOURCES: Saturday lecture, Docker docs, LinkedIn Learning video
"""
```

**Why this matters:**
- Quick identification when browsing notebooks
- Know how recent the information is
- Trace back to source if needed
- Portfolio: shows organized learning

#### 2. Setup and Imports
```python
# %% Setup and Imports
# Load libraries needed for this notebook

import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

# Configure display settings
pd.set_option('display.max_columns', None)
plt.style.use('seaborn-v0_8')

# Set random seed for reproducibility
np.random.seed(42)

print("Setup complete!")
```

**Best practices:**
- Group imports logically (standard lib, third-party, local)
- Configure settings once at top
- Set random seeds for reproducibility
- Simple confirmation that cell ran

#### 3. Key Concepts
```python
# %% Key Concepts
"""
Main ideas covered in this notebook:

1. **Containers vs Virtual Machines**
   - Containers share host OS kernel (lightweight)
   - VMs include full OS (heavyweight)
   - Containers start in seconds, VMs in minutes

2. **Images and Containers**
   - Images = read-only templates (blueprints)
   - Containers = running instances of images
   - One image can spawn many containers

3. **Docker Commands**
   - `docker run` - create and start container
   - `docker build` - create image from Dockerfile
   - `docker ps` - list running containers
   - `docker stop` - stop container

4. **Port Mapping**
   - `-p host_port:container_port`
   - Connects external access to internal container
   - Essential for web apps and services
"""
```

**Why this section:**
- Sets expectations for what's covered
- Quick reference without reading whole notebook
- Forces you to identify key learnings
- Study aid: read this section to refresh memory

**Format tips:**
- Use markdown cell (not code comment)
- 3-5 concepts maximum
- Brief explanation under each
- Numbered for easy reference

#### 4-6. Code Example Sections

**Pattern for each concept:**
```python
# %% Concept 1: Container Lifecycle
# What this demonstrates: Creating, running, and managing containers

# Pull image from Docker Hub
!docker pull python:3.9-slim

# Run container interactively
!docker run -it python:3.9-slim python --version
# Output: Python 3.9.X

# Run container in background (detached)
!docker run -d --name my-python python:3.9-slim sleep 3600

# List running containers
!docker ps
# Shows: my-python container running

# Stop container
!docker stop my-python

# Remove container
!docker rm my-python

print("✓ Demonstrated container lifecycle")
```

**Example structure:**
1. **Concept header** - What you're demonstrating
2. **Brief explanation** - What this shows
3. **Code blocks** - Actual commands/code
4. **Comments** - Explain each step
5. **Output annotations** - What you should see
6. **Confirmation** - Checkpoint that it worked

**Tips:**
- **One concept per section** - Don't mix topics
- **Working code only** - Test before committing
- **Explain "why" not just "how"** - "We use -d flag to run in background"
- **Show output** - Include expected results as comments
- **Error handling** - Note common mistakes

#### 7. Practice Problem
```python
# %% Practice Problem
"""
Problem: 
Create a containerized Flask API that returns "Hello, World!" when accessed.

Requirements:
- Use Python 3.9 slim image
- Map port 5000 to host
- Container should run in background
- Be able to curl http://localhost:5000

Approach:
1. Create simple Flask app
2. Write Dockerfile
3. Build image
4. Run container with port mapping
5. Test with curl

Why this works:
Flask runs on port 5000 by default, -p flag maps it to host,
-d flag runs in background so we can test it.
"""

# Step 1: Create Flask app
flask_app = """
from flask import Flask
app = Flask(__name__)

@app.route('/')
def hello():
    return 'Hello, World!'

if __name__ == '__main__':
    app.run(host='0.0.0.0', port=5000)
"""

with open('app.py', 'w') as f:
    f.write(flask_app)

# Step 2: Create Dockerfile
dockerfile = """
FROM python:3.9-slim
WORKDIR /app
RUN pip install flask
COPY app.py .
CMD ["python", "app.py"]
"""

with open('Dockerfile', 'w') as f:
    f.write(dockerfile)

# Step 3: Build image
!docker build -t flask-hello .

# Step 4: Run container
!docker run -d -p 5000:5000 --name flask-app flask-hello

# Step 5: Test (wait a moment for app to start)
import time
time.sleep(2)

!curl http://localhost:5000
# Should output: Hello, World!

# Cleanup
!docker stop flask-app
!docker rm flask-app

print("✓ Practice problem complete!")
```

**Practice problem guidelines:**
- **Real-world application** of concepts learned
- **Step-by-step solution** with explanations
- **Working code** that actually runs
- **Cleanup** at end (don't leave containers running)
- **Difficulty:** Slightly beyond examples (but achievable)

#### 8. Key Takeaways
```python
# %% Key Takeaways
"""
What I learned:
- Containers provide lightweight isolation by sharing the host kernel
- Docker images are immutable templates; containers are running instances
- Port mapping (-p flag) is essential for accessing containerized services
- Always clean up stopped containers and unused images

Common pitfalls:
- Forgetting to publish ports → can't access container services
- Not stopping containers before removing → use docker rm -f
- Using 'latest' tag → not reproducible, pin versions instead
- Running everything as root in containers → security risk

When to use Docker:
- Need consistent environment across dev/staging/prod
- Deploying microservices (one container per service)
- Isolating dependencies (prevent version conflicts)
- CI/CD pipelines (build once, deploy anywhere)

Related concepts to explore:
- Docker Compose for multi-container apps
- Docker volumes for persistent data
- Kubernetes for container orchestration
"""
```

**Takeaways purpose:**
- **Consolidate learning** - What actually matters?
- **Prevent mistakes** - What went wrong when you tried?
- **Context** - When would you actually use this?
- **Next steps** - What should you learn next?

#### 9. Questions & Next Steps
```python
# %% Questions & Next Steps
"""
Questions I still have:
- How does Docker networking actually work under the hood?
- What's the difference between ENTRYPOINT and CMD in Dockerfile?
- Best practices for handling secrets in containers?
- When to use multi-stage builds vs simple builds?

Topics to explore:
- Docker Compose for multi-container orchestration
- Container security best practices
- Docker in CI/CD pipelines
- Kubernetes basics

Resources to check out:
- Docker docs on networking: https://docs.docker.com/network/
- "Docker Deep Dive" book by Nigel Poulton
- Play with Docker online lab: https://labs.play-with-docker.com/
"""
```

**Questions section purpose:**
- **Honest about gaps** - What don't you understand yet?
- **Learning roadmap** - What's next in your journey?
- **Bookmark resources** - Where to find answers
- **Future reference** - When you come back, know what to study

#### 10. References
```python
# %% References
"""
Lectures:
- MLOps Week 1 - Docker Introduction (Dec 14, 2024)
- Office hours with Prof. Chen (Dec 15, 2024)

Reading:
- "Docker Deep Dive" by Nigel Poulton - Chapters 3-4
- Docker Documentation: https://docs.docker.com/get-started/

Videos:
- Docker Tutorial for Beginners (TechWorld with Nana)
  https://www.youtube.com/watch?v=...

Related notebooks:
- [Docker Compose](20241221_docker_compose.ipynb)
- [Kubernetes Intro](../../kubernetes/week-05/20250115_k8s_intro.ipynb)

Cornell notes:
- Page 12-15: Docker architecture theory
"""
```

**References purpose:**
- **Trace sources** - Where did this information come from?
- **Additional learning** - What else should you read?
- **Connect resources** - Link to related materials
- **Credit** - Acknowledge sources (academic integrity)

---

## Creating a New Notebook

### From Template
```bash
cd ~/ds-masters-portfolio

# Copy template
cp templates/notebook_template.ipynb courses/mlops/week-01/20241214_docker_basics.ipynb

# Open in Jupyter
jupyter notebook courses/mlops/week-01/20241214_docker_basics.ipynb
```

### Naming Convention

**Format:** `YYYYMMDD_topic_name.ipynb`

**Examples:**
- `20241214_docker_basics.ipynb`
- `20241221_ci_cd_pipelines.ipynb`
- `20250115_feature_engineering.ipynb`

**Why this format:**
- ✅ Sorts chronologically automatically
- ✅ Unique names (date + topic)
- ✅ Easy to find "when did I learn X?"
- ✅ Professional naming for portfolio

### Filling In Template

**Time estimate:** 20-30 minutes per notebook

**Process:**
1. **Update header** (1 min) - Topic, date, course, sources
2. **Setup imports** (2 min) - What libraries do you need?
3. **Key concepts** (3 min) - List 3-5 main points
4. **Code examples** (15-20 min) - One section per concept
5. **Practice problem** (optional, 10 min) - If you have time
6. **Takeaways** (2 min) - Reflect on what you learned
7. **Questions** (1 min) - What's unclear?
8. **References** (1 min) - List sources

**Don't:**
- ❌ Aim for perfection
- ❌ Include everything from raw notes
- ❌ Write essay-length explanations
- ❌ Copy-paste without understanding

**Do:**
- ✅ Focus on key concepts (3-5 max)
- ✅ Working code examples
- ✅ Brief, clear explanations
- ✅ Done is better than perfect

---

## Jupyter Best Practices

### Code Quality
```python
# ❌ BAD - No explanation, magic numbers
df = pd.read_csv('data.csv')
df = df[df['age'] > 25]
result = df.groupby('city')['salary'].mean()

# ✅ GOOD - Clear intent, explained
# Load customer data
df = pd.read_csv('customer_data.csv')

# Filter to working-age population (25+)
MIN_AGE = 25
df_working_age = df[df['age'] > MIN_AGE]

# Calculate average salary by city
avg_salary_by_city = df_working_age.groupby('city')['salary'].mean()

# Display results
print(f"Found {len(avg_salary_by_city)} cities")
avg_salary_by_city.head()
```

**Guidelines:**
- **Comments explain "why"**, code shows "how"
- **Named constants** instead of magic numbers
- **Descriptive variable names** - `df_clean` not `df2`
- **Show output** - Let reader see results

### Cell Organization
```python
# ✅ GOOD - One clear purpose per cell
# Cell 1: Imports
import pandas as pd
import numpy as np

# Cell 2: Load data
df = pd.read_csv('data.csv')

# Cell 3: Basic exploration
print(df.shape)
df.head()

# Cell 4: Data cleaning
df_clean = df.dropna()
```
```python
# ❌ BAD - Everything in one cell
import pandas as pd
df = pd.read_csv('data.csv')
print(df.shape)
df_clean = df.dropna()
result = df_clean.groupby('x')['y'].mean()
# ... 50 more lines
```

**Cell guidelines:**
- **One logical step per cell**
- **Run cells in order should work**
- **Rerunning middle cell shouldn't break things**
- **~10-20 lines per cell max**

### Markdown Usage
```markdown
## Section Heading

Brief introduction to what this section covers.

### Subsection

More specific topic within the section.

**Key point:** Use bold for emphasis.

- Bullet points for lists
- Keep it concise
- Not essay paragraphs

Code inline: `docker run -d`

Math inline: $\mu = \frac{1}{n}\sum_{i=1}^{n} x_i$
```

**Markdown tips:**
- **Headers** - Use ## and ### for structure
- **Bold/italic** - Sparingly for emphasis
- **Lists** - Organize information
- **Code formatting** - Use backticks for commands
- **Math** - LaTeX for formulas if needed

### Output Management
```python
# ✅ Display subset, not entire dataframe
df.head(10)  # First 10 rows

# ✅ Sample for large datasets
df.sample(5)  # Random 5 rows

# ✅ Summarize instead of printing everything
print(f"Loaded {len(df)} rows")
print(df.describe())

# ❌ Don't print entire large dataframe
df  # Shows all rows (bad for 100k+ rows)
```

**Output guidelines:**
- **Truncate large outputs** - Sample or head()
- **Visualize when possible** - Plots > numbers
- **Clear output** - Use clear_output() in loops
- **Suppress unnecessary** - Add semicolon to end

### Reproducibility
```python
# Set random seeds
import random
import numpy as np

RANDOM_SEED = 42
random.seed(RANDOM_SEED)
np.random.seed(RANDOM_SEED)

# Pin versions in requirements
# requirements.txt:
# pandas==1.5.3
# scikit-learn==1.2.2

# Document environment
import sys
print(f"Python version: {sys.version}")
print(f"Pandas version: {pd.__version__}")
```

**Reproducibility checklist:**
- ✅ Set random seeds
- ✅ Pin package versions
- ✅ Document environment
- ✅ Relative paths (not `/Users/you/...`)
- ✅ Include sample data or generation code

---

## Advanced Patterns

### Reusable Functions
```python
# %% Helper Functions

def load_and_clean_data(filepath):
    """
    Load CSV and perform standard cleaning.
    
    Args:
        filepath: Path to CSV file
    
    Returns:
        Cleaned DataFrame
    """
    df = pd.read_csv(filepath)
    df = df.dropna()
    df = df.reset_index(drop=True)
    return df

def plot_distribution(series, title):
    """Quick distribution plot with stats."""
    fig, ax = plt.subplots(figsize=(10, 6))
    series.hist(bins=50, ax=ax)
    ax.axvline(series.mean(), color='r', linestyle='--', label=f'Mean: {series.mean():.2f}')
    ax.set_title(title)
    ax.legend()
    plt.show()

# Use functions in later cells
df = load_and_clean_data('data.csv')
plot_distribution(df['age'], 'Age Distribution')
```

### Progress Tracking
```python
# For long-running operations
from tqdm.notebook import tqdm

results = []
for item in tqdm(large_list, desc="Processing items"):
    result = expensive_operation(item)
    results.append(result)
```

### Interactive Widgets
```python
# Create interactive explorations
import ipywidgets as widgets
from IPython.display import display

def plot_filtered_data(threshold):
    filtered = df[df['value'] > threshold]
    plt.figure(figsize=(10, 6))
    filtered['value'].hist(bins=50)
    plt.title(f'Values > {threshold}')
    plt.show()

slider = widgets.IntSlider(min=0, max=100, value=50, description='Threshold:')
output = widgets.interactive_output(plot_filtered_data, {'threshold': slider})

display(slider, output)
```

---

## GitHub Integration

### Committing Notebooks
```bash
cd ~/ds-masters-portfolio

# Add new notebook
git add courses/mlops/week-01/20241214_docker_basics.ipynb

# Commit
git commit -m "Week 1: Docker basics - containers, images, lifecycle"

# Push
git push origin main
```

### Notebook Rendering

**GitHub automatically renders:**
- Markdown cells
- Code cells
- Output (text, plots, tables)
- Images

**Looks professional without any extra work!**

### Linking Notebooks

**In docs/courses/MLOps.md:**
```markdown
### 3. Containerization

**Related notebooks:** 
- [Docker Basics](../../courses/mlops/week-01/20241214_docker_basics.ipynb)
- [Docker Compose](../../courses/mlops/week-02/20241221_docker_compose.ipynb)
```

**In notebook, link to docs:**
```python
"""
For conceptual overview of Docker architecture, 
see docs/courses/MLOps.md or Cornell notes page 12-15.
"""
```

### nbviewer Alternative

For better rendering than GitHub:
```markdown
View this notebook on [nbviewer](https://nbviewer.org/github/alejandro-pizza/ds-masters-portfolio/blob/main/courses/mlops/week-01/20241214_docker_basics.ipynb)
```

---

## Workflow Integration

### Raw Notes → Jupyter

**Sunday/Monday processing:**

1. **Identify code-heavy topic** in raw notes
2. **Copy template** with proper naming
3. **Open in Jupyter**
4. **Fill in header** from raw notes
5. **Extract code examples** from raw notes
6. **Test all code** - make sure it runs
7. **Add explanations** in markdown
8. **Write takeaways** - synthesis
9. **Save and commit**

### Cross-referencing

**In Jupyter, reference Cornell:**
```python
"""
For theoretical foundation of these algorithms,
see Cornell notebook page 23-26: "ML Algorithms Theory"
"""
```

**In Cornell, reference Jupyter:**
```
See Jupyter notebook: 20241214_ml_algorithms.ipynb
for working implementations of these concepts
```

### Knowledge Base Updates

**After creating notebook:**
```bash
# Update course page
nano docs/courses/MLOps.md

# Add under relevant concept:
**Related notebooks:** 
- [Docker Basics](../../courses/mlops/week-01/20241214_docker_basics.ipynb) ← ADD THIS
```

---

## Common Issues

### "Notebook won't run on another machine"

**Causes:**
- Hardcoded file paths
- Missing dependencies
- Different package versions

**Solutions:**
- Use relative paths: `../data/file.csv`
- Include requirements.txt
- Pin versions: `pandas==1.5.3`

### "Output takes forever to load on GitHub"

**Causes:**
- Large outputs (100k+ rows printed)
- Many plots (50+ visualizations)

**Solutions:**
- Clear output before committing: Cell → All Output → Clear
- Use `.head()` to limit rows
- Compress plots: `plt.savefig('plot.png', dpi=72)`

### "Cell outputs don't match code"

**Causes:**
- Cells run out of order
- Global state changed

**Solutions:**
- Always Kernel → Restart & Run All before committing
- Design cells to be order-independent when possible
- Use functions instead of modifying global variables

### "Can't reproduce results"

**Causes:**
- No random seed set
- External data changed
- Package versions different

**Solutions:**
- Set `np.random.seed(42)` at top
- Include data generation code or sample
- Pin package versions

---

## Jupyter Shortcuts

### Must-Know

- **Shift+Enter** - Run cell, select next
- **Ctrl+Enter** - Run cell, stay selected
- **A** - Insert cell above
- **B** - Insert cell below
- **DD** - Delete cell
- **M** - Convert to markdown
- **Y** - Convert to code
- **Esc** - Command mode
- **Enter** - Edit mode

### Useful

- **Ctrl+Shift+-** - Split cell at cursor
- **Shift+M** - Merge selected cells
- **II** - Interrupt kernel
- **00** - Restart kernel
- **Shift+L** - Toggle line numbers
- **H** - Show all shortcuts

---

## Next Steps

1. **Create your first notebook** from template
2. **Process one page** of raw notes into Jupyter
3. **Commit to GitHub** and view rendering
4. **Update knowledge base** with link
5. **Review** this guide as you develop your workflow

Remember: Notebooks are for **demonstration and learning**, not production code. 
Focus on clarity and teaching yourself (future you is your audience).
