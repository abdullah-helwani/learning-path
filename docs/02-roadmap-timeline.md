# 02 — The Roadmap: 12 Months, Week by Week

> **Assumptions:** you're a recent graduate who already knows Python for data/ML (NumPy, pandas, scikit-learn, and probably PyTorch or TensorFlow) and ML theory. You have **no professional software engineering experience** and you're new to Git. You can study **~30 hours/week**.
>
> **Studying part-time (~15 h/week)?** Use the same order and stretch each phase to about 1.7× its length. The plan then takes **~20 months**. Don't skip phases. Make the projects smaller instead.
>
> **Already know something?** Take the "exit test" at the end of each phase. If you pass it, move on.

---

## Timeline at a glance

```
Month:   1        2        3        4        5        6        7        8        9        10       11       12
Week:    1-2 | 3 ------- 8 | 9 -------------- 16 | 17 ------------- 24 | 25 ---------- 31 | 32 ---------- 38 | 39 ------ 44 | 45 ------------ 52
Phase:   P0  |     P1      |         P2         |         P3         |        P4        |        P5        |      P6      |        P7
         Git |  SWE basics |      Back-end      |   AI Engineering   |    Front-end     |  Cloud & MLOps   | System Design|  Capstone + Job hunt
         & CLI| Python/SQL |  FastAPI/Postgres  |  RAG/Agents/Evals  |  TS/React/Next   |  AWS/IaC/LLMOps  | classic+ML+AI|  interviews
Project: P0  |     P1      |         P2         |      P3 + P4       |        P5        |        P6        |      P7      |        P8 (capstone)
─────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
Ongoing:     DSA practice (5–6 h/wk) ──────────────────────────────────────────────────────────────────────────────────────────▶ ~150+ problems
Ongoing:              Reading: DDIA, A Philosophy of Software Design, AI Engineering (Chip Huyen) ─────────────────────────────▶
Ongoing:                                                       Applying for jobs (light from wk 24, full from wk 38) ───────────▶
Ongoing:                                                       Open-source contributions (from wk 24) ──────────────────────────▶
```

| Phase | Weeks | Focus | Project you finish | You become employable as… |
|---|---|---|---|---|
| **P0** | 1–2 | Git, GitHub, terminal, dev setup | P0: Learning log + GitHub profile | — |
| **P1** | 3–8 | Python like an engineer, testing, SQL, networking basics, DSA start | P1: Tested and packaged CLI tool with CI | — |
| **P2** | 9–16 | Back-end: APIs, PostgreSQL, auth, Docker, async, deployment | P2: Production-style REST API (deployed) | Junior back-end (weak) |
| **P3** | 17–24 | AI engineering: LLM APIs, RAG, evals, agents, MCP | P3: RAG system with evals · P4: Agent + MCP server | **Junior AI engineer** ✅ *start applying* |
| **P4** | 25–31 | Front-end: HTML/CSS, JS, TypeScript, React, Next.js | P5: Full-stack AI web app | Junior full-stack / AI engineer |
| **P5** | 32–38 | Cloud (AWS), Terraform, CI/CD, Kubernetes basics, fine-tuning, serving, monitoring | P6: Fine-tune + serve + compare | AI / ML engineer ✅ *apply at full volume* |
| **P6** | 39–44 | System design: classic, ML, and GenAI | P7: Scalable URL shortener + load test | Interview-ready |
| **P7** | 45–52 | Capstone with real users, interviews, applications | P8: Capstone product | 🎯 Hired |

---

## How to spend a 30-hour week

| Block | Hours | What |
|---|---|---|
| Main phase: learn | 10 | Courses, docs, tutorials for the current phase |
| Main phase: build | 10 | Work on the phase project. **Building is where real learning happens.** |
| DSA | 5 | NeetCode/LeetCode, 1 problem per day (see [05-interview-prep.md](05-interview-prep.md)) |
| Reading | 2 | One engineering book on the reading track |
| Public work | 2 | Write the weekly log, push to GitHub, post what you learned on LinkedIn or a blog |
| Review | 1 | Sunday: review the week, plan the next one, update [06-skills-checklist.md](06-skills-checklist.md) |

