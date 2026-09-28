# Fictional walkthrough: transactional CSV import

This example explains the records. It represents no implemented feature, actual commit, or active backlog item. All identifiers below are fictional.

**Requirement REQ-EX-1:** When a user imports a CSV file, either every valid row is committed or the stored collection remains unchanged. If a row is invalid, report its line number.

**Platform question:** Does the selected database transaction cover both new records and the import summary? The platform expert checks the actual library/version and runs a rollback experiment. A documentation claim about transactions alone would not settle which writes participate.

**ADR-EX-1:** Use one database transaction for the records and summary. Compare that with buffering the entire import and compensating deletes. Record memory cost, lock duration, and error-reporting tradeoffs. The named owner accepts the decision.

| Obligation | Acceptance condition |
| --- | --- |
| O-1 | Valid input commits records and summary together |
| O-2 | A later invalid row leaves both unchanged |
| O-3 | Error identifies the invalid row |

Its implementation line reads **open**.

**WL-EX-1:** Implement transactional import, covering all three obligations. Track: import. Milestone: first usable importer. Implementation category: advanced. Review: one independent reviewer; the project may raise this if stored-data impact warrants it.

The coordinator assigns an implementation worktree with a known base. An independent test brief specifies a valid file, a failure after one valid row, and the expected line number. The implementer writes the code and updates the plan with actual results.

The reviewer checks the combined candidate in a separate worktree. One experiment commits the first row early. The rollback test must now fail because stored data changed; a syntax error would not be useful proof. The reviewer removes the mutation and records the result against the candidate examined.

Suppose rollback and valid input pass, but the line number remains wrong. The candidate sets the ADR's implementation line to **partial**; the rollback and commit tests carry the evidence for O-1 and O-2. The ADR is still accepted. The original work item cannot be called complete unless its scope is explicitly revised and a new work item cites O-3.

After all obligations pass and the required review is complete, the final candidate sets the line to **complete** in the same diff as the fix, and the PR describes it. At merge, the forge identifies the actual integrated commit. Nobody writes that commit into the ADR: `git blame` on the implementation line leads to the change that set it, and from there to its merge and PR. If this project defines 'shipped' as released, release evidence remains pending even after merge.

The important transition is explicit: accepted design → candidate implementation → verified and reviewed candidate → integrated change → released behavior, if release is part of the project's lifecycle.
