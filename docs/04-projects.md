# 04 — Projects (in order)

> Projects are **the most important part of this plan.** Recruiters and interviewers can't see your courses, but they can see your GitHub, open your deployed app, and ask you about your design choices.
>
> The projects **build on each other**: the API from P2 becomes the back-end of the RAG system in P3, which gets a front-end in P5 and a fine-tuned model in P6. By the end you'll have **one deep, production-grade AI system** plus several focused projects. That's much more impressive than 20 tutorial clones.

| # | Project | Phase | Weeks | Main skills it proves |
|---|---|---|---|---|
| P0 | Learning log + GitHub profile | P0 | 1–2 | Git, GitHub, Markdown |
| P1 | **Paper Radar** CLI | P1 | 3–8 | Clean Python, testing, SQL, CI |
| P2 | **DocVault** API | P2 | 9–16 | Back-end, PostgreSQL, auth, Docker, deployment |
| P3 | **AskMyDocs** RAG | P3 | 19–24 | RAG, embeddings, evals, observability |
| P4 | **DevScout** agent + MCP server | P3 | 22–24 | Agents, tool calling, MCP, AI security |
| P5 | Full-stack AI app (Next.js) | P4 | 29–31 | TypeScript, React, Next.js, streaming UI, E2E tests |
| P6 | **Fine-tune vs Prompt** | P5 | 35–38 | Fine-tuning, serving, cloud, IaC, cost analysis |
| P7 | **SnapLink** URL shortener | P6 | 41 | System design in practice, caching, load testing |
| P8 | **Capstone**: a real product with real users | P7 | 45–49 | Everything, plus product sense |
| ➕ | Open-source contributions | P3–P7 | 24+ | Working in real codebases with real reviewers |

---

## Rules for every project

1. **Its own GitHub repository**, with a good README (template at the bottom of this page).
2. **Small commits with clear messages** and **feature branches + PRs**, even when you're working alone. It's good practice and looks professional.
3. **Tests + CI** (GitHub Actions) from P1 onward. A green CI badge in the README.
4. **Deployed with a live URL** from P2 onward, wherever possible.
5. **No secrets in Git.** Use `.env` files (listed in `.gitignore`) and `.env.example`.
6. **A short write-up** (blog post or LinkedIn post) when you finish.

---

## P0 — Learning log + GitHub profile

**Weeks 1–2 · Phase 0**

**What:** use **this repository** as your learning log, and create a professional GitHub profile.

**Requirements:**
- [ ] Create your GitHub **profile README** (a repo named exactly like your username) with a short bio, your target role ("aspiring AI engineer"), and the tech you're learning.
- [ ] In this repo, every week, create a branch `log/week-XX`, add `progress/week-XX.md` from the [template](../progress/weekly-log-template.md), open a PR, and merge it.
- [ ] Tick off items in [06-skills-checklist.md](06-skills-checklist.md) through PRs.
- [ ] Create a `dotfiles` repo with your shell config, `.gitconfig` and VS Code settings.
- [ ] Practise a merge conflict on purpose: edit the same line on two branches, merge them, and resolve the conflict.

**Done when:** you've made 10+ PRs to this repo and your GitHub profile looks professional.

---

## P1 — Paper Radar CLI (tested Python tool)

**Weeks 3–8 · Phase 1**

**What:** a command-line tool that fetches new AI papers from the **arXiv API** for topics you choose, stores them in **SQLite**, lets you search, tag and mark them as read, and prints a weekly digest.

**Why:** it proves you can write **real software** in Python, not notebooks. Every later project depends on these habits.

**Stack:** Python 3.12+, uv, Typer, httpx, SQLite, pytest, ruff, mypy, GitHub Actions.

**Requirements:**
- [ ] `paper-radar fetch --topic "retrieval augmented generation" --days 7`
- [ ] `paper-radar search "agents"`, `paper-radar tag <id> must-read`, `paper-radar digest`
- [ ] Proper project structure (`src/` layout, `pyproject.toml`), type hints everywhere, passes `ruff` and `mypy`.
- [ ] SQLite schema with at least 2 related tables (papers, tags), with SQL written by hand (no ORM yet).
- [ ] **Tests** for parsing, the database layer and the CLI commands. The network is **mocked**. Coverage above 80%.
- [ ] Errors handled gracefully (network failure, bad input) and logging instead of `print`.
- [ ] **GitHub Actions** runs lint, type check and tests on every PR.

