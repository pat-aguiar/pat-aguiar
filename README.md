# Patricia Aguiar

Software engineer working on document extraction — turning messy real-world documents into structured data that can be trusted. Deterministic parsing first, LLM fallback, confidence scoring on every result.

Before software: seven years as a structural engineer in New York, where being confidently wrong has physical consequences. A tool I wrote there in 2020 is still in production today. MS from Lehigh; [thesis](https://preserve.lehigh.edu/lehigh-scholarship/graduate-publications-theses-dissertations/theses-dissertations/space-time
) on detecting damage in noisy sensor data using a model's own prediction residuals as the signal.

**Open to full-time engineering roles — remote, full overlap with US hours.**

  📧 paguiar.eng@gmail.com · 💼 [LinkedIn](https://www.linkedin.com/in/pat-aguiar/) · 🔗 [AE-SYNC](https://aesync.co)


---

## Stack

* **Languages:** Python, TypeScript, JavaScript, SQL
* **AI & extraction:** OpenAI, Anthropic, Gemini · Pydantic schema validation · prompt engineering · PyMuPDF · OCR · confidence scoring
* **Backend:** FastAPI, Node.js/Express, SQLAlchemy, SQLModel, PostgreSQL, Redis, Supabase, REST, OpenAPI, WebSockets
* **Frontend:** React, TypeScript, Vite, Tailwind CSS, Konva
* **Infra & practice:** Docker, AWS EC2, nginx, GitHub Actions, pytest, Vitest, circuit breakers, structured JSON observability, ADRs

---

## Projects

#### [AE-SYNC](https://aesync.co/) |  production document extraction platform

Codebase private · [architecture writeup](https://github.com/pat-aguiar/aesync-architecture)

Three-tier extraction over CAD and PDF construction drawings: deterministic parsing first, Gemini fallback when no vectors exist, a confidence score attached to every result. Built for a domain where a confidently wrong answer is expensive.

* Async processing on FastAPI background tasks with a polling hook that reconstructs sheet geometry from scale metadata; calibration snaps pixels to drafting units (1/4″=1′-0″).
* React/Konva canvas editor with topology-preserving drag and stretch — move one wall, every connected wall follows — plus undo/redo and autosave.
* Auth-validated uploads: sanitization, size limits, per-user storage partitioning.

Python · FastAPI · Supabase · React · TypeScript · Konva · Gemini API · Docker · Render · Netlify · GitHub Actions

#### [VeriLabel](https://github.com/pat-aguiar/verilabel) | extraction with deterministic validation

The same architecture in a different document domain. The model proposes; deterministic rules decide.

* PDF text extraction (PyMuPDF) → GPT-4o constrained to JSON-mode output → a configurable rule engine validating every extracted value against thresholds stored in Postgres, classifying each submission as passing or flagged.
* Modeled variable extraction output as a JSON column alongside strongly-typed relational fields — the shape of extracted data changes per document, the schema around it shouldn't.
* Normalized environment-specific database URLs so local SQLite and hosted Postgres run on the same SQLAlchemy engine.

Python · FastAPI · SQLModel · PostgreSQL · OpenAI GPT-4o · PyMuPDF · React · TypeScript · Render

#### [Tempo API Sandbox](https://github.com/pat-aguiar/tempo-api-sandbox) | structured schemas from unstructured input

Unstructured code in, validated OpenAPI 3.0 spec out — the same extraction problem with source code as the document.

* Event-driven pipeline: a Postgres webhook triggers a Deno edge function that calls Anthropic and writes the generated spec back to the database. Closed entirely server-side, no client polling; Supabase CDC pushes results to the UI the moment processing finishes.
* Transpiles arbitrary submitted React/TypeScript at runtime (@babel/standalone) inside a constrained execution scope with a per-keystroke-reset error boundary, so a render failure can't take down the surrounding app.
* Two test runtimes in one repo — Vitest for the frontend upload flow, Deno test for edge-function webhook-payload validation. 7 ADRs covering the XSS sandboxing and CDC trade-offs.

React · TypeScript · Vite · Tailwind CSS · @babel/standalone · Supabase (Postgres, Auth, Realtime, Edge Functions) · Deno · Anthropic API

#### [Vision Telemetry Platform](https://github.com/pat-aguiar/glacier-vision-telemetry-platform) | real-time ML inference ingestion and monitoring

The problem from my MS thesis, rebuilt on a production stack: noisy sensor data arriving continuously, and the question of what to trust in it.

* Idempotent ingestion of classification events from edge devices into a partitioned, time-series Postgres schema — duplicate submissions and network retries handled safely at the insert layer.
* Bounding-box overlays rendered as normalized (0–1) SVG coordinates that resize with the image, with zero pixel-math conversion — the same spatial-geometry-over-extracted-output problem as the AE-SYNC canvas.
* Live WebSocket dashboard with sliding-window buffers and a throttled-state hook capping re-renders under high throughput; auto-reconnect with backoff and jitter.
* Constant-time credential comparison across two independently rotatable auth roles, custom ASGI middleware capping request body size, per-client rate limiting on ingestion. 48 tests (26 pytest, 22 Vitest).

Python · FastAPI · SQLAlchemy (async) · PostgreSQL · React · TypeScript · WebSockets · Docker · nginx · AWS EC2

#### [Property Analytics Engine](https://github.com/pat-aguiar/property-analytics-engine) | graceful degradation

A service that detects when its dependency is failing and degrades deliberately, rather than returning results it can't stand behind.

* Circuit breaker (opossum) around a Redis-backed counter with configured failure-threshold and timeout policies, plus a degraded-mode fallback that keeps returning valid responses during a Redis outage rather than failing hard.
* Structured JSON logging capturing per-operation duration and explicit breaker state transitions — open, half-open, closed.
* Integration test exercising the full request path against a live Redis instance, with an ephemeral Redis container provisioned by GitHub Actions on every push and PR.

Node.js · Express 5 · Redis · Winston · GitHub Actions

---

Native fluency in English and Portuguese. Nine years in the US; based in Brazil, full overlap with US hours.
