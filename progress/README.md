# Progress Log

Keep one file per week here: `week-01.md`, `week-02.md`, …

**How to add a week (Git practice every week):**

```bash
git switch main && git pull
git switch -c log/week-XX
cp progress/weekly-log-template.md progress/week-XX.md
# fill it in
git add progress/week-XX.md
git commit -m "docs: add week XX learning log"
git push -u origin log/week-XX
# open a Pull Request on GitHub → review → merge
```

Other files that belong here:
- `job-ad-analysis.md`: your count of skills from 25 real job ads ([how to do it](../docs/09-job-search-strategy.md#job-ad-analysis))
- `applications.md` (or a spreadsheet): every job application you send and its status
- `system-design/`: one Markdown write-up per system design you practise
- `dsa-notes.md`: patterns and tricks from the problems you solve

| Phase | Weeks | Started | Finished | Exit test passed? |
|---|---|---|---|---|
| P0: Git & tooling | 1–2 | | | ☐ |
| P1: SWE fundamentals | 3–8 | | | ☐ |
| P2: Back-end | 9–16 | | | ☐ |
| P3: AI engineering | 17–24 | | | ☐ |
| P4: Front-end | 25–31 | | | ☐ |
| P5: Cloud & MLOps | 32–38 | | | ☐ |
| P6: System design | 39–44 | | | ☐ |
| P7: Capstone & job hunt | 45–52 | | | ☐ |
