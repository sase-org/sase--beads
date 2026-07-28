# Bead: sase-u.3 — Phase 3 — Selective row updates + render-result caching

[Bead Pages](../README.md) / [sase-u](README.md) / sase-u.3

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-u.3`
**Created:** 2026-04-26 07:23:44 UTC · **Closed:** 2026-04-26 08:51:59 UTC
**Plan:** [202604/instant\_jk\_navigation.md](https://github.com/sase-org/sase--plans/blob/main/202604/instant_jk_navigation.md)

## Description

Single-row state changes patch only the affected row via OptionList.replace_option_at. Memoize format_agent_option/format_banner_option keyed on stable inputs. Apply to ChangeSpecs and Axe tabs as well.

## Notes

COMMIT: 50a21c6b

## Dependencies

- **Depends on:** [sase-u.2](sase-u.2.md) ✓
- **Blocks:** [sase-u.4](sase-u.4.md) ✓

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`e2f4617`](https://github.com/sase-org/sase/commit/e2f4617bcfb2df449d8dbcb296f4f3367a3d73ba) | feat(ace): selective row updates + render-result cache for agents tab (sase-u.3) | [sase-u.3](sase-u.3.md) | 2026-04-26 08:52:03 |
