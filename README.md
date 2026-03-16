<div align="center">

```
██████╗  █████╗ ██╗  ██╗███████╗███████╗██╗  ██╗
██╔══██╗██╔══██╗██║ ██╔╝██╔════╝██╔════╝██║  ██║
██████╔╝███████║█████╔╝ █████╗  ███████╗███████║
██╔══██╗██╔══██║██╔═██╗ ██╔══╝  ╚════██║██╔══██║
██║  ██║██║  ██║██║  ██╗███████╗███████║██║  ██║
╚═╝  ╚═╝╚═╝  ╚═╝╚═╝  ╚═╝╚══════╝╚══════╝╚═╝  ╚═╝
          M A H A P A T R O
```

</div>

```bash
$ whoami
  Rakesh Mahapatro — Backend Engineer & Full-Stack Developer

$ cat specialization.txt
  → REST API design & server architecture
  → Real-time systems  (Socket.IO · Server-Sent Events)
  → AI agent pipelines (LangGraph · RAG · pgvector)
  → Database modeling  (MongoDB · PostgreSQL · MySQL)

$ echo $STATUS
  building things that scale ▮
```

[![LinkedIn](https://img.shields.io/badge/-LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/rakesh-mahapatro-452b67365)
[![Email](https://img.shields.io/badge/-Email-EA4335?style=flat-square&logo=gmail&logoColor=white)](mailto:rakeshmahapatro85@gmail.com)
[![GitHub](https://img.shields.io/badge/-GitHub-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/rakesh-mahapatro-456)

---

## `$ cat about.txt`

I build **backend systems** — the kind where data flows through well-defined layers, failures are handled gracefully, and the API contract is something you can actually trust.

My work lives in Express/FastAPI route handlers, Mongoose schemas, JWT middleware, Socket.IO event loops, and LangGraph agent nodes. I reach for React and Next.js to surface that backend functionality in the browser — but every design decision starts from the server.

Current focus: **AI agent orchestration**, **real-time event-driven architecture**, and writing APIs that are a pleasure to consume.

---

## `$ cat stack.txt`

```
┌─────────────────────────────────────────────────────────────────┐
│                                                                 │
│  BACKEND                                                        │
│  Node.js · Express.js · FastAPI · Python · REST API design      │
│  JWT · OAuth 2.0 PKCE · bcrypt · Joi · Passport.js             │
│  Middleware chains · CORS · Route guards · Error handling       │
│                                                                 │
│  DATABASES                                                      │
│  MongoDB + Mongoose   →  document modeling, aggregation pipes   │
│  PostgreSQL (Supabase)→  relational schemas, pgvector search    │
│  MySQL                →  structured data, joins                 │
│  Vector Store         →  embedding ingestion, semantic retrieval│
│                                                                 │
│  REAL-TIME & STREAMING                                          │
│  Socket.IO  →  WebSocket rooms, presence, event broadcasting    │
│  SSE        →  server-sent events, live streaming pipelines     │
│                                                                 │
│  AI / AGENTS                                                    │
│  LangGraph  →  multi-agent DAG orchestration                    │
│  RAG        →  PDF ingestion, chunking, pgvector retrieval      │
│  Groq API   →  Llama 3.3 70B inference                         │
│                                                                 │
│  FRONTEND                                                       │
│  React · Next.js · Redux Toolkit · Tailwind CSS · shadcn/ui     │
│                                                                 │
│  DEPLOYMENT                                                     │
│  Vercel · Render · MongoDB Atlas · Supabase · Cloudinary        │
│  Git · GitHub · Postman                                         │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

---

## `$ ls -la ~/projects/`

---

### ⚡ AgentIQ — AI Agentic Workforce for Sales Automation

> `FastAPI` `LangGraph` `Groq (Llama 3.3 70B)` `Supabase/pgvector` `Salesforce OAuth 2.0 PKCE` `FPDF2` `SSE` `Next.js 16`
>
> 🏆 Built for **NeuraX 2.0 — National Level Hackathon**

An end-to-end hackathon demo that automates the entire sales proposal lifecycle using a **LangGraph ReAct agent** wired into live Salesforce CRM data and a private RAG Knowledge Base.

**System Architecture:**
```
  Salesforce CRM ──OAuth 2.0 PKCE──► FastAPI Backend
       (live leads)                        │
                                     LangGraph ReAct Loop
  Supabase Postgres  ◄─match_documents─►  ┌──────────────────┐
  + pgvector (KB)          RPC            │  CRM Tool        │ ← fetch leads from Salesforce
                                          │  RAG Tool        │ ← semantic KB search
  Groq / Llama 3.3 70B ◄─────────────────│  Proposal Tool   │ ← generate + export PDF
                                          └──────────────────┘
                                                 │ SSE (agent step events only)
  Next.js 16 Frontend ◄────live logs────────────┘
                       ◄────PDF via POST /api/agent/export-pdf (separate fetch)
```

**What's technically interesting:**
- ReAct loop (Reason → Act → Observe) — agent decides tool order based on context at inference time
- Private RAG pipeline: PDF/DOC ingestion → chunking → `all-MiniLM-L6-v2` embeddings → Supabase Postgres + pgvector, queried via `match_documents` RPC
- Live Salesforce CRM sync via OAuth 2.0 PKCE — real lead context flowing into agent at inference time
- PDF proposal generation via FPDF2 — exported through `POST /api/agent/export-pdf`; SSE streams agent step events only, PDF fetched separately
- Live agent observability via SSE — every ReAct step streamed to browser (Fetching CRM → Searching KB → Drafting PDF → Final Review)
- Batch CSV pipeline for mass proposal generation across hundreds of leads simultaneously

[![GitHub](https://img.shields.io/badge/GitHub-AgentIQ-181717?style=flat-square&logo=github)](https://github.com/rakesh-mahapatro-456/agentiq)

---

### 🔴 Codexa — Real-time Collaborative DSA Platform

> `Node.js` `Express.js 5` `MongoDB` `Socket.IO` `node-cron` `Cloudinary` `Next.js 15` `Redux` `Tailwind CSS`
>
> [Live Demo →](https://codexa-tau.vercel.app)

A gamified DSA practice platform built around a **WebSocket-heavy backend** and an **automated cron job system**. The real-time layer is the core product — XP, streaks, and daily targets all run server-side.

**Backend highlights:**
```
  Client A ──────►                    ┌─────────────────────────┐
  Client B ──────► Socket.IO Server   │  Room Management        │
  Client C ──────►   (event loop) ───►│  Presence tracking      │
                                      │  Message broadcasting    │
                                      │  File share via WS       │
                                      └─────────────────────────┘
                                                  │
                                      ┌─────────────────────────┐
                                      │  XP & Progression Engine│
                                      │  Streak logic           │
                                      │  Badge / Leaderboard    │
                                      │  (schema only, not impl)│
                                      └─────────────────────────┘
                                                  │
                                      ┌─────────────────────────┐
                                      │  Cron Jobs (IST)        │
                                      │  dailyTarget   → 00:00  │
                                      │  dailyChallenge→ 00:00  │
                                      └─────────────────────────┘
```
- Socket.IO room architecture with presence tracking and event broadcasting
- Server-side XP engine — streak calculation, level thresholds; Badge and Leaderboard models exist in schema but are not yet implemented
- Cron jobs via `node-cron` — auto-assign daily targets and generate 5-problem daily challenges at midnight IST
- Problem status system: `-1` backlog → `0` today (cron-assigned) → `1` solved → `2` future
- Cloudinary upload pipeline — file/image ingestion with metadata persisted to MongoDB
- JWT auth (custom) + full CRUD REST API for problems, users, progress, rooms

[![GitHub](https://img.shields.io/badge/GitHub-Codexa-181717?style=flat-square&logo=github)](https://github.com/rakesh-mahapatro-456/codexa)

---

### 🟡 Flow CRM — Lead Management System

> `Node.js` `Express.js` `MongoDB` `JWT` `bcrypt` `Joi` `React` `Redux` `AG Grid` `Tailwind CSS`
>
> [Live Demo →](https://flow-crm-theta.vercel.app)

A full-stack lead management system with JWT auth, server-side enum/string filtering, pagination, and a rich Lead schema covering the full CRM lifecycle.

**Backend highlights:**
```
  Frontend (React + AG Grid)
         │
         ▼
  Express REST API
  ├── /api/user    →  auth (signup, login, logout, me)
  └── /api/leads   →  CRUD + filtering + pagination
         │
         ▼
  Auth Middleware  →  JWT verify on every /api/leads route
         │
         ▼
  MongoDB (Mongoose)
  ├── User  →  name, username, email, passwordHash
  └── Lead  →  source, status, score, lead_value,
               is_qualified, last_activity_at, timestamps
```
- Lead schema covers full CRM lifecycle — source, status (new / contacted / qualified / lost / won), score, value, activity tracking
- Server-side filtering on enum fields (`status`, `source`) and string fields; paginated responses `{ data, page, total, hasMore }`
- JWT stored in httpOnly cookies — validated on every protected route; bcrypt password hashing; Joi validation on write routes
- AG Grid on the frontend — sortable, filterable data tables with real-time UI updates after every CRUD operation
- Protected route middleware with proper 401/403 error handling

[![GitHub](https://img.shields.io/badge/GitHub-FlowCRM-181717?style=flat-square&logo=github)](https://github.com/rakesh-mahapatro-456/Flow-Crm)

---

### 🟠 Catalogo — E-Commerce Platform

> `Node.js` `Express.js` `MongoDB` `JWT` `bcrypt` `React` `Redux` `Vite` `Tailwind CSS`
>
> [Live Demo →](https://catalogo-seven-kappa.vercel.app) · [Demo Video →](https://youtu.be/qt7saA_NRGI)

Full-stack e-commerce system with **Role-Based Access Control**, a cart engine, and a checkout pipeline.

**Backend highlights:**
```
  Request → Auth Middleware (JWT Bearer) → Controller Role Check
                                                  │
                                     ┌────────────┴────────────┐
                                   ADMIN                     USER
                                POST /products            GET /products
                                PATCH /products/:id       GET /cart
                                DELETE /products/:id      POST /cart
                                                          POST /cart/checkout
                                Unauthorized  →  403 Access Denied
```
- RBAC enforced at controller level — role checked before any business logic executes
- Cart engine maintains server-side state; checkout generates full order summary/receipt
- Input validated with Joi on every write route; passwords hashed with bcrypt

[![GitHub](https://img.shields.io/badge/GitHub-Catalogo-181717?style=flat-square&logo=github)](https://github.com/rakesh-mahapatro-456/Catalogo)

---

### 🟢 Wanderlust — Travel Listings Platform

> `Node.js` `Express.js` `MongoDB` `Passport.js` `Cloudinary` `LocationIQ` `MapLibre GL` `MapTiler` `EJS` `Bootstrap`
>
> [Live Demo →](https://wander-lust-90sw.onrender.com/listings)

MVC-architecture travel listings app with geospatial data, image hosting, and a review system — a clean reference for server-rendered patterns.

**Backend highlights:**
```
  POST /listings  →  Joi validation → Cloudinary upload → LocationIQ geocode
                                              │
                              ┌───────────────┴───────────────┐
                        image { url, filename }          GeoJSON coords
                        stored in MongoDB                stored in MongoDB
                              │                                │
                        served via CDN               MapLibre GL + MapTiler
                                                      renders map on page
```
- LocationIQ geocoding API → GeoJSON coordinates stored in MongoDB and rendered via MapLibre GL + MapTiler tiles
- Cloudinary image upload pipeline (`multer-storage-cloudinary`) — `{ url, filename }` stored in MongoDB
- Passport-Local-Mongoose session auth with httpOnly cookie handling
- Cascading deletes — orphaned reviews auto-removed when parent listing is deleted (Mongoose middleware)

[![GitHub](https://img.shields.io/badge/GitHub-Wanderlust-181717?style=flat-square&logo=github)](https://github.com/rakesh-mahapatro-456/wander-Lust)

---

### 🔵 ReadQuest — Book Discovery App

> `Node.js` `Express` `React` `Redux` `Vite` `Open Library API` `Tailwind CSS` `shadcn/ui`
>
> [Live Demo →](https://read-quest.vercel.app)

Book discovery app with an **Express proxy backend** that handles CORS and forwards requests to the Open Library API. Search results are cached in Redux to avoid redundant API calls.

**Highlights:**
```
  Frontend (React + Vite)
         │
         ▼  VITE_BASE_URL
  Express Backend (proxy) — Render
  ├── GET /api/search          →  proxy → Open Library /search.json
  └── GET /api/books/:workId   →  proxy → Open Library /works/:workId.json

  User search → Redux store check
                     │
             ┌───────┴────────┐
         cached             not cached
             │                    │
       return instantly      GET /api/search → store in Redux
```
- Express proxy backend handles CORS — frontend never calls Open Library directly
- Redux caching layer — repeated searches return instantly without hitting the API
- Search history (`lastQuery`, `lastBooks`) and theme preference persisted in localStorage

[![GitHub](https://img.shields.io/badge/GitHub-ReadQuest-181717?style=flat-square&logo=github)](https://github.com/rakesh-mahapatro-456/ReadQuest)

---

## `$ cat github_stats.txt`

<div align="center">

![GitHub Stats](https://github-readme-stats.vercel.app/api?username=rakesh-mahapatro-456&show_icons=true&theme=dark&hide_border=true&bg_color=0d1117&title_color=58a6ff&text_color=8b949e&icon_color=58a6ff)

![Top Languages](https://github-readme-stats.vercel.app/api/top-langs/?username=rakesh-mahapatro-456&layout=compact&theme=dark&hide_border=true&bg_color=0d1117&title_color=58a6ff&text_color=8b949e)

![GitHub Streak](https://github-readme-streak-stats.herokuapp.com/?user=rakesh-mahapatro-456&theme=dark&hide_border=true&background=0d1117&ring=58a6ff&fire=58a6ff&currStreakLabel=58a6ff)

</div>

---

```bash
$ uptime
  APIs shipped. Agents deployed. Databases indexed.
  Always learning. Always building.

$ echo $CONTACT
  📧  rakeshmahapatro85@gmail.com
  💼  linkedin.com/in/rakesh-mahapatro-452b67365
  🐙  github.com/rakesh-mahapatro-456
```
