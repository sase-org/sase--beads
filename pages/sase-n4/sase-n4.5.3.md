# Bead: sase-n4.5.3 — Restore disable provenance and document usage-limit policy

[Bead Pages](../README.md) / [sase-n4.5](sase-n4.5.md) / sase-n4.5.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-n4.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-n4.land.md) · **Assignee:** `sase-n4.5.3` · **Size:** medium
**Created:** 2026-08-16 14:20:19 EDT · **Closed:** 2026-08-16 15:01:30 EDT
**Plan:** [202608/finish\_usage\_limit\_auto\_disable.md](https://github.com/sase-org/sase--plans/blob/main/202608/finish_usage_limit_auto_disable.md)

## Description

surface-and-document: render automatic, manual, and unknown disable provenance in the current split Launch Control provider modules and top-bar tooltip, add the commented usage_limit configuration block without disturbing newer config fields, document detection, reset hints, machine-wide expiry, clearing, retry precedence, and extension/replacement semantics, and cover the surfaces including intentional visual snapshots.

## Notes

[2026-08-16T18:48:20Z · sase-n4.5.3] PROPOSED FOLLOW-UP: Clean up stale Symvision epic-symbol entries for closed bead sase-na.2 — just check fails before scoped tests because RankedWord, WordRankingContext, build_word_ranking_context, rank_history_words, and rank_recent_history_words are still whitelisted against the closed bead.

[2026-08-16T18:57:40Z · sase-n4.5.3] PROPOSED FOLLOW-UP: Triage unrelated escalated verification failures — test-scoped escalated to the full suite and failed six tests/test_file_panel.py render/update assertions plus tests/test_bead/test_cli_golden.py::test_bead_cli_golden_contract[stats] adding "Flags: 0"; the focused provenance unit tests and updated provider-routing visual snapshots pass.

[2026-08-16T19:00:11Z · sase-n4.5.3] PROPOSED FOLLOW-UP: Triage unrelated top-level Models Panel visual mismatch — tests/ace/tui/visual/test_ace_png_snapshots_models_panel.py::test_models_panel_provider_disabled_png_snapshot differs only in a far-right background region outside the modal while the provider-routing modal provenance snapshots pass exactly.

[2026-08-16T19:01:30Z · sase-n4.5.3] Implemented provider-disable provenance labels in Launch Control provider rows/descriptions and top-bar tooltip, added the commented llm_provider.usage_limit default-config block, updated configuration/LLM/ACE docs, and accepted provider-routing modal PNG snapshots after inspecting expected/actual/diff artifacts. Verified: just install; just fmt; pytest tests/test_models_panel_provider_rendering.py tests/test_provider_disables_indicator.py; just test-visual provider-routing modal, until-cleared, and narrow snapshots; provider-disable indicator visual snapshots passed; git diff --check. just check is blocked by unrelated stale Symvision closed-bead entries; test-scoped escalated to full suite and hit unrelated file_panel/bead stats failures; top-level Models Panel visual background mismatch is unrelated. Proposed follow-up notes recorded on this phase bead.

[2026-08-16T19:04:47Z · sase-n4.5.3] Implemented provider-disable provenance display in Launch Control rows, selected-provider descriptions, and top-bar tooltip; added commented usage-limit defaults plus docs and focused unit/visual coverage. Verified just install, just fmt, focused provider rendering and indicator pytest, provider-routing modal PNG snapshots, provider-disable indicator PNG snapshots, and git diff --check. just check was blocked by unrelated Symvision whitelist state, and the escalated scoped lane hit unrelated file_panel/bead stats failures recorded as PROPOSED FOLLOW-UP notes.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-n4.5.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-n4.5.3/README.md) | [sase-n4.5.3](sase-n4.5.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`2509e39`](https://github.com/sase-org/sase/commit/2509e3990c17db2a237e57f945357934f9b7ede3) | feat: show provider-disable provenance in Launch Control | [sase-n4.5.3](sase-n4.5.3.md) | 2026-08-16 15:06:05 EDT |
