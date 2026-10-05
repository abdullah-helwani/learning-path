# 01 — Job Market Research (October 2026)

> Goal of this document: figure out **which job to aim for** and **which skills employers actually ask for**, using current data rather than guesses. Every number below has a source at the bottom of the page.

---

## 1. Summary

1. **"AI Engineer" is the fastest-growing job title right now.** It is #1 on LinkedIn's *Jobs on the Rise 2026* list for the US. The skills listed most often for it are **LangChain, RAG (retrieval-augmented generation) and PyTorch**.
2. **The market is split in two.** AI engineering hiring is growing fast. Generalist junior software hiring is weak. The Pragmatic Engineer reports AI engineering openings up about **60%** in a year at top companies, against about **7%** for software engineering.
3. **Software development jobs are coming back, but mostly for people who can show real skill.** Indeed Hiring Lab (July 2026) found US software development postings up about **15%** since early 2025, while total postings fell **7%**. However, **71%** of that growth was in *senior* roles and **37%** came from jobs with "AI" in the title.
4. **Junior candidates who have only done coursework struggle. Juniors with production-grade AI projects, cloud skills, and good engineering habits still get hired.** Recruiters are looking for proof that you can ship working software.
5. **Python, SQL, JavaScript/TypeScript, React, FastAPI, Docker, cloud, and LLM tooling** make up the core stack that keeps showing up across surveys and job ads.

**What this means for you:** you already have AI/ML knowledge, which is the scarce part. What you're missing is **software engineering**: Git, back-end, front-end, testing, deployment, and system design. Employers don't want an AI engineer who can train a model in a notebook. They want one who can **ship an AI feature to real users** and keep it running. The plan in this repository is built to close exactly that gap.

---

## 2. Key data points

### 2.1 Fastest-growing roles

| Source | Finding |
|---|---|
| LinkedIn *Jobs on the Rise 2026* (US) | #1 **AI Engineer**, #2 **AI Consultant/Strategist**, and **Data Annotator** also on the list. AI engineers are concentrated in tech, IT services and consulting; top hubs are San Francisco, New York and Dallas. Most common skills: **LangChain, RAG, PyTorch**. |
| LinkedIn *Skills on the Rise 2026* | Fastest-growing skills: **AI engineering, prompt engineering, model training & fine-tuning**. Specific skills named include **FastAPI, OpenAI API, Google Gemini, LangChain, RAG, vector databases, data annotation, XGBoost**. |
| WEF *Future of Jobs Report 2025* | Fastest-growing jobs to 2030: **big data specialists, fintech engineers, AI & ML specialists, software & application developers, security management specialists**. 86% of employers expect AI to transform their business by 2030. |

### 2.2 Hiring trends

| Source | Finding |
|---|---|
| Indeed Hiring Lab (Jul 2026) | US software development postings **+~15%** since Feb 2025, while all postings fell **7%**. **71%** of the increase in software postings (May 2025 → May 2026) came from **senior** roles, and **37%** came from jobs with **AI in the title**. The occupations most exposed to AI are now seeing the **biggest rebound** in postings. |
| Indeed Hiring Lab (Dec 2025 data) | In software development, IT and R&D, **20%+ of job postings mention AI**. |
| The Pragmatic Engineer (2026) | AI engineering openings at top companies **+60%** year over year, compared with **+7%** for software engineering. Many large companies have 50–100% more AI engineering listings than a year ago. AI engineers get **higher offers**. The market is described as *"amazing for AI and a few specialist roles, and a major struggle for everyone else."* |
| Several 2026 market reports | Entry-level and new-grad hiring is **well below pre-2022 levels**. Candidates with **production AI projects, cloud skills or systems skills** get noticeably more offers than candidates with only coursework. Postings that ask for AI skills pay a premium. |

### 2.3 What developers actually use (Stack Overflow Developer Survey 2025)

| Category | Top results |
|---|---|
| Languages | JavaScript 66% · HTML/CSS 62% · SQL 59% · **Python 58% (+7 points, the biggest jump of any language)** · Bash/Shell 49% |
| Web frameworks | Node.js 49% · **React 45%** · jQuery 23% · **Next.js 21%** · Express 20% · ASP.NET Core 20% · Angular 18% · Vue 18% · **FastAPI 15% (+5 points, one of the biggest movers)** · Spring Boot 15% |
| AI tools | **84%** of developers use or plan to use AI tools, and **47%** use them **daily** |

