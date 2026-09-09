# Optional automation — not implemented

Add machinery only after the manual records prove useful. Start with one local command, then call that same command from the chosen forge. Prompt instructions and local hooks help agents remember; required server-side checks enforce the project's merge policy.

1. **Verification entry point.** Configure `scripts/verify` with real project checks. Make checkout and comparison base explicit for change-sensitive validation. Reject zero relevant tests, skipped mandatory checks, and incomplete runs where the test tooling permits reliable detection.
2. **Reference checks.** Validate stable IDs, links, legal statuses, duplicate items, and ADR obligation references. Structure alone does not prove implementation.
3. **Completion checks.** Compare base and candidate. Require removed/completed work to have a durable record, archived plan where applicable, updated obligations, and relevant evidence. Support partial work explicitly.
4. **Review requirements.** Calculate potential risk from changed paths and declared affected requirements. Require review evidence for the candidate being integrated, from the configured independent reviewers. Protect policy changes from bypassing their own checks.
5. **Forge integration.** Run checks before merge and report integrated PR-to-commit relationships after merge. Close an issue only when its complete scope is satisfied. Keep the offline workflow usable when services are unavailable.
6. **Drift report.** Surface accepted ADR obligations with no implementation or remaining work, stale behavioral evidence, and completed work with missing integration records.

Choose schemas, protected-branch settings, identity/provenance mechanisms, and forge adapters in the consuming project. This package provides no issue synchronization, CI workflow, self-hash receipt mechanism, or automatic semantic proof.
