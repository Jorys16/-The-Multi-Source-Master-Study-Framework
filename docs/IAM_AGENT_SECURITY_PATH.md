# IAM and AI Agent Security Learning Path

IAM is a cross-cutting engineering discipline, not only a cloud console topic.

## The core vocabulary

| Term | Meaning |
|---|---|
| Identity | A representation of a user, service, device, workload, or agent |
| Principal | An entity that can make a request in a security system |
| Authentication | Verification of an identity claim |
| Authorization | A decision about whether an identity may perform an action on a resource |
| Policy | Rules used to make authorization decisions |
| Credential | Evidence or secret used to establish identity |
| Token | A data structure carrying claims or delegated authority |
| Scope | A bounded set of permissions or operations |
| Workload identity | A verifiable identity for software running as a workload |
| Audit event | A record of an action, decision, identity, and context |

Authentication answers “who are you?” Authorization answers “what are you allowed to do?”

## Learning sequence

### 1. Identity and trust foundations
Learn identities, accounts, principals, subjects, resources, actions, trust boundaries, and identity lifecycle.

Exercise: list the identities in a web application: user, frontend, backend service, database service, CI runner, and AI agent.

### 2. Authentication
Learn passwords, MFA, passkeys, sessions, cookies, token basics, certificates, signatures, and credential lifecycle.

Exercise: trace a login session and explain where credentials are stored and validated.

### 3. OAuth 2.0 and OpenID Connect
Learn the roles (client, authorization server, resource server, resource owner), authorization code flow, PKCE, ID token vs access token, refresh tokens, scopes, consent, and token validation.

Exercise: diagram a browser login and API access flow. Never treat an ID token as a general API access token.

### 4. Authorization models
Learn RBAC, ABAC, ownership checks, resource policies, least privilege, deny rules, policy evaluation, and separation of duties.

Exercise: implement a backend permission check and test both allowed and denied requests.

### 5. Multi-tenant application security
Learn tenant boundaries, row ownership, object-level authorization, data leakage, and safe query patterns.

Exercise: create two test users and prove that user A cannot fetch or modify user B's records by guessing IDs.

### 6. Workload identity and cloud IAM
Learn service identities, short-lived credentials, role assumption, trust policies, identity policies, resource policies, permission boundaries, and audit trails. Study AWS IAM first for the chosen cloud path; compare enterprise identity products later.

Exercise: give one service permission to read one specific storage location, then test that a different action is denied.

### 7. Identity governance
Learn provisioning, deprovisioning, access reviews, ownership, expiration, audit, privileged access, credential rotation, and incident response.

Exercise: design an agent offboarding procedure and verify access is revoked.

### 8. Agent identity and delegated access
Distinguish an agent acting on behalf of a human from an autonomous workload with its own identity. Learn agent ownership, identity lifecycle, task identity, delegation limits, tool identity, approval, and audit.

Exercise: give a research agent read-only access to approved records and deny writes.

### 9. MCP and tool authorization
Learn host/client/server boundaries, capabilities, tool schemas, server trust, authorization, user consent, and audit.

Exercise: build a read-only MCP tool and prove that unauthorized tools cannot be called.

### 10. Policy-as-code and workload identity standards
Explore Open Policy Agent/Rego and SPIFFE/SPIRE after the foundational models are clear.

Exercise: write a small policy that evaluates principal, action, resource, and context; test allow and deny cases.

### 11. AI-specific threats
Study prompt injection, untrusted retrieved content, confused deputy problems, excessive agency, privilege escalation, data exfiltration, and unsafe tool composition.

Exercise: provide a malicious instruction inside a retrieved document and verify that the agent cannot exceed its explicit permissions.

## Integration into the 40 weeks

- W01–06: identity, principal, process identity, trust boundaries.
- W07–10: cookies, sessions, browser auth state, secrets in frontend.
- W11–12: authentication foundations, RBAC, middleware, object ownership.
- W13–16: schema, tenant isolation, AWS IAM foundations, deployment credentials.
- W17–20: data pipeline permissions, service roles, workload identities.
- W21–26: secure model credentials and authorization-aware RAG.
- W27–31: agent identities, delegation, tool scopes, MCP, approval, revocation.
- W32–36: zero trust, policy-as-code, governance, audit, incident response.
- W37–40: threat model, access review, security test matrix, capstone defense.

## Security invariants for the capstone

1. The model never grants itself permissions.
2. Authorization is enforced in trusted backend/policy code before tool execution.
3. Every record access checks ownership or tenant authorization server-side.
4. RAG retrieval is filtered by the caller's access rights before evidence is supplied to a model.
5. Agent tools have the smallest permissions needed for their task.
6. Consequential actions require explicit approval where defined by product policy.
7. Credentials are short-lived where possible, stored securely, rotated, and revocable.
8. Every sensitive action records the actor, tool, resource, decision, and outcome.
9. Denied actions are tested, not merely successful flows.
10. Prompt injection does not bypass authorization.

## Important distinction

OAuth 2.0, OpenID Connect, RBAC, ABAC, SPIFFE, OPA, AWS IAM, and Microsoft Entra are not interchangeable products. Some are protocols, some are authorization models, some are frameworks or standards, and some are vendor platforms. Learn the underlying problem and model first, then the implementation.
