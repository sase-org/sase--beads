# Bead: sase-ik.3 — Consume segments in ACE, guard the floor, and correct the docs

[Bead Pages](../README.md) / [sase-ik](README.md) / sase-ik.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.ws](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.ws/README.md) · **Assignee:** `sase-ik.3` · **Size:** medium
**Created:** 2026-08-09 15:55:03 EDT · **Closed:** 2026-08-10 08:14:29 EDT
**Plan:** [202608/glossary\_line\_break\_matching.md](https://github.com/sase-org/sase--plans/blob/main/202608/glossary_line_break_matching.md)

## Description

python: move the sase-core-rs window, carry span segments through the facade into the prompt highlight map, normalize wrapped matched text in the preview card, add a published-minimum smoke gate, and fix the docs that promise line-local matching.

## Notes

[2026-08-10T11:58:56Z · sase-ik.3] PROPOSED FOLLOW-UP: Refresh generated memory README validation output — `just check-full` fails `sase validate` because `init memory --check` wants to update ~/.local/share/chezmoi/home/sase/memory/README.md (+2/-3), unrelated to this phase.

[2026-08-10T11:59:05Z · sase-ik.3] PROPOSED FOLLOW-UP: Stabilize prompt-highlighting visual snapshots against prompt catalog workers — running the full `tests/ace/tui/visual/test_ace_png_snapshots_prompt_highlighting.py` file under `just test-visual` timed out existing cases on pending worker `prompt-catalog:0`; the new wrapped-glossary snapshot passes when that warm is suppressed locally.

[2026-08-10T12:12:08Z · sase-ik.3] PROPOSED FOLLOW-UP: Investigate stale full non-visual `just test` lane under xdist — this phase’s full `just test` attempt remained non-terminal for over twelve minutes with no accessible output, matching the repo’s existing governed-suite instability rather than the focused glossary tests.

[2026-08-10T12:14:29Z · sase-ik.3] Implemented Python segment consumption, core floor ratchet, preview normalization, CI smoke, docs, tests, and wrapped PNG snapshot. Verified: just install; just fmt; smoke_sase_core_rs_glossary_line_break; exact published-floor smoke; validate_sase_core_rs_version --published-minimum; focused pytest 59 passed; wrapped visual snapshot 1 passed; git diff --check. just check-full reached validation and failed on unrelated generated memory README drift; full just test attempt went stale; follow-ups noted.

[2026-08-10T12:16:12Z · sase-ik.3] Verified glossary segment consumer phase: install/formatting passed; smoke_sase_core_rs_glossary_line_break passed against installed and exact published floor 0.23.0; validate_sase_core_rs_version --published-minimum passed; focused non-visual pytest passed with 59 tests; wrapped glossary PNG snapshot passed; git diff --check clean. Known unrelated gaps recorded as PROPOSED FOLLOW-UP notes: generated memory README validation drift and stale full just test lane.

## Dependencies

- **Depends on:** [sase-ik.2](sase-ik.2.md) ✓ · ⧖ 2026-08-09

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ik.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ik.3/README.md) | [sase-ik.3](sase-ik.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`12af4fe`](https://github.com/sase-org/sase/commit/12af4fefe097d6c2bfea9e8f636609aad03aa612) | feat(glossary): consume wrapped match segments in ACE | [sase-ik.3](sase-ik.3.md) | 2026-08-10 08:17:14 EDT |
