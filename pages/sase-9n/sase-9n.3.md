# Bead: sase-9n.3 — Emit \`split\_file.\<full\_module\>.@\` member names from the toobig\_split chop

[Bead Pages](../README.md) / [sase-9n](README.md) / sase-9n.3

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-9n.3` · **Size:** small
**Created:** 2026-07-25 16:59:41 UTC · **Closed:** 2026-07-25 18:28:58 UTC
**Plan:** [202607/toobig\_split\_at\_names.md](https://github.com/sase-org/sase--plans/blob/main/202607/toobig_split_at_names.md)

## Description

"Phase 3 - Chop: emit split_file.<module>.@ names" section: change `_agent_name` in the bugyi-chops `toobig_split` module to drop the path digest and the 48-character slug truncation and end the member name with `.@`, update its tests, and bump the `sase` floor to the release that contains the planner change.

## Notes

Implemented in gh:bbugyi200/bugyi-chops: toobig_split now emits split_file.<full dotted module>.@ member names, tests cover authored templated names, SASE planning to concrete toobig-0...0 names, and full-path preservation after removing the 48-char truncation. Verification: BUGYI_CHOPS_VENV_BIN=/home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_17/.venv/bin just check passed. PyPI currently reports sase latest 0.11.1, so the existing 0.12.0 floor was left unchanged as the next release floor.

## Dependencies

- **Depends on:** [sase-9n.2](sase-9n.2.md) ✓
