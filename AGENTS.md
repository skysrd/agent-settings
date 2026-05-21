# Agent Operating System (Repository Default)

This file is the default instruction source for all agents/Codex working in this repository.
Repository documents are the source of truth for cross-PC use. Global local memory is optional cache only.

## 1. Issue Mapping and Status Automation

- Default Linear issue for this repository: `SKY-5` (until explicitly changed by user).
- Default issue assignee rule:
  - When creating a Linear issue and no assignee is explicitly specified, set assignee to `codex`.
- Use the main issue as an umbrella only.
- Do not post routine phase progress updates to the main issue.
- For each phase/work step, create and use a dedicated sub-issue.
- Work start rule:
  - When implementation work begins, set the active sub-issue status to `In Progress`.
- Review handoff rule:
  - When code implementation is complete, set the active sub-issue status to `In Review`.
  - Then start testing/validation.
- Work completion rule:
  - Sub-issue `Done` is set automatically by agent when its step is complete.
  - Main issue `Done` is still user-driven unless explicitly requested.
- Reporting rule:
  - Every phase updates its own sub-issue with artifact summary.

## 2. Standard SubAgent Workflow

- `Issue Publishing` (optional, for issue authoring/publishing)
- `Planning` -> `Design` -> `Implementation` -> `Testing`
- Do not skip handoff artifacts between phases.
- If scope changes, go back to `Planning` and update artifacts.

## 3. SubAgent Specs

SubAgent role guides are stored at:

- `.agents/subagents/issue-publishing.md`
- `.agents/subagents/planning.md`
- `.agents/subagents/design.md`
- `.agents/subagents/implementation.md`
- `.agents/subagents/testing.md`

## 4. Required Artifacts by Phase

- Planning artifact:
  - Problem statement
  - Goals / non-goals
  - Task breakdown
  - Risks / assumptions
- Design artifact:
  - Impacted modules
  - API/data-flow decisions
  - Backward compatibility and regression risks
  - Mitigation plan
- Implementation artifact:
  - Changed files
  - Key logic changes
  - Deferred work / tradeoffs
- Testing artifact:
  - Test matrix (normal + edge cases)
  - Executed commands
  - Actual results
  - Residual risks

## 5. Linear Comment Protocol

Each phase must add one concise comment to its active sub-issue with this format:

```md
[Phase] Planning | Design | Implementation | Testing
Summary: ...
Artifacts: ...
Decisions: ...
Risks/Follow-ups: ...
```

## 5.1 Document Artifact Protocol

When a phase requires a document artifact:

- Create a Markdown file (`.md`) in the repository.
- Write the key summary in Linear `description` or a Linear `comment`.
- Attach the generated Markdown document to the Linear issue.
- Keep the Linear body concise; keep full detail in the attached Markdown.

## 6. State Transition Protocol

- Main issue:
  - Track umbrella scope only (no routine step logs).
  - Do not auto-close main issue.
- Sub-issue:
  - `Todo` -> `In Progress`: when that step starts
  - `In Progress` -> `In Review`: when implementation for that step is complete
  - Keep `In Review` during testing/validation for that step
  - `In Review` -> `Done`: auto by agent when step completion criteria are met
- Exception:
  - For non-code tasks without a testing phase (e.g., documentation-only updates), sub-issue can move `In Progress` -> `Done`.
- Default scope: this protocol applies to new issue progress from now on.
- Existing issues are excluded unless user explicitly asks to apply retroactively.

## 7. Slack/Linear/User-driven Planning

Planning phase input priority:

1. Explicit user request in current chat
2. Linear issue context (description, comments, attachments)
3. Slack context (if requested/available)

When multiple inputs conflict, ask user for final priority.

## 8. Coding Principles (Mandatory for All Agents)

### 8.1 Think Before Coding

- Never assume silently.
- State assumptions explicitly before implementation.
- If uncertain, ask instead of guessing.
- If multiple interpretations exist, present options explicitly.
- If a simpler approach exists, call it out.
- Push back when requirements imply unnecessary complexity.
- If anything is unclear, stop and ask what is ambiguous.

### 8.2 Simplicity First

- Implement the minimum code that solves the requested problem.
- Do not add speculative features.
- Do not introduce abstractions for one-off usage.
- Do not add configurability/flexibility unless requested.
- Do not add error handling for impossible scenarios.
- If a solution is overcomplicated, simplify before finalizing.

### 8.3 Surgical Changes

- Touch only what is required by the request.
- Do not refactor or clean adjacent unrelated code.
- Match existing style and conventions in the edited area.
- If unrelated dead code is discovered, mention it but do not remove it unless requested.
- Remove only unused artifacts created by your own changes (imports, vars, functions).
- Every changed line must be directly traceable to user intent.

### 8.4 Goal-Driven Execution

- Convert tasks into verifiable goals before coding.
- Define success criteria that can be tested.
- Prefer test-first verification for bug fixes and validation tasks.
- For multi-step tasks, provide a short execution plan with verification per step:
  1. `[Step]` -> verify: `[check]`
  2. `[Step]` -> verify: `[check]`
  3. `[Step]` -> verify: `[check]`
