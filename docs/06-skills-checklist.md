# 06 — Skills Checklist

> Tick a box only when you can **do it without a tutorial** or **explain it to someone else**. Update this file through a **pull request** every Sunday. It's good Git practice, and the history shows your progress.
>
> Legend: 🟢 required for a junior AI engineer job · 🟡 strongly recommended · 🔵 bonus / later

---

## 1. Tools and workflow
- [ ] 🟢 Navigate and work in a Linux terminal (files, permissions, processes, pipes, environment variables)
- [ ] 🟢 Write a simple Bash script
- [ ] 🟢 Use SSH and SSH keys
- [ ] 🟢 Use VS Code productively (debugger, extensions, keyboard shortcuts)
- [ ] 🟢 Use an AI coding assistant (Claude Code / Cursor / Copilot) and review its output critically
- [ ] 🟡 Basic vim or nano for editing on servers

## 2. Git and GitHub
- [ ] 🟢 init, clone, add, commit, push, pull, fetch
- [ ] 🟢 Branches, switching, merging
- [ ] 🟢 Pull requests: create, review, request changes, merge
- [ ] 🟢 Resolve a merge conflict
- [ ] 🟢 Undo things: `restore`, `reset` (soft/mixed/hard), `revert`, `reflog`
- [ ] 🟢 Write good commit messages (Conventional Commits)
- [ ] 🟢 `.gitignore`, and never committing secrets
- [ ] 🟡 Rebase (including interactive rebase on your *own* branches), squash, cherry-pick
- [ ] 🟡 `git stash`, `git bisect`, `git blame`
- [ ] 🟡 GitHub Issues, Projects, Actions, Releases
- [ ] 🟡 Contribute to an open-source project (fork → branch → PR)

## 3. Python (engineering level)
- [ ] 🟢 Project setup with uv and `pyproject.toml`, virtual environments
- [ ] 🟢 Type hints everywhere, with mypy or pyright passing
- [ ] 🟢 ruff for linting and formatting
- [ ] 🟢 OOP, dataclasses, Pydantic models
- [ ] 🟢 Exceptions, custom errors, logging
- [ ] 🟢 Generators, decorators, context managers, closures
- [ ] 🟢 pytest: fixtures, parametrize, mocking, coverage
- [ ] 🟢 asyncio: `async`/`await`, `gather`, timeouts
- [ ] 🟡 Concurrency: threads vs processes vs async, and the GIL
- [ ] 🟡 Packaging and publishing to PyPI
- [ ] 🔵 Profiling (cProfile, py-spy) and performance optimization

## 4. CS fundamentals and DSA
- [ ] 🟢 Big-O analysis
- [ ] 🟢 Arrays, hash maps, sets, stacks, queues, linked lists
- [ ] 🟢 Trees, BST, heaps, tries
- [ ] 🟢 Graphs: BFS, DFS, topological sort
- [ ] 🟢 Binary search, two pointers, sliding window
- [ ] 🟢 Recursion and backtracking
- [ ] 🟢 Dynamic programming (1-D and 2-D)
- [ ] 🟡 Dijkstra, union-find, intervals, greedy
- [ ] 🟢 NeetCode 150 progress: ☐ 25 ☐ 50 ☐ 75 ☐ 100 ☐ 125 ☐ 150
- [ ] 🟢 Networking: DNS, TCP/IP, HTTP/HTTPS, TLS basics
- [ ] 🟡 Operating systems: processes, threads, memory, file systems

## 5. Databases
- [ ] 🟢 SQL: SELECT, JOINs, GROUP BY/HAVING, subqueries, CTEs
- [ ] 🟢 Window functions
- [ ] 🟢 Schema design and normalization
- [ ] 🟢 Indexes, plus reading `EXPLAIN ANALYZE`
- [ ] 🟢 Transactions, ACID, isolation levels
- [ ] 🟢 PostgreSQL in practice (psql, constraints, JSONB)
- [ ] 🟢 ORM (SQLAlchemy 2.0) + migrations (Alembic)
- [ ] 🟢 Redis: caching, TTL, basic data structures
- [ ] 🟡 Replication, sharding, connection pooling
- [ ] 🟡 NoSQL: when and why (document, key-value, wide-column)
- [ ] 🟢 Vector search: pgvector and/or a vector database

## 6. Back-end
- [ ] 🟢 REST API design (resources, status codes, pagination, errors, versioning)
- [ ] 🟢 FastAPI: routing, dependencies, Pydantic validation, OpenAPI docs
- [ ] 🟢 Authentication: password hashing, JWT, sessions, OAuth2 concepts
- [ ] 🟢 Authorization (ownership checks, roles)
- [ ] 🟢 Background jobs and queues (Celery/ARQ), retries, idempotency
- [ ] 🟢 File uploads and object storage (S3)
- [ ] 🟢 Testing APIs (unit + integration with a real DB)
- [ ] 🟢 Structured logging, health checks, error handling
- [ ] 🟢 Security: OWASP Top 10 (SQLi, XSS, CSRF, SSRF, broken access control), CORS, rate limiting
- [ ] 🟢 Server-Sent Events and streaming responses
- [ ] 🟡 WebSockets
- [ ] 🟡 Basic Node.js/Express (or Next.js route handlers)
- [ ] 🔵 A second back-end language (Go or TypeScript/Node)

