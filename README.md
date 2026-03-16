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

> `FastAPI` `LangGraph` `Groq (Llama 3.3 70B)` `Supabase/pgvector` `Salesforce OAuth 2.0 PKCE` `SSE` `Next.js 16`
>
> 🏆 Built for **NeuraX 2.0 — National Level Hackathon**

An enterprise-grade AI platform that automates the entire sales proposal lifecycle using a **multi-agent LangGraph pipeline** wired into live Salesforce CRM data and a private RAG Knowledge Base.

**System Architecture:**
```
  Salesforce CRM ──OAuth 2.0 PKCE──► FastAPI Backend
       (live leads)                        │
                                     LangGraph DAG
  Supabase pgvector ◄──semantic──►  ┌──────────────┐
   (Knowledge Base)    search       │  Discovery   │ ← fetches live CRM lead
                                    │  Research    │ ← semantic KB search
  Groq / Llama 3.3 70B ◄───────────│  Writer      │ ← generates proposal
                                    │  Scoring     │ ← critiques on 1–100 scale
                                    └──────────────┘
                                           │ SSE stream
  Next.js 16 Frontend ◄─────live logs──────┘
```

**What's technically interesting:**
- Non-linear 4-node agent pipeline — stateful, resumable, full observability via SSE thought console
- Private RAG pipeline: PDF/DOC ingestion → chunking → `pgvector` embeddings → semantic retrieval at query time
- Live Salesforce CRM sync via OAuth PKCE — real lead context flowing into agent at inference time
- Proposal scorer evaluates personalization, CTA strength, value proposition — outputs actionable improvement hints
- Batch CSV pipeline for mass proposal generation across hundreds of leads simultaneously

[![GitHub](https://img.shields.io/badge/GitHub-AgentIQ-181717?style=flat-square&logo=github)](https://github.com/rakesh-mahapatro-456/agentiq)

---

### 🔴 Codexa — Real-time Collaborative DSA Platform

> `Node.js` `Express.js` `MongoDB` `Socket.IO` `Cloudinary` `React` `Redux` `Tailwind CSS`
>
> [Live Demo →](https://codexa-tau.vercel.app)

A gamified DSA practice platform built around a **WebSocket-heavy backend**. The real-time layer is the core product — everything else (XP, streaks, leaderboard) runs through it.

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
                                      │  Badge unlock triggers  │
                                      │  Leaderboard ranking    │
                                      └─────────────────────────┘
```
- Socket.IO room architecture with presence tracking and event broadcasting
- Server-side XP engine — streak calculation, level thresholds, badge unlock logic
- Cloudinary upload pipeline — file/image ingestion with metadata persisted to MongoDB
- JWT auth (httpOnly cookies) + full CRUD REST API for problems, users, progress, rooms

[![GitHub](https://img.shields.io/badge/GitHub-Codexa-181717?style=flat-square&logo=github)](https://github.com/rakesh-mahapatro-456/codexa)

---

### 🟡 Flow CRM — Lead Management System

> `Node.js` `Express.js` `MongoDB` `JWT` `bcrypt` `Joi` `React` `Redux` `Tailwind CSS`
>
> [Live Demo →](https://flow-crm-theta.vercel.app)

A production-grade CRM backend built around a custom **server-side query engine** with multi-type filtering and paginated responses.

**Backend highlights:**
```
  GET /leads?status=active&revenue[gt]=50000&createdAt[between]=...
        │
        ▼
  ┌──────────────────────────────────────────────────────┐
  │  Filter Engine                                       │
  │  ├── string   →  equals | contains                  │
  │  ├── enum     →  equals | in                        │
  │  ├── numeric  →  equals | gt | lt | between         │
  │  ├── date     →  on | before | after | between      │
  │  └── boolean  →  equals                             │
  │  All filters: AND logic, processed server-side       │
  └──────────────────────────────────────────────────────┘
        │
        ▼
  Paginated MongoDB query  →  { data, page, total, hasMore }
```
- All query processing happens server-side — never pushed to the client
- JWT httpOnly cookie auth with bcrypt hashing and Joi validation at every route
- Protected route middleware with proper 401/403 error handling

[![GitHub](https://img.shields.io/badge/GitHub-FlowCRM-181717?style=flat-square&logo=github)](https://github.com/rakesh-mahapatro-456/Flow-Crm)

---

### 🟠 Catalogo — E-Commerce Platform

> `Node.js` `Express.js` `MongoDB` `JWT` `bcrypt` `Joi` `React` `Redux` `Vite`
>
> [Live Demo →](https://catalogo.vercel.app)

Full-stack e-commerce system with **Role-Based Access Control**, a cart engine, and a checkout pipeline.

**Backend highlights:**
```
  Request → Auth Middleware → Role Guard → Route Handler
                                  │
                          ┌───────┴───────┐
                        ADMIN           USER
                     POST /products    GET /products
                     PATCH /:id        GET /cart
                     DELETE /:id       POST /cart
                                       POST /cart/checkout
                     Unauthorized  →  403 Forbidden
```
- RBAC enforced at middleware level — role checked before any handler executes
- Cart engine maintains server-side state; checkout generates full order summary/receipt
- Input validated with Joi on every write route; passwords hashed with bcrypt

[![GitHub](https://img.shields.io/badge/GitHub-Catalogo-181717?style=flat-square&logo=github)](https://github.com/rakesh-mahapatro-456/Catalogo)

---

### 🟢 Wanderlust — Travel Listings Platform

> `Node.js` `Express.js` `MongoDB` `Passport.js` `Cloudinary` `Mapbox/GeoJSON` `EJS` `Bootstrap`
>
> [Live Demo →](https://wander-lust-90sw.onrender.com/listings)

MVC-architecture travel listings app with geospatial data, image hosting, and a review system — a clean reference for server-rendered patterns.

**Backend highlights:**
- GeoJSON coordinate storage + Mapbox integration for location-aware listing display
- Cloudinary image upload pipeline — multi-image handling with URL metadata in MongoDB
- Passport-Local-Mongoose session auth with secure cookie handling
- Cascading deletes — orphaned reviews auto-removed when parent listing is deleted

[![GitHub](https://img.shields.io/badge/GitHub-Wanderlust-181717?style=flat-square&logo=github)](https://github.com/rakesh-mahapatro-456/wander-Lust)

---

### 🔵 ReadQuest — Book Discovery App

> `React` `Redux` `Vite` `Open Library API` `Tailwind CSS` `shadcn/ui`
>
> [Live Demo →](https://read-quest.vercel.app)

Frontend-focused project — search, client-side caching, search history, and dark/light theme over the Open Library API. Clean example of Redux state management and external API integration.

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
