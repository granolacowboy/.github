# Public development policy

AI-assisted development is normal in these repositories. Public Git history should record the engineering change, not the execution transcript of the tool that helped produce it.

## Public record

Keep pull requests and commits focused on information useful to a maintainer:

- what materially changed;
- why the change matters when the reason is not obvious from the diff;
- validation performed;
- security, compatibility, or operational consequences;
- durable decisions or invariants that future work must preserve.

Do not place model attribution, agent session URLs or IDs, prompt transcripts, tool chatter, or generated-by boilerplate in pull request metadata or commit messages.

Ordinary technical references to AI systems are expected and are not discouraged. A change involving Claude, Codex, an LLM API, an agent framework, or another AI component should name that technology when it is relevant to the engineering.

## Durable reasoning

Promote reasoning according to its value:

- current repository invariants belong in `AGENTS.md` or equivalent maintainer guidance;
- non-obvious decisions with meaningful alternatives or reversal cost belong in `DECISIONS.md`, an ADR, or an appropriate design document;
- verification evidence belongs with tests, reports, or the pull request;
- agent execution telemetry belongs outside public Git history.

Raw agent transcripts are not durable project documentation and should not be copied into repositories by default.

## Merge history

Curated public repositories should use squash merges with a concise pull request title as the canonical public change record. Intermediate agent/worktree commits are implementation detail; the resulting `main` history should remain readable without knowledge of the agent runtime.
