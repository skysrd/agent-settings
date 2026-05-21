# Global Agent Workflow Default

## Lifecycle

- Unless explicitly stated otherwise by user, create a new Linear issue before work starts.
- Use one primary issue per task by default.
- Follow standard phases in order: Planning -> Design -> Implementation -> Testing.
- Manage issue state by phase:
  - Planning: `In Planning`
  - Design: `In Design`
  - Implementation: `In Implementation`
  - Testing: `In Testing`
- After testing summary is posted, move to `In Review`.
- Never auto-set `Done`.
- Set `Done` only when user explicitly requests, or user changes status directly.
- Leave phase summary comments in the working issue.

## Standard Status Flow

- `Todo` -> `In Planning` -> `In Design` -> `In Implementation` -> `In Testing` -> `In Review` -> `Done`
- `Done` is always user-driven unless explicitly requested.

## Phase Model

- Planning
- Design
- Implementation
- Testing

## Role Intent

- Planning: build actionable plan from user request, Linear, Slack
- Design: make safe structure decisions minimizing regressions
- Implementation: deliver code from approved design
- Testing: validate normal/edge/failure behaviors

## Phase Output to Linear

Each phase leaves a concise note:

```md
[Phase] <name>
Summary: ...
Artifacts: ...
Decisions: ...
Risks/Follow-ups: ...
```

If a document artifact is needed:
- create a Markdown file (`.md`),
- write a concise summary in Linear description/comment,
- attach the Markdown document to the issue.

## Document Deliverable Policy

- If a task produces a document-style deliverable, always create a Markdown artifact (`.md`).
- Attach the Markdown file to the related Linear issue.
- Also paste the deliverable content into the issue body or a comment.

## Subagent Handoff Policy

- When subagents are used, each subagent must produce a Markdown handoff before task closure.
- Preferred location (worktree): `<repo>/docs/handoffs/`.
- Fallback location (global): `~/.codex/memories/handoffs/`.
- If both are available, store in worktree and keep global only for cross-repo or ad-hoc context.
- Filename convention:
  - `handoff-<issue-or-task-id>-<agent-or-step>-<YYYYMMDD-HHMM>.md`
  - or overwrite a stable `handoff.md` when user explicitly requests a single rolling file.
- Minimum sections required in handoff:
  - `Summary`
  - `Context`
  - `Scope`
  - `Changes`
  - `Validation`
  - `Artifacts`
  - `Open Risks`
  - `Next Actions`
- Handoff must include absolute file paths for modified files and the exact validation commands executed.
- A concise handoff summary must also be posted to the related Linear issue comment.

## Coding Principles (Mandatory)

1. Think Before Coding
- State assumptions explicitly.
- If uncertain or ambiguous, ask.
- Surface alternatives/tradeoffs instead of choosing silently.

2. Simplicity First
- Build only what was asked.
- No speculative abstractions/configuration.
- Prefer the smallest correct solution.

3. Surgical Changes
- Modify only directly related code.
- Do not refactor unrelated areas.
- Remove only unused code introduced by your own changes.

4. Goal-Driven Execution
- Translate work into verifiable goals.
- For multi-step tasks, include step + verification checks.
- Validate outcomes with tests/checks before closing.
