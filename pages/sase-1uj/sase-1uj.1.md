# Bead: sase-1uj.1 — Catalog Gemini 4 Neon in sase's agy manifest

[Bead Pages](../README.md) / [sase-1uj](README.md) / sase-1uj.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.1eo](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.1eo.md) · **Assignee:** `sase-1uj.1` · **Size:** medium
**Created:** 2026-11-20 16:42:51 EST · **Closed:** 2026-11-20 17:44:39 EST
**Plan:** [202611/gemini\_neon\_research\_swarm.md](https://github.com/sase-org/sase--plans/blob/main/202611/gemini_neon_research_swarm.md)

## Description

catalog: add the four gemini-4-neon slugs, short aliases, and info advisories to models.yml, teach the TUI the neon short name, correct the stale Hydrogen availability prose, and update agy tests, docs, and model-picker PNG goldens.

## Notes

[2026-11-20T22:44:13Z · sase-1uj.1] PROPOSED FOLLOW-UP: tests/completion/test_snapshot.py drifts on clean base (sase artifact link list description_digest) — fails with and without this phase change; needs just sync-completion-spec or a spec fix

[2026-11-20T22:44:24Z · sase-1uj.1] PROPOSED FOLLOW-UP: tests/dispatch/test_machine_bootstrap_real_gateway.py errors on clean base (needs real gateway; 2 triaged KNOWN, 2 NEW) — environmental, plus KNOWN audit-site and FLAKY publication-budget failures in just check

[2026-11-20T22:44:39Z · sase-1uj.1] Cataloged Gemini 4 Neon: 4 slugs + neon4* aliases + Pro/Ultra advisories in models.yml, Hydrogen paid-Pro advisories, neon TUI short name, corrected Hydrogen prose in agy.md/models.md, regenerated model tables, updated 8 tests + 2 PNG goldens (28 models, neon-xhigh effort row verified visually). Touched tests: 139 passed. just fix clean. Full check: all lint/docs gates pass; 4 failed + 4 errors reproduce identically on clean base (snapshot drift, real-gateway env, KNOWN audit, FLAKY budget) and are recorded as PROPOSED FOLLOW-UPs.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1uj.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1uj.1/README.md) | [sase-1uj.1](sase-1uj.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`7e59092`](https://github.com/sase-org/sase/commit/7e590921e33a9d6b6b8e1c174fc2e053bbb38da5) | feat(models): add gemini-4-neon agy family with Pro/paid-Pro advisories | [sase-1uj.1](sase-1uj.1.md) | 2026-11-20 17:46:21 EST |
