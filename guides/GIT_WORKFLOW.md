# Git Workflow Guide

Complete guide for using Git and GitHub to manage your learning repository.

---

## Why Git for Learning?

### Benefits

**Version Control:**
- ✅ Never lose work (everything backed up)
- ✅ See what you learned when (commit history)
- ✅ Undo mistakes easily (revert changes)
- ✅ Try experiments safely (branches)

**Portfolio:**
- ✅ Shows your learning journey
- ✅ Professional presence (GitHub profile)
- ✅ Code samples for job applications
- ✅ Demonstrates Git skills

**Discipline:**
- ✅ Regular commits = regular processing
- ✅ Commit messages = progress summary
- ✅ Green squares = motivation
- ✅ Public accountability (if repo is public)

---

## Git Basics

### Core Concepts
```
Working Directory  →  Staging Area  →  Local Repository  →  Remote (GitHub)
(Your files)         (git add)        (git commit)         (git push)
```

**Working Directory:**
- Files on your computer
- Where you edit and create

**Staging Area:**
- Files ready to commit
- `git add` moves files here

**Local Repository:**
- Committed changes on your computer
- `git commit` saves here

**Remote Repository:**
- GitHub (online backup)
- `git push` sends changes here

---

## Essential Commands

### Daily Workflow
```bash
# 1. Check what changed
git status

# 2. Add files to staging
git add .                         # Add everything
git add courses/mlops/            # Add specific folder
git add *.ipynb                   # Add all notebooks

# 3. Commit with message
git commit -m "Week 1: Docker basics"

# 4. Push to GitHub
git push origin main

# That's it! 90% of your Git usage
```

### Checking Status
```bash
# See what's changed
git status

# See changes in files
git diff                         # All changes
git diff filename.ipynb          # Specific file

# See commit history
git log                          # Full history
git log --oneline                # Compact view
git log --oneline -10            # Last 10 commits
```

### Viewing History
```bash
# Pretty commit log
git log --graph --oneline --all

# Who changed what
git blame filename.py

# Show specific commit
git show commit-hash
```

---

## Weekly Workflow

### Sunday/Monday Processing
```bash
# Navigate to repository
cd ~/ds-masters-portfolio

# Check current status
git status
# Should show: modified/new files in courses/, docs/

# Review what you're about to commit
git diff

# Add all new/modified files
git add .

# Commit with descriptive message
git commit -m "Week 3: MLOps - CI/CD pipelines and Docker Compose"

# Push to GitHub
git push origin main

# Verify on GitHub
# Visit: https://github.com/[username]/ds-masters-portfolio
```

### Commit Message Format

**Pattern:** `Week [X]: [Course(s)] - [Topics covered]`

**Good examples:**
```
Week 1: MLOps - Docker basics and containerization
Week 2: MLOps and MDA - Docker Compose and data lake architecture
Week 3: Statistics - Hypothesis testing and confidence intervals
Backfill: Machine Learning - Decision trees implementation
Project: Customer churn prediction - Initial EDA
Update: Add Docker networking to MLOps knowledge base
Fix: Correct formula in statistics Cornell notes
```

**Bad examples:**
```
Update files                     # Too vague
Week 3                           # No information about content
asdf                             # Not descriptive
Added stuff                      # Not professional
```

**Why good commit messages matter:**
- Future you will thank present you
- Easy to find when something was learned
- Portfolio viewers understand your progress
- Professional habit for career

---

## Common Scenarios

### Scenario 1: Forgot to Commit Last Week
```bash
cd ~/ds-masters-portfolio

# Check what's uncommitted
git status

# See how far behind you are
git log origin/main..HEAD

# Commit everything at once
git add .
git commit -m "Weeks 2-3: Catch-up commit - Docker and CI/CD concepts"
git push origin main

# Note: Better to commit weekly, but this works in a pinch
```

### Scenario 2: Made Mistake in Commit Message
```bash
# Oops, just committed with typo
git commit -m "Week 3: Docke basics"  # Typo!

# Fix the last commit message (before pushing)
git commit --amend -m "Week 3: Docker basics"

# Now push
git push origin main

# Note: Only do this if you haven't pushed yet
```

