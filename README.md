# Full-Stack + Applied AI + IAM Engineering Residency

A single source of truth for a 40-week, project-led engineering program covering:

- Computer Science, Python, C++, data structures, algorithms, and software engineering
- Full-stack development with TypeScript, React, Node.js, Express, SQL, and PostgreSQL
- Data engineering, mathematics, statistics, machine learning, and deep learning
- Generative AI, LLM applications, embeddings, RAG, pgvector, retrieval, and evaluation
- Agent engineering, tool calling, MCP, orchestration, and agent lifecycle
- Identity and Access Management (IAM), workload identity, authorization, and AI agent security
- AWS cloud engineering, DevOps, observability, reliability, and production operations

The program's capstone is a secure AI-powered job-search and application-intelligence platform inspired by MigrateMate and Jobscan.

## Program at a glance

| Item | Plan |
|---|---|
| Start | 16 November 2026 |
| MVP v1 target | 16 May 2027 |
| Program end | 22 August 2027 |
| Duration | 40 weeks |
| Study budget | About 20 hours/week |
| Learning style | Lecture → visual explanation → demo → guided lab → independent work → review → project sprint |
| Primary product languages | TypeScript and Python |
| Systems/problem-solving language | C++ |
| Primary cloud learning path | AWS |
| Cross-cutting security strand | IAM and AI agent security |

## Start here

1. Read [Program Charter](docs/PROGRAM_CHARTER.md).
2. Read the [40-week Roadmap](docs/ROADMAP_40_WEEKS.md).
3. Follow the [Learning Method](docs/LEARNING_METHOD.md) for every topic.
4. Use the [Course Catalog](docs/COURSE_CATALOG.md) and [Resource Map](docs/RESOURCES.md).
5. Track progress in the [Tracking folder](tracking/README.md).
6. Build the [Capstone](docs/CAPSTONE_SPEC.md) incrementally.
7. Follow the [IAM & Agent Security Path](docs/IAM_AGENT_SECURITY_PATH.md).
8. Use the [AWS Certification Path](docs/AWS_CERTIFICATION_PATH.md) as a supporting objective, not as a substitute for building.

## Repository map

```text
.
├── README.md
├── docs/
│   ├── PROGRAM_CHARTER.md
│   ├── ROADMAP_40_WEEKS.md
│   ├── COURSE_CATALOG.md
│   ├── LEARNING_METHOD.md
│   ├── IAM_AGENT_SECURITY_PATH.md
│   ├── AWS_CERTIFICATION_PATH.md
│   ├── CAPSTONE_SPEC.md
│   ├── GIT_GITHUB_WORKFLOW.md
│   ├── ASSESSMENT_RUBRIC.md
│   └── RESOURCES.md
├── templates/
│   ├── WEEKLY_LESSON.md
│   ├── ASSIGNMENT.md
│   └── ARCHITECTURE_DECISION_RECORD.md
├── tracking/
│   ├── README.md
│   ├── WEEKLY_PROGRESS.md
│   ├── SKILLS_MATRIX.md
│   ├── SPACED_REPETITION.md
│   └── MVP_MILESTONES.md
├── capstone/
│   ├── README.md
│   ├── frontend/README.md
│   ├── backend/README.md
│   ├── ai-service/README.md
│   └── infrastructure/README.md
└── .github/
    ├── PULL_REQUEST_TEMPLATE.md
    └── ISSUE_TEMPLATE/
        ├── weekly-learning.yml
        └── blocker-or-bug.yml
```

## Rules of the residency

- Understand before adopting. No framework or AI tool is a substitute for fundamentals.
- Build in vertical slices. A feature should connect UI, API, data, tests, and documentation.
- Keep `main` working. Use branches and small, reviewable pull requests.
- Treat IAM as a system property. Enforce authorization in trusted code and policy layers, never by trusting the model's answer.
- Use AI coding assistants as reviewers and tutors. Do not keep code you cannot explain.
- Record evidence. A topic is not complete because a video was watched.
- Track uncertainty. Mark unclear concepts and revisit them using spaced retrieval.
- Keep cloud spend controlled. Use budgets, cost alerts, and cleanup checklists.

## External reference models

- [TTP Summer 2026 repository](https://github.com/aghaffar570/ttp-summer-2026) — weekly curriculum, assignments, demos, review, Git workflow, and capstone practices.
- Applied AI Engineer Bootcamp brochure supplied in the learning conversation — foundations, GenAI, RAG, agent engineering, MCP, production, and capstone themes.

This repository is an independent personal learning workspace. It is not affiliated with TTP, Columbia Engineering, Fullstack Academy, AWS, Microsoft, or other referenced organizations.
