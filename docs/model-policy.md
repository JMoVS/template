# Optional capability and review policy

This is a planning convention. No enforcement or model identity verification is implemented here.

Use capability categories that can be remapped as models change. Keep exact model/version and reasoning settings in project configuration, informed by performance on the project's tasks.

| Category | Suitable starting scope |
| --- | --- |
| Bounded | Mechanical changes with explicit scope and strong checks |
| Advanced | Multi-file implementation, routine design tradeoffs, substantial debugging |
| Frontier | Novel architecture, difficult failure analysis, consequential independent review |

These are routing hints, not measured intelligence scores. A smaller local model may implement a well-specified item while a stronger reviewer is required before integration. Leave the item pending review when that reviewer is unavailable offline.

Each work item can record an advisory implementation category, minimum review category, required independent reviews, and the reason. When newly affected requirements raise the risk, reassess the review requirement before integration. A deterministic path/requirement map can flag potential impact; it cannot discover all semantic effects. Require an explicit impact assessment too.

If adopted later as a merge rule, use protected policy and trusted harness/CI provenance for actual model/version, reasoning setting, role, candidate revision, and outcome. A model's self-written 'frontier reviewed' label is not attestation. Missing provenance remains unverified. Two passes by the same implementer are not independent review, and multiple agents can share blind spots.

Permit documented, authorized exceptions where the project chooses; record the reason and residual risk. Do not silently downgrade requirements to make a gate pass.
