# Week 01 — Computing Foundations, Environment, Git, and Identity Vocabulary

- Dates: 16–22 November 2026
- Stage: Engineering foundations
- Workload: approximately 20 hours
- GitHub issue: https://github.com/Jorys16/-The-Multi-Source-Master-Study-Framework/issues/1

## Why this week matters

Before learning frameworks, understand what a program is, how it runs, how you work with the machine, and how changes are recorded. We introduce identity vocabulary because secure software starts by distinguishing the actor making a request from the permission to perform an action.

## Learning objectives

By the end of this week, you should be able to:
- Explain source code, compiler/interpreter, process, CPU, memory, input, and output.
- Use terminal commands to navigate, create, inspect, and run files.
- Explain repository, working tree, staging area, commit, branch, and remote.
- Create a Git repository and publish a small program.
- Distinguish identity, principal, authentication, authorization, resource, and trust boundary.

## Conceptual redundancy

- Primary: [CS50x](https://cs50.harvard.edu/x/) — begin with the introductory computer-science material and the computer/memory/programming mental models.
- Alternate: [MIT OpenCourseWare](https://ocw.mit.edu/) — use one introductory lecture or reading to compare explanations.
- Developer tools: [The Missing Semester](https://missing.csail.mit.edu/) — terminal and command-line workflow.
- Reference: [Pro Git](https://git-scm.com/book/en/v2) — first chapters on version control and Git basics.

Do not try to finish all four resources. Use the primary sequence, one alternate explanation for a confusing concept, and references while performing the lab.

## Mental model 1 — From source code to output

A source file is a human-readable description of instructions. A compiler or interpreter translates or executes those instructions. A running program becomes a process with state and resources. The CPU executes instructions, memory stores code/data/state while running, and I/O moves information across boundaries.

Draw:

```text
Source file
   |
Compiler / interpreter / runtime
   |
Running process
   |
CPU executes instructions <--> memory stores state
   |
Input / output
```

Questions to answer:
1. Is source code itself a running process?
2. What information changes when a variable is assigned?
3. Why can two processes run the same program but hold different state?
4. What does a runtime provide?

## Mental model 2 — Git records snapshots

Git tracks content snapshots and the history that connects them.

```text
Working tree -> Staging area -> Commit -> Remote repository
      |               |            |
    edit            select       snapshot
```

Draw your own version and explain what each step means. Practice branches only after you can explain the normal commit workflow.

## Mental model 3 — Identity is not permission

- Identity: the represented user or workload.
- Principal: the actor making the request.
- Authentication: proving or validating the identity.
- Authorization: deciding whether the principal may perform an action on a resource.
- Trust boundary: a point where data or control crosses between components with different trust assumptions.

Example: a logged-in user can be authenticated but still lack authorization to read another user's resume.

## Monday — Lecture and setup (4 hours)

- 60 min: introductory CS lesson on what computers do and what a program is.
- 45 min: draw source → runtime → process → CPU/memory → output.
- 60 min: install/verify editor, terminal, Git, and language runtime needed for your first exercise.
- 45 min: read Git basics and create a short vocabulary note.
- 30 min: explain identity vs authentication vs authorization in your own words.

## Tuesday — Guided lab (4 hours)

1. Create a new local folder for a tiny program.
2. Create a source file and run it.
3. Change an input and predict the output before running again.
4. Add a deliberate error; observe the error; fix it.
5. Initialize Git, inspect status, stage the file, commit it.
6. Create a branch, make a small change, commit, and merge it.
7. Write the exact setup/run steps in a README.

Expected evidence: a working program, meaningful commits, and a setup README.

## Wednesday — Independent assignment (4 hours)

Build a small command-line program that:
- Accepts a name or simple input.
- Validates that the input is not empty.
- Produces a predictable output.
- Handles at least two invalid-input cases.
- Separates input, processing, and output into clear steps.

Stretch: write a second version in another language after the first version works. Compare how each language executes the program at a high level.

## Thursday — Capstone discovery (4 hours)

Do not start complex application code yet.

- Write a one-paragraph problem statement for the job-search intelligence platform.
- Identify the target user and one concrete problem.
- Write three user stories.
- Add acceptance criteria to each story.
- Sketch one dashboard page.
- Identify the main actors: candidate user, backend service, database, future AI service.
- Open or update the repository issue with your design notes.

## Friday — Knowledge check and review (4 hours)

Attempt these before reading the answers.

1. What is the difference between source code and a running process?
2. What role does memory play while a process runs?
3. What does Git's staging area do?
4. What is the difference between a commit and a branch?
5. Can an authenticated user be denied access to a resource? Explain.
6. Why should authorization be checked by a trusted server-side component?

### Answer key

1. Source code is a program representation; a process is an executing instance with its own runtime state.
2. Memory holds instructions/data/state that the process and system use while executing.
3. It selects the changes that will be included in the next commit.
4. A commit is a recorded snapshot in history; a branch is a movable reference to a line of development.
5. Yes. Authentication establishes identity; authorization decides whether that identity may perform the requested action.
6. Client UI and model outputs are untrusted; the server must enforce access rules before returning data or executing actions.

## Definition of Done

- [ ] Can explain the program execution diagram without notes.
- [ ] Can create, run, debug, and document a small program.
- [ ] Can use status, add, commit, branch, and merge in Git.
- [ ] Can explain identity, principal, authentication, and authorization.
- [ ] Has a product problem statement, three user stories, and one wireframe.
- [ ] Has linked evidence in the Week 1 GitHub issue.
- [ ] Has entered key concepts into spaced repetition.

## Spaced retrieval

- Same day: explain source code vs process.
- +1 day: redraw the runtime and Git diagrams.
- +3 days: fix a fresh program error and explain the root cause.
- +7 days: demonstrate the Git workflow from a clean working tree.
- +14 days: explain authentication vs authorization using a new example.
- +30 days: trace a small program and identify its state changes.
