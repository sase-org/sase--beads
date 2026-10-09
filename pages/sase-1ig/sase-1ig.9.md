# Bead: sase-1ig.9 — Point sase-core's remedies at the new names

[Bead Pages](../README.md) / [sase-1ig](README.md) / sase-1ig.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ym](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0ym.md) · **Assignee:** `sase-1ig.9` · **Size:** small
**Created:** 2026-10-08 18:23:31 EDT · **Closed:** 2026-10-09 01:27:30 EDT
**Plan:** [202610/just\_install\_pypi\_dev\_venv.md](https://github.com/sase-org/sase--plans/blob/main/202610/just_install_pypi_dev_venv.md)

## Description

core-strings: in linked sase-core, change the triage environment remedies and verdict remedy to `just install-venv`, change the bead JSONL unknown-operation remedy to `sase update` / `just install-dev`, regenerate goldens and tests, and let the dual-repo commit move sase's core pin.

## Notes

[2026-10-09T05:27:30Z · sase-1ig.9] core-strings done in linked sase-core (4 files): triage environment remedies + remedy_for and verdict remedy now say just install-venv; bead JSONL unknown-operation remedy now says run sase update or just install-dev; golden environment_missing_binding regenerated via UPDATE_TRIAGE_GOLDENS=1; jsonl unknown-op test strengthened to assert sase update + just install-dev and reject bare just install. Verified: focused triage (56) + bead::jsonl (19) tests pass, just fmt clean, full sase tool run check gate succeeded exit=0. No sase-side changes needed (already migrated; no assertions on Rust strings); no memory edits (phase has none). Dual-repo commit + sase core-pin move left for the land agent (agents never commit).

## Dependencies

- **Depends on:** [sase-1ig.7](sase-1ig.7.md) ✓ · ⧖ 2026-10-08
- **Depends on:** [sase-1ig.8](sase-1ig.8.md) ✓ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ig.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ig.9/README.md) | [sase-1ig.9](sase-1ig.9.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@4ea91b9`](https://github.com/sase-org/sase-core/commit/4ea91b95b51ee988320adcfea4e3cd54140a110b) | fix(triage): point environment and bead remedies at install-venv/install-dev | [sase-1ig.9](sase-1ig.9.md) | 2026-10-09 01:28:41 EDT |
