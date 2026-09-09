# Work queue

This file is authoritative until `docs/project.md` names a replacement. Active items are ordered by priority. Tracks group related work; dependencies determine readiness. Completed items leave this active queue when the project's completion rule is satisfied; their IDs remain in archived plans and Git history.

## WL-001 — Configure this starter for the project

- Status: ready.
- Track: project setup. Milestone: none. Depends on: none.
- Outcome: project rules, commands, authority, and first real work item are concrete.
- Requirements / ADR obligations: not applicable to scaffold configuration.
- Scope: complete `docs/project.md`; replace sample requirements; configure `scripts/verify`; choose optional harness/model settings; create the first real item.
- Acceptance: relevant project checks actually run; the placeholder verifier is removed; no configured authority or command is left ambiguous.
- Implementation capability: bounded, advisory. Review: one independent configuration review.
- Plan: create from `templates/plan.md` if the work needs multiple sessions.

The fictional walkthrough is not active backlog work.
