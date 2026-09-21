# Bead: sase-14t.2 — Per-provider research swarm segments

[Bead Pages](../README.md) / [sase-14t](README.md) / sase-14t.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0oi](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0oi.md) · **Assignee:** `sase-14t.2` · **Size:** medium
**Created:** 2026-09-20 20:51:32 EDT · **Closed:** 2026-09-20 22:29:19 EDT
**Plan:** [202609/research\_swarm\_providers.md](https://github.com/sase-org/sase--plans/blob/main/202609/research_swarm_providers.md)

## Description

swarm: rewrite the research_swarm xprompt around four provider-gated researcher segments plus an always-run lead, rename its inputs to `<provider>` / `<provider>_model`, switch report suffixes to provider short names, move the clan declaration onto the lead, and update the plugin's config, tests, and docs.

## Notes

[2026-09-21T02:28:36Z · sase-14t.2] PROPOSED FOLLOW-UP: extend research-highlights agent_name_globs to grk/mus — top-level __grk/__mus drafts are not excluded by path globs and only cld/cdx agents are name-excluded, so new researchers would trigger per-draft Highlights PDFs; provider.py __a/__b docstring is also stale

[2026-09-21T02:29:19Z · sase-14t.2] just check green (ruff+mypy+58 passed); dry-run plan_typed_launch_units shows shared clan research.0 with tribe/summary resolving on lead declarer, so no Jinja fallback needed; defaults expand to cdx+cld+lead, grok/muse opt-in, disables/flags drop segments, all-off yields solo lead

## Dependencies

- **Depends on:** [sase-14t.1](sase-14t.1.md) ✓ · ⧖ 2026-09-20
- **Blocks:** [sase-14t.3](sase-14t.3.md) ◐ · ⧖ 2026-09-20
- **Blocks:** [sase-14t.4](sase-14t.4.md) ✓ · ⧖ 2026-09-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-14t.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-14t.2/README.md) | [sase-14t.2](sase-14t.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-research-artifacts | [`sase-research-artifacts@343a1ec`](https://github.com/sase-org/sase-research-artifacts/commit/343a1ecd5458a97ab038bbb8413dc52fe3e4775a) | feat(research): gate swarm researchers per provider | [sase-14t.2](sase-14t.2.md) | 2026-09-20 22:30:52 EDT |
