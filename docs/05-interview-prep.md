# 05 — Interview Preparation: Every Skill You'll Be Tested On

> This page covers **what interviews look like** for your target roles, **every topic you need to know**, and **how to practise**. Use it as a checklist from month 6 onward, and as your main study guide in months 10–12.

---

## 1. What the interview process looks like

### AI Engineer / Applied AI Engineer (typical 2026 loop)

| Stage | Length | What happens |
|---|---|---|
| Recruiter screen | 30 min | Your background, motivation, salary expectations. Have a clear 60-second "about me" ready. |
| Technical screen | 45–60 min | LLM fundamentals + **live coding**, often with an LLM API (e.g. "build a small RAG or tool-calling script"), or a DSA problem |
| Take-home (some companies) | 2–6 h | For example: "Build a small RAG + agent, **with evals**". Always include an eval and a README. |
| Onsite / virtual loop | 3–5 rounds | Coding (DSA or practical), **AI/LLM system design**, **AI deep-dive** (RAG, evals, agents, fine-tuning), project deep-dive, behavioral |

The topic mix reported for 2026 AI engineer loops is roughly **40% RAG/evals/agents, 30% production systems, 20% LLM internals, 10% behavioral**. Several guides now describe **eval methodology as "the new system design"**: expect at least one question like *"How would you build a golden set, use LLM-as-judge, and catch regressions before production?"*

### Software Engineer (Back-end / Full-stack)
Online assessment (HackerRank/CodeSignal, 70–90 min, 2–4 DSA problems) → phone screen (1 DSA problem) → onsite: 2× coding, 1× system design (often skipped for new grads, but more and more common), 1× behavioral. Some companies use a **practical round** instead: build a small API, debug existing code, or review a PR.

### ML Engineer
Coding (DSA + ML coding such as "implement k-means / logistic regression / attention in NumPy") → ML fundamentals → **ML system design** → behavioral.

### AI in interviews
Some companies now **allow or even expect AI coding tools** in practical rounds, while others **ban** them completely. Prepare for both: be able to solve problems by hand, *and* be able to show that you use AI tools well (clear prompts, reviewing output, catching AI mistakes).

---

## 2. Coding interview (DSA)

### How to practise
- **NeetCode 150** in roadmap order (from Week 3, ~1 problem per day). Then **Grind 75** as review.
- **Process for each problem:** try it for 25 minutes on your own → if you're stuck, watch the NeetCode explanation → **code it yourself without looking** → write the pattern in your notes → **re-solve it 3 days and 2 weeks later**.
- From month 9, practise **under interview conditions**: timer on, talking out loud, no autocomplete.
- Count only problems **you can re-solve alone**. Doing 150 well is better than skimming 500.

### Topics and patterns, in learning order

| # | Topic | Key patterns | Typical problems |
|---|---|---|---|
| 1 | Arrays & hashing | Hash map counting, prefix sums | Two Sum, Group Anagrams, Top K Frequent, Product Except Self |
| 2 | Two pointers | Opposite ends, fast/slow | Valid Palindrome, 3Sum, Container With Most Water |
| 3 | Sliding window | Fixed and variable window | Longest Substring Without Repeating, Min Window Substring |
| 4 | Stack | Monotonic stack | Valid Parentheses, Daily Temperatures, Min Stack |
| 5 | Binary search | On arrays and on the answer | Search Rotated Array, Koko Eating Bananas |
| 6 | Linked list | Dummy node, reversal, fast/slow | Reverse List, Merge Two Lists, Detect Cycle, LRU Cache |
| 7 | Trees | DFS (recursive), BFS (queue) | Max Depth, Level Order, Validate BST, LCA |
| 8 | Tries | Prefix tree | Implement Trie, Word Search II |
| 9 | Heap / priority queue | Top-K, two heaps | Kth Largest, Median from Data Stream, Merge K Lists |
| 10 | Backtracking | Choose / explore / un-choose | Subsets, Permutations, Combination Sum, N-Queens |
| 11 | Graphs | BFS/DFS, topological sort, union-find | Number of Islands, Course Schedule, Clone Graph |
| 12 | Advanced graphs | Dijkstra, MST | Network Delay Time, Min Cost to Connect Points |
| 13 | 1-D DP | Memoization → tabulation | Climbing Stairs, House Robber, Coin Change, LIS |
| 14 | 2-D DP | Grids, two strings | Unique Paths, LCS, Edit Distance |
| 15 | Greedy & intervals | Sort + sweep | Merge Intervals, Meeting Rooms, Jump Game |
| 16 | Math & bits | | Pow(x,n), Single Number, Counting Bits |