**Stretch goals:**
- Publish to PyPI so people can `pip install paper-radar`.
- Add an `--llm-summary` flag that summarizes abstracts with an LLM. (A preview of Phase 3; keep it optional.)
- Package it as a Docker image.

**Done when:** a stranger can install and use it by following your README, and CI is green.

---

## P2 — DocVault API (production-style REST API)

**Weeks 9–16 · Phase 2**

**What:** a multi-user **document management API**. Users sign up, log in, upload documents (PDF, Markdown, TXT), organize them into collections, share them with other users, and search them by metadata. A background worker extracts text from each upload.

**Why:** it proves you can build a **real back-end**: databases, auth, background jobs, containers, testing and deployment. **It also becomes the foundation of your AI system in P3.**

**Stack:** FastAPI, Pydantic v2, PostgreSQL, SQLAlchemy 2.0, Alembic, Redis, Celery/ARQ, MinIO (S3-compatible), Docker Compose, pytest + Testcontainers, GitHub Actions. Deploy to Render, Railway or Fly.io.

**Requirements:**
- [ ] **Auth:** sign up, log in, JWT access + refresh tokens, hashed passwords (argon2/bcrypt). Optional: "Login with GitHub" (OAuth).
- [ ] **Authorization:** users only see their own documents and the ones shared with them. Write a test that proves it.
- [ ] **CRUD** for collections and documents, with **pagination**, **filtering** and **sorting**.
- [ ] **File upload** to MinIO/S3, with size and type validation.
- [ ] **Background job:** text extraction runs in a worker. Document status goes `pending → processing → ready/failed`, with retries.
- [ ] **Caching** of frequent reads in Redis, with correct invalidation.
- [ ] **Rate limiting** on auth endpoints.
- [ ] **Database migrations** with Alembic, plus a seed script.
- [ ] **Tests:** unit + integration against a real PostgreSQL (Testcontainers). CI runs them.
- [ ] **Observability:** structured JSON logs, request IDs, and `/health` and `/ready` endpoints.
- [ ] **Docker Compose** brings up the whole stack with one command: `docker compose up`.
- [ ] **Deployed** with HTTPS. The README links to the live OpenAPI docs.

**Stretch goals:**
- Full-text search with PostgreSQL `tsvector`.
- Webhooks: notify an external URL when a document is ready.
- An audit log table.

**Done when:** it's deployed, it's tested in CI, and the README has an architecture diagram and a "how to run locally" section that works.

---

## P3 — AskMyDocs (production RAG with evals)

**Weeks 19–24 · Phase 3**

**What:** extend DocVault so users can **ask questions about their documents** and get **streamed answers with citations**, along with **measured quality**.

**Why:** RAG is the most requested AI engineering skill (around 65% of applied LLM job listings, per one 2026 analysis). Most candidates' RAG projects stop at "it works on my example". **Yours will have an evaluation suite, tracing and numbers.** That's what makes it production-grade.

**Stack:** your P2 API, pgvector (inside the PostgreSQL you already run), an embedding model (OpenAI/Cohere/Voyage or an open model such as BGE/E5 via sentence-transformers), a reranker, an LLM API (Claude/OpenAI/Gemini), plus a local Ollama option. Langfuse or Phoenix for tracing, Ragas/DeepEval plus your own eval scripts.

