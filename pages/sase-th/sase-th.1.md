# Bead: sase-th.1 — Delete the dead glossary and memory-web symbols

[Bead Pages](../README.md) / [sase-th](README.md) / sase-th.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0d8](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0d8.md) · **Assignee:** `sase-th.1` · **Size:** small
**Created:** 2026-08-25 07:31:59 EDT · **Closed:** 2026-08-25 07:46:36 EDT
**Plan:** [202608/repair\_red\_master\_ci.md](https://github.com/sase-org/sase--plans/blob/main/202608/repair_red_master_ci.md)

## Description

symvision: retire the ten unused public symbols the config-glossary retirement stranded, so the lint job's symvision stage passes again.

## Notes

[2026-08-25T11:46:08Z · sase-th.1] PROPOSED FOLLOW-UP: Fix repo formatting drift in src/sase/sdd/_store_link.py — just check fails at ruff format --check before lint/tests; the file is clean/untouched in this phase.

[2026-08-25T11:46:36Z · sase-th.1] Verified exact symvision PASS, targeted pytest PASS, changed-file ruff format/check PASS; just check reached pre-existing clean-file fmt failure in src/sase/sdd/_store_link.py and follow-up noted.

## Dependencies

- **Blocks:** [sase-th.7](sase-th.7.md) ◐ · ⧖ 2026-08-25

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-th.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-th.1/README.md) | [sase-th.1](sase-th.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5fff948`](https://github.com/sase-org/sase/commit/5fff948a9735e7f613006a10c8cb34ea8c363d88) | fix(memory): retire dead glossary symbols | [sase-th.1](sase-th.1.md) | 2026-08-25 07:47:55 EDT |
