# Bead: sase-12w.6.3 — Complete SSH transport and integrated detached acceptance

[Bead Pages](../README.md) / [sase-12w.6](sase-12w.6.md) / sase-12w.6.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-12w.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-12w.land.md) · **Assignee:** `sase-12w.6.3` · **Size:** large
**Created:** 2026-09-18 13:56:25 EDT · **Closed:** 2026-09-18 18:33:18 EDT
**Plan:** [202609/sudo\_detached\_landing\_repairs.md](https://github.com/sase-org/sase--plans/blob/main/202609/sudo_detached_landing_repairs.md)

## Description

remote: fix SSH script encoding and root liveness, preserve uncertain remote attempts, stream remote output, and prove local/remote completion through realistic acceptance tests.

## Notes

[2026-09-18T21:47:49Z · sase-12w.6.3] PROPOSED FOLLOW-UP: just check lint (symvision) still flags three pre-existing unused public symbols from the 264eedc6c4 lazy-export trim, unrelated to this remote sudo phase: ArtifactFileCache and TailCache in src/sase/agent/artifact_files_cache.py, MultiPrompt in src/sase/agent/multi_prompt.py. They are only re-exported via sase.agent.__init__ lazy maps and test imports. Do not fold them into sase-12w.6.3.

PROPOSED FOLLOW-UP: sase-core just check failed once on federation_worker::imp::tests::listener_creates_private_socket_and_rejects_symlink with 'federation worker is already running for .../worker.sock'; isolated retry passed. Record as a flake if it recurs.

[2026-09-18T22:32:26Z · sase-12w.6.3--1] PROPOSED FOLLOW-UP: tests/completion/test_loader.py::test_fish_loader_sources_grammar_once_and_skips_later_ensure failed in the full `just test` monitor tadp9xgwqys8 (15 failed, 43185 passed) and again in isolation (`assert 2 == 1` on _ensure_call_count). Unrelated to this remote sudo phase: no completion files in the dirty tree. The fish loader unsets __SASE_COMPLETION_LOADER_ACTIVE after the first source, so a later `complete -C 'sase '` re-runs `completion ensure`. Do not fold this into sase-12w.6.3.

[2026-09-18T22:33:18Z · sase-12w.6.3--1] Remote SSH transport and detached acceptance for sase-12w.6.3 is complete.

Verified Rust coverage: sase-core sudo attempt wire (optional validated remote_handoff on version-1 attempts, legacy absence, malformed absolute-path rejection) plus sase_core_py binding tests; clippy and focused sudo tests. Full sase-core just check failed once on unrelated flake federation_worker::imp::tests::listener_creates_private_socket_and_rejects_symlink (already-running worker.sock) and passed on isolated retry.

Verified Python coverage: focused sudo tests (ssh, execution, detach, acceptance, core, gate, parser; 64+ passed after format). just fix and mypy/ruff for the sudo changes. Full `just test` monitor tadp9xgwqys8: 43185 passed, 15 skipped, 15 failed. None of the failures are sudo/SSH nodes.

Unrelated full-suite failures recorded, not fixed: 14-node sidecar clone HEAD/staging cluster already tracked as sase-130 (independent +1 from this run); tests/completion/test_loader.py::test_fish_loader_sources_grammar_once_and_skips_later_ensure proposed as follow-up (fails in isolation, fish loader re-runs ensure). Pre-existing unused public symbols ArtifactFileCache/TailCache/MultiPrompt remain on the earlier follow-up note. sase bead epic-symbols sase-12w.6.3 is empty. Parent epic sase-12w.6 left open.

## Dependencies

- **Depends on:** [sase-12w.6.2](sase-12w.6.2.md) ✓ · ⧖ 2026-09-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-12w.6.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-12w.6.3.md) | [sase-12w.6.3](sase-12w.6.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`12a37df`](https://github.com/sase-org/sase/commit/12a37df03752e9d5f4fe0d979e7d1b2d94bdcb06) | feat(sudo): complete remote SSH transport and detached acceptance | [sase-12w.6.3](sase-12w.6.3.md) | 2026-09-18 18:36:33 EDT |