### Must know cold
- **Big-O** of every operation on lists, dicts, sets, heaps and deques in Python, and of common algorithms (sorting O(n log n), BFS/DFS O(V+E), binary search O(log n)).
- Python tools: `collections` (`Counter`, `defaultdict`, `deque`), `heapq`, `bisect`, `functools.lru_cache`, `itertools`, slicing, comprehensions, `sorted(key=…)`.

### How to behave in the coding round (the UMPIRE method)
1. **Understand:** repeat the problem, ask about edge cases and input sizes.
2. **Match:** say which pattern it looks like.
3. **Plan:** explain your approach and its complexity **before** you code. Start with brute force if needed.
4. **Implement:** write clean code, use good names, and talk while you code.
5. **Review:** walk through an example by hand. Check edge cases (empty input, one element, duplicates).
6. **Evaluate:** state the time and space complexity, and how you'd improve it.

> Interviewers grade **communication and problem-solving process** almost as much as the final code.

---

## 3. Python and software engineering questions

- Mutable vs immutable types, and the mutable default-argument trap.
- `is` vs `==`, shallow vs deep copy.
- Generators and iterators, `yield`, lazy evaluation.
- Decorators, context managers (`with`), closures.
- `*args` / `**kwargs`, type hints, dataclasses, Pydantic.
- The GIL, threading vs multiprocessing vs asyncio. When to use each.
- How `dict` works (hash table) and why lookup is O(1) on average.
- Exceptions, and logging good practice.
- Testing: unit vs integration vs E2E, mocking, fixtures, what to test, and why TDD.
- SOLID principles, composition vs inheritance, dependency injection, common design patterns (factory, strategy, adapter, repository).
- Code review: what you look for in a PR.
- Git: merge vs rebase, how to resolve a conflict, how to undo a pushed commit (`revert`), and why not to force-push shared branches.

---

## 4. Back-end and web questions

**HTTP and APIs**
- What happens when you type a URL into the browser (DNS → TCP → TLS → HTTP → server → response → rendering).
- HTTP methods, idempotency (which methods are idempotent?), status codes (200, 201, 204, 301/302, 400, 401 vs 403, 404, 409, 422, 429, 500, 502/503/504).
- REST vs GraphQL vs gRPC vs WebSockets vs Server-Sent Events (SSE is how LLM streaming usually works).
- API design: pagination (offset vs cursor), versioning, error formats, rate limiting, idempotency keys.

**Auth and security**
- Authentication vs authorization. Sessions + cookies vs JWT, and the pros and cons of each.
- OAuth2 / OIDC flow at a high level. Password hashing (why bcrypt/argon2 and never MD5/SHA for passwords).
- CORS, CSRF, XSS, SQL injection, SSRF, and how to prevent each one.

**Databases**
- SQL vs NoSQL: when to use each.
- Indexes: how a B-tree index works, when an index *hurts*, composite index column order.
- Transactions and ACID. Isolation levels and the anomalies they allow (dirty read, non-repeatable read, phantom read).
- Normalization vs denormalization. The N+1 query problem.
- Write a SQL query live: JOIN + GROUP BY + HAVING, window functions (`ROW_NUMBER`, `RANK`), "second-highest salary", "top 3 per group".
- Replication vs sharding. Connection pooling.

**Systems**
- Caching strategies (cache-aside, write-through, write-back), TTLs, invalidation, cache stampede.
- Message queues: why use them, at-least-once delivery, idempotent consumers, dead-letter queues.
- Docker: image vs container, layers, multi-stage builds. Kubernetes: Pod, Deployment, Service.
- Processes vs threads. Concurrency vs parallelism. Deadlocks.
- Observability: logs vs metrics vs traces, and what SLI, SLO and SLA mean.

---

## 5. Front-end questions

