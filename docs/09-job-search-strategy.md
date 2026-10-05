# 09 — Job Search Strategy

> Skills alone don't get you hired. You also need to be **visible**, **credible**, and **in front of the right people**. Start this work at **month 6**, not month 12.

---

## 1. Timeline

| When | What |
|---|---|
| Month 1 | GitHub profile README. LinkedIn profile updated with your target ("Aspiring AI Engineer, building in public"). |
| Months 1–12 | Post what you learn weekly on LinkedIn and/or a blog. Short posts are fine. |
| Month 4 | First CV draft. Start following companies you like and engineers who work there. |
| **Month 6 (week 24)** | **Start applying, 5/week**: internships, graduate programs, junior AI/back-end roles, freelance gigs. Start contributing to open source. |
| Month 7–8 | Networking: 2–3 conversations per week with engineers (coffee chats, communities, meetups). |
| **Month 9–10 (week 38)** | **Apply at full volume: 10–15 targeted applications per week.** Mock interviews begin. |
| Month 11–12 | Interview loops, take-homes, offers, negotiation. |

> Why start at month 6? Because hiring processes take 1–3 months, rejections early on teach you what's missing, and interviews are a skill that needs practice. The worst case is that you get practice. The best case is that you get hired early.

---

## 2. Your CV (résumé)

**Format:** 1 page, a simple single-column layout (ATS-friendly: no tables, icons or photos for most international jobs), and PDF.

**Structure:**
1. **Header:** name, city/country (+ "open to remote/relocation" if true), email, LinkedIn, GitHub, portfolio/blog.
2. **Summary** (2 lines, optional): *"AI Engineer with a background in ML. I build and deploy production LLM applications (RAG, agents, evals) with Python, FastAPI, Next.js and AWS."*
3. **Skills** (grouped): Languages · AI/LLM · Back-end · Front-end · Cloud/DevOps · Databases.
4. **Projects** (your main section until you have work experience): 3–4 projects, **each with a link and impact numbers**.
5. **Experience:** internships, freelance work, teaching assistant roles, research. Anything real.
6. **Open source:** merged PRs, with links.
7. **Education:** degree, university, year, and relevant coursework or a thesis if it's AI-related.
8. **Certifications** (optional): at most 1–2 relevant ones.

**How to write a project bullet:** *action verb + what you built + technology + measurable result*

✅ *"Built a RAG system over 2,000 university documents (FastAPI, pgvector, Claude). Added hybrid search + reranking, improving retrieval recall@5 from 0.71 to 0.89 on a 150-question eval set. p95 latency 1.6 s, $0.40 per 1k queries."*

✅ *"Fine-tuned Qwen 7B with QLoRA for issue classification: 91% F1 vs 88% for a few-shot GPT model at 1/12 the cost per request. Served with vLLM on AWS (Terraform, GitHub Actions)."*

❌ *"Worked on a chatbot using AI."*

**Tailor the CV for each application:** reorder skills and projects to match the job ad's keywords. Spend 10 minutes per application, not 1.

---

## 3. GitHub and portfolio

