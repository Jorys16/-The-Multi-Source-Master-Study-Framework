# Git and GitHub Engineering Workflow

## Repository rules

- `main` should remain in a working state.
- Every meaningful task starts as an issue.
- Use one branch per issue or focused change.
- Make small, descriptive commits.
- Open a pull request for review, even when working solo.
- Run tests and inspect the diff before merging.
- Link pull requests to issues.
- Keep documentation and tracking records current.

## Branch names

- `feat/<short-description>`
- `fix/<short-description>`
- `docs/<short-description>`
- `test/<short-description>`
- `chore/<short-description>`

## Suggested commit prefixes

- `feat:` new capability
- `fix:` bug fix
- `docs:` documentation
- `test:` tests
- `refactor:` behavior-preserving code change
- `chore:` tooling or maintenance

## Solo pull request checklist

- [ ] The linked issue describes the problem.
- [ ] The PR is small and has one clear purpose.
- [ ] Tests pass.
- [ ] Error and edge cases are considered.
- [ ] Authorization/denial cases are tested when relevant.
- [ ] No secrets, tokens, or private data are included.
- [ ] README/API/architecture docs are updated if needed.
- [ ] I can explain every meaningful change.
- [ ] Screenshots, traces, or test output are attached when useful.

## Issue workflow

1. Create an issue with context and acceptance criteria.
2. Add priority and stage in the title or body.
3. Create a branch.
4. Implement and test.
5. Open a PR and link the issue with `Closes #N`.
6. Review the diff against requirements.
7. Merge only after checks pass.
8. Update weekly progress and skill evidence.

## Example commands

```bash
git switch main
git pull --ff-only
git switch -c feat/profile-api
# implement one focused task
git status
git add .
git commit -m "feat: add candidate profile endpoint"
git push -u origin feat/profile-api
```

Use GitHub's web interface or CLI to open a PR. Never force-push to shared history without a clear reason.
