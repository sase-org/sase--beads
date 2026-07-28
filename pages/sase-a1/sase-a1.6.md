# Bead: sase-a1.6 — Land the new surfaces as one coherent contract

[Bead Pages](../README.md) / [sase-a1](README.md) / sase-a1.6

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-a1.6` · **Size:** small
**Created:** 2026-07-27 16:34:50 UTC · **Closed:** 2026-07-27 21:13:29 UTC
**Plan:** [202607/bead\_history\_truthful\_close.md](https://github.com/sase-org/sase--plans/blob/main/202607/bead_history_truthful_close.md)

## Description

integrate: reconcile the two halves into one documented contract — bead docs, the generated `sase_beads` skill, the land and phase xprompts, the published core version window — and produce end-to-end acceptance evidence against the live store.

## Notes

[2026-07-27T21:13:18Z · sase-a1.6] Integrated the bead contract docs and generated skill source: docs/beads.md now keeps the command reference alphabetic and removes manual claimed-state wording; src/sase/xprompts/skills/sase_beads.md documents history, note append, close --force/--resolution, update --notes replacement, and reopen-ancestor behavior. Regenerated provider skills with .venv/bin/sase skill init --force, ran chezmoi apply, and .venv/bin/sase init skills --check passes. Verified PyPI latest sase-core-rs is 0.12.1 and pyproject.toml already requires >=0.12.1,<0.13.0. Acceptance evidence: sase bead history sase-5t.5 --field notes --format full exposes the multi-revision notes chain; live lost-notes scan found 418 affected beads / 524 revisions versus the design snapshot's 509 because the store moved; TTY restore completed and committed plans sidecar ec3c4329, and a fresh scan reports no findings. sase bead show sase-5t renders RESOLUTION with (unrecorded). Scratch store: unforced parent close rejected without closing, --force --resolution done rejected, --force --resolution canceled succeeded and recorded forced_descendant_ids, reopening the phase reopened the parent and removed the closed resolution display. Live structural queries: closed bead with non-closed descendant = 0; same-instant child/parent closures = 47 rather than 28, with 3 added after this plan by a separate forced close under sase-a4. just check was run twice: formatting, lint, SASE validation, and committed-plan checks pass; full test stage repeatedly fails only tests/test_suite_gate_integration.py::test_scaled_suite_runs_share_capacity_and_release_after_sigkill, which passes both isolated and under xdist-targeted reruns.

## Dependencies

- **Depends on:** [sase-a1.4](sase-a1.4.md) ✓
- **Depends on:** [sase-a1.5](sase-a1.5.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-a1.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-a1.6/README.md) | [sase-a1.6](sase-a1.6.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`6ad452e`](https://github.com/sase-org/sase/commit/6ad452e1e84d47bafc39eb3a2850a954a1891768) | docs(beads): document truthful completion contract (sase-a1.6) | [sase-a1.6](sase-a1.6.md) | 2026-07-27 21:17:33 |
