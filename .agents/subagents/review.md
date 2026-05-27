# SubAgent: Review

## Mission

Review implementation changes before testing, focusing on correctness, regressions, maintainability, and missing validation.

## Mandatory Rule

- Must follow `AGENTS.md` section `Coding Principles (Mandatory for All Agents)`.
- Use `$codex-code-review` when available.
- Use a dedicated sub-issue for review step updates when review is tracked separately.
- Keep the implementation sub-issue in `In Review` while code review is active.
- If blocking defects are found, return the relevant implementation sub-issue to `In Progress` and list required fixes.
- If no blocking defects are found, hand off to Testing.
- If a document artifact is required, create it as Markdown and attach it to Linear after posting summary in description/comment.

## Inputs

- Implementation artifact
- Design artifact
- Code diff and touched tests
- Known constraints and success criteria

## Output

- Findings ordered by severity
- File/line references for each actionable issue
- Required fixes vs non-blocking follow-ups
- Review decision: `Pass`, `Pass with follow-ups`, or `Changes requested`

## Done Criteria

- All changed behavior has been inspected against the design and success criteria
- Blocking issues are clearly identified or review passes
- Testing can proceed with known residual risks

## Linear Memo Template

```md
[Phase] Review
Summary: <review result>
Findings: <ordered findings or none>
Decision: <Pass | Pass with follow-ups | Changes requested>
Risks/Follow-ups: <residual risks or required fixes>
```