**Requirements:**
- [ ] **Ingestion:** when a document becomes `ready`, a background job chunks it, embeds it and stores it in pgvector, keeping metadata (document, page, section).
- [ ] **Compare at least 2 chunking strategies** and choose one based on eval results.
- [ ] **Hybrid retrieval** (PostgreSQL full-text/BM25 + vector) followed by **reranking**.
- [ ] **Answer generation** with **inline citations** (document + page). Answers are **streamed** (Server-Sent Events).
- [ ] **"I don't know"** behaviour when nothing relevant is retrieved. No hallucinated answers.
- [ ] **Access control** in retrieval: users must never retrieve chunks from documents they can't access. (This is a classic bug, so write a test for it.)
- [ ] **Golden eval set** of at least 100 questions with expected sources and answers, built from a real document set (for example, your university's regulations, a company's public docs, or a set of papers).
- [ ] **Eval report:** retrieval recall@5, MRR, answer faithfulness, answer relevance, latency (p50/p95), and **cost per query**. Shown as a table in the README.
- [ ] **Eval runs in CI** on a small subset. The build fails if quality drops below a threshold.
- [ ] **Tracing**: every request is traced (retrieval results, prompt, tokens, latency, cost).
- [ ] **Prompt-injection test**: a document containing "ignore previous instructions…" must not hijack the system.

**Stretch goals:**
- Query rewriting and HyDE, compared with evals.
- A semantic cache for repeated questions.
- Multi-modal: answer questions about tables and images in PDFs.
- Support a second language (for example Arabic or your native language) and evaluate it separately. This is a strong differentiator in many markets.

**Done when:** deployed, the eval table is in the README, and you've written a blog post: *"How I built and evaluated a RAG system: what worked and what didn't"*.

---

## P4 — DevScout (agent + MCP server)

**Weeks 22–24 · Phase 3**

**What:** an **AI agent that helps triage GitHub issues** for an open-source repo. It reads new issues, searches the codebase and docs, finds duplicates, suggests labels, drafts a helpful first reply, and **asks a human to approve** before posting anything. Its tools are exposed through an **MCP server** that you write yourself.

**Why:** it proves you understand **agents** (planning, tools, memory, failure modes), **MCP** (now a standard way to connect AI to tools), and **AI safety in practice**: human-in-the-loop and limited permissions.

**Stack:** Python, the MCP Python SDK (FastMCP), an LLM API with tool calling, LangGraph (after a version without a framework), the GitHub API, your P3 retrieval for docs search, and Langfuse for tracing.

**Requirements:**
- [ ] **Version 1, no framework:** a hand-written tool-calling loop with a max-steps limit, timeouts and error handling.
- [ ] **Version 2, LangGraph:** the same agent as a graph with explicit states, including a **human approval** step.
- [ ] **MCP server** exposing tools: `search_issues`, `search_code`, `search_docs`, `get_issue`, `draft_comment`, `add_label` (the write tools require approval).
- [ ] Your MCP server also works in an existing MCP client (for example Claude Desktop, Claude Code, or another MCP-compatible client).
- [ ] **Read-only by default.** Write actions need explicit approval and are logged.
- [ ] **Eval set** of 30+ real historical issues with known correct labels and duplicates. Report label accuracy and duplicate-detection precision and recall.
- [ ] **Failure analysis** section in the README: where the agent fails and why.

**Stretch goals:**
- A GitHub App or GitHub Action that runs DevScout automatically on new issues in a demo repo.
- Compare 2–3 models on cost, latency and accuracy.

**Done when:** you can show a demo video of the agent triaging real issues, with eval numbers.

---

## P5 — Full-stack AI app (Next.js front-end for P3/P4)

**Weeks 29–31 · Phase 4**

**What:** a polished web app for AskMyDocs (and DevScout): sign in, upload documents, organize collections, chat with your documents with streamed answers, click citations to open the source page, and view an **eval dashboard**.

**Why:** it proves you can build a **full product**, not only a back-end. Many AI engineer roles (especially at startups) want people who can ship the whole feature.

**Stack:** TypeScript, Next.js (App Router), Tailwind CSS, shadcn/ui, TanStack Query, React Hook Form + Zod, Vercel AI SDK (streaming), Auth.js (or your P2 JWT auth), Vitest + React Testing Library, Playwright. Deploy on Vercel.

