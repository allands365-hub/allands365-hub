# Hey, I'm Allan D'Souza

**AI-native Full-stack Engineer & Engineering Lead** based in Mumbai — agents, retrieval, and LLM infrastructure.

I build production LLM systems where the model loop is the product, and I lead the team that ships
them. Agents that run real workflows with human approval gates, retrieval that respects permissions,
and the boring-but-essential parts — evals, budgets, fallbacks, contracts that can't drift — that
make them safe to point at a business.

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
Retrieval   embeddings (Gemini · Voyage AI · FastEmbed) · pgvector · hybrid search + RRF · reranking · Cognee/Kuzu
Backend     Python/FastAPI · Java/Spring Boot · TypeScript/Node · Postgres · SQL Server · Redis · Convex
Frontend    React 19 · Next.js 16 · TypeScript · Tailwind · Motion · React Native · Kotlin Multiplatform
Infra       Vercel · Netlify · Cloudflare · Coolify · Blaxel · Docker · GitHub Actions · Grafana/Prometheus/Loki
Quality     Playwright · axe · Testcontainers · pytest · Vitest · contract & population-level tests
Delivery    scrum · sprint planning · architecture/design reviews · PRD/TRD/ADR writing
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
| [**Achyut Charters**](https://achyutcharters.com) · live | Private jet & helicopter charter site for a client — English, Hindi and Kannada with Gemini translation, staff admin for trips and empty-leg bookings. Playwright across 8 browser/viewport projects, axe on every route, Lighthouse 98–100 | Next.js 16, Convex, Tailwind 4, Motion |
| **Laser Mosquito Defender** | Edge-vision home device on a Raspberry Pi 5 — fail-closed fire-decision gates, tested arming state machine, hardware interlock, YOLOv8 person/pet detection. ~1,190 tests; runs in shadow mode | Python, OpenCV, ONNX Runtime, ZeroMQ, C firmware |
| [**NoteSync**](https://github.com/allands365-hub/notesync) | Auto-detect meetings, record, transcribe & summarise — local-first, search across every past meeting | Electron, Groq Whisper/LLaMA, SQLite FTS5 |
| **Bill Karo** | GST-compliant invoicing for Indian MSMEs — WhatsApp reminders, mobile-first | React Native, Fastify, Neon, Drizzle |
| [**BuildAi Arena**](https://25-hackathon.vercel.app) | Hackathon platform connecting sponsors and builders | Next.js, Supabase, Groq |
| [**AI-Newz**](https://github.com/allands365-hub/AI-Newz) | AI newsletter generator — RSS to summarised email | React, FastAPI, Groq |
| [**Agent Marketplace**](https://github.com/allands365-hub/Agent_marketplace) | Discover and connect with AI agents | Next.js, Supabase |
| [**PickMyTree**](https://github.com/allands365-hub/whiterock_estate) | Adopt a mango tree, follow it through the season — Razorpay checkout, webhook-driven fulfilment, farm-admin ops | Next.js, Convex, Razorpay |

---

## Experience

**Edmik / Indivue (Kademin)** — AI Engineer → Engineering Lead · *Feb 2026 – Present*
Lead a team of 5 engineers since April 2026 — scrum master, sprint planning, architecture and design —
and own the AI layer of a production education platform (Spring Boot backend; React, Next.js,
Android and Kotlin Multiplatform apps). ~7,700 commits across 15+ repos.

- **Edmik Brain** — an AI onboarding agent that turns a school's spreadsheets, timetable images and
  PDFs into a reviewable draft, committed through a ledger that can halt, resume and adopt; and
  **Ask Kademin**, a permission-aware RAG assistant (pgvector + Postgres full-text, reciprocal-rank
  fusion, access filtered in SQL) built into four apps in English and Hindi, rolling out to real users.
- **ModelChain** — the single LLM path for all Brain code: JSON-schema output, Gemini → GPT-5.6 Luna →
  Kimi fallback, retries, deadlines, and a test that fails if any configured model has no price.
- **LLM cost control** — per-institute token budgets with holds reserved before every call and
  exactly-once refunds; AI feature-gating where role is the gate.
- **CA Practice OS** (pre-production) — multi-tenant SaaS for CA firms: two Gemini models read each
  document independently with disagreements sent to human review, a model-selection eval harness that
  tracks hallucinated values, and forced row-level security enforced by a catalog-reading test.
- **Reliability** — led the SQL Server → PostgreSQL migration, proved by a result-diff harness
  against the old engine; LLM grading of handwritten answers; Grafana MCP server on Blaxel so prod
  metrics and logs are queryable over MCP.

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

*Open to senior AI-native full-stack and AI engineering roles — agents, retrieval, and LLM infrastructure.*
