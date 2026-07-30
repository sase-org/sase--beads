# Bead: sase-as.6 — Route hardcoded role tuples through the role registry

[Bead Pages](../README.md) / [sase-as](README.md) / sase-as.6

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-as.6` · **Size:** medium
**Created:** 2026-07-29 14:31:19 UTC · **Closed:** 2026-07-29 15:30:38 UTC
**Plan:** [202607/artifact\_tranche\_zero\_and\_generic\_sidecar\_roles.md](https://github.com/sase-org/sase--plans/blob/main/202607/artifact_tranche_zero_and_generic_sidecar_roles.md)

## Description

role-consumers: replace every remaining literal `("plans", "research", "beads")` tuple and `research`-named branch across repo inventory, linked-repo paths, `sase repo path`, doctor, commit finalization, SDD path helpers, agent env, and the ACE file panel with the generic role registry, and document the role model.

## Notes

[2026-07-29T15:30:38Z · sase-as.6] Implemented generic sidecar-role consumers and role-model docs. Verified 172 focused tests pass; just check passed formatting, keep-sorted, Ruff, mypy, pyscripts, Symvision, and size lint. Full just test reached 23,615 passed / 7 skipped; its two xprompt selector failures passed in isolation, while three unrelated AXE-description PNG golden mismatches reproduce independently. git diff --check is clean.

## Dependencies

- **Depends on:** [sase-as.5](sase-as.5.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-as.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-as.6/README.md) | [sase-as.6](sase-as.6.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`107904b`](https://github.com/sase-org/sase/commit/107904b6bea97c5d036921b2fbbc7ee92e7ceb0e) | feat(sdd): route document sidecars through role registry | [sase-as.6](sase-as.6.md) | 2026-07-29 15:32:05 |
