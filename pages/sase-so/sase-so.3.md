# Bead: sase-so.3 — Emit keyed basename templates from bugyi-chops

[Bead Pages](../README.md) / [sase-so](README.md) / sase-so.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0c6](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0c6.md) · **Assignee:** `sase-so.3` · **Size:** small
**Created:** 2026-08-24 07:02:27 EDT · **Closed:** 2026-08-24 07:23:49 EDT
**Plan:** [202608/toobig\_split\_identity\_tribe.md](https://github.com/sase-org/sase--plans/blob/main/202608/toobig_split_identity_tribe.md)

## Description

keyed_basename_names: replace full path member names with stable collision-safe keyed basename templates in the plugin.

## Notes

[2026-08-24T11:23:49Z · sase-so.3] Keyed basename templates land in bugyi-chops: _agent_name now emits <basename>.{@<path-digest>} under clan toobig-@, with no split_file. or parent path segments. Verified raw proposals have one stable keyed marker per path, duplicate basenames stay collision-safe, and SASE planning yields toobig-0.large.0 / toobig-0.shared.0 / toobig-0.large.1. Bridge tests inspect dispatched prompts (not mocked names): eligible launch identity is toobig-0.large.0; skipped first proposal launches the surviving shared member with clan metadata intact; a tail re-plan makes that member the declarer. README examples updated. just install + just check passed in the opened checkout against this SASE venv (ruff/mypy/95 tests/twine).

## Dependencies

- **Blocks:** [sase-so.4](sase-so.4.md) ◐ · ⧖ 2026-08-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-so.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-so.3/README.md) | [sase-so.3](sase-so.3.md) | 0 |
