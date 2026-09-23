# Bead: sase-170.4 — Clan-level tribe edits from the Agents tab

[Bead Pages](../README.md) / [sase-170](README.md) / sase-170.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0pw.w0](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0pw.w0.md) · **Assignee:** `sase-170.4` · **Size:** medium
**Created:** 2026-09-23 11:39:57 EDT · **Closed:** 2026-09-23 14:06:59 EDT
**Plan:** [202609/tribe\_clan\_summaries\_and\_clan\_records.md](https://github.com/sase-org/sase--plans/blob/main/202609/tribe_clan_summaries_and_clan_records.md)

## Description

clan_tribe_edits: make the tribe modal on a clan member or the synthetic clan row write an Edited clan record (including sticky unsets) through the durable directive path, with optimistic display, modal copy, docs, and tests.

## Notes

[2026-09-23T18:06:10Z · sase-170.4] PROPOSED FOLLOW-UP: symvision flags ClanSummaryDigest in _agent_tribe_clan_summaries.py as unused-public (pre-existing on clean tree, from phase 170.1) — just check stays red until it is privatized, used cross-module, or whitelisted

[2026-09-23T18:06:59Z · sase-170.4] Clan tribe edits write Edited records (source edited/identity tui) with canonicalized names; synthetic rows do record-only edits, member edits keep meta+prompt rewrites, one record per (clan,generation) deduped. Verified: 40 focused tribe/directive tests pass, just test-scoped 2461 passed, ruff+mypy+all other just-check gates green. Only failure is pre-existing symvision unused-public ClanSummaryDigest from phase 170.1, confirmed on clean tree and filed as PROPOSED FOLLOW-UP.

## Dependencies

- **Depends on:** [sase-170.3](sase-170.3.md) ✓ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-170.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-170.4/README.md) | [sase-170.4](sase-170.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`372135a`](https://github.com/sase-org/sase/commit/372135af742b8ec04e08ce47781a94de289ae3eb) | feat(clans): clan-level tribe edits from the Agents tab | [sase-170.4](sase-170.4.md) | 2026-09-23 14:20:05 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-170.4][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-170.4/README.md

<!-- sase:referenced-by:end -->
