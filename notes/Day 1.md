# DAY 1: Linux Basics & Git Fundamentals

**Environment:** Windows with Git Bash  
**Focus:** Local Git workflow only  
**Approach:** Learn concepts → Apply independently

---

## PART 1: Setup & Environment

### **Install Git Bash**
- Download: https://git-scm.com/download/win
- Install with default settings
- Open Git Bash terminal

### **Understanding Windows Paths in Git Bash**
```bash
Windows:     C:\Users\YourName
Git Bash:    /c/Users/YourName

Windows:     D:\Projects  
Git Bash:    /d/Projects

Home:        ~  (shortcut to /c/Users/YourName)
```

**Task 1.1:** Navigate to your Desktop and verify the path
```bash
cd ~/Desktop
pwd
```

---

## PART 2: Linux Command Basics

### **Essential Commands (Try Each)**
```bash
pwd              # Where am I?
ls               # List files
ls -la           # List with hidden files
mkdir foldername # Create directory
cd foldername    # Enter directory
cd ..            # Go up one level
touch file.txt   # Create empty file
cat file.txt     # View file
echo "text"      # Print text
echo "text" > file.txt    # Write to file
echo "text" >> file.txt   # Append to file
cp source dest   # Copy
mv old new       # Move/rename
rm filename      # Delete file
```

**Task 2.1:** Create this structure on your Desktop
```
devops-training/
├── practice/
├── projects/
└── notes/
```

**Task 2.2:** Inside `notes/`, create `commands.txt` and list 5 Linux commands you just learned

**Deliverable:** Screenshot showing folder structure with `tree` or `ls -R`

---

## PART 3: Git Configuration

### **Configure Your Identity**
```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@company.com"
git config --global core.editor "nano"
git config --global init.defaultBranch main

# Verify
git config --list
```

**Task 3.1:** Configure Git with your details and verify the configuration

**Deliverable:** Output of `git config --list` showing your name and email

---

## PART 4: Your First Repository

### **Git Workflow Concept**
```
Working Directory → Staging Area → Repository
   (your files)    →  (git add)   → (git commit)
```

### **Core Commands**
```bash
git init                    # Initialize repo
git status                  # Check status
git add filename            # Stage specific file
git add .                   # Stage all files
git commit -m "message"     # Commit with message
git log                     # View history
git log --oneline           # Compact history
git diff                    # See unstaged changes
git diff --staged           # See staged changes
```

**Task 4.1:** Create Repository "task-manager"
```bash
# Go to devops-training/projects/
# Create folder task-manager
# Initialize Git
# Verify with git status
```

**Task 4.2:** Create These Files
- `README.md` - Project description (what is task manager?)
- `.gitignore` - Add these lines: `*.log`, `*.tmp`, `temp/`

**Task 4.3:** Make Your First Commit
- Stage both files
- Commit with message: "Initial commit: Project setup"
- Verify with `git log`

**Deliverable:** Repository with 1 commit

---

## PART 5: Building Commit History

### **Good Commit Messages**
```bash
✅ "Add user login functionality"
✅ "Fix typo in README"
✅ "Update .gitignore for Python"

❌ "changes"
❌ "fix"
❌ "update"
```

**Task 5.1:** Create Project Structure
```
task-manager/
├── README.md
├── .gitignore
├── src/
│   └── main.py
├── docs/
│   └── TODO.md
└── tests/
    └── test_main.py
```

**Task 5.2:** Make 5 Separate Commits
1. Commit: Create src/main.py with a print statement
2. Commit: Create docs/TODO.md with 3 todo items
3. Commit: Create tests/test_main.py with placeholder comment
4. Commit: Update README.md with project structure section
5. Commit: Update .gitignore to include `__pycache__/` and `*.pyc`

**Rules:**
- Each commit = ONE logical change
- Meaningful commit messages
- Use `git status` before each commit

**Deliverable:** `git log --oneline` showing 6 commits (including initial)

---

## PART 6: Viewing History & Changes

### **Exploration Commands**
```bash
git log                     # Full history
git log --oneline           # Compact
git log -3                  # Last 3 commits
git log --stat              # With file stats
git log -p                  # With changes
git show <commit-hash>      # Specific commit
git diff                    # Unstaged changes
git diff --staged           # Staged changes
git log --graph --all       # Visual graph
```

**Task 6.1:** Modify src/main.py
- Add 3 new lines of code
- Use `git diff` to see changes
- Don't commit yet

