# agents — Federal Contracting Agent Packages

Open-source agent packages for federal acquisition work, based on the
[1102tools federal-contracting-agents](https://github.com/1102tools-dev/federal-contracting-agents)
catalog. Each package is self-contained: it vendors its own skills, deterministic
validators, runtime guidance, and pinned MCP server configuration, so one install
covers one federal contracting job end to end.

## Scope

Stewardship of the **Market Research** and **Acquisition Policy** agents is moving
here from the 1102tools marketplace. The remaining 1102tools agents — GovCon Growth,
Pre-Award, and Other Transaction — stay in that catalog.

## How the packages work

The skill is the portable source of truth. Native wrappers for Codex and Claude Code
improve discovery and presentation without duplicating domain logic. Packages follow
the [Agent Plugins 1.0](https://agent-plugins.org/specification) specification, and
agent versions are tracked separately from the marketplace catalog version.

## Requirements

- Codex (Desktop or CLI), or Claude Code (Desktop or CLI)
- Python 3.10 or newer
- [`uv` and `uvx`](https://docs.astral.sh/uv/)
- LibreOffice for full document rendering and workbook recalculation

No account is required. Some federal data providers need a free API key — `SAM_API_KEY`
for SAM.gov, `BLS_API_KEY` for wage data, `PERDIEM_API_KEY` for travel rates. USASpending
and GSA CALC+ need no key. Configure credentials in the environment that launches the
client, then restart it. Never paste a key into a conversation; no credentials are stored
in this repository.

## Install

Add this repository as a plugin marketplace, then install the agent you need.

```bash
# Claude Code
claude plugin marketplace add acqagent/agents
claude plugin install <agent-name>@acqagent

# Codex
codex plugin marketplace add acqagent/agents --ref main
codex plugin add <agent-name>@acqagent
```

Start a fresh session after installing. In Claude Code type `/` and begin typing the
agent name; in Codex type `@` and do the same.

## Related repositories

- [acqagent/skills](https://github.com/acqagent/skills) — portable acquisition skills
- [acqagent/mcps](https://github.com/acqagent/mcps) — federal contracting MCP servers

## Attribution

Originally built by James Jenrette. Independently developed and not endorsed by any
federal agency. MIT licensed.
