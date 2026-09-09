# Architecture decisions

Create records from `templates/adr.md`. Keep accepted reasoning available; substantive reversals need a linked superseding decision. Correct factual errors transparently without rewriting an accepted decision to imply it always said something else.

Decision lifecycle: **Proposed → Accepted**, or **Proposed → Withdrawn**. An accepted decision may later be **Superseded** or **Deprecated**. Record who accepted it and when, under the project's authority rules.

Implementation is a separate dimension, recorded per obligation: **not started**, **partial**, or **implemented in candidate**. Integration and release each get separate evidence when known. A partly delivered ADR remains accepted; acceptance does not close its obligations.

Every open obligation should have linked remaining work. Every implementation claim should identify the implementation and evidence, with limitations. When active backlog headings are removed, preserve the work ID and resolve it through an archived plan, issue, or Git history.

Historical shipment evidence survives later changes. Evidence that behavior still holds can become stale when the relevant code or environment changes. Do not confuse those two claims.
