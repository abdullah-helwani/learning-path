# From ML Graduate to Full-Stack AI Engineer: a 12-Month Learning Path

A complete, ordered plan covering **software engineering, back-end, front-end, cloud, system design and production AI engineering**, with courses, tools, projects, interview preparation and a week-by-week timeline. It's based on **job-market data from 2026**.

> **Who this is for:** a recent graduate with AI/ML knowledge (Python, ML theory, maybe PyTorch) but **no professional software engineering experience**, who is new to Git and wants to be job-ready for the most in-demand AI roles.

---

## 🎯 The recommendation in one paragraph

Aim to become a **Full-Stack AI Engineer** (also called *Applied AI Engineer* or *LLM Engineer*). **AI Engineer is the #1 fastest-growing job** on LinkedIn's *Jobs on the Rise 2026* list, and AI engineering openings at top companies grew about **60%** in a year, compared with about **7%** for general software engineering. Employers mostly ask for **Python, LLM APIs, RAG, agents, evals, FastAPI, cloud and Docker**, and they want people who can **ship AI features to real users**, not only train models in notebooks. You already have the ML intuition, which is the hard-to-teach part. This plan adds the **software engineering** that turns it into a job: Git → Python engineering → back-end → AI engineering → front-end → cloud/MLOps → system design → a capstone with real users. It also qualifies you for **back-end** and **ML engineer** roles, so you have three ways in instead of one. [Full research and sources →](docs/01-job-market-research.md)

---

## 🗓️ The timeline at a glance (~30 h/week · ~20 months at 15 h/week)

| Phase | Weeks | Focus | Project you'll ship |
|---|---|---|---|
| **P0** | 1–2 | **Git, GitHub, terminal**, dev setup | Learning log (this repo) + GitHub profile |
| **P1** | 3–8 | **Python like an engineer**, testing, SQL, HTTP, DSA starts | *Paper Radar*: tested CLI tool with CI |
| **P2** | 9–16 | **Back-end**: FastAPI, PostgreSQL, auth, Docker, Redis, queues, deployment | *DocVault*: production-style REST API |
| **P3** | 17–24 | **AI engineering**: LLM APIs, RAG, **evals**, agents, **MCP**, AI security | *AskMyDocs* RAG with evals + *DevScout* agent & MCP server |
| **P4** | 25–31 | **Front-end**: HTML/CSS, JavaScript, TypeScript, React, Next.js | Full-stack AI web app |
| **P5** | 32–38 | **Cloud & MLOps**: AWS, Terraform, CI/CD, Kubernetes basics, fine-tuning, vLLM, monitoring | *Fine-tune vs Prompt*: train, serve and compare on AWS |
| **P6** | 39–44 | **System design**: classic + ML + GenAI | *SnapLink*: URL shortener with load tests |
| **P7** | 45–52 | **Capstone + interviews + applications** | A real AI product with real users |

**Running alongside the phases:** DSA practice (~5 h/week, 150+ problems) · engineering books (DDIA, *AI Engineering*) · public writing · **job applications from week 24** · open-source contributions from week 24.

---

## 📚 What's in this repository

| # | Document | What it gives you |
|---|---|---|
| 01 | [Job market research](docs/01-job-market-research.md) | The most in-demand roles and skills in 2026, with data and sources, plus a comparison of roles and the recommendation |
| 02 | [**Roadmap & timeline**](docs/02-roadmap-timeline.md) | ⭐ **Start here.** The week-by-week plan, with an exit test for each phase |
| 03 | [Courses & resources](docs/03-courses-and-resources.md) | 100 courses, books and docs **in order** (marked must-do vs optional, free vs paid) |
| 04 | [Projects](docs/04-projects.md) | 9 portfolio projects with full requirements, stretch goals and "definition of done" |
| 05 | [Interview prep](docs/05-interview-prep.md) | Every interview topic: DSA, Python, back-end, front-end, ML, **LLM/RAG/agents/evals**, system design, behavioral |
| 06 | [Skills checklist](docs/06-skills-checklist.md) | ~140 skills to tick off as you learn them |
| 07 | [Git & GitHub guide](docs/07-git-github-guide.md) | Learn Git properly, with exercises **using this repo** |
| 08 | [Tools & setup](docs/08-tools-and-setup.md) | What to install and when, plus a standard Python project and CI template |
| 09 | [Job search strategy](docs/09-job-search-strategy.md) | CV, GitHub, LinkedIn, where to apply, referrals, networking, negotiation |
| — | [progress/](progress/) | Your weekly logs (template included) |

---

## 🚀 Your first week: start today

1. **Day 1:** Set up your machine using [08-tools-and-setup.md](docs/08-tools-and-setup.md) (Git, VS Code, a terminal, and WSL2 if you're on Windows).
2. **Day 1–3:** Watch the [MIT Missing Semester](https://missing.csail.mit.edu/) shell lectures and play [OverTheWire Bandit](https://overthewire.org/wargames/bandit/) levels 0–10.
3. **Day 4–6:** Read the [Git guide](docs/07-git-github-guide.md) and play [Learn Git Branching](https://learngitbranching.js.org/).
4. **Day 6:** Clone this repo and make your **first Pull Request**: add `progress/week-01.md` using the [template](progress/weekly-log-template.md).
5. **Day 7:** Rest, then read [the roadmap](docs/02-roadmap-timeline.md) for Week 2.

---

## 🧭 Principles of this plan

1. **Build more than you watch.** About half your time goes into projects. Recruiters hire proof of work, not certificates.
2. **One deep system beats many shallow ones.** The projects build on each other into one production-grade AI system (back-end → RAG → agent → front-end → fine-tuned model → cloud).
3. **Measure everything.** Evals, latency and cost numbers in every AI project. This is what separates AI *engineers* from demo builders.
4. **Use AI tools, but learn the fundamentals first.** Use AI as a tutor in the early phases and as a power tool later. Interviews test both.
5. **Start applying at month 6.** Don't wait until you feel 100% ready, because nobody ever does.
6. **Consistency beats intensity.** 4–5 focused hours a day for 12 months will change your career.

---

## 🔄 Keep it up to date

The AI field moves fast. Every 3 months:
- re-check the [job market sources](docs/01-job-market-research.md#5-sources),
- redo your [job-ad analysis](docs/09-job-search-strategy.md#job-ad-analysis) for your target market,
- swap any tool or framework that has fallen out of use. **The concepts** (APIs, databases, retrieval, evals, system design) **stay the same**.

*Last updated: October 2026.*
