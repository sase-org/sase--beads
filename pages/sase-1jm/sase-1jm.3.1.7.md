# Bead: sase-1jm.3.1.7 — Archive workflow regressions, performance evidence, and PNGs

[Bead Pages](../README.md) / [sase-1jm.3.1](sase-1jm.3.1.md) / sase-1jm.3.1.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1jm.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.3.md) · **Assignee:** `sase-1jm.3.1.7` · **Size:** medium
**Created:** 2026-10-10 20:21:23 EDT · **Closed:** 2026-10-11 18:26:13 EDT
**Plan:** [202610/agents\_archive\_view\_phase.md](https://github.com/sase-org/sase--plans/blob/main/202610/agents_archive_view_phase.md)

## Description

archive-proof: complete cross-phase regression coverage and deterministic Archive PNG fixtures, benchmark warm opening and j/k at archive scale, and capture targeted goldens through sase monitor. Inspect all golden changes and resolve implementation regressions. Verify both flag states, parking, detail ownership, no-write reading, isolation, query parity, and unaffected Inbox first paint; record evidence for the child epic land agent, without closing sase-1jm.3 or any ancestor.

## Notes

[2026-10-11T21:38:19Z · sase-1jm.3.1.7] PROPOSED FOLLOW-UP: banner/pulse/tail cursor leaves a stuck "Loading archived run…" placeholder — paint_archive_detail_placeholder clears via show_empty but the pushed titled card persists with the reader idle (runtime.loading=False, key=None); decide the banner-cursor detail contract (keep previous content vs empty) in the reader/detail owner phase

[2026-10-11T21:38:27Z · sase-1jm.3.1.7] PROPOSED FOLLOW-UP: Archive j/k key-to-paint p95 vs the 16 ms plan budget needs the CI slow-lane verdict — this host measures ~20 ms p50 (dispatch ~6 ms + frame/paint) while the pre-existing axe 16 ms bench measures p95 36 ms here, so the miss is host load, not an Archive regression; confirm on quiet runners via just test-slow

[2026-10-11T21:57:02Z · sase-1jm.3.1.7] EVIDENCE (archive-proof, pending final check c31ed998a46060b0008f183c63b8351b): 18/18 tests/ace/tui/test_agent_archive_proof.py green warning-free (flag states, parking round-trip, scope errors, pre-gate no-compile, identity stability, no-write marking, pulse-not-agent, guards+marks isolation, TUI-vs-CLI identity order on real corpus, footer-sync-on-snapshot); bench_tui_jk_archive wired into bench_tui_jk.py — warm open median 77.9 ms (<100, 7 samples, real 11k-row Rust corpus, SVG paint proof + revalidation settle) and Archive j/k paint samples via new route_archive_key hook (dispatch ~6 ms; p95/16 ms left to CI slow lane: this host gives ~20 ms while the pre-existing axe 16 ms bench gives p95 36 ms here); 9 Archive PNG goldens captured via fix-tui-screenshots (8 created + updates, manifest ff780616adb94a7387f081c5a67d88e2/48ae7c7194a541c787e6a3467682ad22, every golden pixel-inspected); fixed Archive conditional footer not installing on open (footer followed incidental renders only) by syncing on chrome activation + every applied snapshot; 2 PROPOSED FOLLOW-UP notes recorded (banner-cursor stuck loading placeholder; j/k CI confirmation)

[2026-10-11T22:25:43Z · sase-1jm.3.1.7--1] PROPOSED FOLLOW-UP: test_archive_missing_index_png_snapshot golden is capture-timing flaky — alternates between pass and a 978px/0.064% mismatch (tab-strip horizontal offset at row ~4 around `,a Inbox`), identical 978px diff on repeat runs of the unchanged tree; visual lane is excluded from just check; needs a tab-strip/pulse settle wait before capture or a golden re-capture

[2026-10-11T22:26:13Z · sase-1jm.3.1.7--1] Fixed the just-check failure: lint (test waits) flagged 5 waits in this phase's new files; added inline sase-test-wait pragmas to the 4 polling/soak asyncio.sleeps (bench_tui_jk_archive.py x2, visual snapshots x2) and replaced the bounded pause-scroll loop in the Archive help golden with wait_for_visual_idle (matching select_main_card pattern). Verified: just _lint-test-waits green, pinned ruff check and ruff format clean on both files, 18/18 test_agent_archive_proof.py green, Archive help PNG snapshot green; prior evidence stands (warm Archive open median 77.9ms <100ms on real 11k corpus with SVG paint proof, j/k dispatch ~6ms with p95/16ms left to CI slow lane, 9 goldens pixel-inspected, conditional footer syncs on chrome activation + every snapshot). Recorded one PROPOSED FOLLOW-UP: missing_index golden is capture-timing flaky (alternating pass/978px tab-strip offset, visual lane excluded from check). No epic-symbol leftovers.

## Dependencies

- **Depends on:** [sase-1jm.3.1.6](sase-1jm.3.1.6.md) ✓ · ⧖ 2026-10-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jm.3.1.7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.3.1.7.md) | [sase-1jm.3.1.7](sase-1jm.3.1.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`11e73e8`](https://github.com/sase-org/sase/commit/11e73e82325a3506489419bec9bcabc45a2dc194) | feat(agents-archive): proof coverage, benchmarks, and PNG goldens with test-wait lint fixes | [sase-1jm.3.1.7](sase-1jm.3.1.7.md) | 2026-10-11 18:30:07 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1jm.3.1.7--1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jm.3.1.7.md

<!-- sase:referenced-by:end -->