**Requirements:**
- [ ] Sign up and log in against your P2 API.
- [ ] Document upload with progress and processing status (`pending → ready`).
- [ ] **Chat UI with streaming**, markdown rendering, **clickable citations** that open the source document at the right page, and stop/regenerate buttons.
- [ ] Chat history saved per user.
- [ ] Thumbs up/down feedback on answers, stored in the back-end. (This is real user-feedback data for your evals.)
- [ ] **Eval dashboard** page: charts of your eval metrics over time.
- [ ] **Responsive** (works on mobile), **accessible** (keyboard navigation, labels), dark mode.
- [ ] Unit tests for components, plus **Playwright E2E** tests for log in → upload → ask → see citation.
- [ ] Lighthouse: accessibility ≥ 90, performance ≥ 90.

**Done when:** a non-technical friend can use the app without your help.

---

## P6 — Fine-tune vs Prompt (train, serve and compare)

**Weeks 35–38 · Phase 5**

**What:** pick a narrow task from your own system (for example, **classifying GitHub issue labels** for DevScout, or **extracting structured fields from documents** for DocVault). Then compare:
1. a large API model with a good prompt (few-shot),
2. a **small open model fine-tuned with LoRA/QLoRA** on your data,
3. optionally, the small model without fine-tuning.

Serve the fine-tuned model yourself and deploy everything to **AWS with Terraform**.

**Why:** it proves you can do the **ML engineering** side (data, training, serving, cost) and make **data-driven decisions** about when fine-tuning is worth it. That trade-off comes up in almost every AI engineering interview.

**Stack:** Hugging Face Transformers, PEFT, TRL or Unsloth, MLflow or W&B, vLLM (OpenAI-compatible server), Docker, Terraform, AWS (ECR, ECS or EC2 GPU/Bedrock, S3), GitHub Actions, Prometheus/Grafana or CloudWatch.

**Requirements:**
- [ ] Dataset: at least 1,000 labeled examples (real data, or synthetic data checked by hand), with train/validation/test splits and a **data card**.
- [ ] Baseline with the API model, then the fine-tuned small model (for example a 1–8B open model). Every experiment tracked in MLflow/W&B.
- [ ] **Comparison table:** accuracy/F1, latency p50/p95, **cost per 1,000 requests**, and GPU memory.
- [ ] Serve the fine-tuned model with **vLLM** behind an OpenAI-compatible endpoint. Your P3/P4 code should switch models through configuration only.
- [ ] Infrastructure defined in **Terraform**. CI/CD builds and deploys the images.
- [ ] Monitoring: requests, latency and errors on a dashboard.
- [ ] A **written conclusion**: when would you choose each option in a real company?

**Stretch goals:**
- Quantize the model (AWQ/GGUF) and add the quality vs speed trade-off to your table.
- DPO on preference data from your P5 thumbs up/down feedback.
- Kubernetes deployment (kind locally, or EKS if you have credits).

**Done when:** the comparison table and conclusion are in the README, and you can explain every number in it.

---

## P7 — SnapLink (scalable URL shortener with load tests)

**Week 41 · Phase 6**

**What:** the classic system design interview problem, **actually built and measured**: a URL shortener with redirects, analytics, caching and rate limiting, load-tested to find its limits.

**Why:** most candidates can only draw this on a whiteboard. You'll have measured it. In interviews you can say: *"When I built this, the database became the bottleneck at around X requests/sec, so I added a Redis cache and the p99 latency dropped from A to B."*

**Stack:** FastAPI (or Go, if you want to try a second language), PostgreSQL, Redis, Nginx as a load balancer with 2–3 API replicas in Docker Compose, k6 or Locust for load testing, Prometheus + Grafana.

**Requirements:**
- [ ] Short-code generation. Document why you chose your method (base62 counter vs hash vs random) and how you avoid collisions.
- [ ] Redirect with **cache-aside** in Redis. Click analytics written **asynchronously** (through a queue or stream), not in the request path.
- [ ] **Rate limiter** (token bucket in Redis) that you implement yourself.
- [ ] **Load test:** find the maximum RPS and p99 latency before and after caching and with 1 vs 3 replicas. Include graphs in the README.
- [ ] A design doc in the README: requirements, back-of-the-envelope estimates, API, data model, diagram, bottlenecks, and how it would scale to 100× the traffic.

