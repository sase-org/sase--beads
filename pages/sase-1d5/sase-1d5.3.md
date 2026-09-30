# Bead: sase-1d5.3 — Provenance facts, audience flags, and the beta flag

[Bead Pages](../README.md) / [sase-1d5](README.md) / sase-1d5.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0tz](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0tz.md) · **Assignee:** `sase-1d5.3` · **Size:** large
**Created:** 2026-09-30 01:57:12 EDT · **Closed:** 2026-09-30 11:19:47 EDT
**Plan:** [202609/public\_bead\_attachments.md](https://github.com/sase-org/sase--plans/blob/main/202609/public_bead_attachments.md)

## Description

audience_cli: create the public_bead_attachments beta flag, gather provenance facts in Python (stat mode, git status, anonymous remote-visibility probe with cache, zones, run window, actor), scan ingested bytes, run the core decision, and add -K/--private, -W/--public, and -y/--yes to the five note-bearing verbs. Covers the agent-widening refusal, human confirmation, duplicate-digest intent, local-only reasons, the 🌐/🔒 write echo, the public_max_bytes config, and a count-only scanner run over the published transcripts.

## Notes

[2026-09-30T13:52:57Z · sase-1d5.3--1] Scanner count-only run over published agents transcripts (sase-1d5.3 verification): scanned 21467 files (21463 chat.md/prompt.md transcripts + 4 cited file objects) with core attachment_scan_file via Python authoring wrapper (production env). Files with hits: 17. By hit kind: known_value=12, credential_pattern=2, env_dump=3. By rule: known-value=12, env-dump-window=3, high-entropy-assignment=1, telegram-bot-token=1. Scanner rules_version=1. Credential coverage: 12 known-value + 1 telegram-bot-token = 13 files, matching the research report's 13 known files (12 LLM-provider key + 1 bot token). No values, lines, or contents recorded.

[2026-09-30T15:18:28Z · sase-1d5.3--3] PROPOSED FOLLOW-UP: just check stays red in _setup at tools/validate_sase_core_rs (prompt-prediction probe expects confident=True ghost=[the]; installed and freshly master-built sase-core-rs 0.36.x returns confident=False ghost=[]). The probe exercises only the Rust extension, so no Python change in this phase can affect it; verified by running the probe directly against the installed extension with identical output on all three just check attempts (17m, 24m, 7s runs). Likely sase-core 0.36 prediction-behavior drift vs the validator calibrated in 9d60b97513; needs a core-side or validator-side fix plus pin review, owned outside audience_cli. This phase's own gates are green: 15 audience CLI tests, 649 neighbor attachment/CLI tests, ruff, mypy, symvision, flags --static, keep-sorted, prettier, sase validate, epic-symbols clean.

[2026-09-30T15:19:47Z · sase-1d5.3--3] audience_cli done: beta flag public_bead_attachments with both-state tests; lazy provenance (owner-only, checkout/ignore, remote-visibility probe, zones, run window, actor); authoring pipeline classifies, scans via attachment_scan_file, decides via attachment_audience_decision with agent-widening refusal before mutation, human TTY/-y confirm, duplicate-digest intent, local CAS metadata; -K/-W/-y on all five verbs with validation, fast-path fallthrough, flag-off behavior; public_max_bytes 25MiB/95MiB with queue-for-missing-store routing and 🌐/🔒 echoes; pin moved past core audience commit; docs section added. Verified: 15 audience CLI tests, 649 neighbor attachment/CLI tests, ruff, mypy, symvision, flags --static, keep-sorted, prettier, sase validate green; epic-symbols clean; scanner count-only run over 21467 transcripts recorded earlier (17 hits, 13 credential files as researched). Full just check stays red only in _setup at the prompt-prediction validator probe, reproduced identically on the clean base (Rust-extension-only behavior, out of scope; PROPOSED FOLLOW-UP note recorded).

## Dependencies

- **Depends on:** [sase-1d5.1](sase-1d5.1.md) ✓ · ⧖ 2026-09-30
- **Blocks:** [sase-1d5.4](sase-1d5.4.md) ◐ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1d5.3](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1d5.3.md) | [sase-1d5.3](sase-1d5.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`c330cd8`](https://github.com/sase-org/sase/commit/c330cd870ad582c10f3ec4a108c09874aa98377e) | feat(bead-attachments): audience decisions for attachment authoring (sase-1d5.3) | [sase-1d5.3](sase-1d5.3.md) | 2026-09-30 11:34:28 EDT |
