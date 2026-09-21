# Bead: sase-157.6 — Decide how attachment validation treats symlinked ancestors

[Bead Pages](../README.md) / [sase-157](README.md) / sase-157.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0oj](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0oj.md) · **Assignee:** `sase-157.6` · **Size:** medium
**Created:** 2026-09-21 06:25:50 EDT · **Closed:** 2026-09-21 08:26:57 EDT
**Plan:** [202609/macos\_portability.md](https://github.com/sase-org/sase--plans/blob/main/202609/macos_portability.md)

## Description

gateway-attachments: adjudicate whether a platform symlink ancestor should make a notification attachment undownloadable, implement the decision in validate_attachment_path, and fix the five route tests.

## Notes

[2026-09-21T12:26:57Z · sase-157.6] Took branch (b): symlinked ancestors allowed (macOS /tmp,/var aliases), final-component symlink + ParentDir traversal still rejected; canonical path stored in token and re-verified at download. Changed routes/support.rs (validate_attachment_path + is_symlink, decision comment), contract.rs:410 wording + regenerated mobile_api_v1.json snapshot, added symlink_pointing_outside_tmp_is_not_downloadable test. Verified: ./scripts/check.sh all green on Linux; 27/27 notification+contract tests pass natively on mac; old code fails under symlinked TMPDIR while new code passes (sensitivity check); mac checkout restored clean; no epic-symbol leftovers.

## Dependencies

- **Depends on:** [sase-157.3](sase-157.3.md) ✓ · ⧖ 2026-09-21
- **Blocks:** [sase-157.9](sase-157.9.md) ✓ · ⧖ 2026-09-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-157.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-157.6/README.md) | [sase-157.6](sase-157.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@3f56910`](https://github.com/sase-org/sase-core/commit/3f569106e7b4d3711c0daa2987daf666e328c2c3) | fix(gateway): allow symlinked ancestors in attachment validation | [sase-157.6](sase-157.6.md) | 2026-09-21 08:30:42 EDT |
