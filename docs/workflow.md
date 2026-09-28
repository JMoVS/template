# Working across sessions and agents

## A bounded change

1. Select a ready work item. Resolve blockers and acceptance conditions; create a plan only if useful.
2. Research unknown facts and obtain acceptance for consequential design decisions.
3. Commit briefing documents (plan, independent test specification) first; new worktrees start from committed history. Assign implementation in an isolated worktree with a known base. Parallel agents own separate scopes and branches.
4. Integrate their changes into a candidate branch; resolve interactions and run relevant checks there.
5. Review that candidate independently. Material fixes require renewed checks and review of affected behavior.
6. Update work accounting and archive the plan when the configured completion rule is met. Record integration or release evidence at the stage when it exists.

Worktrees and pull requests fit together: worktrees isolate local edits; branches identify candidate history; a pull request presents a branch for integration. You can use one PR per bounded item, with multiple internal agent branches feeding its candidate. Separate PRs make sense when changes are independently reviewable. Recheck the combined result after dependencies land.

## Review loops

- First-round findings go back to the same implementer, whose context is intact.
- A blocking finding in a later round means the work is not converging at that capability. Start a fresh implementer one capability category higher (see the [model policy](model-policy.md)), and a fresh reviewer with a different starting lens.
- If the highest routine category fails twice, propose the most capable and most expensive option to the decision owner. Never escalate to it automatically.
- Check where findings cluster. When they sit in input plumbing (parsing another tool's output, configuration, file formats) rather than in the rule being implemented, change the input instead of patching each finding; the plumbing is the defect surface.
- Before integration, review the whole combined diff once more. Earlier passes each saw a version that changed afterwards.

## Records with different jobs

- Requirement: what the system must do.
- ADR: why a consequential approach was chosen, its obligations, and one implementation-state line. It cites no work items.
- Work item: a bounded deliverable and its current readiness.
- Plan: execution state for that item, including the next step and unresolved findings.
- Review: independent findings and the candidate/evidence examined.
- Integration or release history: when the change reached the relevant destination.

Tracks are continuing areas of work; milestones are finite outcomes with completion criteria. Use labels or an equivalent field for tracks and milestones for release or delivery goals. Priority is separate from both. A milestone does not enforce dependencies or prove completion by itself.

## Offline operation

For local models, provision weights and the runtime before disconnecting; provision tools, packages, and fixtures too. Verify that the chosen harness and model actually operate offline. Cloud-only agents cannot do so; cached scope still supports manual work or later continuation. Keep requirements, ADRs, plans, and verification code in Git. Build, test, review, and commit locally where available and within the configured authority.

If issues become the authoritative queue, cache the relevant issue scope with its source, retrieval time, and version where available. Treat the snapshot as reference. Record local findings in the active plan as pending reconciliation; do not maintain a second editable issue database. Reserve work IDs before going offline or use collision-resistant temporary IDs and reconcile them explicitly.

After reconnecting, fetch the current target branch and issue scope. Resolve scope changes, integrate, and rerun checks/review affected by the new candidate. An offline review is evidence for the revision it inspected; it is not approval of unseen later changes.

## Closing without relying on memory

The starter's closure procedure is manual. Review the work item and each affected ADR obligation before declaring completion. Keep stable work IDs in archived plans or durable issue links after removing completed items from the active queue.

Automation should eventually check this transition and generate reports. See the roadmap; none of those gates is installed by this template. In particular, do not attempt to embed a commit's own final hash into that commit. Record known earlier evidence, then obtain merge/release evidence from history or an explicit later update.

Forges usually resolve a merge commit to its pull request, but not a commit from the branch. From a branch commit, `git log --merges --ancestry-path --reverse <commit>..<target>` lists merges in landing order; the first one that integrated a pull request is the landing merge. A `--first-parent` variant misses commits made before the branch merged its target.
