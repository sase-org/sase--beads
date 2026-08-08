# Bead: sase-ha.2 — The Muse provider and its JSONL stream parser

[Bead Pages](../README.md) / [sase-ha](README.md) / sase-ha.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.ve](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.ve/README.md) · **Assignee:** `sase-ha.2` · **Size:** medium
**Created:** 2026-08-07 20:45:42 EDT · **Closed:** 2026-08-07 21:22:38 EDT
**Plan:** [202608/muse\_provider.md](https://github.com/sase-org/sase--plans/blob/main/202608/muse_provider.md)

## Description

provider: add `MuseProvider` and `_subprocess_muse`, register the `muse` entry point, map tiers and the full canonical reasoning-effort vocabulary, deploy skills to Muse's native root, add the doctor setup fallback, and test both against recorded release-keyed fixtures.

## Notes

[2026-08-08T01:16:16Z · sase-ha.2] PROPOSED FOLLOW-UP: `muse exec` rejects `--model` unless `--provider meta` is passed — if a future phase ever adds an echo/preset smoke mode, it must drop `--model` rather than append `--provider echo`.

[2026-08-08T01:22:17Z · sase-ha.2] PROPOSED FOLLOW-UP: pre-existing gate test failures at HEAD (a1cc172d3) — tests/test_gate_cli_show.py (4) and tests/gate_conformance/test_gate_conformance.py[cli|ace-legacy_shared_input] fail with GateError unanswerable_option for option 'audit' ('reason' required but not declared under inputs); reproduces with all sase-ha.2 changes stashed.

[2026-08-08T01:22:38Z · sase-ha.2] Added MuseProvider (src/sase/llm_provider/muse.py) + JSONL stream parser (_subprocess_muse.py), muse entry point in pyproject.toml, _subprocess.py re-export, doctor setup fallback, and 39 tests against three release-keyed R708.1 fixtures. Verified: just check lint gates all pass; scoped test lane 27337 passed with only 6 failures, all pre-existing at HEAD (gate_cli_show + gate_conformance, reproduced with my changes stashed) and noted as a follow-up. Live muse exec run on muse-spark-1.2-contributor at --reasoning-effort ultra returned OK once, streamed live_reply.md, wrote no diagnostics, left no prompt file.

## Dependencies

- **Blocks:** [sase-ha.4](sase-ha.4.md) ✓ · ⧖ 2026-08-07
- **Blocks:** [sase-ha.5](sase-ha.5.md) ◐ · ⧖ 2026-08-07
- **Blocks:** [sase-ha.6](sase-ha.6.md) ◐ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ha.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ha.2/README.md) | [sase-ha.2](sase-ha.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`44fa7ee`](https://github.com/sase-org/sase/commit/44fa7eee2445bc1b33742cd3ffef7f7a983110d0) | feat(llm-provider): add the Muse Code provider and its JSONL stream parser | [sase-ha.2](sase-ha.2.md) | 2026-08-07 21:23:25 EDT |
