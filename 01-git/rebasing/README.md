# 🔄 Git Rebase in Detail

`git rebase` is an advanced command in Git used to **rewrite commit history**.  
Instead of merging, it moves or combines commits onto a new base commit.  

---

## 📌 What is Rebase?

- A **merge** creates a new commit that joins two branches together.  
- A **rebase** takes commits from one branch and **re-applies them** on top of another branch, creating a **linear history**.

👉 In simple terms:  
- **Merge** = "Keep both histories, create a join point."  
- **Rebase** = "Rewrite my work as if I started from the latest branch."

---

## ✅ Why Use Rebase?

- To **maintain a clean, linear history** (no messy merge commits).
- To make your branch look as if it was developed on top of the latest `main`.
- Useful before opening a Pull Request → makes reviewing easier.

---

## 🛠️ Basic Rebase Workflow

### Example Scenario
- You branched off `main` into `feature-login`.
- Meanwhile, someone updated `main`.
- Your branch is now **behind** `main`.

### Using Rebase

# Step 1: Switch to your branch
git checkout feature-login

# Step 2: Rebase onto main
git rebase main
👉 This takes your commits from feature-login and replays them on top of the latest main.

# 🧩 Rebase vs Merge Example
Without Rebase (Merge)
scss
Copy code
A---B---C  (main)
         \
          D---E  (feature)
           \
            Merge Commit (M)
With Rebase
mathematica
Copy code
A---B---C  (main)
             \
              D'---E'  (feature rebased)
## ✅ The history looks cleaner (no merge commit).

## 🎯 Interactive Rebase
You can also edit, reorder, squash, or drop commits with interactive rebase.

bash
Copy code
git rebase -i HEAD~3
## 👉 Opens the last 3 commits in an editor:

pgsql
Copy code
pick 1234abc Add login page
pick 5678def Fix CSS
pick 9abcd12 Update README
You can change:

pick → keep the commit

squash → combine commits

reword → edit commit message

drop → remove commit

Example (squashing):

pgsql
Copy code
pick 1234abc Add login page
squash 5678def Fix CSS
pick 9abcd12 Update README

## ✅ Combines commits 1234abc + 5678def into one.

# ⚠️ Important Notes on Rebase
Never rebase shared/public branches (it rewrites history, causing conflicts for others).

Safe to rebase your local/private branches before pushing.

If conflicts occur during rebase:

bash
Copy code
git status              # see conflicts
git add conflicted-file
git rebase --continue   # resume rebase
To abort a rebase:

bash
Copy code
git rebase --abort