### Scenario 3: Want to Undo Last Commit
```bash
# Committed but realize something is wrong

# Option A: Keep changes, undo commit
git reset --soft HEAD~1
# Changes are still there, just not committed
# Fix issues, then commit again

# Option B: Keep changes, unstage them
git reset HEAD~1
# Changes are there but not staged
# More control over what to commit

# Option C: Completely undo (careful!)
git reset --hard HEAD~1
# DELETES changes, cannot be undone
# Only use if you're sure

# After fixing, commit again
git add .
git commit -m "Week 3: Docker basics (corrected)"
git push origin main
```

### Scenario 4: Accidentally Committed Large File
```bash
# Oh no, committed a 500MB dataset

# Remove from last commit
git rm --cached data/large_file.csv
git commit --amend -m "Week 3: Docker basics (removed dataset)"

# Add to .gitignore
echo "data/*.csv" >> .gitignore
git add .gitignore
git commit -m "Add data files to gitignore"

# Push
git push origin main --force  # Need force because we amended
```

### Scenario 5: Work on Multiple Machines
```bash
# On laptop, made changes
git add .
git commit -m "Week 3: Docker notes"
git push origin main

# Later, on desktop...
cd ~/ds-masters-portfolio

# Pull latest changes
git pull origin main

# Now desktop has laptop's work
# Continue working, commit, push
git add .
git commit -m "Week 3: Add Docker practice problems"
git push origin main

# Back to laptop...
git pull origin main
# Now laptop has desktop's work
```

### Scenario 6: Merge Conflict
```bash
# Edited same file on two machines
# Forgot to pull before editing

git push origin main
# Error: remote has changes you don't have

# Pull and merge
git pull origin main

# If conflict:
# Git marks conflicts in files like:
<<<<<<< HEAD
Your version of text
=======
Remote version of text
>>>>>>> origin/main

# Edit file to keep what you want
nano conflicted_file.md
# Remove conflict markers, keep correct version

# Stage and commit the resolution
git add conflicted_file.md
git commit -m "Resolve merge conflict in conflicted_file"
git push origin main
```

---

## Branching for Projects

### When to Branch

**Use branches for:**
- ✅ Major projects (branch per project)
- ✅ Experimental work
- ✅ Collaborative group projects
- ✅ Trying new organization approaches

**Don't branch for:**
- ❌ Weekly notes (just commit to main)
- ❌ Simple updates
- ❌ Minor edits

### Branch Workflow
```bash
# Create and switch to new branch
git checkout -b project-customer-churn

# Work on project, commit as usual
git add .
git commit -m "Add initial data exploration"

# Push branch to GitHub
git push origin project-customer-churn

# Continue working...
git add .
git commit -m "Build baseline model"
git push origin project-customer-churn

# When project complete, merge to main
git checkout main
git merge project-customer-churn

# Push merged changes
git push origin main

# Delete branch (optional)
git branch -d project-customer-churn
git push origin --delete project-customer-churn
```

### Viewing Branches
```bash
# List local branches
git branch

# List all branches (including remote)
git branch -a

# Switch between branches
git checkout main
git checkout project-customer-churn
```

---

## .gitignore Best Practices

### What to Ignore

Your `.gitignore` should exclude:
```
# Jupyter
.ipynb_checkpoints/
*/.ipynb_checkpoints/*

# Python
__pycache__/
*.pyc
venv/
env/

# Data files (usually too large)
*.csv
*.xlsx
*.parquet
*.db
data/
datasets/

# OS files
.DS_Store
Thumbs.db

# IDE
.vscode/
.idea/

# Personal
raw_notes/       # Keep physical notes local
personal/
scratch/

# Large files
*.zip
*.tar.gz
models/*.h5      # Large model files
```

### Checking .gitignore
```bash
# Is file ignored?
git check-ignore -v filename.csv

# List all ignored files
git status --ignored
```

### Adding to .gitignore After Commit
```bash
# Oops, already committed large file

# Remove from Git (keep local file)
git rm --cached large_file.csv

# Add to .gitignore
echo "*.csv" >> .gitignore

# Commit the removal
git add .gitignore
git commit -m "Add CSV files to gitignore and remove committed data"
git push origin main
```

