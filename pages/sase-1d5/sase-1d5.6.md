# Bead: sase-1d5.6 — Audience badges, access states, and bead-page embeds

[Bead Pages](../README.md) / [sase-1d5](README.md) / sase-1d5.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0tz](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0tz.md) · **Assignee:** `sase-1d5.6` · **Size:** medium
**Created:** 2026-09-30 01:57:16 EDT · **Closed:** 2026-09-30 13:27:48 EDT
**Plan:** [202609/public\_bead\_attachments.md](https://github.com/sase-org/sase--plans/blob/main/202609/public_bead_attachments.md)

## Description

presentation: add 🌐/🔒 audience badges in show, read, history, and attachment list plus JSON visibility. Add the 🔒 no access, ⧉ on origin with dispatch hint, and ⛔ blocked states. Bead pages link public files, embed public images, render tokens as chips, and never show private digests or reasons.

## Notes

[2026-09-30T17:27:22Z · sase-1d5.6] PROPOSED FOLLOW-UP: just check _setup validate_sase_core_rs prompt-prediction probe fails identically on clean base (exit 1, confident False, support 3 vs min_support 4; sase-1d5.4 already tracks this)

[2026-09-30T17:27:48Z · sase-1d5.6] presentation landed: 🌐/🔒 badges on show/read/history/attachment list descriptors; read --format json and attachment list -j gain materialized visibility plus local audience_reason; new no_access/blocked/origin_only states with badges, %dispatch hint, and pager parity; bead pages link public files via raw attachments-sidecar URLs, embed public images (4/note, auto-fetch cap), render tokens as links/chips, never show private digests or reasons; docs badges table updated. Verified: new 17-test presentation suite plus ~640 neighboring tests pass; ruff/mypy clean; symvision unchanged vs base. just check _setup validate_sase_core_rs probe fails identically on clean base (recorded as PROPOSED FOLLOW-UP). TUI detail lines inherit badge prefixes via shared helper; sase-1d5.7 owns TUI chips/goldens.

## Dependencies

- **Depends on:** [sase-1d5.4](sase-1d5.4.md) ✓ · ⧖ 2026-09-30
- **Blocks:** [sase-1d5.7](sase-1d5.7.md) ✓ · ⧖ 2026-09-30
- **Blocks:** [sase-1d5.8](sase-1d5.8.md) ✓ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1d5.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1d5.6/README.md) | [sase-1d5.6](sase-1d5.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`451b161`](https://github.com/sase-org/sase/commit/451b1619ea62fb6cb889223a9ad71e65e0457928) | feat(bead-attachments): audience badges, access states, and bead-page embeds (sase-1d5.6) | [sase-1d5.6](sase-1d5.6.md) | 2026-09-30 13:30:25 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1d5.6][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1d5.6/README.md

<!-- sase:referenced-by:end -->
