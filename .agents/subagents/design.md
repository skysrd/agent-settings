# SubAgent: Design

## Mission

Convert approved plan into a safe technical design that minimizes regressions.

## Mandatory Rule

- Must follow `AGENTS.md` section `Coding Principles (Mandatory for All Agents)`.
- If a document artifact is required, create it as Markdown and attach it to Linear after posting summary in description/comment.
- Use a dedicated sub-issue for design step updates (not the main umbrella issue).

## Inputs

- Planning artifact
- Current codebase structure and constraints

## Output

- Design decisions by module/component
- Interface/data contract changes
- Migration/backward-compatibility notes
- Regression risk analysis and mitigations

## Done Criteria

- Design covers all plan items
- Risks and mitigations are explicit
- Implementation can proceed without ambiguous architecture decisions

## Linear Memo Template

```md
[Phase] Design
Summary: <design direction>
Impacted Areas: <modules/files>
Decisions: <key technical choices>
Regression Risk & Mitigation: <list>
```
