# 🛠 GitHub Local Setup — Troubleshooting Guide

This guide documents common issues I encountered while setting up and pushing a GitHub project locally on Windows using Git Bash — and how I fixed them.

It serves as a quick reference for others (and future me) when things don't go as expected.

---

## ❌ Error: `src refspec main does not match any`

### 💡 What it means:
You're trying to push a branch (`main`), but it doesn't exist yet because no commit has been made.

### ✅ Fix:
Make your first commit before pushing:

```bash
git add .
git commit -m "Initial commit: setup project structure"
git push -u origin main

❌ Error: fatal: unable to auto-detect email address
💡 What it means:
Git doesn’t know your identity, and it needs your name and email before it can create a commit.

✅ Fix:
Set your Git username and email globally:

bash
Copy
Edit
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
*Use the email associated with your GitHub account.


❌ Error: fatal: protocol 'https' is not supported
💡 What it means:
Your remote URL is broken or malformed — usually from pasting the wrong format when setting the GitHub origin.

✅ Fix:
First, check your remote:

bash
Copy
Edit
git remote -v
If it's wrong, reset it with:

bash
Copy
Edit
git remote set-url origin https://github.com/yourusername/splunk-learning-journal.git
Then push:

bash
Copy
Edit
git push -u origin main

🧠 Pro Tips
Use git status often to check your current state

Use git log to view commit history

Use .gitignore to keep junk files out of your repo

Create a .keep file in empty folders if you want Git to track them

