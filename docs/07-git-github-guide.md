# 07 — Git and GitHub: A Practical Guide for Beginners

> You said you don't know how to use Git properly. That's normal, and it's the **first** thing to fix, because every software job uses Git every day. This guide teaches the 20% of Git you'll use 95% of the time, and gives you exercises **using this very repository**.

---

## 1. The mental model (read this first)

- **Git** is a tool on your computer that records **snapshots** (called *commits*) of your project over time. You can go back to any snapshot, compare snapshots, and work on several versions in parallel (*branches*).
- **GitHub** is a website that stores a copy of your Git repository online (a *remote*) and adds collaboration features: pull requests, code review, issues and CI.

A file moves through **three areas**:

```
 Working directory  ──git add──▶  Staging area  ──git commit──▶  Local repository  ──git push──▶  GitHub (remote)
 (files you edit)                 (what goes into                (your history)                   (shared history)
                                   the next commit)
                     ◀──────────────────────────── git pull / git fetch ◀──────────────────────────────
```

- A **commit** is a snapshot plus a message plus a pointer to the previous commit.
- A **branch** is just a movable label that points to a commit. `main` is the default branch.
- `HEAD` means "where I am right now".
- `origin` is the default name for your GitHub copy of the repository.

---

## 2. One-time setup

```bash
# Who you are (this appears in every commit)
git config --global user.name "Your Name"
git config --global user.email "you@example.com"

# Sensible defaults
git config --global init.defaultBranch main
git config --global pull.rebase false      # 'git pull' merges (simplest while you're learning)
git config --global core.editor "code --wait"   # use VS Code for commit messages

# Check your settings
git config --list
```

### Connect to GitHub with SSH (recommended)

```bash
ssh-keygen -t ed25519 -C "you@example.com"   # press Enter to accept the defaults; set a passphrase
cat ~/.ssh/id_ed25519.pub                     # copy this output
```
Then on GitHub: **Settings → SSH and GPG keys → New SSH key**, paste the key, and save. Test it:
```bash
ssh -T git@github.com     # should say: "Hi <username>! You've successfully authenticated"
```

> **Never share your private key** (`id_ed25519`, the file *without* `.pub`).

---

## 3. The daily workflow (memorize this)

```bash
# 0. Start of the day: get the latest main
git switch main
git pull

# 1. Create a branch for your task
git switch -c feature/add-week-03-log

# 2. Work... then check what changed
git status                 # which files changed
git diff                   # what exactly changed

# 3. Stage and commit in small, logical pieces
git add progress/week-03.md
git commit -m "docs: add week 3 learning log"

# 4. Push the branch to GitHub
git push -u origin feature/add-week-03-log    # -u only the first time for this branch

# 5. On GitHub: open a Pull Request → review your own diff → merge
# 6. Back locally: update main and delete the finished branch
git switch main
git pull
git branch -d feature/add-week-03-log
```

**Golden rules:**
1. **Commit small and often.** Each commit should do one thing.
2. **Never commit secrets** (API keys, passwords, `.env`). If you do it by accident, **rotate the key immediately**. Deleting the file in a later commit is not enough, because the key stays in the history.
3. **Don't work directly on `main`.** Use a branch and a PR, even when you're working alone.
4. **Pull before you start working**, and push at least daily.
5. **Read `git status` often.** It tells you what's going on and usually suggests the right command.

---

## 4. Writing good commit messages

Use the **Conventional Commits** style. It's common in companies and open source:

```
<type>: <short summary in the imperative mood, ≤ 72 chars>

<optional body: WHY you made the change, not just what>
```

| Type | Use for |
|---|---|
| `feat` | A new feature |
| `fix` | A bug fix |
| `docs` | Documentation only |
| `test` | Adding or fixing tests |
| `refactor` | Code change that doesn't change behaviour |
| `chore` | Tooling, dependencies, configuration |
| `ci` | CI pipeline changes |