**Done when:** the README reads like a system design interview answer, backed by real measurements.

---

## P8 — Capstone: a real AI product with real users

**Weeks 45–49 · Phase 7**

**What:** build something **real people use**. This is the project you'll talk about most in interviews.

**Requirements (whatever idea you choose):**
- [ ] It solves a **real problem for real users**. Talk to at least 5 potential users **before** building.
- [ ] Full stack: Next.js front-end, FastAPI back-end, PostgreSQL, deployed on the cloud.
- [ ] An AI core (RAG, agent, extraction, classification or generation) with an **eval suite** and **tracing**.
- [ ] **Real usage:** 10–50 users. Track usage, quality metrics and costs.
- [ ] At least **2 iterations** based on feedback, documented in a changelog.
- [ ] **Case study** (blog post): problem → users → design → evals → results → lessons. Plus a 2–3 minute **demo video**.

**Idea list (pick one, or better, find your own problem):**
1. **University assistant:** RAG over your university's regulations, course catalog and FAQs for students, in their language, with citations.
2. **Small-business AI support agent:** a local shop, clinic or NGO answers customer questions on WhatsApp or web chat from its own documents, with human handoff.
3. **Arabic/multilingual document AI:** extract structured data from scanned forms or invoices (OCR + LLM), with an evaluation of accuracy per field.
4. **Job-application copilot:** compares a CV against job ads, finds skill gaps, and maps them to learning resources. (You understand this problem well.)
5. **Meeting/lecture notes agent:** transcribe (Whisper) → summarize → extract action items → push to a calendar or task tool via MCP.
6. **Code-review assistant** for student projects: an MCP server + agent that reviews PRs against a rubric.
7. **Health or legal information navigator** (careful: strong guardrails, citations only, "not advice" disclaimers, and evals for refusal behaviour).
8. **Open-source contribution:** instead of a new product, become a regular contributor to an AI open-source project and ship a significant feature. This counts as a capstone too.

**Done when:** real users have used it, and you have numbers and a story to tell.

---

## ➕ Open-source contributions (from week 24)

**Why:** it's the closest thing to real job experience. You read a large codebase, follow contribution rules, write tests, and get code review from experienced engineers. All of it is public.

**How:**
1. Pick tools **you actually used** in your projects: LangChain/LangGraph, LlamaIndex, Hugging Face (transformers, datasets, smolagents, TRL), Langfuse, Ragas, Qdrant, pgvector, FastAPI, the MCP SDKs, Ollama, vLLM.
2. Start with **docs fixes, examples and small bugs** (labels like `good first issue`, `help wanted`, `documentation`).
3. Read `CONTRIBUTING.md` first. Run the tests locally. Keep each PR small and focused.
4. Be patient and polite with reviewers. Ask questions in issues before starting big changes.
5. **Goal:** 2–3 merged PRs by week 52. List them on your CV under "Open Source".

---

## README template for every project

Copy this into each project's `README.md`:

````markdown
# Project Name

One sentence: what it does and for whom.

[Live demo](https://...) · [Demo video](https://...) · [Blog post](https://...) · ![CI](badge-url)

![Screenshot or GIF](docs/demo.gif)

## Why I built this
The problem, and what I wanted to learn.

## Features
- ...

## Architecture
![Architecture diagram](docs/architecture.png)
Short explanation of the components and how data flows.

## Tech stack
| Layer | Tech | Why I chose it |
|---|---|---|

## Results / Evals
| Metric | Value |
|---|---|
| Retrieval recall@5 | 0.87 |
| Faithfulness | 0.92 |
| p95 latency | 1.8 s |
| Cost / 1k queries | $0.40 |

## Run locally
```bash
git clone ...
cp .env.example .env
docker compose up
```

## Tests
```bash
uv run pytest
```

## Design decisions and trade-offs
- Chose X over Y because ...

## What I'd do next
- ...
````

👉 Next: how to pass the interviews → [05-interview-prep.md](05-interview-prep.md)