- The JavaScript **event loop** (call stack, microtasks vs macrotasks). Predict the output of `setTimeout` + `Promise` code.
- **Closures**, `this` binding, `let`/`const`/`var` and hoisting, `==` vs `===`, prototypes.
- Promises, `async`/`await`, error handling, `Promise.all` vs `allSettled`.
- TypeScript: `type` vs `interface`, generics, unions and narrowing, `unknown` vs `any`.
- React: what causes a re-render, why `key` matters, `useState`/`useEffect`/`useMemo`/`useCallback`/`useRef`, lifting state, controlled vs uncontrolled inputs, custom hooks.
- Next.js: server components vs client components, SSR vs SSG vs ISR vs CSR, server actions.
- CSS: box model, Flexbox vs Grid, specificity, responsive design.
- Web performance (Core Web Vitals: LCP, INP, CLS), accessibility basics.
- Live task: "build a search box with debounce", "fetch and display a paginated list", "build a todo app".

---

## 6. ML fundamentals (you already know these, so rehearse them out loud)

- Bias–variance trade-off, overfitting and regularization (L1 vs L2, dropout, early stopping).
- Metrics: precision, recall, F1, ROC-AUC vs PR-AUC (and when to use each), RMSE vs MAE, ranking metrics (NDCG, MRR, MAP).
- Imbalanced data: resampling, class weights, threshold tuning, choosing the right metric.
- Train/validation/test splits, cross-validation, **data leakage** (with examples).
- Gradient descent variants (SGD, momentum, Adam), learning-rate schedules, vanishing and exploding gradients, batch norm vs layer norm.
- Trees vs linear models vs neural nets. Bagging vs boosting (Random Forest vs XGBoost).
- CNNs, RNNs, and why transformers replaced RNNs.
- **ML coding:** implement in NumPy (no libraries) logistic regression with gradient descent, k-means, softmax + cross-entropy, a single attention head, top-k sampling.

---

## 7. LLM and AI engineering questions (your most important round)

### LLM internals
- [ ] Explain the transformer: self-attention, multi-head attention, Q/K/V, positional encodings (RoPE), residual connections, layer norm, decoder-only vs encoder-decoder.
- [ ] Why attention is O(n²) in sequence length, and the main tricks against it (FlashAttention, sliding window, GQA/MQA).
- [ ] Tokenization: BPE, why LLMs struggle with spelling and arithmetic, and how tokens relate to cost.
- [ ] **KV cache:** what it is, why it speeds up generation, and why it uses so much memory.
- [ ] Sampling: temperature, top-k, top-p, greedy, beam search, and when to use each.
- [ ] The training pipeline: pre-training → SFT → RLHF / DPO / RL with verifiable rewards. What reasoning models do differently.
- [ ] Context windows, the "lost in the middle" effect, long-context vs RAG.
- [ ] Hallucinations: why they happen and how to reduce them (grounding, citations, constrained outputs, verification).
- [ ] Embeddings: how they're trained (contrastive learning), cosine similarity, dimensions vs cost.

### Building with LLMs
- [ ] **Prompting vs RAG vs fine-tuning:** when to use each (a very common question). Know the cost, latency, data needs and freshness trade-offs.
- [ ] Structured outputs and JSON mode, tool/function calling (how it works under the hood), streaming.
- [ ] Prompt engineering techniques, and why to version and test prompts.
- [ ] Cost and latency optimization: smaller models, **model routing**, prompt caching, semantic caching, batching, streaming, shorter prompts, parallel calls.
- [ ] Choosing between API models and self-hosted open models (privacy, cost at scale, control, ops burden).

### RAG (expect "How would you build a RAG system for X?")
- [ ] The full pipeline: parsing → chunking → embedding → indexing → retrieval → reranking → context building → generation → citation → evaluation → monitoring.
- [ ] Chunking strategies and their trade-offs. Chunk size vs retrieval quality.
- [ ] Vector index types (HNSW vs IVF), and vector DB vs pgvector.
- [ ] **Hybrid search** (BM25 + dense) and why it helps (exact names, codes, rare terms). Reranking with cross-encoders.
- [ ] Query rewriting, HyDE, multi-query, metadata filtering, parent-document retrieval.
- [ ] **Access control** in RAG (filtering by user permissions *before* retrieval).
- [ ] Failure modes: wrong chunks retrieved, right chunks but wrong answer, stale data, conflicting documents, prompt injection inside documents.
- [ ] Knowing when RAG isn't the answer: when a SQL query or a tool call works better ("text-to-SQL" or agentic retrieval).