---

## GitHub Features

### README.md

**Make your README informative:**
```markdown
# Data Science Masters Portfolio

Brief description of your program and learning system.

## Structure
- courses/ - Refined Jupyter notebooks
- docs/ - Knowledge base
- projects/ - Course projects

## Current Courses
- MLOps
- Modern Data Architectures

[Link to knowledge base](docs/README.md)
```

### Issues

**Track TODOs and bugs:**
```
Title: Backfill Statistics course notes
Label: backfill, documentation

Description:
Need to create notebooks for key statistics concepts:
- [ ] Hypothesis testing
- [ ] Regression analysis
- [ ] Bayesian inference

Priority: Medium
```

### Projects (GitHub Projects)

**Organize semester work:**
```
Board: Spring 2025
Columns: To Do, In Progress, Done

Cards:
- Process Week 1 notes
- Complete MLOps assignment
- Backfill ML course
- Prepare for midterm
```

### GitHub Desktop (Optional)

**If you prefer GUI over command line:**

1. Download: https://desktop.github.com/
2. Sign in with GitHub account
3. Clone repository
4. Visual interface for:
   - Viewing changes
   - Creating commits
   - Pushing to GitHub
   - Managing branches

**Still learn command line basics** (more powerful, universal)

---

## Troubleshooting

### "Fatal: Not a git repository"
```bash
# You're not in the right directory
pwd  # Check where you are

# Navigate to repository
cd ~/ds-masters-portfolio

# Verify it's a git repo
ls -la .git  # Should exist
```

### "Permission denied (publickey)"
```bash
# SSH key issue

# Check if you have SSH key
ls -la ~/.ssh

# If not, generate one
ssh-keygen -t ed25519 -C "your_email@example.com"

# Add to GitHub: Settings → SSH Keys → New SSH key
cat ~/.ssh/id_ed25519.pub
# Copy output and paste into GitHub

# Or use HTTPS instead of SSH
git remote set-url origin https://github.com/username/repo.git
```

### "Your branch is ahead of origin/main by X commits"
```bash
# You have local commits not pushed

# Push them
git push origin main
```

### "Your branch is behind origin/main by X commits"
```bash
# Remote has changes you don't

# Pull them
git pull origin main
```

### "Merge conflict"
```bash
# Edited same file in two places

# Pull to trigger merge
git pull origin main

# Git shows conflicts in files:
<<<<<<< HEAD
Your version
=======
Remote version
>>>>>>> origin/main

# Edit file, choose what to keep
nano conflicted_file.md

# Remove conflict markers, save

# Stage and commit
git add conflicted_file.md
git commit -m "Resolve merge conflict"
git push origin main
```

### "Detached HEAD state"
```bash
# Checked out specific commit

# To fix, get back on a branch
git checkout main
```

---

## Advanced Tips

### Aliases (Shortcuts)
```bash
# Add to ~/.gitconfig or ~/.zshrc

git config --global alias.st status
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.ci commit
git config --global alias.unstage 'reset HEAD --'

# Now use shortcuts
git st        # instead of git status
git co main   # instead of git checkout main
```

### Stashing
```bash
# Need to switch branches but have uncommitted work

# Stash changes
git stash

# Do other work, switch branches, etc.

# Restore stashed changes
git stash pop

# View stashes
git stash list
```

### Cherry-Picking
```bash
# Want specific commit from another branch

# Get commit hash
git log feature-branch

# Apply that commit to current branch
git cherry-pick abc123def
```

### Viewing Diff of Notebooks
```bash
# Notebooks are JSON, hard to read diffs

# Install nbdime
pip install nbdime

# Configure for git
nbdime config-git --enable

# Now git diff shows readable notebook changes
```

---

## GitHub Profile Optimization

### Contributions Graph

**Your green squares:**
- Commits count toward graph
- Visible on profile
- Shows consistency

