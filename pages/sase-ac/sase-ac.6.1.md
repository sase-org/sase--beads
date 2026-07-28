# Bead: sase-ac.6.1 — Repair project-local definition paths and browser namespaces

[Bead Pages](../README.md) / [sase-ac.6](sase-ac.6.md) / sase-ac.6.1

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-ac.6.1` · **Size:** small
**Created:** 2026-07-28 13:13:57 UTC · **Closed:** 2026-07-28 14:01:54 UTC
**Plan:** [202607/xprompt\_identity\_landing.md](https://github.com/sase-org/sase--plans/blob/main/202607/xprompt_identity_landing.md)

## Description

browser_identity: fix the `project_local_config:` definition-path regression and stop `get_all_project_local_prompts()` from emitting directory-key namespaces into the ACE xprompt browser and doctor.

## Notes

[2026-07-28T14:00:42Z · sase-ac.6.1] Implemented canonical project-local prompt namespaces for get_all_project_local_prompts(), repaired project_local_config definition-path resolution for canonical and legacy directory-key identifiers, added regressions, restored the missing sase-ac.6 landing plan link pair, and verified with focused xprompt/browser/doctor/catalog tests plus SASE_PYTEST_WORKERS=4 just check. The default parallel just check was run twice and only hit unrelated single-test flakes that each passed in isolation.

## Dependencies

- **Blocks:** [sase-ac.6.5](sase-ac.6.5.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ac.6.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ac.6.1/README.md) | [sase-ac.6.1](sase-ac.6.1.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`0db608e`](https://github.com/sase-org/sase/commit/0db608e985e2031bdb8a58322d8f29b0ce8484fb) | fix(xprompt): canonicalize project-local browser identities (sase-ac.6.1) | [sase-ac.6.1](sase-ac.6.1.md) | 2026-07-28 14:07:20 |
