# Issue Tracker

## Provider

- Type: GitHub Issues
- Repository: `monet88/hanquest`
- Repository URL: `https://github.com/monet88/hanquest`
- Default branch: `main`

## Sources of Truth

- The canonical product specification is `docs/specs/hanquest-platform.md`.
- GitHub Issue #1 is the complete tracking mirror of the canonical specification.
- Whenever the canonical specification changes, update its GitHub issue mirror in the same operation.
- Implementation tickets inherit only the user stories and acceptance criteria explicitly assigned to their slice.
- GitHub Issues are canonical for implementation-ticket identity, status and dependencies. Numbered Markdown mirrors live under `docs/issues/` for agent handoff and offline review.
- Whenever an implementation issue's title, scope, acceptance criteria, blockers or status changes, update its matching Markdown mirror in the same operation.

## Publication Rules

- Update an explicitly named existing issue instead of creating a duplicate.
- Otherwise create one GitHub issue per approved tracer-bullet ticket in dependency order.
- Use concise feature titles without decorative prefixes.
- Include the parent issue, end-to-end behavior, acceptance criteria and actual blocker issue numbers.
- After GitHub returns the real issue identity, create or update its numbered `docs/issues/` mirror; never predict issue numbers in a mirror.
- Apply `ready-for-agent` only when the issue has an executable scope, an approved testing seam and a measurable Definition of Done that fits one fresh agent context.
- The `ready-for-agent` label on Issue #1 applies only to the Phase 1 scope declared in the specification.
- Use the connected GitHub app for issue reads and writes.
- Return only actual issue numbers and canonical URLs reported by GitHub.
