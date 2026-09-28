# Architecture decisions

Create records from `templates/adr.md`. Keep accepted reasoning available; substantive reversals need a linked superseding decision. Correct factual errors transparently without rewriting an accepted decision to imply it always said something else.

Decision lifecycle: **Proposed → Accepted**, or **Proposed → Withdrawn**. An accepted decision may later be **Superseded** or **Deprecated**. Record who accepted it and when, under the project's authority rules.

Implementation is a separate dimension, recorded once per ADR on its own line: **open** (no obligation implemented), **partial** (some implemented, the rest still intended), **partial-closed** (some implemented, the rest deferred or retired, and the ADR states which and why), or **complete**. The change that implements an obligation updates this line in the same diff as the code, and review checks the claim against code and tests. The line therefore cannot run ahead of the integrated code. A missing line means unknown: verify in code. A partly delivered ADR stays accepted.

Per-obligation truth lives where it can be checked: code, tests, and evidence records that cite the obligation IDs. A table of per-obligation states and evidence links inside the ADR drifts from the code it describes, and a specification that reads as further along than the code misleads the next implementer.

References inside an ADR point only at durable in-repository records: decision and obligation IDs, requirement IDs, evidence-record IDs, commit IDs, and repository paths. Never issue or pull-request numbers, forge URLs, or work-queue IDs. Issue text is revised in place, and forge numbers do not survive a migration. The direction is one-way: work items and pull requests cite the ADR, and the ADR states its own deferrals. Implementation history is derived from Git, never written into the ADR: the commit that last changed the implementation line leads to its merge commit and pull request.

Record every alternative actually weighed and why it lost, including designs built and then replaced during implementation. A decision whose rejected options are missing gets relitigated.

Historical shipment evidence survives later changes. Evidence that behavior still holds can become stale when the relevant code or environment changes. Do not confuse those two claims.