✅ `feat: add hybrid search with BM25 and pgvector`
✅ `fix: prevent users from retrieving chunks of unshared documents`
❌ `update`, `fix stuff`, `asdf`, `final version 2`

---

## 5. Branching, merging and pull requests

```bash
git branch                 # list local branches
git branch -a              # list local + remote branches
git switch <branch>        # move to a branch
git switch -c <new>        # create a branch and move to it
git merge <branch>         # merge <branch> INTO the current branch
git log --oneline --graph --all   # see history as a graph (use this often!)
```

### Merge vs rebase (a common interview question)
- **Merge** combines two branches and creates a *merge commit*. History shows exactly what happened. It's **safe on shared branches**.
- **Rebase** *replays* your commits on top of another branch, which gives a straight, clean history. But it **rewrites commits**, so **only rebase branches that nobody else is using**.

```bash
# Update your feature branch with the latest main (two options):
git switch feature/x
git merge main             # option A: safe, creates a merge commit
git rebase main            # option B: cleaner history, only for your own unshared branch
```

### A good pull request
- A small, focused change (ideally under 400 lines).
- A clear title and description: **what** changed, **why**, **how to test** it, and screenshots for UI changes.
- CI is green before you ask for review.
- Reply to every review comment, and push fixes as new commits.

---

## 6. Resolving merge conflicts

A conflict happens when two branches change the **same lines**. Git marks the conflict in the file:

```
<<<<<<< HEAD
This is the line on your current branch
=======
This is the line from the branch you're merging
>>>>>>> feature/other
```

**To resolve it:**
1. Open the file (VS Code shows "Accept Current / Incoming / Both" buttons).
2. Edit the file to the correct final content and **delete the markers** (`<<<<<<<`, `=======`, `>>>>>>>`).
3. `git add <file>`
4. `git commit` (for a merge) or `git rebase --continue` (for a rebase).
5. If you panic: `git merge --abort` or `git rebase --abort` takes you back to where you started.

---

## 7. Undoing things (the most useful section)

| Situation | Command |
|---|---|
| Discard changes in a file you haven't staged | `git restore <file>` |
| Unstage a file (keep the changes) | `git restore --staged <file>` |
| Fix the message or content of the **last** commit (not pushed yet) | make the changes, `git add`, then `git commit --amend` |
| Undo the last commit but keep the changes | `git reset --soft HEAD~1` |
| Throw away the last commit **and** its changes (dangerous) | `git reset --hard HEAD~1` |
| Undo a commit that is **already pushed** (safe) | `git revert <commit-hash>` (creates a new commit that undoes it) |
| Save unfinished work temporarily | `git stash`, and later `git stash pop` |
| "I lost a commit!" | `git reflog` shows every place `HEAD` has been, then `git switch -c rescue <hash>` |
| Find which commit introduced a bug | `git bisect start`, `git bisect bad`, `git bisect good <hash>`, … |
| Who changed this line, and why? | `git blame <file>` |

