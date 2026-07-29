# Hey, I'm Allan D'Souza

**AI Engineer** based in Mumbai — agentic systems, retrieval, and memory.

I build agents that run real workflows: multi-step orchestration with human approval gates,
knowledge and memory layers agents can actually rely on, and the boring-but-essential parts —
evals, budgets, fallbacks — that make them safe to point at a business.

---

## What I Do

- **Agent orchestration** — stateful multi-step workflows, tool/function calling, human-in-the-loop
  approval gates, webhook and schedule triggers, bounded loops with latency budgets and graceful
  degradation
- **Retrieval & memory** — chunking, embeddings, vector search, reranking, knowledge graphs,
  citation verification and anti-hallucination constraints
- **Wiring agents into real systems** — email, chat, project management, observability, via APIs,
  webhooks, and MCP
- **Making it measurable** — eval harnesses, population-level tests, contract-seam guards, token
  budgeting and cost tracking

---

## Tech I Work With

```
Agents      multi-step workflows · tool calling · HITL approval · MCP · evals · model routing
Retrieval   embeddings (Voyage AI · FastEmbed) · pgvector · ChromaDB · reranking · Cognee/Kuzu
Backend     Python/FastAPI · Java 17/Spring Boot · TypeScript/Node · Postgres · SQL Server · Convex
Frontend    React 19 · Next.js 16 · TypeScript · Tailwind · Bun · React Native · Electron
Infra       Vercel · Railway · Cloudflare · Blaxel · Docker · GitHub Actions · Grafana/Prometheus/Loki
```

---

## Featured Projects

### Agentic systems

| Project | What it does | Tech |
|---|---|---|
| [**Distill**](https://github.com/allands365-hub/distill) | AI bug-triage & release operator — multi-step workflow with a human approval gate, wired into Gmail, Slack and Linear. Webhook auto-triage on inbound mail. | Lemma SDK, Python, agent workflows |
| [**MindMeld**](https://github.com/allands365-hub/mindmeld) | Every meeting folds into one queryable knowledge graph — full memory lifecycle: remember, recall across meetings, enrich, forget | Next.js 16, FastAPI, Cognee, Groq Whisper, Kuzu |
| [**KSP Crime Intelligence**](https://github.com/allands365-hub/ksp-crime-intelligence) | Crime intelligence platform over 674k records — geospatial hotspot detection, offender network analysis, forecasting & anomaly detection, plus a bounded NL Ask-AI agent (typed tool registry, schemas derived from signatures, live eval at 8/10 tool selection) running fully on Zoho Catalyst | Next.js, deck.gl, ECharts, FastAPI, scikit-learn, Zoho Catalyst (QuickML LLM) |
| **OSS Warden** | AI-powered GitHub issue triage in ~10s — multi-agent, serverless | CrewAI, MCP, Modal |

### Retrieval & applied ML

| Project | What it does | Tech |
|---|---|---|
| [**MSME Health Card**](https://github.com/allands365-hub/idbi-msme-health-card) · [live](https://idbi-msme-health-card.vercel.app/) | Explainable credit scoring for credit-invisible small businesses — WOE/logistic scorecard + ONNX challenger | Next.js 16, TypeScript, optbinning, XGBoost→ONNX |
| **Jaanch Lite** | Legal document intelligence — domain embeddings + instruction-following reranking + citation verification against 50+ Indian Acts | Python, Voyage AI, ChromaDB, Instructor |
| **Juristudio** | AI Canadian legal research — 28k cases, CREAC memos, 3-tier citation verification | Next.js, Convex, Voyage AI |
| [**Coachsync**](https://www.coachsync.in) | Multi-tenant coaching-institute SaaS with semantic question matching | Next.js, Bun, pgvector |

### Products & tools

| Project | What it does | Tech |
|---|---|---|
| [**NoteSync**](https://github.com/allands365-hub/notesync) | Auto-detect meetings, record, transcribe & summarise — local-first, search across every past meeting | Electron, Groq Whisper/LLaMA, SQLite FTS5 |
| **Bill Karo** | GST-compliant invoicing for Indian MSMEs — WhatsApp reminders, mobile-first | React Native, Fastify, Neon, Drizzle |
| [**BuildAi Arena**](https://25-hackathon.vercel.app) | Hackathon platform connecting sponsors and builders | Next.js, Supabase, Groq |
| [**AI-Newz**](https://github.com/allands365-hub/AI-Newz) | AI newsletter generator — RSS to summarised email | React, FastAPI, Groq |
| [**Agent Marketplace**](https://github.com/allands365-hub/Agent_marketplace) | Discover and connect with AI agents | Next.js, Supabase |
| [**PickMyTree**](https://github.com/allands365-hub/whiterock_estate) | Adopt a mango tree, follow it through the season — Razorpay checkout, webhook-driven fulfilment, farm-admin ops | Next.js, Convex, Razorpay |

---

## Experience

**Edmik / Indivue (Kademin)** — AI Engineer · *Feb 2026 – Present*
Own the AI layer of a production education platform (Spring Boot / SQL Server backend, four React
frontends). AI feature-gating and permission system, token budgeting with cost-basis tracking,
multi-provider model routing (Gemini 3 Flash → Kimi k2.5 fallback), and an LLM evaluation pipeline
that grades handwritten student answers via OCR. Also deployed the Grafana MCP server on Blaxel so
production metrics and logs are queryable over MCP. ~2,600 commits across 8 repos.

**Allan Travels** — Co-founder / Operator · *2017 – Present*
Car rental business. Built and still run the booking and billing automation it operates on.

**Apar Games** — Game Designer · *2012 – 2017*
Shipped 10+ titles across Steam, iOS, Android and web — Scribbled Arena, Twilight Zone, Traffic
Controller. Designed mechanics, feedback loops and in-game economies, iterating on live analytics.

---

## How I Build Agents

Getting an agent to work once is the easy part. Making it behave predictably on the thousandth run,
on input nobody anticipated, against a system where being wrong costs something — that's the job.
Three things carry most of the weight:

**Guardrails are part of the design, not a setting added later.** Every agent I ship gets an explicit
blast radius decided before the first prompt is written. Distill routes low-confidence *and* P0 items
to human approval. The Edmik grader is advisory-only — accurate enough to be useful, not accurate
enough to be trusted alone. The KSP agent is capped at two rounds and a 15s budget, and degrades
gracefully instead of retrying into the void. The Grafana MCP server runs read-only, write tools
disabled, on a Viewer-scoped token.

**Knowing when *not* to build an agent.** Distill's priority rubric and duplicate detection look like
obvious LLM work and are deliberately plain Python, unit-tested — cheaper, repeatable, debuggable.
A rubric that drifts between runs is worse than no rubric. The LLM does only what needs judgement.

**Monitoring is the deliverable, not the follow-up.** If an agent is reliable, there's an eval that
says so with a number — KSP ships with a scripted live eval at 8/10 tool selection, 10/10 within
budget. Tool schemas are derived from function signatures so they can't drift from the code, and a
population test loops the full registry so a new tool can't skip coverage. LLM spend is tracked per
feature and per tenant rather than discovered on an invoice. Production metrics and logs are
queryable over MCP.

---

## Let's Connect

- **Portfolio:** [allan-portfolio.framer.website](https://allan-portfolio.framer.website/)
- **Email:** allands365@gmail.com
- **Location:** Mumbai, India — comfortable working US-overlapping hours

---

*Currently open to AI Engineer roles — agentic systems, retrieval, and applied LLM infrastructure.*
