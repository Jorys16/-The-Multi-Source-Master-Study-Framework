# Capstone: Secure AI Job-Search and Application Intelligence Platform

## Product concept

A job-search platform combining selected ideas from job matching and application preparation products. It helps a candidate manage a profile and resumes, understand job requirements, compare evidence against a role, and prepare applications with AI assistance.

This is a learning capstone, not a claim of affiliation with or reproduction of any third-party product.

## Product principles

- User value before feature count.
- Explainable fit analysis, not an opaque score alone.
- Source-grounded AI responses with evidence.
- Human approval for consequential actions.
- Privacy, authorization, and tenant isolation by design.
- Measurable quality and known limitations.

## Core user journeys

1. Create an account and manage a candidate profile.
2. Upload or enter resume content and review extracted information.
3. Save a job description and inspect its requirements.
4. Compare candidate evidence to job requirements.
5. View an explainable fit analysis with strengths, gaps, and supporting evidence.
6. Track an application through a status lifecycle.
7. Ask questions about the user's own resume and selected job with cited evidence.
8. Use a bounded assistant to prepare application materials, with user approval before sensitive actions.

## Architecture direction

Start with a modular monolith or small set of services. Do not introduce microservices or multi-agent orchestration without a concrete need.

Planned technology:
- Frontend: React + TypeScript.
- Backend: Node.js + Express + TypeScript.
- Database: PostgreSQL.
- AI/data service: Python.
- Vector search: pgvector.
- Identity: secure authentication plus backend authorization; later compare managed identity integrations.
- Cloud: AWS selected services based on architecture and cost.
- Delivery: GitHub Actions, Docker where useful, tests, logs, metrics, traces.

## First milestones

### M0 — Discovery and setup
- Problem statement and target user.
- User stories and acceptance criteria.
- Repository, issue board, code standards, setup documentation.

### M1 — UX shell
- Wireframes and responsive app shell.
- Navigation and UI states.
- Accessibility baseline.

### M2 — API foundation
- Express API and contracts.
- Validation, errors, tests, documentation.

### M3 — Relational foundation and PERN alpha
- ERD and migrations.
- User/profile/resume metadata/job/application records.
- Authentication and object-level authorization.
- Deployment and smoke tests.

### M4 — Data and deterministic matching
- Data normalization and quality checks.
- Transparent baseline matching.
- Error analysis and user-facing explanation.

### M5 — LLM extraction and ingestion
- Model adapter and structured outputs.
- Document parser, provenance, chunking.
- Human review/correction.

### M6 — RAG and MVP v1
- Embeddings and pgvector.
- Semantic and hybrid retrieval.
- Evidence display/citations.
- Retrieval and answer evaluation.
- MVP v1 target: 16 May 2027.

### M7 — Bounded agent workflows
- Tool schemas and scopes.
- Approval gates.
- State, idempotency, audit.
- Optional MCP read-only interface.

### M8 — Production readiness
- Threat model, IAM, privacy, observability.
- Cost/latency limits and rollback.
- Evaluation regression and security testing.

### M9 — Portfolio and demo
- Fresh clone setup.
- Architecture and ERD.
- API documentation and tests.
- Evaluation/security report.
- Demo script, case study, technical defense.

## Core data entities (initial hypothesis)

Users, CandidateProfiles, Resumes, ResumeSections, Jobs, JobRequirements, SavedJobs, Applications, MatchAnalyses, Documents, DocumentChunks, Embeddings, AssistantSessions, ToolCalls, AccessPolicies, AuditEvents.

Refine the model only after requirements and access boundaries are understood.

## Security acceptance criteria

- User A cannot read or mutate User B's records, even by guessing IDs.
- Every sensitive endpoint applies server-side authorization.
- Secrets are not committed or exposed in browser bundles.
- RAG retrieval is scoped to authorized user data before model context is assembled.
- Agents cannot call tools outside their permission set.
- Consequential actions have approval checks.
- Token expiry, revocation, invalid credentials, and denied actions are tested.
- Audit events are emitted for sensitive access and tool actions.

## Definition of Done for any feature

- User story and acceptance criteria exist.
- Design/data/API changes are documented.
- Implementation is readable and scoped.
- Unit/integration tests cover success and failure.
- Authorization tests exist when data or tools are protected.
- No secrets or private user data are committed.
- The feature is demoable locally.
- Documentation is updated.
- A short retrospective records trade-offs and remaining risks.
