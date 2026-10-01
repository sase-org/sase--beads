# Bead: sase-1e3.5 — TTS engines, narrator profiles, credentials, retries, cache, and pricing

[Bead Pages](../README.md) / [sase-1e3](README.md) / sase-1e3.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.3z](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.3z.md) · **Assignee:** `sase-1e3.5` · **Size:** medium
**Created:** 2026-10-01 14:42:48 EDT · **Closed:** 2026-10-01 15:25:56 EDT
**Plan:** [202610/sase\_listen.md](https://github.com/sase-org/sase--plans/blob/main/202610/sase_listen.md)

## Description

engines: add the Engine protocol and the Gemini, OpenAI-compatible, and offline tone adapters. Add narrator profiles, secret resolution from env or command, retry with backoff, the content-addressed LRU chunk cache, and dated pricing estimates. Verify Gemini with a single live call.

## Notes

[2026-10-01T19:25:15Z · sase-1e3.5] Engines phase live verification (2026-10-01): one real Gemini call via client.interactions.create, model gemini-3.8-flash-tts, voice Charon, style as speech_metadata annotation -> status completed, audio/wav mono 16-bit 24000 Hz, decoded to s16le PCM. test_live_gemini_two_sentences passes with SASE_LISTEN_LIVE=1 and key from pass. DEVIATION from plan: pinned model rejects system_instruction (400 Developer instruction is not enabled), and 2.5-flash-preview-tts gave persistent 500s; adapter uses the documented interactions.create + speech_metadata.style channel instead of generate_content, never inlining style into the transcript. SDK gotcha fixed in adapter: keep genai Client alive for the whole call or its GC closes the HTTP transport (RuntimeError: client has been closed). sase tool run check green: 51 passed, 1 skipped (live).

[2026-10-01T19:25:34Z · sase-1e3.5] PROPOSED FOLLOW-UP: pipeline/cli phase should consider a narrators.<name>.max_chars config key for Kokoro-FastAPI voices (OpenAI adapter already accepts a per-call max_chars override; adding the key needs scaffold-owned config.py change)

[2026-10-01T19:25:56Z · sase-1e3.5] Engines phase done and verified: Engine protocol + Gemini/OpenAI-compatible/tone adapters, narrator + secret resolution, jittered retry honoring Retry-After, content-addressed LRU chunk cache, dated pricing estimates. sase tool run check green (ruff, format, mypy --strict, codespell, 51 passed + 1 live skipped). Live Gemini call verified end to end (gemini-3.8-flash-tts/Charon, speech_metadata style channel, 24 kHz PCM out); documented deviation recorded in phase notes. No --epic-symbol leftovers.

## Dependencies

- **Depends on:** [sase-1e3.1](sase-1e3.1.md) ✓ · ⧖ 2026-10-01
- **Blocks:** [sase-1e3.6](sase-1e3.6.md) ◐ · ⧖ 2026-10-01

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1e3.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1e3.5/README.md) | [sase-1e3.5](sase-1e3.5.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:research.38.cdx][1] | Verify TTS engine and PyPI release evidence before stating install availability | 1 |
| read-by | [agent:research.38.cld][2] | Check phase progress/notes for sase-listen user-facing research | 1 |
| read-by | [agent:research.38.grk][3] | Need child phase scope for sase-listen user-facing research | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.research.38.cdx/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.research.38.cld/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.research.38.grk/README.md

<!-- sase:referenced-by:end -->