- **Pin your best 6 repos:** P3 (RAG), P5 (full-stack), P6 (fine-tune), P4 (agent/MCP), P8 (capstone), P7 (system design).
- **Every pinned repo has:** a README following the [template](04-projects.md#readme-template-for-every-project), a live link or demo GIF, an architecture diagram, **eval results**, and a green CI badge.
- **Profile README:** who you are, what you're building, your tech stack, links to your blog posts.
- **Portfolio site** (optional but nice): a simple Next.js site on Vercel with your projects, blog and CV. That's a mini-project in itself.
- **Contribution graph:** consistent commits show discipline. Don't fake it, because experienced reviewers can tell.

---

## 4. LinkedIn

- **Headline:** `AI Engineer | LLMs, RAG, Agents | Python · FastAPI · Next.js · AWS`. Not "Graduate looking for opportunities".
- **About:** 3–5 lines covering your story, what you build, and what you're looking for.
- **Featured section:** your best project, demo video and blog post.
- **Turn on "Open to Work"** (visible to recruiters only, if you prefer).
- **Post weekly:** "This week I learned X / built Y / here's a mistake I made and how I fixed it". Building in public is how many juniors get noticed by recruiters and founders.
- **Connect** with engineers at companies you want to join, with a short personal note. Comment thoughtfully on their posts.

---

## 5. Where to find jobs

| Type | Where |
|---|---|
| General | [LinkedIn Jobs](https://www.linkedin.com/jobs/), Indeed, Glassdoor, company career pages |
| Startups | [Wellfound](https://wellfound.com/), [Y Combinator: Work at a Startup](https://www.workatastartup.com/), [Hacker News "Who is hiring?"](https://news.ycombinator.com/submitted?id=whoishiring) (posted monthly) |
| Remote | [We Work Remotely](https://weworkremotely.com/), [Remote OK](https://remoteok.com/), [Welcome to the Jungle](https://www.welcometothejungle.com/), remote filters on LinkedIn |
| Middle East / Gulf | [Bayt](https://www.bayt.com/), LinkedIn (filter by UAE / Saudi Arabia / Qatar), and the career pages of regional tech and AI companies and government AI programs |
| Europe | LinkedIn, Welcome to the Jungle, country-specific boards, EU Blue Card friendly companies |
| AI-specific | AI company career pages (model labs, AI dev-tools companies, AI startups). The Latent Space and AI Engineer communities often share job boards. |
| Freelance | Upwork, Contra, Toptal (harder to get into), local businesses (direct outreach) |

**Wherever you are:** remote AI roles are competitive but open globally. **Local companies and startups in your own region** are often easier first jobs and a great way to get your first 1–2 years of experience.

---

## 6. How to apply (quality over quantity)

1. **Read the job ad carefully.** If you match **~60%** of the requirements, apply. Job ads are wish lists.
2. **Tailor your CV** (10 minutes): mirror their keywords.
3. **Look for a referral first:** find an engineer at the company on LinkedIn, message them briefly, and mention a specific project of yours that's relevant to their product. Referrals get interviews at a much higher rate than cold applications.
4. **Optional, and very effective at startups:** send a short message to the hiring manager or founder with a link to a **small demo built for their product** (for example, a 1-day RAG prototype over their public docs).
5. **Track everything** in a spreadsheet: company, role, date, source, referral (yes/no), status, next step, notes.

### Funnel expectations (typical for juniors)
`100 applications → ~10–15 first calls → ~4–6 technical rounds → ~1–2 offers`

The numbers improve a lot with referrals, tailored applications, and strong projects. **If you get no calls after 50 applications, the problem is your CV or targeting. If you get calls but no offers, the problem is interviewing.** Diagnose which one it is and fix it.

---

## 7. Networking (it's not as scary as it sounds)

- **Communities:** DataTalks.Club Slack, Hugging Face Discord, the MLOps Community, local meetups and hackathons, university alumni groups.
- **Hackathons** (online and local, especially AI hackathons): you build something fast, meet engineers, and sometimes get hired directly.
- **Coffee chats:** *"Hi [name], I'm an ML graduate building production AI projects (e.g. [link]). I saw you work on [X] at [company]. Could I ask you 2–3 questions about how your team evaluates LLM features? 15 minutes, whenever suits you."* Most people say yes if the message is short, specific and respectful.
- **Give before you ask:** share useful posts, help people in Discords, and fix docs in open-source projects.

---

## 8. Alternative routes to your first job

- **Internships and graduate programs**, even unpaid or short ones, if you can afford it. They turn into full-time offers.
- **Freelance AI projects:** small businesses need chatbots, document automation and RAG. One paid project counts as real experience on a CV.
- **Teaching assistant / mentor** at a bootcamp or university: this builds communication skills and your network.
- **Open-source → job:** active contributors to AI open-source projects regularly get hired by the companies behind them.
- **Adjacent role first:** back-end engineer, data engineer, ML ops, solutions engineer or technical support at an AI company. Then move internally into AI engineering after 6–12 months.

---

## 9. Offers and negotiation

- Always ask for the offer **in writing**, and **never accept on the spot**: "Thank you! Could I have a few days to review it?"
- Research salary ranges on levels.fyi, Glassdoor and local sources for your city or country.
- Negotiate politely, even as a junior. The worst answer is "no". Mention competing offers if you have them.
- Consider the whole package: learning opportunities, mentorship, the tech stack (is it AI work?), remote flexibility, visa support, equity, and the title.
- **Your first job matters most for what you learn.** A strong team that ships real AI products beats a slightly higher salary.

---

## Job-ad analysis

Before Phase 3 (and again in Phase 6), collect **25 real job ads** for your target role **in your target market** (your country, a region you'd move to, or remote). Count how often each skill appears:

| Skill | Count (out of 25) | Do I have it? | Which phase / project covers it? |
|---|---|---|---|
| Python | | | P1–P8 |
| RAG | | | P3 |
| LangChain/LangGraph | | | P3, P4 |
| FastAPI | | | P2 |
| AWS / GCP / Azure | | | P5 |
| Docker / Kubernetes | | | P2, P5 |
| React / Next.js | | | P4 |
| Fine-tuning | | | P6 |
| Evals | | | P3 |
| … | | | |

Save it as `progress/job-ad-analysis.md` and **adjust the plan** if your local market wants something different (for example, Azure instead of AWS, or Java instead of Node). The plan should follow your market.
