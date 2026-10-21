# Bead: sase-1nf.10.1.9 — Repair Apollo and prove bounded publication on both hosts

[Bead Pages](../README.md) / [sase-1nf.10.1](sase-1nf.10.1.md) / sase-1nf.10.1.9

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1nf.10](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nf.10.md) · **Assignee:** `sase-1nf.10.1.9` · **Size:** medium
**Created:** 2026-10-20 15:40:53 EDT
**Plan:** [202610/publication\_drain\_fixes.md](https://github.com/sase-org/sase--plans/blob/main/202610/publication_drain_fixes.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| related | file:explicit:eaaaade9836ab612d5ce7c78 | attached via sase artifact create --bead |

<!-- sase:links:end -->

## Description

recovery-proof: verify installed revisions, preserve unique Apollo content before repairing the stale replay and manifest mismatch, run small publication canaries on both hosts, and publish acceptance evidence for the land agent.

## Notes

[2026-10-21T05:57:01Z · sase-1nf.10.1.9] RECOVERY-PROOF STEP 1 — installed revisions are STALE on both hosts, update will fix: athena sase 5ffaa1f513438c + core f9aa563c114c; apollo identical (sase 5ffaa1f51, core gf9aa563c1). Required: sase 5803ddfa0b + core pin 461e7a18. Verified GitHub master==5803ddfa0b and sase-core HEAD==461e7a18 via ls-remote, so plain sase update picks up all 8 landed phases. Installed CLI confirms staleness: sase agent sync has no -l/--retry-limit or -e/--retry-error-class flags. No production mutation was run with stale code.

[2026-10-21T05:57:09Z · sase-1nf.10.1.9] FRESH PRODUCTION STATE (read-only, 2026-10-21): athena outbox 3390 issues (3387 quarantined: ~2918 timeout-within-120s, ~459 lock-busy, 10 other; 2 retired, 1 stalled). Apollo outbox 781 (497 quarantined, 284 retired). Apollo bob-cli: 1 ahead / 566 behind; 372 rows fail rebasing stale 2abeff3f9 (the exact stale-replay signature). Apollo sase: 0 ahead / 7 behind; bbugyi200.apollo.03 manifest file-set mismatch blocks research + sase-1aq/sase-1dr/sase-1df/sase-1bf and more (>150 rows). Digest check OK on both hosts. No destructive step taken.

[2026-10-21T05:57:14Z · sase-1nf.10.1.9] PROPOSED FOLLOW-UP: apollo job and tailnet projects fail git fetch with ERROR: Repository not found (seen in sase agent sync --check --refresh); unrelated to publication drains, needs remote-access triage before sase-1nf.11 bulk drain

[2026-10-21T05:57:22Z · sase-1nf.10.1.9] FIXTURE HERITAGE + FOLLOW-UP RUNBOOK: local real-Git idempotent-replay/resume proof stands on phase-8 close evidence at this exact HEAD (5803ddfa0b): verified backup without reset, unique chats/sessions/pending objects after apply, interrupt resume, already_complete idempotence, HEAD-drift refuse (sase-core + sase checks passed, 1 KNOWN pre-existing tagged-commit failure). A local re-run was attempted (just rust-install 2x9min, cold build still compiling sase_core) and deferred. POST-UPDATE RUNBOOK for gate follow-up: (1) verify sase --version==5803ddfa0b-era + core 461e7a18 on both hosts; (2) apollo: discover hidden clones via sase repo open, run tools/agents_publication_recover_replay report then apply for bob-cli (expect 2abeff3f9), then sase agent sync --repair-manifest for bbugyi200.apollo.03, push via normal transaction, verify remote manifest; (3) athena: profile one timeout hood (tools/agents_publication_profile -H <hood>), bounded drain limit 1 then at most one batch of 25 per project, record keys/timings/payload/remote rev; (4) apollo canary per repaired class/project; (5) publish research artifact, attach to phase, run sase bead epic-symbols, close ONLY this phase.

[2026-10-21T11:36:10Z · sase-1nf.10.1.9] RECOVERY-PROOF CONTINUATION (2026-10-21 11:31 UTC): both hosts now run clean SASE 5639375bfd0b43bb49dfd761d96a4bf6668fabe6 and core 461e7a1818903ac578c0c0bf0377a9c206bacf32; local ancestry confirms 5803ddfa0b is included. Fresh doctor: athena 3395 rows (3389 quarantined, 4 active, 2 retired); apollo 787 (497 quarantined, 6 active, 284 retired). Apollo bob-cli remains 1 ahead/566 behind on cached refs, 388 quarantined errors name 2abeff3f9; 298 sase errors name bbugyi200.apollo.03. No production repair/retry performed. Baseline attached as file:explicit:eaaaade9836ab612d5ce7c78. Per the user requirement for previously unfinished phases, preparing a validated five-phase child epic for replay recovery, manifest repair, Athena canary, Apollo canaries, and fixture/automatic-completion proof, with its land agent closing only this enclosing phase after acceptance. Shared canary budgets persist across continuations. epic-symbols empty; no tracked source or memory changes.

## Dependencies

- **Depends on:** [sase-1nf.10.1.8](sase-1nf.10.1.8.md) ✓ · ⧖ 2026-10-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1nf.10.1.9](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1nf.10.1.9.md) | [sase-1nf.10.1.9](sase-1nf.10.1.9.md) | 0 |
