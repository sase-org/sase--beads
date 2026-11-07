# Bead: sase-1rq.2.1.6 — Clear CORE\_LAG from Publish and the release PR floor smoke

[Bead Pages](../README.md) / [sase-1rq.2.1](sase-1rq.2.1.md) / sase-1rq.2.1.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1rq.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.2.md) · **Assignee:** `sase-1rq.2.1.6` · **Size:** small
**Created:** 2026-11-07 10:24:48 EST · **Closed:** 2026-11-07 11:04:05 EST
**Plan:** [202611/sase\_ci\_green.md](https://github.com/sase-org/sase--plans/blob/main/202611/sase_ci_green.md)

## Description

release-path: Publish's sync-release-metadata (run 42375016682) and the release PR #322 CI's release-core-floor-smoke (run 42375244107) both failed on CORE_LAG with floor 0.43.3. sase-core-rs 0.44.0, which contains sase's pin c8adc878, has been on PyPI since 2026-11-07 14:58 UTC. Confirm that a Publish run after that time ratchets the release branch's floor and goes green, and that the floor smoke then passes. Fix the ratchet or smoke tooling only if it still fails.

## Notes

[2026-11-07T16:04:05Z · sase-1rq.2.1.6] CORE_LAG cleared; no code change needed. (1) PR #322 still OPEN, unmerged. (2) Publish run 42387581264 (workflow_dispatch, master ef00c509, created 15:41Z, after the 14:58Z 0.44.0 upload) concluded success: release + sync-release-metadata both success; ratchet log 'PINNED(0.44.0, files=...)' and 'sase-core-rs ratchet ==0.43.2 -> ==0.44.0 applied', pushed bc1b8dcc..4bcb3e4c 'chore: sync release metadata' to release-please--branches--master (pyproject now sase-core-rs==0.44.0). (3) PR #322 CI run 42387908413 on head 4bcb3e4c concluded success: release-core-floor-smoke passed every step ('sase-core-rs pin confirmed: 0.44.0', bindings/contracts, 7 smoke probes, contract set 1130 passed). The preceding CI run 42387852230 on bc1b8dcc (release-please refresh before the sync push) failed floor smoke as expected and is superseded. (4) Master pin still c8adc878 at tip b7ca9f34; Core Pin Ratchet PR #319 (-> dec432ca) still open. (5) Correction for verify: lint/test/visual-test/perf-floors/ace-page-group-isolation/build-core on the release PR are SKIPPED BY DESIGN, not gated by floor smoke: build-core.yml:62-66 skips source-mode build-core on release-please--branches--master ('its core comes from the floor-smoke leg instead'), every other job needs build-core; docs-build (ci.yml:328) and tutorial-tests (ci.yml:710) are excluded on PRs by their own if:. So the release PR's CI does not depend on the full-ci phase. Master has since moved to b7ca9f34, so the next Publish will refresh #322 again; verify should re-read that run.

## Dependencies

- **Blocks:** [sase-1rq.2.1.7](sase-1rq.2.1.7.md) ◐ · ⧖ 2026-11-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1rq.2.1.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1rq.2.1.6/README.md) | [sase-1rq.2.1.6](sase-1rq.2.1.6.md) | 0 |
