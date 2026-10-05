# Bead: sase-1g6.4 — Scan carries audio into the library and embeds the player

[Bead Pages](../README.md) / [sase-1g6](README.md) / sase-1g6.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.research.0b.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.research.0b.linker.w0.md) · **Assignee:** `sase-1g6.4` · **Size:** medium
**Created:** 2026-10-04 18:40:14 EDT · **Closed:** 2026-10-04 20:43:34 EDT
**Plan:** [202610/research\_swarm\_listen\_card.md](https://github.com/sase-org/sase--plans/blob/main/202610/research_swarm_listen_card.md)

## Description

bob-scan-audio: move same-stem audio with its PDF, late-pair orphan audio to an already-scanned PDF, add bob-managed `audio` frontmatter, insert the `![[lib/<type>/<stem>.mp3]]` player once below the PDF task, report orphans in doctor, and document it.

## Notes

[2026-10-05T00:37:59Z · sase-1g6.4] PROPOSED FOLLOW-UP: sase-1g6.2 create audio discovery did not land on origin (HEAD 99293a5 is the listen-card banner; bound_audio_path only looks for a same-stem .mp3 already beside the PDF). Scan late-pairing still backfills if the MP3 is dropped in xlib; do not reimplement create discovery in this phase.

[2026-10-05T00:38:05Z · sase-1g6.4] PROPOSED FOLLOW-UP: fix the pre-existing bob-cli clippy hard failure at tests/cli/capture/pomodoro_name.rs:808 (unconditional || true); identical on origin/master so just all stops at lint; recorded by sase-1g6.2 and sase-1g6.3; no existing task bead tracks it.

[2026-10-05T00:43:07Z · sase-1g6.4] PROPOSED FOLLOW-UP: cargo test --test cli completion::zsh_adapter::real_zsh_first_tab_completes failed once in the full parallel suite with "zpty driver failed" despite SETUP OK/FIRST-TAB OK; passes in isolation on this tree and on clean origin; no existing task bead tracks it.

[2026-10-05T00:43:34Z · sase-1g6.4] Scan moves same-stem audio with PDF intake, late-pairs xlib audio onto existing lib PDFs, writes command-managed audio frontmatter plus one-shot player embed, and doctor warns on orphans without failing. cargo fmt --check pass; 107 highlights_ref unit tests pass; 85 highlights_ref CLI tests pass (intake+embed, late-pair/deleted-embed stays deleted, destination conflict, doctor orphan warning). No --epic-symbol leftovers. just all stops at the pre-existing clippy deny in tests/cli/capture/pomodoro_name.rs:808 (identical on origin; recorded as follow-up citing sase-1g6.2). Full cargo test: 955 CLI passed; one zsh completion flake in the parallel suite that passes in isolation on this tree and on origin.

## Dependencies

- **Depends on:** [sase-1g6.2](sase-1g6.2.md) ✓ · ⧖ 2026-10-04
- **Depends on:** [sase-1g6.3](sase-1g6.3.md) ✓ · ⧖ 2026-10-04

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1g6.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1g6.4/README.md) | [sase-1g6.4](sase-1g6.4.md) | 0 |
