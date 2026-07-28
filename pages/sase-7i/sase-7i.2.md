# Bead: sase-7i.2 — Relink wait\_on chains across dedupe-skipped proposals

[Bead Pages](../README.md) / [sase-7i](README.md) / sase-7i.2

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-7i.2`
**Created:** 2026-07-19 17:20:08 UTC
**Plan:** [202607/fix\_toobig\_split\_chop\_dedupe.md](https://github.com/sase-org/sase--plans/blob/main/202607/fix_toobig_split_chop_dedupe.md)

## Description

'Relink wait_on chains across dedupe-skipped proposals' section: change apply_chop_once_per so a proposal whose wait_on dependency was skipped as a once-per duplicate is relinked to its nearest accepted ancestor instead of being skipped, with launch and preview plumbing for the remapped waits.

## Notes

COMMIT: 7ef34829e

## Dependencies

- **Blocks:** [sase-7i.5](sase-7i.5.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-7i.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-7i.2/README.md) | [sase-7i.2](sase-7i.2.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`7ef3482`](https://github.com/sase-org/sase/commit/7ef34829ef0a31143a358bab6e6ccb85006046dc) | fix(axe): relink waits across deduped chop proposals (sase-7i.2) | [sase-7i.2](sase-7i.2.md) | 2026-07-19 17:42:53 |