## 7. Front-end
- [ ] 🟢 Semantic HTML and accessibility basics
- [ ] 🟢 CSS: box model, Flexbox, Grid, responsive design
- [ ] 🟢 JavaScript: closures, `this`, promises, async/await, modules, the event loop
- [ ] 🟢 DOM and events, `fetch`
- [ ] 🟢 TypeScript: types, interfaces, generics, narrowing
- [ ] 🟢 React: components, props, state, effects, hooks, keys, lists, forms
- [ ] 🟢 Next.js App Router: server/client components, routing, data fetching, server actions
- [ ] 🟢 Tailwind CSS + a component library (shadcn/ui)
- [ ] 🟢 Streaming chat UI (Vercel AI SDK or SSE by hand)
- [ ] 🟡 Data fetching and caching (TanStack Query), forms (React Hook Form + Zod)
- [ ] 🟡 Testing: Vitest + React Testing Library, Playwright E2E
- [ ] 🔵 Web performance (Core Web Vitals), advanced accessibility

## 8. AI engineering
- [ ] 🟢 Explain transformers, attention, tokenization, KV cache, sampling
- [ ] 🟢 Use LLM APIs (OpenAI, Anthropic, Gemini): messages, system prompts, streaming
- [ ] 🟢 Structured outputs (JSON Schema / Pydantic)
- [ ] 🟢 Tool / function calling
- [ ] 🟢 Prompt engineering and prompt versioning
- [ ] 🟢 Embeddings and similarity search
- [ ] 🟢 Chunking strategies
- [ ] 🟢 Build a full RAG pipeline with citations
- [ ] 🟢 Hybrid search + reranking
- [ ] 🟢 **Evals:** golden datasets, retrieval metrics, LLM-as-judge, error analysis
- [ ] 🟢 Tracing and observability (Langfuse / Phoenix / OpenTelemetry)
- [ ] 🟢 Build an agent from scratch (tool loop, limits, error handling)
- [ ] 🟢 An agent framework (LangGraph)
- [ ] 🟢 Build an MCP server
- [ ] 🟢 AI security: prompt injection, guardrails, PII, OWASP LLM Top 10
- [ ] 🟢 Cost and latency optimization (routing, caching, streaming)
- [ ] 🟡 Run open models locally (Ollama) and compare them with API models
- [ ] 🟡 Fine-tuning with LoRA/QLoRA (PEFT, TRL, Unsloth)
- [ ] 🟡 Model serving with vLLM, plus quantization
- [ ] 🟡 Multi-modal (vision, speech with Whisper)
- [ ] 🔵 DPO / preference tuning
- [ ] 🔵 Training a small LLM from scratch (nanoGPT / nanochat)

## 9. Cloud, DevOps and MLOps
- [ ] 🟢 Docker: Dockerfile, multi-stage builds, volumes, networks
- [ ] 🟢 Docker Compose for multi-service apps
- [ ] 🟢 CI/CD with GitHub Actions (lint, test, build, deploy)
- [ ] 🟢 Deploy an app to a PaaS (Render / Railway / Fly.io / Vercel)
- [ ] 🟢 AWS core: IAM, EC2, S3, RDS, ECR, ECS/Fargate, Lambda, CloudWatch
- [ ] 🟢 Billing alerts and cost awareness
- [ ] 🟡 Terraform (Infrastructure as Code)
- [ ] 🟡 Kubernetes basics: Pods, Deployments, Services, Ingress, Helm
- [ ] 🟡 Monitoring: Prometheus + Grafana, metrics/logs/traces
- [ ] 🟡 Experiment tracking (MLflow / W&B), data and model versioning
- [ ] 🔵 One cloud certification (AWS SAA or ML Engineer Associate)
- [ ] 🔵 GPU basics and distributed training

## 10. System design
- [ ] 🟢 Scalability basics: vertical vs horizontal scaling, load balancing, stateless services
- [ ] 🟢 Caching (strategies, eviction, CDN)
- [ ] 🟢 Database scaling: replication, partitioning, consistent hashing
- [ ] 🟢 Queues and streams (Kafka/SQS), async processing
- [ ] 🟢 CAP theorem, consistency models
- [ ] 🟢 Rate limiting algorithms (token bucket, sliding window)
- [ ] 🟢 Back-of-the-envelope estimates
- [ ] 🟢 The interview framework (requirements → estimates → API → data → design → deep dive)
- [ ] 🟡 10+ classic designs written up
- [ ] 🟡 3+ ML system designs written up
- [ ] 🟢 3+ GenAI system designs written up (RAG at scale, chat service, agent platform)

## 11. Professional skills
- [ ] 🟢 Write clear READMEs and design docs
- [ ] 🟢 Explain technical decisions and trade-offs out loud
- [ ] 🟢 Give and receive code review politely and usefully
- [ ] 🟢 8 behavioral stories (STAR) ready
- [ ] 🟢 CV, LinkedIn and GitHub profile polished
- [ ] 🟡 Technical blog with 3+ posts
- [ ] 🟡 2+ merged open-source PRs
- [ ] 🟡 Talk to users and turn feedback into features (product sense)

## 12. Portfolio
- [ ] P0: Learning log + GitHub profile
- [ ] P1: Paper Radar CLI
- [ ] P2: DocVault API (deployed)
- [ ] P3: AskMyDocs RAG with evals (deployed)
- [ ] P4: DevScout agent + MCP server
- [ ] P5: Full-stack Next.js AI app (deployed)
- [ ] P6: Fine-tune vs prompt comparison (on AWS)
- [ ] P7: SnapLink with load tests
- [ ] P8: Capstone with real users
- [ ] Open source: ☐ 1st PR merged ☐ 2nd ☐ 3rd