### Rules that make this plan work

1. **Build every week.** Watching courses without building gives you the illusion of learning.
2. **Use Git for everything from day 1.** Commit daily. Your GitHub contribution graph is part of your CV.
3. **Use AI coding assistants carefully.** In Phases 0–2, use AI as a **tutor** (to explain, review, quiz you), not as a code generator. If you can't write it without AI, you haven't learned it, and many interviews forbid AI. From Phase 3 onward, use Claude Code, Cursor or Copilot fully, as professionals do, and always read and understand every line.
4. **Done is better than perfect.** Each project has a "definition of done". When you meet it, ship it and move on.
5. **Write it down.** Keep a weekly log in [`progress/`](../progress/). It shows you how far you've come, and it becomes material for interview stories.
6. **Rest one day a week.** This is a 12-month plan, so pace yourself to finish it.

---

## Phase 0 — Developer tooling: Git, terminal, setup (Weeks 1–2)

**Goal:** be comfortable in the terminal and use Git and GitHub every day without thinking about it.

### Week 1 — Terminal and environment
- [ ] Set up your machine using [08-tools-and-setup.md](08-tools-and-setup.md) (Linux/WSL2/macOS, VS Code, uv, Git, Docker).
- [ ] **MIT Missing Semester** lectures: *Shell*, *Command-line Environment*, *Development Environment and Tools*. Do the exercises.
- [ ] **OverTheWire Bandit** levels 0–15. This is a game that teaches Linux commands.
- [ ] Learn: `cd ls pwd mkdir rm cp mv cat less head tail grep find chmod ps kill | > >> && $PATH env ssh curl`.
- [ ] Take your first steps in a text editor inside the terminal (`nano`, or basic `vim`).

