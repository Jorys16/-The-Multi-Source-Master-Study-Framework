# Capstone Engineering Studio

The application code will live here as the program progresses. Start small and keep the architecture understandable.

## Planned components

- `frontend/`: React + TypeScript.
- `backend/`: Node.js + Express + TypeScript.
- `ai-service/`: Python services for parsing, retrieval, evaluation, and model integration.
- `infrastructure/`: cloud configuration, Docker, CI/CD, and infrastructure-as-code artifacts.

## Initial architecture principle

Begin with a modular monolith or small number of services. Split services only when the product, deployment, security, or scaling requirements justify the added complexity.

## Engineering rules

- Requirements and acceptance criteria before implementation.
- API and database contracts before cross-component integration.
- Server-side authorization on every protected operation.
- No private user data or credentials in this public repository.
- Tests for success, failure, and denied access.
- Evaluation for model and retrieval behavior.
