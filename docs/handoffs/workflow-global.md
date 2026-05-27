# Agent Global Workflow (Mirror)

This file mirrors the currently applied global agent workflow policy so the repository can track operational standards in version control.

## Default Execution

- Unless explicitly stated otherwise by user, create an appropriately scoped Linear parent issue before work starts.
- Create implementation-sized Linear sub-issues under the parent issue so progress is visible in the Linear app in real time.
- Follow phases in order:
  - `In Planning`
  - `In Design`
  - `In Implementation`
  - `In Review`
  - `In Testing`
- Do not auto-set `Done`. `Done` is user-driven.

## Subagent Handoff

- When subagents are used, each subagent must leave a Markdown handoff.
- Preferred location: `<repo>/docs/handoffs/`
- Global fallback: `~/.codex/memories/handoffs/`
- Recommended filename:
  - `handoff-<issue-or-task-id>-<agent-or-step>-<YYYYMMDD-HHMM>.md`
- Required sections:
  - `Summary`
  - `Context`
  - `Scope`
  - `Changes`
  - `Validation`
  - `Artifacts`
  - `Open Risks`
  - `Next Actions`

## Linear Reporting

- Use the parent issue for request-level scope and summary only.
- Use sub-issues for phase/work-step progress and artifacts.
- Post phase summary comments in the related issue:
  - `[Phase] Planning`
  - `[Phase] Design`
  - `[Phase] Implementation`
  - `[Phase] Review`
  - `[Phase] Testing`
- For document deliverables:
  - create Markdown,
  - attach to Linear issue,
  - paste summary or full content in issue body/comment.
