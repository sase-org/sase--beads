# Bead: sase-ac.6.3 — Canonicalize and register-back project workflow loading

[Bead Pages](../README.md) / [sase-ac.6](sase-ac.6.md) / sase-ac.6.3

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-ac.6.3` · **Size:** medium
**Created:** 2026-07-28 13:14:30 UTC · **Closed:** 2026-07-28 13:36:04 UTC
**Plan:** [202607/xprompt\_identity\_landing.md](https://github.com/sase-org/sase--plans/blob/main/202607/xprompt_identity_landing.md)

## Description

workflow_identity: give `get_all_workflows()` the same canonical-identity and registry-backed resolution `get_all_xprompts()` received, so a project's `.yml` workflow xprompts resolve by canonical name and outside the checkout.

## Notes

[2026-07-28T13:35:36Z · sase-ac.6.3] Implemented canonical workflow project identity: get_all_workflows() now canonicalizes names/keys/aliases, registry fallback uses enabled canonical namespaces, matching current checkouts skip the registry read, and CWD workflow sources retain precedence. Added registered-project YAML coverage for canonical/key/alias refs, alternate-checkout precedence, and disabled-project exclusion. Verification: focused workflow-loader suite 16 passed; formatting, Ruff, mypy, pyscripts, Symvision, and toobig passed; committed-plan validation passed; full suite reached 22,981 passed / 7 skipped with one unrelated concurrency timeout that passed immediately in isolation. Full just check remains blocked only by the pre-existing missing SDD plan link 202607/prompts/xprompt_identity_landing.md -> ../xprompt_identity_landing.md.

## Dependencies

- **Blocks:** [sase-ac.6.5](sase-ac.6.5.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ac.6.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ac.6.3/README.md) | [sase-ac.6.3](sase-ac.6.3.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`699456a`](https://github.com/sase-org/sase/commit/699456a521e25e0aaa38f4e289db38e71a6488a6) | fix(xprompt): canonicalize workflow project identity (sase-ac.6.3) | [sase-ac.6.3](sase-ac.6.3.md) | 2026-07-28 13:37:41 |
