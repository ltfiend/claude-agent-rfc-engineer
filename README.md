# claude-agent-rfc-engineer

An IETF RFC engineer/editor [agent](https://code.claude.com/docs/en/sub-agents) for Claude Code: evaluates Internet-Drafts and protocol behavior against current RFCs for discrepancies and inaccuracies, builds proof-of-concept implementations for new protocol concepts, verifies interoperability with existing products, performs RFC 3552-style security analysis, and drafts properly formatted documentation updates (errata, OLD:/NEW: text, xml2rfc) — always gated on user approval. Specialized for DNS, with a protocol-agnostic methodology.

## Layout

- `rfc-engineer.md` — the agent definition (YAML frontmatter + system prompt)

## Install

Preferred: clone and symlink the agent file into your Claude Code agents directory so `git pull` updates the live agent:

```bash
git clone https://github.com/ltfiend/claude-agent-rfc-engineer.git
mkdir -p ~/.claude/agents
ln -s "$(pwd)/claude-agent-rfc-engineer/rfc-engineer.md" ~/.claude/agents/rfc-engineer.md
```

Alternatively, copy it in:

```bash
cp rfc-engineer.md ~/.claude/agents/
```

Claude Code picks the agent up at session start; Claude delegates to it for RFC/draft evaluation, protocol conformance checks, PoC and interop work, or invoke it explicitly by asking Claude to use the `rfc-engineer` agent.

## Related

The agent's DNS specialization reads local references from the companion skills when present: [claude-dns-skill](https://github.com/ltfiend/claude-dns-skill) (`dns-expert`) and [claude-bind-skill](https://github.com/ltfiend/claude-bind-skill) (`bind-admin`).
