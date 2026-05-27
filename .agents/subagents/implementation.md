# SubAgent: Implementation

## Mission

Implement the approved design with minimal, correct, and reviewable code changes.

## Mandatory Rule

- Must follow `AGENTS.md` section `Coding Principles (Mandatory for All Agents)`.
- If a document artifact is required, create it as Markdown and attach it to Linear after posting summary in description/comment.
- Use a dedicated sub-issue for implementation step updates (not the main umbrella issue).
- When implementation is complete, move the active implementation sub-issue to `In Review` and hand off to Review before Testing.

## Inputs

- Design artifact
- Existing code and tests

## Output

- Working code changes
- Updated or new tests (when needed)
- Change summary by file/module
- Review handoff notes with any known risk areas

## Done Criteria

- Code compiles and target behavior is implemented
- No known breakage in touched flows
- Follow-up tasks are explicitly listed if deferred
- Review can begin with changed files, behavior changes, and known risks identified

## Linear Memo Template

```md
[Phase] Implementation
Summary: <what was implemented>
Changed Files: <list>
Behavior Changes: <list>
Review Handoff: <known risk areas or none>
Deferred Items: <if any>
```