**To maximize:**
- ✅ Commit weekly (at minimum)
- ✅ Use meaningful commit messages
- ✅ Push regularly (commits don't count until pushed)

### Profile README

**Create `username/username` repository:**
```markdown
# Hi, I'm [Your Name] 👋

## About Me
Data Science graduate student at [University]

## Currently Learning
- MLOps and production ML systems
- Modern data architectures
- Advanced statistics

## Projects
- [Project 1](link) - Description
- [Project 2](link) - Description

## Learning System
I use an [ETL-based learning system](link) for organizing coursework

📫 Connect: [LinkedIn](url) | [Email](mailto:)
```

### Pinned Repositories

**Pin your best work:**
1. ds-masters-portfolio (this repository)
2. etl-learning-system (if you made it)
3. Top 2-3 projects

---

## Git Cheat Sheet

### Most Common Commands
```bash
# Daily use
git status                   # What changed?
git add .                    # Stage everything
git commit -m "message"      # Commit changes
git push origin main         # Send to GitHub
git pull origin main         # Get from GitHub

# Checking history
git log --oneline            # View commits
git diff                     # See changes

# Fixing mistakes
git reset HEAD~1             # Undo last commit (keep changes)
git checkout -- filename     # Discard changes to file

# Branching
git branch                   # List branches
git checkout -b new-branch   # Create and switch
git merge branch-name        # Merge branch

# Share & Update
git fetch [alias]            # Fetch down all the branches that Git remote
git merge [alias]/[branch]   # Merge a remote granch into your current branch to bring up to date
git push [alias][branch]     # Transmot local branch commits to the remote repo branch
git pull                     # Fetch and merge any commits from the tracking remote branch (aka if you do online edits)
```

### Emergency Commands
```bash
# Messed up, want fresh copy
git fetch origin
git reset --hard origin/main

# Accidentally deleted file
git checkout HEAD -- filename

# Want to start over
cd ..
rm -rf repository-name
git clone https://github.com/username/repo.git
```

---

## Integration with Learning Workflow

### During Weekly Processing
```bash
# After processing session complete:

# 1. Stage everything
git add .

# 2. Commit with summary
git commit -m "Week 3: Docker Compose and networking - MLOps"

# 3. Push to GitHub
git push origin main

# 4. Verify on GitHub
# Open browser, check repository

# 5. Check contribution graph (dopamine hit!)
```

### After Completing Project
```bash
# If you used a branch
git checkout main
git merge project-branch
git push origin main
git branch -d project-branch

# If you worked on main
git add projects/project-name/
git commit -m "Complete customer churn prediction project"
git push origin main
```

### End of Semester
```bash
# Create semester tag
git tag -a spring-2025 -m "Spring 2025 semester complete"
git push origin spring-2025

# Tag marks this point in history
# Can always return to it
```

---

## Resources

### Learning Git

**Interactive Tutorials:**
- Learn Git Branching: https://learngitbranching.js.org/
- GitHub Learning Lab: https://lab.github.com/

**Documentation:**
- Git Official Docs: https://git-scm.com/doc
- GitHub Docs: https://docs.github.com/
- GitHub Education: https://education.github.com/

**Books:**
- Pro Git (free): https://git-scm.com/book/en/v2
- GitHub for Dummies

**Videos:**
- Git & GitHub Crash Course (FreeCodeCamp)
- Git Tutorial for Beginners (Programming with Mosh)

### Git GUIs

**Desktop Apps:**
- GitHub Desktop (easiest)
- GitKraken (powerful)
- SourceTree (feature-rich)

**IDE Integration:**
- VS Code (built-in)
- PyCharm (built-in)
- Jupyter Lab Git extension

---

## Summary

**Git gives you:**
- ✅ Backup of all work
- ✅ History of learning
- ✅ Professional portfolio
- ✅ Collaboration capability
- ✅ Experimentation safety

**Use Git to:**
- 📝 Commit weekly after processing
- 🔍 Review your learning history
- 🎯 Track progress over time
- 💼 Build professional presence
- 🔄 Work across devices

**Remember:**
- Commit messages matter
- Push regularly (backup!)
- .gitignore large files
- Branches for major projects
- It's okay to make mistakes (that's what Git is for!)

---

*Git seems complex at first, but the basic workflow (add, commit, push) covers 90% of daily use. Master that, and learn the rest as needed.*