**Takeaway:** Python + SQL + JavaScript/TypeScript + React/Next.js + FastAPI covers most of what the industry uses. Being productive with **AI coding tools** is now expected.

### 2.4 What AI Engineer job ads ask for

Here is what kept appearing in 2026 job descriptions and skill reports, roughly in order of frequency:

1. **Python** (strong, production quality: async, typing, testing), plus **SQL**
2. **LLM APIs** (OpenAI, Anthropic Claude, Google Gemini): structured outputs, tool/function calling, streaming
3. **RAG**: embeddings, chunking, vector databases (pgvector, Pinecone, Weaviate, Qdrant, Milvus), hybrid search, reranking. One 2026 analysis found RAG in about **65%** of applied LLM job listings.
4. **Agents**: tool calling, multi-step workflows, LangGraph / LlamaIndex / CrewAI / smolagents, **MCP (Model Context Protocol)**
5. **Evals and observability**: golden datasets, LLM-as-judge, regression testing, tracing (Langfuse, OpenTelemetry)
6. **Back-end and APIs**: **FastAPI**, REST, async, PostgreSQL, Redis, queues
7. **Deployment and MLOps/LLMOps**: Docker, CI/CD, cloud (AWS/GCP/Azure), monitoring, cost and latency optimization
8. **Fine-tuning**: LoRA/QLoRA, PEFT, plus model serving (vLLM) and quantization
9. **AI security**: prompt injection, guardrails, PII handling
10. **Product sense and communication**: turning a business problem into an AI feature, then measuring whether it works

Senior postings often ask for "at least one RAG pipeline shipped to production users". **You can't get production experience without a job, but you can come very close with deployed projects that have real users, evals and monitoring.** That's why the projects in this plan are built that way.

---

## 3. Role comparison: which job fits you?

| Role | What you do | Core skills | Demand (2026) | Fit for you |
|---|---|---|---|---|
| **AI Engineer / Applied AI / LLM Engineer** | Build products on top of foundation models: RAG, agents, evals, deployment | Python, LLM APIs, RAG, agents, evals, back-end, cloud | 🔥 Highest growth | ⭐ **Best fit.** Uses your ML background and pays the most. You need SWE skills on top. |
| **ML Engineer** | Train, deploy and monitor ML models in production | Python, PyTorch, MLOps, data pipelines, cloud, serving | High, often wants experience | Very good fit, and it overlaps heavily with AI engineering |
| **Back-end Engineer (Python)** | APIs, databases, distributed services | Python/Go/Java, SQL, APIs, Docker, cloud, system design | Steady, competitive at junior level | Good **fallback**. Every skill transfers to AI engineering. |
| **Full-Stack Engineer** | Front-end + back-end features end to end | TypeScript, React/Next.js, Node or Python, SQL | Steady, very competitive | Good at startups, especially "full-stack AI engineer" roles |
| **Forward-Deployed / Solutions Engineer (AI)** | Build AI solutions with or for customers | AI engineering + communication | Growing at AI companies | Good if you enjoy working with people as well as code |
| **Data Engineer** | Pipelines, warehouses, streaming | SQL, Python, Spark, Airflow, dbt, cloud | High | OK. A different direction from what you asked for. |
| **Data Scientist** | Analysis, experiments, modeling | Stats, Python, SQL, ML | Flat, many applicants | Weaker. Crowded at junior level. |
| **MLOps / AI Platform Engineer** | Infrastructure for training and serving | Kubernetes, cloud, IaC, GPUs, serving | High, usually mid/senior | A good *second* job after 1–2 years |

---

## 4. My recommendation

### 🎯 Primary target: **Full-stack AI Engineer** (Applied AI / LLM Engineer)

That means an engineer who can:

- build a **production back-end** in Python (FastAPI + PostgreSQL + Docker),
- build **AI features** with LLMs (RAG, agents, tool use, MCP, fine-tuning),
- **measure** those features (evals, tracing, cost and latency),
- build a **usable front-end** (TypeScript + React/Next.js),
- **deploy and operate** it in the cloud (AWS, CI/CD, monitoring),
- **explain the trade-offs** in a system design interview.

### Why this target

- It's where demand is growing fastest, according to LinkedIn, Indeed and The Pragmatic Engineer.
- Your AI/ML background already covers the hardest-to-learn part: the intuition for how models behave and fail.
- Each software engineering skill you add makes you more employable as an AI engineer, and it also qualifies you for **back-end** and **ML engineer** roles. That gives you **three doors instead of one**.

