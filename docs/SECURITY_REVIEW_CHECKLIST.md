# Security Review Checklist

Use this checklist before merging features that handle identity, personal data, AI retrieval, tools, or cloud resources.

## Identity and authentication
- [ ] Principal and identity source are documented.
- [ ] Tokens/sessions are validated by trusted code.
- [ ] Token audience, issuer, signature, expiry, and relevant claims are checked where applicable.
- [ ] Credentials and refresh tokens are not exposed to browser bundles or logs.
- [ ] Revocation/expiry behavior is understood and tested.

## Authorization
- [ ] Authorization is enforced server-side before data access or tool execution.
- [ ] Principal, action, resource, and context are evaluated.
- [ ] Least privilege is applied.
- [ ] Ownership and tenant boundaries are enforced.
- [ ] Both allow and deny cases are tested.
- [ ] No authorization decision depends on model-generated text.

## AI and RAG
- [ ] Retrieved documents are treated as untrusted content.
- [ ] User/tenant access filters apply before private content reaches the model.
- [ ] Prompt injection cannot grant new permissions.
- [ ] Model outputs are validated and treated as untrusted.
- [ ] Tool calls are checked independently of model intent.
- [ ] Consequential actions have approval gates where required.

## Workload and agent identity
- [ ] Agent/service identity and owner are recorded.
- [ ] Delegated user access is distinguished from autonomous workload identity.
- [ ] Tool permissions are scoped to the task.
- [ ] Credentials are short-lived where practical and can be revoked.
- [ ] Agent lifecycle includes creation, review, rotation, disablement, and deletion.
- [ ] Sensitive actions produce audit events.

## Cloud and operations
- [ ] Secrets are stored outside source control.
- [ ] IAM roles and policies are least privilege.
- [ ] Logs redact secrets and sensitive personal data.
- [ ] Alerts, incident handling, and rollback are documented.
- [ ] Cloud budget and resource cleanup are configured.
