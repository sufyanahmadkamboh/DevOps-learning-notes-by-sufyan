# 🐙 Git & GitHub Basics

This guide introduces **Git** (a version control system) and **GitHub** (a platform for hosting Git repositories).  
It’s designed for beginners who want to understand not just the commands, but also the **why** and **how** behind Git and GitHub.

---

## 📌 What is Git?
Git is a **Distributed Version Control System (DVCS)**. It lets you:
- Track changes in your files (especially source code).
- Revert to older versions when needed.
- Work on different features in isolation using branches.
- Collaborate with others without overwriting each other’s work.

Think of Git as a **time machine + collaboration tool** for your code.

---

## 🌍 What is GitHub?
[GitHub](https://github.com) is a **cloud-based platform** that hosts Git repositories. It adds collaboration features such as:
- **Remote storage**: Save your code on the cloud.
- **Collaboration**: Multiple people can work on the same project.
- **Pull Requests (PRs)**: Suggest changes that others can review before merging.
- **Issues & Discussions**: Track bugs, ideas, and tasks.
- **Actions (CI/CD)**: Automate workflows (testing, deployments, etc.).

> 🔑 **Key difference**: Git is the tool, GitHub is the hosting service.  
> You can use Git **without GitHub**, but you cannot use GitHub effectively without Git.

---

## ✅ Why Use Git & GitHub?

### Benefits of Git:
- **Version history** – every change is recorded.
- **Branching** – work on new features without affecting main code.
- **Collaboration** – team members can contribute simultaneously.
- **Backup** – your project is safe even if your local system crashes.

### Benefits of GitHub:
- **Remote repository** accessible from anywhere.
- **Community collaboration** (open-source).
- **Code reviews via Pull Requests**.
- **Integration** with CI/CD tools (Jenkins, GitHub Actions, etc.).

---

## 🛠️ Basic Workflow with Example

Imagine you’re working on a **website project**:

1. **Create repository (local + remote)**  

   git init                   # start Git in your local folder
   git remote add origin https://github.com/username/website.git
Add project files

bash
Copy code
git add index.html style.css
Commit changes (save a snapshot)

bash
Copy code
git commit -m "Add homepage and styling"
Push to GitHub (remote repo)

bash
Copy code
git push origin main
Collaborate with others

Your teammate clones the repo:

bash
Copy code
git clone https://github.com/username/website.git
They add a new feature (contact.html) on a new branch:

bash
Copy code
git checkout -b add-contact-page
git add contact.html
git commit -m "Add contact page"
git push origin add-contact-page
They create a Pull Request on GitHub for you to review and merge.

## 🧩 Commonly Used Commands (with Explanation)
## 🔎 Checking Status
bash
Copy code
git status
## 👉 Shows which files are modified, staged, or untracked.
Example:

modified: index.html → file was changed but not staged.

untracked: new.js → new file not yet tracked by Git.

## ➕ Staging Files
bash
Copy code
git add filename.txt
git add .   # add all changes
## 👉 Moves changes to the staging area (like preparing for a snapshot).
Example: git add index.html means you’re telling Git: “I want to include this file in my next commit.”

## 💾 Committing Changes
bash
Copy code
git commit -m "Add login feature"

## 👉 Takes a snapshot of staged files. Every commit should have a clear message describing what changed.

## 🚀 Pushing to GitHub
bash
Copy code
git push origin main
## 👉 Sends local commits to the remote GitHub repository.
Example: After writing code, you push so teammates can see the updates.

## 📥 Pulling Updates
bash
Copy code
git pull origin main

## 👉 Brings the latest changes from GitHub into your local repo.
Example: Before starting work, always git pull to avoid conflicts.

## 🌱 Branching
bash
Copy code
git checkout -b feature-login

## 👉 Creates and switches to a new branch called feature-login.
Why? → To work on new features without touching the main branch.

## 🔀 Merging
bash
Copy code
git checkout main
git merge feature-login
## 👉 Combines changes from feature-login branch into main.
Used when a feature is ready to go live.

## 🧹 Undoing Mistakes
Discard changes in a file:

bash
Copy code
git checkout -- filename.txt
Unstage a file:

bash
Copy code
git reset filename.txt
Fix last commit message:

bash
Copy code
git commit --amend -m "Corrected commit message"


## ✅ Pros:
Free & open source.

Works offline.

Excellent branching model.

GitHub adds collaboration & visibility.