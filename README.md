# Engineering with agents: a project starter

A small, language-neutral scaffold for projects developed over many sessions with different coding agents. It combines four useful roles with durable requirements, architecture decisions, a single work queue, and evidence of completion.

Start small: an implementer and an independent reviewer are often enough. Add an architect when a consequential decision is unresolved, and a platform expert when an uncertain fact could change the design.

## Start here

1. Give your agent [START-HERE.md](START-HERE.md) to adopt this in a fresh or existing project. It contains a paste-ready prompt and the adaptation procedure.
2. For a fresh repo, fill in [project configuration](docs/project.md) and [requirements](docs/requirements.md). For an existing repo, merge the useful parts into its established records using the adoption guide.
3. Adapt [AGENTS.md](AGENTS.md); choose who accepts decisions and who authorizes integration.
4. For a fresh repo, configure real checks in [scripts/verify](scripts/verify). It deliberately exits unsuccessfully until configured. Preserve existing verification when adopting.
5. Create the first bounded item in the authoritative queue. The supplied [BACKLOG.md](BACKLOG.md) is only a fresh-project starting point.
6. Choose a license before publishing this as a reusable public template.

Use this as a normal repository with a working tree. Git's `--bare` repository mode is a different thing and is unnecessary here. The starter contains no application code or chosen license.

## The parts

| Part | Purpose |
| --- | --- |
| [AGENTS.md](AGENTS.md) | Shared working contract |
| [Roles](docs/roles/README.md) | Architect, platform expert, implementer, reviewer |
| [Workflow](docs/workflow.md) | Worktrees, handoffs, offline work, completion |
| [ADRs](docs/adr/README.md) | Decision lifecycle and implementation obligations |
| [Templates](templates/README.md) | Copyable records and delegation briefs |
| [Model policy](docs/model-policy.md) | Optional capability and review expectations |
| [Harness adapters](docs/harnesses.md) | Shared rules with thin tool-specific entry points |
| [Automation roadmap](docs/automation-roadmap.md) | Proposed checks, explicitly unimplemented |

The role structure is drawn from an existing agent workflow. The generalized templates are a starting design, not a claim that every coding agent follows them reliably. This package supplies instructions and examples; it does not implement backlog synchronization, model attestation, or merge gates.

For sharing, start with the adoption guide and worked example. Use this repository as a template for fresh projects, or point an agent at START-HERE.md to adapt the workflow to an existing project. The workflow itself does not depend on a particular forge.
