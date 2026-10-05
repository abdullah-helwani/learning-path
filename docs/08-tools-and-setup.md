# 08 — Tools and Development Environment

> Install these during **Week 1**. You don't need everything on day one: install each tool when its phase begins. The ⏱ column shows when you'll need it.

---

## 1. Operating system

| You have | Do this |
|---|---|
| **Windows** | Install **WSL2 with Ubuntu** ([Microsoft guide](https://learn.microsoft.com/en-us/windows/wsl/install)) and do all development inside WSL. Most servers and job environments run Linux. |
| **macOS** | Install [Homebrew](https://brew.sh/) and use the built-in Terminal or iTerm2. |
| **Linux** | You're ready. Ubuntu LTS is the easiest choice. |

**Hardware:** any laptop with 16 GB RAM is enough. You **don't need a GPU**: use Colab, Kaggle or rented GPUs for fine-tuning, and APIs or small local models (Ollama) for everything else.

---

## 2. Tools by phase

| ⏱ Phase | Tool | Purpose | Install / link |
|---|---|---|---|
| P0 | **Git** | Version control | `sudo apt install git` / `brew install git` |
| P0 | **GitHub account** | Remote repos, PRs, CI, portfolio | [github.com](https://github.com/). Apply for the free [GitHub Student Developer Pack](https://education.github.com/pack) if you still have a student email. |
| P0 | **VS Code** | Editor | [code.visualstudio.com](https://code.visualstudio.com/) + extensions below |
| P0 | Terminal tools | Productivity | `zsh` + [Oh My Zsh](https://ohmyz.sh/) (optional), `tmux`, `fzf`, `ripgrep`, `bat`, `jq`, `htop` |
| P1 | **uv** | Python versions, virtual envs, dependencies (replaces pip/venv/pyenv/poetry) | [docs.astral.sh/uv](https://docs.astral.sh/uv/) |
| P1 | **ruff** | Linter + formatter | `uv add --dev ruff` |
| P1 | **mypy** or **pyright** | Type checking | `uv add --dev mypy` |
| P1 | **pytest** | Testing | `uv add --dev pytest pytest-cov` |
| P1 | **pre-commit** | Run checks automatically before each commit | [pre-commit.com](https://pre-commit.com/) |
| P1 | **SQLite** + **DB Browser for SQLite** | Learning SQL | [sqlitebrowser.org](https://sqlitebrowser.org/) |
| P1 | **HTTPie** or **Bruno** | Calling APIs (Bruno is an open-source alternative to Postman) | [httpie.io](https://httpie.io/) · [usebruno.com](https://www.usebruno.com/) |
| P2 | **Docker Desktop** (or Docker Engine on Linux) | Containers | [docs.docker.com/get-docker](https://docs.docker.com/get-docker/) |
| P2 | **PostgreSQL** (run it in Docker) + **DBeaver** or **pgAdmin** | Database + GUI | `docker run -e POSTGRES_PASSWORD=dev -p 5432:5432 postgres:17` · [dbeaver.io](https://dbeaver.io/) |
| P2 | **Redis** (in Docker) | Cache and queues | `docker run -p 6379:6379 redis` |
| P2 | **Render** / **Railway** / **Fly.io** account | Deploying back-ends | Free or cheap tiers |
| P3 | **LLM API keys**: OpenAI, Anthropic, Google AI Studio | Building AI apps | ⚠️ **Set monthly spending limits.** Use cheaper models for development. |
| P3 | **Ollama** | Run open LLMs locally for free | [ollama.com](https://ollama.com/) |
| P3 | **Langfuse** (cloud free tier or self-hosted) | LLM tracing and evals | [langfuse.com](https://langfuse.com/) |
| P3 | **Claude Code** / **Cursor** / **GitHub Copilot** | AI coding assistants | Use one seriously from Phase 3 onward |
| P3 | **Jupyter** (inside VS Code) | Experiments only. Real code lives in `.py` modules. | VS Code Jupyter extension |
| P4 | **Node.js LTS** via **nvm** or **fnm** + **pnpm** | JavaScript/TypeScript tooling | [nvm](https://github.com/nvm-sh/nvm) · [pnpm.io](https://pnpm.io/) |
| P4 | **Vercel** account | Deploying Next.js | [vercel.com](https://vercel.com/) |
| P5 | **AWS account** + **AWS CLI** | Cloud | ⚠️ **Turn on MFA, create budgets and billing alerts BEFORE doing anything else.** Never use the root account day to day. |
| P5 | **Terraform** | Infrastructure as Code | [developer.hashicorp.com/terraform/install](https://developer.hashicorp.com/terraform/install) |
| P5 | **kubectl** + **kind** | Local Kubernetes | [kind.sigs.k8s.io](https://kind.sigs.k8s.io/) |
| P5 | **Google Colab** / **Kaggle** / **RunPod** / **Modal** | GPUs for fine-tuning | Free tiers first |
| P5 | **MLflow** or **Weights & Biases** | Experiment tracking | Free |
| P6 | **k6** or **Locust** | Load testing | [k6.io](https://k6.io/) · [locust.io](https://locust.io/) |
| P6 | **Excalidraw** or **draw.io** | System design diagrams | [excalidraw.com](https://excalidraw.com/) · [draw.io](https://www.drawio.com/) |

---

## 3. VS Code extensions

- **Python**, **Pylance**, **Ruff** (Microsoft / Astral)
- **Jupyter**
- **Docker** / **Dev Containers**
- **GitLens** (see who changed what) and **Git Graph**
- **ESLint**, **Prettier**, **Tailwind CSS IntelliSense** (from Phase 4)
- **Markdown All in One**, **markdownlint**
- **Even Better TOML**, **YAML**
- **Error Lens** (shows errors inline)
- **REST Client** (send HTTP requests from `.http` files)
- **HashiCorp Terraform** (from Phase 5)
- An AI assistant: **Claude Code**, **GitHub Copilot**, or use **Cursor** as your editor

---

## 4. A standard Python project setup (copy this for every project)

```bash
uv init my-project --package     # creates a src/ layout with pyproject.toml
cd my-project
uv add httpx pydantic            # runtime dependencies
uv add --dev pytest pytest-cov ruff mypy pre-commit
uv run pytest                    # run tests inside the project's environment
uv run ruff check . && uv run ruff format .
uv run mypy src
```

Add a basic CI workflow at `.github/workflows/ci.yml`:

```yaml
name: CI
on: [push, pull_request]
jobs:
  check:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: astral-sh/setup-uv@v6
      - run: uv sync --all-extras --dev
      - run: uv run ruff check .
      - run: uv run ruff format --check .
      - run: uv run mypy src
      - run: uv run pytest --cov
```

---

## 5. Organizing your learning

- **This repository:** weekly logs in [`progress/`](../progress/) and the checklist in [06-skills-checklist.md](06-skills-checklist.md).
- **GitHub Projects board:** create columns *Backlog → This week → In progress → Done* and add one card per roadmap item.
- **Notes:** [Obsidian](https://obsidian.md/) or Notion. Write notes in your own words, especially DSA patterns and system design write-ups.
- **Spaced repetition** (optional): [Anki](https://apps.ankiweb.net/) for interview facts (Big-O, HTTP codes, latency numbers, LLM concepts).
- **Calendar:** block fixed study hours every day, as if it were a job.