**Task 6.2:** Practice Staging
- Stage the file
- Use `git diff --staged` to see staged changes
- Commit with appropriate message

**Task 6.3:** History Analysis
- Find the commit hash of your 3rd commit
- Use `git show <hash>` to view that commit's changes
- Use `git log --stat` to see which files changed in each commit

**Deliverable:** Answers to:
- What was your 3rd commit message?
- Which file had the most changes?
- How many total commits do you have?

---

## PART 7: Undoing Changes

### **Important Commands**
```bash
git restore filename          # Discard unstaged changes (⚠️ permanent!)
git restore --staged filename # Unstage file
git reset HEAD~1              # Undo last commit (keep changes)
```

**Task 7.1:** Practice Unstaging
- Modify README.md and main.py
- Stage both files
- Unstage only README.md
- Commit only main.py
- Then stage and commit README.md separately

**Task 7.2:** Practice Discarding Changes
- Add "TEMPORARY TEST" line to TODO.md
- View the change with `git diff`
- Discard the change using `git restore`
- Verify it's gone

**Deliverable:** Clean working directory (`git status` shows "nothing to commit")

---

## PART 8: Final Challenge

**Task 8.1:** Build a Calculator Project

Requirements:
```
calculator/
├── README.md          # Project description, features list
├── .gitignore         # Python patterns
├── src/
│   └── calculator.py  # Functions: add, subtract, multiply, divide
├── docs/
│   └── usage.md       # How to use each function
└── tests/
    └── notes.txt      # Testing notes
```

**Rules:**
- Minimum 8 commits
- Each commit = one logical addition
- Meaningful commit messages
- Use proper Git workflow (status → add → commit)

**Suggested Commit Sequence:**
1. Initial setup (README + .gitignore)
2. Add calculator.py with add function
3. Add subtract function
4. Add multiply function
5. Add divide function
6. Create usage.md
7. Update README with features
8. Add testing notes

**Deliverable:** 
- `git log --oneline --graph` output
- Repository with 8+ commits
- All files created and committed

---

## PART 9: Personal Learning Journal

**Task 9.1:** Create Learning Repository

Create: `devops-learning` repository with:
```
devops-learning/
├── README.md
├── week1/
│   ├── day1-notes.md
│   ├── commands-learned.md
│   └── questions.md
└── resources/
    └── git-cheatsheet.md
```

**Task 9.2:** Document Today
- In `day1-notes.md`: What you learned, challenges faced
- In `commands-learned.md`: All commands you used today
- In `questions.md`: Questions for tomorrow
- In `git-cheatsheet.md`: Your personal Git reference

**Task 9.3:** Commit Strategy
- Minimum 5 commits showing logical progression
- Push yourself to write good commit messages

**Deliverable:** Learning journal repository ready for Day 2

---

## DAY 1 COMPLETION CHECKLIST

Run these commands to verify:

```bash
# 1. Git configured?
git config user.name && git config user.email

# 2. Task-manager exists with commits?
cd ~/Desktop/devops-training/projects/task-manager
git log --oneline

# 3. Calculator project exists?
cd ~/Desktop/devops-training/projects/calculator
git log --oneline | wc -l  # Should be 8+

# 4. Learning journal exists?
cd ~/Desktop/devops-training/devops-learning
git status
```

---

## EXPECTED OUTCOMES

By end of Day 1, you should be able to:

✅ Navigate Linux file system in Git Bash  
✅ Create files and directories  
✅ Initialize Git repositories  
✅ Stage and commit changes  
✅ Write meaningful commit messages  
✅ View commit history  
✅ Understand working directory vs staging area  
✅ Discard or unstage changes when needed  

**Total Repositories Created:** 3  
**Total Commits Made:** 20+  
**Time Required:** 6-7 hours  

---

## TROUBLESHOOTING

**"git: command not found"**
→ Restart Git Bash

**Can't see .git folder**
→ Use `ls -la` instead of `ls`

**Stuck in vim editor**
→ Press ESC, type `:q!`, press ENTER

**Wrong commit message**
→ `git commit --amend -m "new message"` (only if not pushed)

---

## DAY 2 PREVIEW

Tomorrow you'll learn:
- GitLab (remote repositories)
- Pushing/pulling code
- Cloning repositories
- Collaboration basics

**Prerequisites for Day 2:**
- Bring your `devops-learning` repository
- GitLab account (we'll create together)
- Questions from today

---

**End of Day 1** 🎯