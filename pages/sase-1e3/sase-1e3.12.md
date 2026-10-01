# Bead: sase-1e3.12 — Install, configure, field-test, and turn on delivery on apollo

[Bead Pages](../README.md) / [sase-1e3](README.md) / sase-1e3.12

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.3z](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.3z.md) · **Assignee:** `sase-1e3.12` · **Size:** medium
**Created:** 2026-10-01 14:43:02 EDT · **Closed:** 2026-10-01 19:09:33 EDT
**Plan:** [202610/sase\_listen.md](https://github.com/sase-org/sase--plans/blob/main/202610/sase_listen.md)

## Description

rollout: install sase-listen and upgrade the plugins on apollo, and add the config through chezmoi. Run doctor, deliver voice auditions and the first real audio edition (the commute-audio research itself) to Telegram, and initialize the feed. Record field notes and a docs sample, then propose Funnel exposure through a gate.

## Notes

[2026-10-01T22:51:36Z · sase-1e3.12] PROPOSED FOLLOW-UP: doctor --online credentials check not implemented in sase-listen 0.1.0 (reports "online check not implemented yet", exit 3); live credential verification falls back to audition render

[2026-10-01T23:07:32Z · sase-1e3.12] Rollout field report (apollo): installed sase-listen 0.1.0 from git source ef84b3b (no PyPI release exists); sase-telegram 0.4.24 + sase-research-artifacts 0.2.0 already current, sendAudio path verified in sase tool env. Chezmoi-managed config applied (narrator gemini, api_key_command pass show gemini_cli_api_key, secrets masked). doctor passes offline. Charon audition OK live (28.6s, 311KB, -16.28 LUFS, ~$0.0064). Narration script commute_audio_from_markdown_narration.md (1662w, 7ch) lint-clean, dry-run 9 chunks ~$0.15. Tone-engine full render OK (706.8s, 5.76MB, 7ch). Feed initialized (apollo.tail297af1.ts.net:8443, token path, auto_publish true), episode published, feed.xml parses. Charon clip + tone episode registered via sase artifact create for Telegram delivery. docs/field-notes.md + docs/assets/sample.mp3 + index.md audio embed written (uncommitted). Funnel NOT opened (no real edition yet).

[2026-10-01T23:07:48Z · sase-1e3.12] PROPOSED FOLLOW-UP: publish sase-listen 0.1.0 to PyPI — release-please merge ef84b3b created no tag and trusted publishing never ran (pip index shows no sase-listen); rollout installed from git source instead

[2026-10-01T23:08:04Z · sase-1e3.12] PROPOSED FOLLOW-UP: implement audition/ls/cache CLI stubs and doctor --online check — sase-listen 0.1.0 prints "not implemented yet (owner: cli phase)" for audition, ls, cache; doctor --online exits 3 "online check not implemented yet"

[2026-10-01T23:08:20Z · sase-1e3.12] PROPOSED FOLLOW-UP: Gemini key is free-tier (10 synth req/day); Kore/Iapetus/Sadaltager auditions and full Gemini edition blocked at 429 — resume with: sase-listen render <research-checkout>/202610/commute_audio_from_markdown/commute_audio_from_markdown_narration.md -n gemini (cache holds 8 chunks); consider paid tier per report monthly-cost table

[2026-10-01T23:08:35Z · sase-1e3.12] PROPOSED FOLLOW-UP: open Tailscale Funnel for the feed once the real Gemini edition lands — tailscale funnel --bg --https=8443 --set-path=/0hQw7ls5w8MSU7fsn5f5oPEFTorGtzED /home/bryan/.local/share/sase-listen/feed (token in chezmoi config); needs user confirmation per plan, tailnet funnel node attribute required

[2026-10-01T23:08:51Z · sase-1e3.12] PROPOSED FOLLOW-UP: commit rollout files — uncommitted: chezmoi live source home/dot_config/sase-listen/config.yml (feed token + auto_publish), research sidecar narration script, sase-listen checkout docs/field-notes.md + docs/assets/sample.mp3 + docs/index.md embed (linked chezmoi checkout untouched; live source edited directly)

[2026-10-01T23:09:33Z · sase-1e3.12] Rollout verified on apollo: git-source install (PyPI missing, filed follow-up), chezmoi config + doctor offline green, live Charon TTS proven, lint-clean narration script + tone-engine full episode rendered and published to initialized feed, both MP3s registered for Telegram sendAudio delivery; Gemini full edition + 3 auditions quota-blocked (resume cached, follow-up filed), funnel deferred (follow-up filed), no epic-symbol leftovers

## Dependencies

- **Depends on:** [sase-1e3.11](sase-1e3.11.md) ✓ · ⧖ 2026-10-01

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1e3.12](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1e3.12/README.md) | [sase-1e3.12](sase-1e3.12.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase--research | [`sase--research@00ea38c`](https://github.com/sase-org/sase--research/commit/00ea38c4be040bd3ee9637a592d7d3c13f6d2b1a) | docs(audio): narration script for commute-audio report (sase-1e3.12 rollout) | [sase-1e3.12](sase-1e3.12.md) | 2026-10-01 19:14:04 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:research.38.cld][1] | Check phase progress/notes for sase-listen user-facing research | 1 |
| read-by | [agent:research.38.grk][2] | Need child phase scope for sase-listen user-facing research | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.research.38.cld/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.research.38.grk/README.md

<!-- sase:referenced-by:end -->
