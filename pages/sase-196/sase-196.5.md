# Bead: sase-196.5 — Guard the raw-submit fallback

[Bead Pages](../README.md) / [sase-196](README.md) / sase-196.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ry.f0](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ry.f0.md) · **Assignee:** `sase-196.5` · **Size:** small
**Created:** 2026-09-25 09:05:39 EDT · **Closed:** 2026-09-25 10:32:02 EDT
**Plan:** [202609/agents\_sidecar\_orphan\_objects.md](https://github.com/sase-org/sase--plans/blob/main/202609/agents_sidecar_orphan_objects.md)

## Description

submit-fallback-guard: reject the manifest template's placeholder commit message in submit and prepare (sase-190). Let `sase final submit` accept a prepare wrapper, point prepare refusals at that one-command fallback, and fix the submit help example and the sase_final skill text that encourage the lossy rebuild.

## Notes

[2026-09-25T14:32:02Z · sase-196.5] Placeholder commit message rejected in submit and prepare (commit_message_placeholder, shared constant); sase final submit accepts a prepare wrapper; prepare refusal hint and submit help/skill text updated; new tests in tests/test_final_submit_fallback_guard.py; sase tool run check passed. Generated skills not deployed (per plan).

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-196.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-196.5/README.md) | [sase-196.5](sase-196.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`7d14286`](https://github.com/sase-org/sase/commit/7d14286e594de40c34f891d54eccbaacbe19d8d4) | feat(finalizers): guard the raw-submit fallback (sase-196.5) | [sase-196.5](sase-196.5.md) | 2026-09-25 10:33:02 EDT |
