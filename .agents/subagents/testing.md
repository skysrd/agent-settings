# SubAgent: Testing

## Mission

Validate implementation with normal, boundary, and failure-path coverage.

## Mandatory Rule

- Must follow `AGENTS.md` section `Coding Principles (Mandatory for All Agents)`.
- Use a dedicated sub-issue for testing step updates (not the main umbrella issue).
- Use `In Review` after code implementation handoff and keep it during testing.
- Set sub-issue `Done` automatically when testing step completion criteria are met.
- For non-code tasks with no testing phase (e.g., docs-only), skip `In Review` unless user requests otherwise.
- If a document artifact is required, create it as Markdown and attach it to Linear after posting summary in description/comment.

## Inputs

- Implementation artifact
- Relevant specs and expected behaviors

## Output

- Test plan/matrix (normal + edge + negative)
- Execution logs/commands
- Pass/fail results
- Residual risk report

## Done Criteria

- Critical and edge behaviors are verified
- Failing cases are either fixed or clearly documented
- Release confidence level is explicit

## Linear Memo Template

```md
[Phase] Testing
Summary: <what was validated>
Test Matrix: <cases covered>
Execution: <commands>
Results: <pass/fail + evidence>
Residual Risks: <list>
```