### Evals (the most important differentiator)
- [ ] How to build a **golden dataset** (from real user queries, generated by an LLM and reviewed by humans, covering edge cases).
- [ ] **Retrieval metrics** (recall@k, precision@k, MRR, nDCG) vs **generation metrics** (faithfulness/groundedness, relevance, correctness).
- [ ] **LLM-as-judge:** how to design the rubric, use pairwise vs pointwise judging, **calibrate against human labels**, and handle the biases (position, verbosity, self-preference).
- [ ] **Error analysis:** read traces by hand, group the failures, fix the biggest group first.
- [ ] Offline evals vs online evals (A/B tests, user feedback, implicit signals).
- [ ] **Regression testing** of prompts and models in CI.

### Agents
- [ ] What an agent is, compared with a workflow. When *not* to use an agent (most of the time a simple workflow is better).
- [ ] The tool-calling loop, planning (ReAct), memory, multi-agent patterns (orchestrator-workers).
- [ ] **Failure modes:** infinite loops, wrong tool choice, compounding errors, high cost, prompt injection through tool outputs. And the mitigations: step limits, timeouts, validation, human approval, least privilege.
- [ ] **MCP:** what it solves (a standard way to connect AI apps to tools and data), servers vs clients, tools vs resources vs prompts.
- [ ] How you evaluate an agent (task success rate, step efficiency, trajectory evaluation, cost per task).

### Fine-tuning and serving
- [ ] Full fine-tuning vs **LoRA** vs **QLoRA**, and how LoRA works (low-rank update matrices).
- [ ] SFT vs DPO vs RLHF. How much data you need. Catastrophic forgetting.
- [ ] **Quantization** (INT8/INT4, GPTQ/AWQ/GGUF) and its quality trade-off.
- [ ] Serving: vLLM (PagedAttention, continuous batching), throughput vs latency, time-to-first-token. GPU memory estimate: **weights ≈ parameters × bytes per parameter**, plus KV cache.
- [ ] Speculative decoding and distillation (what they are).

### AI safety and security in production
- [ ] Prompt injection (direct and indirect) and defenses (no single defense is enough, so use layers).
- [ ] Data leakage, PII handling, and guardrails on input and output.
- [ ] The OWASP Top 10 for LLM applications.

---

## 8. System design interview

### The framework (45 minutes)
1. **Requirements (5 min):** functional and non-functional (scale, latency, availability, consistency). Ask questions.
2. **Estimates (3 min):** users, QPS, storage, bandwidth. Do the maths out loud.
3. **API (3 min):** the main endpoints.
4. **Data model (5 min):** entities, which database and why.
5. **High-level design (10 min):** boxes and arrows (client → LB → services → cache → DB → queue → workers).
6. **Deep dives (15 min):** the 2–3 hardest parts. The interviewer usually picks them.
7. **Bottlenecks and trade-offs (4 min):** single points of failure, scaling, monitoring, what you'd do with more time.

### Practice problems
**Classic:** URL shortener · rate limiter · key-value store · news feed · chat (WhatsApp) · notification system · web crawler · search autocomplete · YouTube/Netflix · Dropbox/Google Drive · Uber · Ticketmaster · payment system · leaderboard · distributed job scheduler

**ML system design:** recommendation system (YouTube/TikTok) · search ranking · ad click prediction · fraud detection · harmful content moderation · people-you-may-know · ETA prediction

**GenAI system design:** ChatGPT-style chat service · enterprise RAG over millions of documents · customer support agent with human escalation · coding assistant · document extraction pipeline · LLM gateway (routing, caching, rate limits, fallbacks, cost tracking) · AI search engine (Perplexity-style) · meeting summarizer · multi-tenant agent platform

**For GenAI designs, always discuss:** model choice and routing · RAG vs fine-tuning · **evals (offline + online)** · guardrails and safety · latency budget (time-to-first-token, streaming) · **cost per request at scale** · caching · fallbacks when a provider is down · data privacy · feedback loops for improvement.