> **Rule:** use `revert` for anything already pushed to a shared branch. Use `reset` and `--amend` only for local commits nobody else has.
>
> When in doubt, check **[Oh Shit, Git!?!](https://ohshitgit.com/)**.

---

## 8. `.gitignore`

Create a `.gitignore` file in every project so that junk and secrets never get committed:

```gitignore
# Python
__pycache__/
*.pyc
.venv/
.pytest_cache/
.mypy_cache/
.ruff_cache/
.coverage
dist/

# Node
node_modules/
.next/

# Secrets and environment variables: NEVER commit these
.env
.env.*
!.env.example

# Editors / OS
.vscode/
.idea/
.DS_Store

# Data and models (use DVC, Git LFS or cloud storage instead)
data/
*.ckpt
*.safetensors
mlruns/
```

GitHub publishes ready-made templates for every language at [github.com/github/gitignore](https://github.com/github/gitignore).

---

## 9. GitHub features you should use

- **Issues:** track tasks and bugs. Create one issue per project milestone.
- **Projects:** a Kanban board (To do / In progress / Done). Use one for this learning plan.
- **Actions:** CI/CD. Run tests on every push (you'll set this up in Phase 1).
- **Releases and tags:** `git tag v1.0.0 && git push --tags`.
- **Profile README:** a repo with the same name as your username, so its README appears on your profile.
- **Pinned repositories:** pin your best 6 projects.
- **Forks:** how you contribute to other people's projects (fork → clone → branch → PR to the original repository).

---

## 10. Exercises using this repository

Do these in order during Week 2. Each one is a real skill.

### Exercise 1: clone and explore
```bash
git clone git@github.com:<your-username>/learning-path.git
cd learning-path
git log --oneline --graph --all
git branch -a
```

### Exercise 2: your first PR
```bash
git switch main && git pull
git switch -c log/week-01
cp progress/weekly-log-template.md progress/week-01.md
# edit progress/week-01.md in VS Code and fill it in
git add progress/week-01.md
git commit -m "docs: add week 1 learning log"
git push -u origin log/week-01
```
Then open the PR on GitHub, read the diff, and merge it. Afterwards:
```bash
git switch main && git pull && git branch -d log/week-01
```

### Exercise 3: tick the checklist
On a new branch `progress/checklist-week-02`, edit [06-skills-checklist.md](06-skills-checklist.md) and change `- [ ]` to `- [x]` for the Git skills you've learned. Commit, push, open a PR, merge.

### Exercise 4: create and resolve a conflict on purpose
```bash
git switch main
echo "Original line" > practice.txt
git add practice.txt && git commit -m "chore: add practice file"

git switch -c conflict-a
echo "Version A" > practice.txt
git commit -am "chore: version A"

git switch main
git switch -c conflict-b
echo "Version B" > practice.txt
git commit -am "chore: version B"

git switch main
git merge conflict-a      # works (fast-forward)
git merge conflict-b      # CONFLICT! resolve it as described in section 6

# Clean up afterwards
git rm practice.txt && git commit -m "chore: remove practice file"
git branch -d conflict-a conflict-b
```

### Exercise 5: undo things safely
- Make a commit with a typo in the message, then fix it with `--amend`.
- Make a commit, push it, then undo it with `git revert`.
- Run `git reset --hard HEAD~1` on a test branch, then **recover** the commit using `git reflog`.

### Exercise 6: clean up with an interactive rebase (on your own branch only)
Make 3 small "wip" commits on a branch, then run `git rebase -i main` and **squash** them into one clean commit. (`-i` opens an editor. Change `pick` to `squash` for the 2nd and 3rd commits.)

### Exercise 7: GitHub Actions
Add `.github/workflows/check.yml` that runs a Markdown link checker or a simple `echo` on every PR. Watch it run in the **Actions** tab.

---

## 11. Cheat sheet

| Goal | Command |
|---|---|
| Start a repo | `git init` / `git clone <url>` |
| Status / diff | `git status` / `git diff` / `git diff --staged` |
| Stage / commit | `git add <file>` / `git add -p` (choose parts of files) / `git commit -m "msg"` |
| History | `git log --oneline --graph --all` / `git show <hash>` |
| Branches | `git switch -c <name>` / `git switch <name>` / `git branch -d <name>` |
| Sync | `git fetch` / `git pull` / `git push` / `git push -u origin <branch>` |
| Merge / rebase | `git merge <branch>` / `git rebase <branch>` |
| Undo | `git restore` / `git reset` / `git revert` / `git reflog` |
| Stash | `git stash` / `git stash list` / `git stash pop` |
| Remotes | `git remote -v` / `git remote add origin <url>` |
| Tags | `git tag v1.0.0` / `git push --tags` |

**Learn more:** [Learn Git Branching](https://learngitbranching.js.org/) · [Pro Git book](https://git-scm.com/book/en/v2) · [Atlassian Git tutorials](https://www.atlassian.com/git/tutorials) · [GitHub Skills](https://skills.github.com/) · [MIT Missing Semester: Version Control](https://missing.csail.mit.edu/)
