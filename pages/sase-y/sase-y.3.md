# Bead: sase-y.3 — Phase 3 — Optional Agent-Friendly CLI Improvements

[Bead Pages](../README.md) / [sase-y](README.md) / sase-y.3

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-y.3`
**Created:** 2026-04-27 18:27:51 UTC · **Closed:** 2026-04-27 18:50:04 UTC
**Plan:** [202604/changespec\_skill\_1.md](https://github.com/sase-org/sase--plans/blob/main/202604/changespec_skill_1.md)

## Description

If Phase 2 finds search output insufficient, add a small machine-readable ChangeSpec CLI surface such as sase changespec show <name> -j, --raw, and list -q '<query>' -j, following existing parser conventions and short-option requirements. If existing search is sufficient, document the skip decision and close this phase without source changes.

## Notes

Phase 3 skipped — no source changes.

Decision: Phase 2 (sase-y.2, commit 959eb3dd) validated that 'sase search -f markdown' and 'sase search -f plain' are sufficient for the sase_changespecs skill across the representative agent workflows (exact lookup, project/status, ancestor/dependency, error/running-state, archive lookup). The only regression-coverage gap — that '&name' is exact and not substring — was filled by tests/test_query_property_filters_name_sibling.py in that commit.

Per this bead's own description ('If existing search is sufficient, document the skip decision and close this phase without source changes'), the optional 'sase changespec show <name> -j / --raw' and 'sase changespec list -q <query> -j' surface is not needed and is intentionally not added. Phase 4 should refine the skill against the existing 'sase search -f markdown/plain' command surface.

## Dependencies

- **Depends on:** [sase-y.2](sase-y.2.md) ✓
- **Blocks:** [sase-y.4](sase-y.4.md) ✓