### Week 2 — Git and GitHub
- [ ] Read [07-git-github-guide.md](07-git-github-guide.md) (in this repo). It's written for you.
- [ ] **Missing Semester**: *Version Control (Git)* lecture.
- [ ] **Learn Git Branching**: all "Main" and "Remote" levels.
- [ ] **Pro Git** book: chapters 1, 2, 3 (branching), and 6 (GitHub).
- [ ] **GitHub Skills**: *Introduction to GitHub*, *Review pull requests*, *Resolve merge conflicts*.
- [ ] Build **Project P0** ([04-projects.md](04-projects.md#p0--learning-log--github-profile)).

**✅ Exit test:** without searching, you can: clone a repo, create a branch, commit, push, open a PR, review it, merge it, resolve a merge conflict, undo a bad commit (`git revert`), and explain the difference between `merge` and `rebase`.

---

## Phase 1 — Software engineering fundamentals (Weeks 3–8)

**Goal:** go from writing Python *notebooks* to writing Python *software*: structured, typed, tested, packaged, and checked by CI.

### Week 3 — Professional Python project setup
- [ ] Project layout (`src/` layout), `pyproject.toml`, virtual environments with **uv**, dependency management.
- [ ] Linters and formatters: **ruff**. Type hints and type checking: **mypy** or **pyright**.
- [ ] **Fluent Python** (2nd ed.): Ch. 1 (Data Model), and the chapters on functions as objects, decorators and closures.
- [ ] Start **DSA track**: NeetCode roadmap → *Arrays & Hashing*.

### Week 4 — Testing and code quality
- [ ] **pytest**: tests, fixtures, `parametrize`, mocking (`unittest.mock`), coverage.
- [ ] Try test-driven development (TDD) on a small kata.
- [ ] Error handling, custom exceptions, the `logging` module (never use `print` for logs).
- [ ] Build a CLI with **Typer** (or `argparse`).
- [ ] Reading track: begin ***A Philosophy of Software Design*** (Ousterhout).

### Week 5 — SQL and databases (part 1)
- [ ] **CS50's Introduction to Databases with SQL** (weeks 0–3), or **SQLBolt** followed by **PostgreSQL Exercises**.
- [ ] Learn: SELECT, JOINs, GROUP BY, subqueries, window functions, indexes, normalization (1NF–3NF), transactions.
- [ ] Use **SQLite** from Python (`sqlite3`).
- [ ] DSA: *Two Pointers*, *Sliding Window*.

### Week 6 — How computers and the web work
- [ ] **HTTP**: methods, status codes, headers, cookies, caching, HTTPS/TLS (MDN HTTP guide).
- [ ] **Networking basics**: DNS, TCP vs UDP, IP, ports, what happens when you type a URL.
- [ ] **Concurrency in Python**: threads vs processes vs `asyncio`, the GIL, when to use each.
- [ ] Use `curl` and **HTTPie** or **Bruno** to call real APIs, for example the GitHub API.
- [ ] DSA: *Stack*, *Binary Search*.

### Weeks 7–8 — Build and ship Project P1
- [ ] Build **Project P1** ([04-projects.md](04-projects.md#p1--paper-radar-cli-tested-python-tool)).
- [ ] **GitHub Actions**: a CI workflow that runs ruff, mypy and pytest on every push and PR.
- [ ] Write a proper README (see the template in [04-projects.md](04-projects.md#readme-template-for-every-project)).
- [ ] Optional: publish the package to PyPI.
- [ ] Reading track: *The Pragmatic Programmer* (skim) or continue Ousterhout.

**✅ Exit test:** you can create a new Python project from scratch with uv, tests, type checks, linting and CI in under 30 minutes. You can write a SQL query with a JOIN and GROUP BY from memory. You can explain what happens when you type a URL into the browser. DSA: about 35–40 problems solved.

---

## Phase 2 — Back-end engineering (Weeks 9–16)

**Goal:** build, test, containerize and deploy a production-style REST API with a real database, authentication and background jobs.

### Week 9 — APIs and FastAPI
- [ ] REST API design: resources, HTTP verbs, status codes, pagination, filtering, versioning, idempotency, error format.
- [ ] **FastAPI official tutorial**: First Steps through Dependencies. Learn **Pydantic v2**.
- [ ] OpenAPI/Swagger: read and use the auto-generated docs.
- [ ] DSA: *Linked List*.

### Week 10 — PostgreSQL for real
- [ ] Install PostgreSQL (in Docker is fine). Use `psql` and DBeaver or pgAdmin.
- [ ] Schema design, constraints, foreign keys, indexes (B-tree, GIN), `EXPLAIN ANALYZE`, transactions and isolation levels.
- [ ] **SQLAlchemy 2.0** tutorial (or SQLModel). Migrations with **Alembic**.
- [ ] The N+1 query problem and how to avoid it.
- [ ] Reading track: start ***Designing Data-Intensive Applications*** (DDIA, 2nd ed.), Ch. 1–2.

### Week 11 — Authentication and security
- [ ] Password hashing (argon2 or bcrypt), sessions vs JWT, refresh tokens, OAuth2 and OpenID Connect (concepts, plus "Login with Google/GitHub").
- [ ] Authorization: roles and permissions, row-level ownership checks.
- [ ] **OWASP Top 10**: SQL injection, XSS, CSRF, broken access control, SSRF.
- [ ] CORS, rate limiting, secrets in environment variables (never commit secrets!).
- [ ] DSA: *Trees* (part 1).

### Week 12 — Docker and Docker Compose
- [ ] **Docker Get Started** guide: images, containers, layers, Dockerfile, multi-stage builds, volumes, networks.
- [ ] **Docker Compose**: run API + PostgreSQL + Redis together with one command.
- [ ] `.dockerignore`, running as a non-root user, keeping images small.
- [ ] Reading track: DDIA Ch. 3.

### Week 13 — Async, caching, background jobs, files
- [ ] `async`/`await` in FastAPI. When async helps (I/O-bound work) and when it doesn't (CPU-bound work).
- [ ] **Redis**: caching patterns (cache-aside, TTLs, invalidation).
- [ ] **Background jobs**: Celery, ARQ or Dramatiq, plus retries and idempotency.
- [ ] File uploads to S3-compatible storage (**MinIO** locally).
- [ ] DSA: *Trees* (part 2), *Tries*.

### Week 14 — Testing and observability for back-ends
- [ ] API tests with pytest + `httpx`/TestClient. Test databases with **Testcontainers**.
- [ ] Unit vs integration vs end-to-end tests, and the testing pyramid.
- [ ] Structured logging (JSON logs), request IDs, health checks, graceful error handling.
- [ ] CI: run the tests against a real PostgreSQL service container in GitHub Actions.
- [ ] Reading track: **The Twelve-Factor App** (short, read it all) and **Cosmic Python** Ch. 1–6.

### Weeks 15–16 — Ship Project P2
- [ ] Finish **Project P2** ([04-projects.md](04-projects.md#p2--docvault-api-production-style-rest-api)).
- [ ] Deploy it on **Render**, **Railway** or **Fly.io** (or a small AWS Lightsail/EC2 server) with HTTPS.
- [ ] Optional: **Full Stack Open** Parts 3–4 (Node.js/Express) for JavaScript back-end exposure.
- [ ] DSA: *Heap / Priority Queue*. Total so far: about 75–80 problems.

**✅ Exit test:** you can build a CRUD API with auth, PostgreSQL, migrations, tests and Docker Compose, then deploy it, all from scratch. You can explain indexes, transactions, JWT vs sessions, and caching strategies.

---

## Phase 3 — AI engineering: LLMs, RAG, evals, agents, MCP (Weeks 17–24)

**Goal:** this is your strongest area. Turn it into **production AI engineering**: build AI features on top of your back-end skills, measure their quality, and make them reliable.

### Week 17 — LLM foundations (fast refresher, since you know ML)
- [ ] **Karpathy**: *Let's build GPT: from scratch, in code*, *Let's build the GPT Tokenizer*, and *Deep Dive into LLMs like ChatGPT*.
- [ ] **The Illustrated Transformer** (Jay Alammar). **Hugging Face LLM Course**, chapters 1–4.
- [ ] Understand: tokenization, attention, context windows, KV cache, sampling (temperature, top-p), pre-training vs SFT vs RLHF/DPO, reasoning models.
- [ ] Reading track: start ***AI Engineering*** (Chip Huyen), Ch. 1–3.

### Week 18 — Using LLM APIs like a professional
- [ ] **OpenAI**, **Anthropic Claude** and **Google Gemini** SDKs: messages, system prompts, multi-turn conversations.
- [ ] **Structured outputs** (JSON Schema / Pydantic), **tool/function calling**, **streaming**, token counting, cost tracking, retries with backoff, rate limits, prompt caching.
- [ ] **Prompt engineering**: provider guides (Anthropic, OpenAI) and the Prompting Guide. Learn few-shot, chain-of-thought, prompt templates, versioning prompts.
- [ ] Run **open models locally** with **Ollama**.
- [ ] **Anthropic Academy**: *Building with the Claude API*.
- [ ] DSA: *Graphs* (BFS/DFS).

### Week 19 — Embeddings and vector search
- [ ] Embeddings, cosine similarity, approximate nearest neighbor search (HNSW, IVF).
- [ ] **pgvector** (vectors inside PostgreSQL, which you already know), plus Qdrant or Chroma.
- [ ] Chunking strategies (fixed, recursive, semantic, document-structure-aware), metadata filtering.
- [ ] **Hybrid search** (BM25 + vectors) and **reranking** (cross-encoders, Cohere/Jina/BGE rerankers).
- [ ] **LLM Zoomcamp** (DataTalks.Club) modules 1–3.

### Week 20 — Build RAG end to end (Project P3 core)
- [ ] Ingestion pipeline: PDF/HTML parsing, cleaning, chunking, embedding, storage, re-indexing.
- [ ] Retrieval → context building → generation with **citations**, streaming through FastAPI.
- [ ] Handle the failure cases: no relevant documents, conflicting sources, prompt injection inside documents.
- [ ] Reading track: *AI Engineering* Ch. 4–6 (evaluation and RAG).

### Week 21 — Evals and observability (what separates you from the crowd)
- [ ] Build a **golden dataset** (50–200 question/answer/source triples).
- [ ] Retrieval metrics: recall@k, MRR, nDCG. Generation metrics: faithfulness, answer relevance.
- [ ] **LLM-as-judge**: how to write judge prompts, calibrate them against human labels, and their pitfalls.
- [ ] **Error analysis**: read Hamel Husain's evals posts and look at your data by hand.
- [ ] Tools: **Ragas** or **DeepEval**, and tracing with **Langfuse** or **Arize Phoenix** (OpenTelemetry).
- [ ] Add an **eval regression test to CI**, so that a bad prompt change fails the build.
- [ ] DSA: *Graphs* (topological sort, union-find).

### Week 22 — Agents
- [ ] First, write a **tool-calling agent loop from scratch** (no framework) so you understand what frameworks do for you.
- [ ] Read Anthropic's **Building Effective Agents**: workflows vs agents, prompt chaining, routing, parallelization, orchestrator-workers, evaluator-optimizer.
- [ ] Then use a framework: **LangGraph** (most requested), plus a look at **smolagents** or **LlamaIndex** agents.
- [ ] Memory (short- and long-term), planning, human-in-the-loop approval, timeouts and loop limits.
- [ ] **Hugging Face Agents Course**, units 1–2.

### Week 23 — MCP and AI security
- [ ] **Model Context Protocol (MCP)**: servers, clients, tools, resources, prompts. Build an MCP server with the official Python SDK (FastMCP).
- [ ] **Hugging Face MCP Course** and **Anthropic Academy**'s MCP courses.
- [ ] **OWASP Top 10 for LLM Applications**: prompt injection, insecure output handling, excessive agency, data leakage.
- [ ] Guardrails: input/output validation, PII redaction, allow-listed tools, sandboxing.
- [ ] DSA: *Backtracking*.

### Week 24 — Ship Projects P3 + P4, and start applying
- [ ] Finish **P3** ([04-projects.md](04-projects.md#p3--askmydocs-production-rag-with-evals)) and **P4** ([04-projects.md](04-projects.md#p4--devscout-agent--mcp-server)).
- [ ] Write a **blog post** about each one: what you built, eval results, what failed, what you learned.
- [ ] **Update your CV and LinkedIn** ([09-job-search-strategy.md](09-job-search-strategy.md)) and **start applying lightly** (5/week) to junior AI engineer, AI intern and graduate roles.
- [ ] Find your first **open-source "good first issue"** in an AI library.
- [ ] Optional deep dive: **Stanford CS336** (Language Modeling from Scratch) or Sebastian Raschka's *Build a Large Language Model (From Scratch)*.

**✅ Exit test:** you can build and deploy a RAG system with citations and streaming, **show eval numbers** for it, explain why each design choice was made, write a tool-calling agent without a framework, and build an MCP server. DSA: about 110 problems.

---

## Phase 4 — Front-end engineering (Weeks 25–31)

**Goal:** be able to build a clean, responsive, accessible web UI for your AI products using the industry's most common stack: **TypeScript + React + Next.js + Tailwind**.

### Week 25 — HTML and CSS
- [ ] Semantic HTML, forms, accessibility basics (labels, alt text, keyboard navigation, ARIA only when needed).
- [ ] CSS: box model, specificity, **Flexbox**, **Grid**, responsive design (media queries, mobile-first), CSS variables.
- [ ] Resources: **MDN Learn web development** or **The Odin Project** Foundations (HTML/CSS parts). Play Flexbox Froggy and Grid Garden.
- [ ] Mini-exercise: rebuild a real landing page from a screenshot.

### Week 26 — JavaScript
- [ ] **javascript.info** Part 1 essentials: types, functions, **closures**, objects, prototypes, classes, `this`, array methods, **promises**, **async/await**, modules, error handling.
- [ ] The **event loop** (microtasks vs macrotasks). This comes up in interviews often.
- [ ] DOM, events, `fetch`. Build a small vanilla JS app (a to-do list or a chat UI calling your P3 API).
- [ ] DSA: *1-D Dynamic Programming*.

### Week 27 — TypeScript
- [ ] **TypeScript Handbook**: basic types, interfaces vs types, unions, narrowing, generics, utility types.
- [ ] **Total TypeScript** free beginner tutorials. **Full Stack Open** Part 9.
- [ ] Tooling: Node.js (via nvm/fnm), **pnpm**, ESLint, Prettier, Vite.

### Week 28 — React
- [ ] **react.dev/learn**: the whole "Learn" section. Components, props, state, effects, lifting state up, keys, refs, custom hooks.
- [ ] **Full Stack Open** Parts 1, 2, 5 (testing React) and 7 (React Router, custom hooks).
- [ ] Data fetching with **TanStack Query**, forms with **React Hook Form + Zod**.
- [ ] Testing: **Vitest** + **React Testing Library**.

### Week 29 — Next.js and modern UI
- [ ] **Next.js Learn** course (App Router): server vs client components, layouts, routing, server actions, route handlers, streaming, caching, metadata.
- [ ] **Tailwind CSS** + **shadcn/ui** for professional-looking components quickly.
- [ ] Authentication in Next.js (**Auth.js**, Clerk or Supabase Auth).
- [ ] **Vercel AI SDK** for streaming chat UIs.
- [ ] DSA: *2-D Dynamic Programming*.

### Weeks 30–31 — Ship Project P5
- [ ] Build **Project P5** ([04-projects.md](04-projects.md#p5--full-stack-ai-app-nextjs-front-end-for-p3p4)): the Next.js front-end for your RAG and agent back-end.
- [ ] End-to-end tests with **Playwright**. Lighthouse score above 90 for accessibility and performance.
- [ ] Deploy the front-end on **Vercel** and connect it to your deployed back-end.

**✅ Exit test:** you can build a responsive, typed, tested React/Next.js app that streams responses from an AI back-end, with auth, and explain the event loop, closures, React re-rendering, and SSR vs CSR vs SSG. DSA: about 130 problems.

---

## Phase 5 — Cloud, DevOps and MLOps/LLMOps (Weeks 32–38)

**Goal:** deploy and operate AI systems the way companies do (cloud, infrastructure as code, CI/CD, containers, monitoring), and own the model side too (fine-tuning, serving, cost).

### Week 32 — Cloud fundamentals (AWS)
- [ ] **AWS Skill Builder**: *Cloud Practitioner Essentials* (free).
- [ ] Core services: **IAM** (least privilege!), **VPC** basics, **EC2**, **S3**, **RDS** (PostgreSQL), **ECR**, **ECS Fargate**, **Lambda**, **CloudWatch**, **Secrets Manager**, and **Bedrock** for hosted LLMs.
- [ ] ⚠️ **Set up billing alerts and budgets on day 1.** Delete resources when you're done with them.
- [ ] Optional: **Cloud Resume Challenge** (a great guided cloud project).

### Week 33 — Infrastructure as Code
- [ ] **Terraform** tutorials (AWS track): providers, resources, variables, state, modules.
- [ ] Deploy your P2/P3 back-end to **ECS Fargate + RDS + S3** using Terraform.
- [ ] Learn the difference between ClickOps and IaC, and why teams prefer IaC.
- [ ] DSA: *Intervals*, *Greedy*.

### Week 34 — CI/CD and Kubernetes basics
- [ ] GitHub Actions pipeline: lint → test → build Docker image → push to ECR/GHCR → deploy, with staging and production environments.
- [ ] **Kubernetes basics** (enough for interviews and reading configs): Pods, Deployments, Services, Ingress, ConfigMaps/Secrets, Helm. Practice locally with **kind** or **minikube**.
- [ ] Read about blue/green and canary deployments, and feature flags.

### Week 35 — Fine-tuning
- [ ] When to fine-tune vs prompt vs RAG. Most of the time the answer is **not** to fine-tune, and you should be able to explain why.
- [ ] Hugging Face **Transformers** + **PEFT** (LoRA/QLoRA) + **TRL** (SFT, intro to DPO). Use **Unsloth** for fast, cheap fine-tuning.
- [ ] Experiment tracking: **MLflow** or **Weights & Biases**. Version your datasets.
- [ ] Rent a GPU cheaply (Colab, Kaggle, RunPod, Lambda, Modal). Track the cost of every run.
- [ ] Reading track: *AI Engineering* Ch. 7–8 (fine-tuning, dataset engineering).

### Week 36 — Model serving and inference optimization
- [ ] Serve models with **vLLM** (understand PagedAttention and continuous batching), plus a look at TGI and Ollama.
- [ ] **Quantization**: GGUF, AWQ, GPTQ, bitsandbytes, and their quality vs speed trade-offs.
- [ ] Latency vs throughput, time-to-first-token, tokens/sec, GPU memory maths (weights + KV cache).
- [ ] Serve your fine-tuned model behind an **OpenAI-compatible API**.
- [ ] Reading track: *AI Engineering* Ch. 9 (inference optimization).
- [ ] DSA: *Math & Geometry*, *Bit Manipulation*. NeetCode 150 complete 🎉

### Week 37 — Monitoring and LLMOps
- [ ] Metrics, logs and traces. **Prometheus + Grafana** basics. **OpenTelemetry**.
- [ ] LLM production monitoring: cost per request, latency percentiles (p50/p95/p99), error rates, user feedback, online evals, drift.
- [ ] Model and prompt versioning, A/B tests, rollbacks.
- [ ] **Made With ML** (MLOps) lessons, or selected **MLOps Zoomcamp** modules.

### Week 38 — Ship Project P6, then apply at full volume
- [ ] Finish **Project P6** ([04-projects.md](04-projects.md#p6--fine-tune-vs-prompt-train-serve-and-compare)).
- [ ] Optional certification (pick **one**): **AWS Solutions Architect – Associate** (broadest recognition) or **AWS Machine Learning Engineer – Associate** (if you target ML engineer roles).
- [ ] **Applications: increase to 10–15 per week.**

**✅ Exit test:** you can deploy a containerized app to AWS with Terraform and CI/CD, fine-tune a small open model with LoRA, serve it with vLLM, and explain the cost, latency and quality trade-offs against an API model.

---

## Phase 6 — System design (Weeks 39–44)

**Goal:** be able to design large systems on a whiteboard (classic, ML and GenAI) and communicate trade-offs clearly. That's what interviewers look for.

### Week 39 — Building blocks
- [ ] Scalability, latency vs throughput, availability (nines, SLAs/SLOs), CAP and PACELC, consistency models.
- [ ] Load balancers, reverse proxies, CDNs, caching layers and eviction policies.
- [ ] SQL vs NoSQL, replication, partitioning/sharding, consistent hashing, indexes (B-tree vs LSM).
- [ ] Message queues and streams (**Kafka**, SQS, RabbitMQ), pub/sub, exactly-once vs at-least-once delivery.
- [ ] Resources: **System Design Primer**, **ByteByteGo System Design 101**, **Hello Interview** core concepts.
- [ ] Reading track: DDIA Ch. 5–9 (replication, partitioning, transactions, distributed systems trouble, consistency).

### Week 40 — The interview framework and the classics
- [ ] Learn the framework: **requirements → estimates → API → data model → high-level design → deep dives → bottlenecks and trade-offs**.
- [ ] *System Design Interview Vol. 1* (Alex Xu): rate limiter, consistent hashing, key-value store, unique ID generator, URL shortener, web crawler, notification system, news feed, chat system, autocomplete.
- [ ] Practice: write up one design per day in a Markdown file in this repo.

### Week 41 — Practice and build
- [ ] Hello Interview / ByteByteGo problems: Dropbox, Ticketmaster, WhatsApp, Uber, YouTube, Leaderboard, Payment system.
- [ ] Build **Project P7** ([04-projects.md](04-projects.md#p7--snaplink-scalable-url-shortener-with-load-tests)): a URL shortener with caching, rate limiting and a load test, so that you've *measured* what you design.

### Week 42 — ML system design
- [ ] *Machine Learning System Design Interview* (Aminian & Xu): recommendations, search ranking, ad click prediction, harmful content detection, people-you-may-know.
- [ ] *Designing Machine Learning Systems* (Chip Huyen): data pipelines, feature stores, training/serving skew, monitoring and drift.
- [ ] The ML design framework: problem framing → metrics (offline/online) → data → features → model → serving → monitoring.

### Week 43 — GenAI / LLM system design
- [ ] *Generative AI System Design Interview* (Aminian & Sheng) and *AI Engineering* Ch. 10.
- [ ] Practice: ChatGPT-style chat service, enterprise RAG over 10M documents, customer-support agent with escalation, code assistant, document-extraction pipeline, multi-tenant LLM gateway (routing, caching, rate limits, fallbacks).
- [ ] Always cover: **evals, guardrails, cost per request, latency budget, caching, model routing, fallback models, data privacy, feedback loops**.

### Week 44 — Mock interviews
- [ ] At least **4 mock system design interviews**: with peers, on Exponent, interviewing.io or Hello Interview mocks, or by recording yourself.
- [ ] Re-do your weakest designs.
- [ ] DSA: timed mixed practice (2 problems in 45 minutes).

**✅ Exit test:** in 45 minutes you can design a URL shortener, a chat system, a RAG system for an enterprise, and a recommendation system, explaining the trade-offs and doing back-of-the-envelope estimates.

---

## Phase 7 — Capstone, interviews and getting hired (Weeks 45–52)

**Goal:** finish one **impressive, real product with real users**, and turn all your preparation into job offers.

### Weeks 45–49 — Capstone (Project P8)
- [ ] Choose and build **P8** ([04-projects.md](04-projects.md#p8--capstone-a-real-ai-product-with-real-users)): full stack + AI + cloud + evals + monitoring.
- [ ] Get **10–50 real users** (classmates, a local business, a community, an NGO, your university).
- [ ] Iterate based on feedback and metrics. Write a detailed **case study**.
- [ ] Record a **2–3 minute demo video**.

### Weeks 45–52 — The job hunt (in parallel)
- [ ] **10–15 targeted applications per week**, with referrals wherever possible ([09-job-search-strategy.md](09-job-search-strategy.md)).
- [ ] **2 mock interviews per week**: alternate coding, system design and AI/LLM rounds.
- [ ] Prepare **8 behavioral stories** (STAR) from your projects ([05-interview-prep.md](05-interview-prep.md#9-behavioral-interview)).
- [ ] Keep up DSA: 1 problem per day, focused on weak topics. Re-solve the NeetCode 150 problems you struggled with.
- [ ] Open source: aim for **2–3 merged PRs** in AI or developer-tools projects by week 52.

### Weeks 50–52 — Interview sprint and buffer
- [ ] Use this time for interview loops, take-homes and negotiation.
- [ ] If you fall behind on anything earlier in the plan, this is your buffer.

**✅ Final exit test:** you have 6+ portfolio projects, 1 capstone with real users, 150+ DSA problems, 10+ system designs written up, 2+ open-source PRs, a strong CV, GitHub profile and LinkedIn, and interviews in progress.

---

## After you get the job

- **First 90 days:** learn the codebase, ship small things fast, ask questions, write things down.
- **Year 2 directions:** go deeper into **AI platform/MLOps** (Kubernetes, GPUs, distributed training), **research engineering** (training, RL, post-training), or **product/full-stack AI**.
- Keep learning: read papers weekly, follow the AI Engineer community, and keep contributing to open source.

👉 Next: the full list of courses in order → [03-courses-and-resources.md](03-courses-and-resources.md)