### Numbers to know
- Latency: L1 cache ~1 ns · RAM ~100 ns · SSD read ~100 µs · round trip within a datacenter ~0.5 ms · disk seek ~10 ms · round trip across continents ~150 ms.
- 1 day ≈ 86,400 s ≈ 10⁵ s. 1M requests/day ≈ 12 QPS. 1B requests/day ≈ 12k QPS.
- A single PostgreSQL instance handles roughly thousands to tens of thousands of simple queries/sec. Redis handles ~100k ops/sec.
- LLM: ~0.75 English words per token. Time-to-first-token is typically hundreds of milliseconds, and generation tens to ~100+ tokens/sec, depending on model and provider.

---

## 9. Behavioral interview

### The STAR format
**S**ituation → **T**ask → **A**ction (what *you* did, saying "I", not "we") → **R**esult (with numbers if possible) + what you learned.

### Prepare these 8 stories from your projects, studies and open-source work
1. **A hard technical problem you solved** (e.g. RAG retrieval quality was poor, so you built evals and improved recall from X to Y).
2. **A failure or mistake**, and what you learned from it.
3. **A disagreement or conflict** (with a teammate, or with a reviewer on an open-source PR).
4. **Learning something new quickly** (this whole plan is that story).
5. **A time you took ownership** or went beyond what was asked.
6. **A time you had to make a trade-off** (speed vs quality, cost vs accuracy, as in the P6 comparison).
7. **Working with users or feedback** (the capstone's real users).
8. **A time you helped someone or led something.**

### Common questions
"Tell me about yourself" (60–90 seconds: past → present → why this role) · "Why this company?" · "Why AI engineering?" · "Your biggest weakness?" · "Tell me about a project you're proud of" (P3 or the capstone, in depth) · "Where do you see yourself in 3 years?"

### Questions to ask the interviewer
- "What does success look like in this role after 6 months?"
- "How do you evaluate your AI features before shipping them?" (This shows you care about evals.)
- "What's the biggest technical challenge the team is facing right now?"
- "How do code review and on-call work on the team?"
- "What does growth look like for junior engineers here?"

---

## 10. Take-home assignments

- **Read the instructions twice.** Do exactly what's asked first, then add one or two "extras".
- Always include a **README**: how to run it, design decisions, trade-offs, what you'd do with more time.
- Include **tests** and, for AI tasks, **a small eval** with numbers. Most candidates skip this, so including it makes you stand out.
- Clean Git history, typed code, a linter, and Docker if it helps people run it.
- Keep to the suggested time limit. If you go over, say so honestly.

---

## 11. The final 8-week interview sprint (weeks 45–52)

| Week | Coding | System design | AI/LLM | Behavioral | Mocks |
|---|---|---|---|---|---|
| 45 | Re-solve NeetCode 150 problems you marked "hard for me" | 2 classic designs | Review §7 internals | Write all 8 STAR stories | 1 |
| 46 | Timed: 2 medium problems in 45 min, ×3 | 2 GenAI designs | RAG + evals questions | Practise them out loud | 2 |
| 47 | Company-tagged problems (LeetCode Premium optional) | 1 ML design + 1 classic | Agents + MCP + security | "Tell me about yourself" | 2 |
| 48 | Timed mixed practice | Re-do your weakest design | Fine-tuning + serving | Project deep-dive practice | 2 |
| 49–52 | Maintenance: 1 problem per day | 1 per week | Prepare for each company's product | Prepare for each company | 2/week |

**Mock interview sources:** friends and peers (free, and you can take turns), interviewing.io, Exponent, Hello Interview, or recording yourself and watching it back. **Doing 10+ mocks before your first real loop makes a big difference.**

👉 Next: track your skills → [06-skills-checklist.md](06-skills-checklist.md)

---

### Sources for the 2026 interview trends
- [Let's Data Science: 50 AI Engineer Interview Questions for 2026](https://letsdatascience.com/blog/50-llm-and-ai-engineer-interview-questions-for-2026)
- [PracHub: AI Engineer Interview Questions 2026: RAG, Agents, Evals, and Production Systems](https://prachub.com/resources/ai-engineer-interview-questions-2026-rag-agents-evals-and-production-systems)
- [Alexey Grigorev: AI Engineering Field Guide: interview questions](https://github.com/alexeygrigorev/ai-engineering-field-guide/blob/main/interview/questions/questions.md)
- [Tech Interview Handbook](https://www.techinterviewhandbook.org/)
