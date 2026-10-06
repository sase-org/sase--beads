# Bead: sase-1eq.12.3 — Relabel the macro-resolution infographic

[Bead Pages](../README.md) / [sase-1eq.12](sase-1eq.12.md) / sase-1eq.12.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1eq.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.land.md) · **Assignee:** `sase-1eq.12.3` · **Size:** small
**Created:** 2026-10-05 10:21:57 EDT · **Closed:** 2026-10-05 12:08:43 EDT
**Plan:** [202610/land\_xprompts\_to\_macros.md](https://github.com/sase-org/sase--plans/blob/main/202610/land_xprompts_to_macros.md)

## Description

infographic: Replace every retired xprompt label in docs/images/macro-resolution-infographic.png with its macro spelling through a deterministic ImageMagick overlay, then update its prompt record and final SHA. Follow the infographic section.

## Notes

[2026-10-05T16:08:23Z · sase-1eq.12.3--1] PROPOSED FOLLOW-UP: just check lint (feature flags) fails identically on clean base tree — tools/sync_macro_input_schemas --check reports workflow inputDefinitions schema out of sync (pre-existing, unrelated to infographic relabel files)

[2026-10-05T16:08:43Z · sase-1eq.12.3--1] Relabeled all 13 retired xprompt labels to macro spelling in docs/images/macro-resolution-infographic.png (1672x941 sRGB, SHA 7529a15d0c2a77f0144d3804cef156b315949de0bf0ac59872ad5ccdd63f314e); full-PNG OCR shows zero xprompt residuals vs 6 in base; all pixel changes confined to the 13 label windows; prompt record and critique SHA updated; prettier fmt fixed and fmt stages green; remaining check failure (sync_macro_input_schemas --check) reproduces identically on clean base tree, recorded as PROPOSED FOLLOW-UP; epic-symbols clean.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1eq.12.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.12.3.md) | [sase-1eq.12.3](sase-1eq.12.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`b6114d4`](https://github.com/sase-org/sase/commit/b6114d4f954f4ed990511254e7e46e6160513fc0) | docs(images): relabel macro-resolution infographic from retired xprompt spelling to macro | [sase-1eq.12.3](sase-1eq.12.3.md) | 2026-10-05 12:10:11 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1gt.land][1] | Need the causal infographic phase scope and notes before reporting new terminology evidence | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1gt.land/README.md

<!-- sase:referenced-by:end -->