### Job titles to search for

`AI Engineer` · `Applied AI Engineer` · `LLM Engineer` · `Generative AI Engineer` · `AI Software Engineer` · `Junior/Associate AI Engineer` · `Machine Learning Engineer (GenAI/LLM)` · `Backend Engineer (Python, AI)` · `Full-Stack Engineer (AI)` · `Forward Deployed Engineer` · `AI Solutions Engineer` · `AI Engineer Intern / Graduate Program`

### How to beat a tough junior market

1. **Proof of work beats certificates.** Deployed projects with real users, evals, tests and a clear README. ([04-projects.md](04-projects.md))
2. **Open-source contributions** to AI tools (LangChain, LlamaIndex, Hugging Face, Langfuse, vLLM docs, and so on). These are public evidence of skill.
3. **Write about what you build** (a blog, LinkedIn posts). Recruiters search for this.
4. **Start applying earlier than you feel ready**: around month 6, not month 12. ([09-job-search-strategy.md](09-job-search-strategy.md))
5. **Target startups and AI-adjacent companies**, not only Big Tech. They hire for skill, not pedigree.
6. **Referrals** convert at a much higher rate than cold applications, so build your network while you learn.
7. **Freelance or contract AI work** (small RAG and chatbot projects) counts as real experience.

---

## 5. Sources

- LinkedIn Jobs on the Rise 2026, as covered by [Dice](https://www.dice.com/career-advice/ai-related-jobs-top-linkedins-fastest-growing-roles-list-for-2026), [HR Leader](https://www.hrleader.com.au/business/27698-ai-engineer-tops-linkedin-s-2026-jobs-on-the-rise-list) and [Forbes](https://www.forbes.com/sites/juliakorn/2026/01/14/future-proof-your-career-with-linkedins-2026-fastest-growing-jobs-list/)
- LinkedIn Skills on the Rise 2026: [LinkedIn News](https://news.linkedin.com/2026/Skills-on-the-rise-2026), [CIO Dive](https://www.ciodive.com/news/linkedin-top-skills-AI-engineering/813595/), [Interview Query](https://www.interviewquery.com/p/linkedin-ai-engineering-fastest-growing-skills-2026)
- Indeed Hiring Lab: [AI and Job Postings: From Destruction to Creation? (Jul 2026)](https://hiringlab.indeed.com/2026/07/08/ai-and-job-postings-from-destruction-to-creation/), [January 2026 Labor Market Update](https://hiringlab.indeed.com/2026/01/22/january-labor-market-update-jobs-mentioning-ai-are-growing-amid-broader-hiring-weakness/)
- The Pragmatic Engineer: [State of the software engineering job market in 2026](https://newsletter.pragmaticengineer.com/p/state-of-the-job-market-2026), [part 2](https://newsletter.pragmaticengineer.com/p/the-job-market-in-2026-part-2), [part 3](https://newsletter.pragmaticengineer.com/p/tech-jobs-market-in-2026-part-3-hiring)
- [Stack Overflow Developer Survey 2025: Technology](https://survey.stackoverflow.co/2025/technology)
- [WEF Future of Jobs Report 2025: fastest growing and declining jobs](https://www.weforum.org/stories/2025/01/future-of-jobs-report-2025-the-fastest-growing-and-declining-jobs/)
- AI Engineer skills in job ads: [TripleTen: AI skills to learn in 2026](https://tripleten.com/blog/posts/ai-skills), [Technovids: AI Engineer Skills 2026](https://technovids.com/ai-engineer-skills)
- Entry-level market: [TechTimes: Entry-Level Tech Jobs 2026](https://www.techtimes.com/articles/317535/20260601/entry-level-tech-jobs-2026-148092-cuts-expose-which-skills-still-get-you-hired.htm), [Final Round AI: Software Engineering Job Market 2026](https://www.finalroundai.com/blog/software-engineering-job-market-2026)
- Middle East / remote AI listings (example job board): [Bayt: AI Engineer jobs in the Middle East](https://www.bayt.com/en/international/jobs/%22ai-engineer%22-jobs/)

> Market data changes quickly. Re-check these sources every few months, and **read 20–30 real job ads for your target role and location** and count which skills appear most often. That's the most accurate research you can do for your own market. A template for this is in [09-job-search-strategy.md](09-job-search-strategy.md#job-ad-analysis).
