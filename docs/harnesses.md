# Harness adapters

Keep shared rules in `AGENTS.md` and role prompts in `docs/roles/`. Test instruction loading in the exact harness and version you use.

The root `CLAUDE.md` imports `AGENTS.md` using Claude Code's documented `@path` syntax. Its role wrappers explicitly tell each subagent to read the shared rules and relevant role file. Implementer and reviewer wrappers request worktree isolation. All wrappers use `model: inherit`; select appropriate models through your actual configuration before delegation. Inheritance is not capability enforcement.

Claude Code reference: [memory imports](https://code.claude.com/docs/en/memory) and [subagent configuration](https://code.claude.com/docs/en/sub-agents).

Codex uses `AGENTS.md` instructions according to its discovery and scope rules. The Claude subagent wrappers do not configure Codex agents. Supply the shared role prompt and delegation brief explicitly when delegating in another harness. Reference: [AGENTS.md guidance](https://learn.chatgpt.com/docs/agent-configuration/agents-md).

For other harnesses and local-model runtimes, configure an entry point that reads the shared contract, project configuration, and assigned role. This package includes no tested adapters for them. Do not assume every tool recognizes the same filenames, imports, permissions, or isolation settings.

Adapter prompts constrain intended behavior; actual filesystem isolation, tool permissions, and review identity depend on the harness. Smoke-test those before giving agents concurrent modifying work.
