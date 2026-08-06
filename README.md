Patricia Aguiar

Full-Stack Software Engineer · MS in Engineering (Lehigh) · Fullstack Academy Alumni · React · Python/FastAPI · Node.js

### Let's Connect
- 📧 Email: paguiar.eng@gmail.com
- 💼 LinkedIn: [linkedin.com/in/pat-aguiar](https://www.linkedin.com/in/pat-aguiar/)
- 🔗 Live project: [app.aesync.co](https://app.aesync.co)

---

Fullstack Engineer with a structural engineering background — seven years designing and delivering technical projects in New York City (Design Engineer → Project Engineer → Project Manager) before shifting into software full-time. I build production applications end-to-end: React/TypeScript frontends, Python/FastAPI and Node/Express backends, real deployments — not local demos.

**Currently building [AE-SYNC](https://app.aesync.co)** — an AI-assisted platform that extracts structural elements from CAD/PDF blueprints and renders them in an interactive canvas editor with topology-preserving geometry (move one wall, every connected wall moves with it).

**Open to full-time Fullstack Engineer roles.**

---

## Tech Stack

* **Languages:** Python, JavaScript (ES6+), TypeScript
* **Frontend:** React, Vite, Tailwind CSS, Konva
* **Backend:** FastAPI, Node.js/Express, SQLAlchemy, SQLModel
* **Data:** PostgreSQL, Redis, Supabase (Auth, Storage, Realtime, Edge Functions)
* **AI/LLM:** OpenAI API, Google Gemini API, Anthropic Claude API
* **DevOps & Practices:** Docker, AWS, Render, Netlify, GitHub Actions, REST APIs, OpenAPI documentation, Circuit Breakers, Structured (JSON) Observability

---

## Featured Projects

#### 1. [Vision Telemetry Platform](https://github.com/pat-aguiar/glacier-vision-telemetry-platform) | **Real-Time Data Platform**

Full-stack telemetry ingestion and live dashboard, deployed with a real test suite behind it.
* **Technical Showcase:** Idempotent event ingestion into a partitioned, time-series Postgres schema; live WebSocket dashboard with sliding-window buffers and throttled state.
* **Rigor:** Constant-time auth checks, dual auth roles, per-client rate limiting; 48-test suite (26 backend, 22 frontend); deployed via Docker/nginx/AWS EC2 with automated HTTPS.
* **Stack:** Python, FastAPI, SQLAlchemy (async), PostgreSQL, React, TypeScript, WebSockets, Docker, AWS EC2, Nginx.

#### 2. [Tempo API Sandbox](https://github.com/pat-aguiar/tempo-api-sandbox) | **AI-Generated OpenAPI Documentation Playground**

A live, interactive sandbox that transpiles and renders submitted React components in-browser, then generates their OpenAPI spec via an AI backend.
* **Technical Showcase:** Dynamically transpiles React/TypeScript strings at runtime (Babel standalone) inside a constrained execution scope, with an event-driven Supabase Edge Function (Deno) calling the Anthropic API for OpenAPI schema generation.
* **Rigor:** Per-keystroke error boundaries, 1000ms debounce on the live editor, real-time Postgres CDC sync back to the UI, and 7 documented ADRs covering the key architectural trade-offs.
* **Stack:** TypeScript, React, Tailwind CSS, @babel/standalone, Supabase (DB, Realtime, Auth, Edge Functions, Deno), Anthropic API.

#### 3. [QuickAI](https://github.com/pat-aguiar/AI-SAAS) | **Full-Stack AI SaaS Platform**

A PERN AI-as-a-service platform with 6 AI-powered tools behind one API.
* **Technical Showcase:** Integrates multiple third-party AI providers (Google Gemini via an OpenAI-SDK-compatible client, Clipdrop) behind a consistent request/response contract.
* **Rigor:** Server-side subscription-tier gating via Clerk plan checks plus a persisted free-usage cap; Neon Postgres data layer powering a public feed with like/unlike toggling.
* **Stack:** React, Node.js, Express, PostgreSQL (Neon), Clerk, Google Gemini API, Clipdrop, Cloudinary.

#### 4. [VeriLabel](https://github.com/pat-aguiar/verilabel) | **AI Document Analysis Platform**

AI-powered document extraction paired with rule-based validation.
* **Technical Showcase:** Extracts PDF text (PyMuPDF), then parses it into structured data via a GPT-4o call constrained to JSON-mode output.
* **Rigor:** Configurable rule engine validates extracted values against Postgres-stored thresholds, automatically classifying each submission.
* **Stack:** Python, FastAPI, SQLModel, PostgreSQL, OpenAI API, React, TypeScript.

#### 5. [Property Analytics Engine](https://github.com/pat-aguiar/property-analytics-engine) | **Fault-Tolerant Backend Microservice**

A focused Node.js microservice built around resilience and CI-gated correctness.
* **Technical Showcase:** Wraps a Redis-backed counter in a circuit breaker (opossum) with failure-threshold policies and a graceful degraded-mode fallback instead of failing hard.
* **Rigor:** Versioned (v1) REST API with routing, business logic, and infrastructure kept in separate layers; live-Redis integration test run via GitHub Actions CI on every push/PR.
* **Stack:** Node.js, Express 5, Redis, Winston, GitHub Actions.

---

## Background

Native fluency in English & Portuguese. MS in Structural Engineering, Lehigh University. Software Engineering Immersive, Fullstack Academy (NYC).
