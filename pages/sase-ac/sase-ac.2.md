# Bead: sase-ac.2 — Namespace and filter the xprompt catalog by user-facing name

[Bead Pages](../README.md) / [sase-ac](README.md) / sase-ac.2

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-ac.2` · **Size:** medium
**Created:** 2026-07-28 11:41:25 UTC · **Closed:** 2026-07-28 12:26:38 UTC
**Plan:** [202607/xprompt\_project\_identity.md](https://github.com/sase-org/sase--plans/blob/main/202607/xprompt_project_identity.md)

## Description

catalog: make the xprompt catalog namespace, tag, and filter project-local xprompts by the canonical user-facing project name so requesting project `sase` returns `sase/reads`.

## Notes

[2026-07-28T12:26:28Z · sase-ac.2] Implemented canonical user-facing project namespaces throughout Python xprompt catalog gathering, inferred classification, filtering, source display, and definition lookup; added key/name/alias dedup regression coverage and removed the now-stale sase-ac Symvision exemptions. Verification: focused catalog/identity tests passed (60 tests); full just test passed (22,902 passed, 7 skipped); formatting and all lint stages passed. just check was attempted but SASE plan-link validation is independently blocked by 229 existing errors in the shared plans sidecar.

## Dependencies

- **Depends on:** [sase-ac.1](sase-ac.1.md) ✓
- **Blocks:** [sase-ac.4](sase-ac.4.md) ✓
- **Blocks:** [sase-ac.5](sase-ac.5.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ac.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ac.2/README.md) | [sase-ac.2](sase-ac.2.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`40f2d52`](https://github.com/sase-org/sase/commit/40f2d526e6b1e0b992dbc3e80c8cee66d5750ac6) | fix(xprompt): canonicalize project catalog namespaces (sase-ac.2) | [sase-ac.2](sase-ac.2.md) | 2026-07-28 12:27:56 |
