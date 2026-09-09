# Fictional walkthrough: transactional CSV import

This example explains the records. It represents no implemented feature, actual commit, or active backlog item. All identifiers below are fictional.

**Requirement REQ-EX-1:** When a user imports a CSV file, either every valid row is committed or the stored collection remains unchanged. If a row is invalid, report its line number.

**Platform question:** Does the selected database transaction cover both new records and the import summary? The platform expert checks the actual library/version and runs a rollback experiment. A documentation claim about transactions alone would not settle which writes participate.

**ADR-EX-1:** Use one database transaction for the records and summary. Compare that with buffering the entire import and compensating deletes. Record memory cost, lock duration, and error-reporting tradeoffs. The named owner accepts the decision.

| Obligation | Acceptance condition | State when ADR is accepted |
| --- | --- | --- |
| O-1 | Valid input commits records and summary together | not started |
| O-2 | A later invalid row leaves both unchanged | not started |
| O-3 | Error identifies the invalid row | not started |

**WL-EX-1:** Implement transactional import, covering all three obligations. Track: import. Milestone: first usable importer. Implementation category: advanced. Review: one independent reviewer; the project may raise this if stored-data impact warrants it.

The coordinator assigns an implementation worktree with a known base. An independent test brief specifies a valid file, a failure after one valid row, and the expected line number. The implementer writes the code and updates the plan with actual results.

The reviewer checks the combined candidate in a separate worktree. One experiment commits the first row early. The rollback test must now fail because stored data changed; a syntax error would not be useful proof. The reviewer removes the mutation and records the result against the candidate examined.

Suppose rollback and valid input pass, but the line number remains wrong. O-1 and O-2 can be marked implemented in candidate with evidence; O-3 remains open. The ADR is still accepted. The original work item cannot be called complete unless its scope is explicitly revised and the remaining obligation receives tracked work.

After all obligations pass and the required review is complete, the PR describes the final candidate. At merge, the forge identifies the actual integrated commit; a report or later bookkeeping update can link it to the obligations. If this project defines 'shipped' as released, release evidence remains pending even after merge.

The important transition is explicit: accepted design → candidate implementation → verified and reviewed candidate → integrated change → released behavior, if release is part of the project's lifecycle.
