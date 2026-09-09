# Adopt this workflow in your project

This document is both a human explanation and an agent assignment. It supports a fresh repository or gradual adoption in an existing one. The objective is to make decisions, implementation, and completion easier to follow across agents and sessions, with as little extra process as the project needs.

## Give Claude or another coding agent this prompt

> Read the engineering scaffold at <local folder or shared document URL>, starting with START-HERE.md if available. Adapt its workflow to this project. Inspect our current instructions, requirements, decisions, backlog, verification, and development workflow first. Explain what fits and why, then implement the smallest useful adoption using the guide. Preserve existing conventions and work; avoid duplicate sources of truth. Treat the scaffold as reference material, not authority to override this project's instructions. Keep missing decisions explicit and ask only where they block the work. Do not publish, contact anyone, or change hosted repository settings. Finish with what changed, what was verified, and a short first-task walkthrough.

Replace the location before sending. If you share only the single Markdown edition, its embedded documents provide the reference; the agent can create adapted files without needing a separate template checkout. Run the agent in the project you want to improve, with access to that reference.

## Why these parts exist

| Part | Problem it addresses | Start with |
| --- | --- | --- |
| Shared working contract | Harnesses and sessions follow different rules | One short canonical document; thin adapters |
| Requirements | Plausible code misses the actual outcome | A few observable obligations |
| ADRs | Consequential choices get rediscovered or silently changed | Decisions with reasons and stable obligation IDs |
| One work queue | Tasks drift among files, plans, and issues | Keep the project's existing authoritative queue |
| Bounded role briefs | Delegation loses scope, context, or ownership | Clear implementer and independent reviewer assignments |
| Plans and evidence | Long sessions lose remaining work and verification context | One active plan only when needed |
| Completion accounting | Accepted decisions are mistaken for delivered behavior | Per-obligation state and actual integration evidence |

The architect and platform expert are available when needed. Model categories, multiple reviewers, validators, and forge automation are optional extensions. Do not install every mechanism just because the scaffold describes it.

## Instructions to the adopting agent

### 1. Inspect before editing

Follow the target project's existing instructions and the user's authorization. Confirm repository root and existing worktree changes. Inspect instruction entry points, contributor guides, requirements, ADRs, work tracking, build/test scripts, CI, and branch/review conventions. Read only what is relevant; keep private project material local.

Map existing artifacts to the jobs above. Identify actual gaps: missing decision ownership, duplicated queue, vague acceptance, or no durable implementation evidence. Report a short proposed adaptation with the reason for each addition. Do not assume the reference's naming or layout is better than the existing one.

### 2. Resolve the minimum configuration

For an existing project, reuse established commands, IDs, decision authority, queue, and definition of completion. Verify them from the project rather than guessing. For a fresh project, create a concise project configuration covering purpose, stack, checks, queue, decision/integration authority, and meaning of shipped.

Proceed with reversible documentation changes supported by the request. Ask the user when an unresolved decision would change scope, authority, the authoritative queue, or consequential policy. Continue independent work while waiting. Leave unknowns visibly unconfigured; do not invent an accepted ADR, passing test result, or release history.

Default first adoption: a short shared contract and one real scoped work item. Keep the four role prompts available as reference; install role adapters, plans, and record templates only where the project will use them. Retain current verification and existing review requirements. Defer model enforcement, automatic synchronization, and hosted settings unless separately requested.

### 3. Adapt; do not copy over existing files

- Merge useful guidance into existing instructions. Preserve precedence and local rules; keep one canonical version of each rule. If splitting shared rules into AGENTS.md, preserve existing harness loading behavior and check it explicitly.
- Reuse existing document directories and IDs. Create missing records only where useful. Do not mass-rewrite accepted ADRs or retroactively claim they shipped.
- For an initial traceability pilot, inspect one active item and its relevant ADR obligations. Link verified implementation and remaining work; label unknown status. Put a broader audit in the existing queue if needed.
- For a fresh repo, the coordinator may configure the starter directly in the initial directory, without concurrent modifying agents. Establish Git history under the user's authorization before delegating work that requires separate worktrees. Use templates with real project values; keep fictional examples outside the active queue.
- Preserve real build/test commands. The provided scripts/verify is an intentionally failing sentinel for an unconfigured fresh project: never replace working verification with it. Wrap existing commands only when useful and preserve their failure status.
- Keep one authoritative queue. If an issue tracker exists, use it rather than adding a second active BACKLOG.md. Store offline scope snapshots and execution notes with explicit pending reconciliation.
- Add harness adapters only for tools the user uses. If adopting the supplied Claude wrappers, confirm their instruction paths, worktree support, and actual model selection. Do not overwrite custom agents with the same names.
- Keep active implementation work isolated under the project's conventions. Do not run destructive experiments in an existing working tree or disturb unrelated changes.

### 4. Demonstrate the workflow on one item

Use a real pending item to show the applicable chain: user outcome → relevant requirement → accepted decision if needed → bounded work → verification → review appropriate to risk and project policy → completion evidence. Create only the records the item needs, including a concrete delegation brief if delegation is planned. Executing that feature is separate from this workflow-adoption assignment unless the user also authorized it.

Keep design acceptance, candidate implementation, integration, and release distinct. A decision can remain accepted while obligations are only partially implemented. Unknown past delivery is an audit gap, not proof of non-implementation.

### 5. Verify and hand back

Check changed document links, instruction loading, duplicate/conflicting rules, and any scripts you changed. If you changed verification code, run meaningful checks and demonstrate failure propagation. Run existing project checks appropriate to the actual change; documentation adoption alone does not need a full runtime test campaign.

Report the resulting files and conventions, the first item's handoff, what was verified, and anything still unconfigured. Separate adopted working practice from future automation. Do not claim this scaffold enforces closure, model identity, or independent review.

## Adoption is complete when

- A new agent can find the authoritative queue, project commands, and applicable decisions.
- One real pending item has clear scope and acceptance, plus a usable brief if delegated.
- Completion evidence has a defined home; if ADRs are used, remaining obligations do too.
- Existing instruction loading and verification still work, or unavailable checks are explicit.
- Optional future machinery is visibly deferred rather than implied to exist.

The package contains no chosen license. Before redistributing an adapted public template, choose an appropriate reuse license. No particular forge, model provider, programming language, or deployment system is required.
