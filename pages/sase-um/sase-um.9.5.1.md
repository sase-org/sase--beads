# Bead: sase-um.9.5.1 — Make bugyi-chops parse gh JSON without host-only environment overrides

[Bead Pages](../README.md) / [sase-um.9.5](sase-um.9.5.md) / sase-um.9.5.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-um.9.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-um.9.land.md) · **Assignee:** `sase-um.9.5.1` · **Size:** medium
**Created:** 2026-08-28 20:17:48 EDT · **Closed:** 2026-08-28 20:43:37 EDT
**Plan:** [202608/finish\_release\_gate\_landing.md](https://github.com/sase-org/sase--plans/blob/main/202608/finish_release_gate_landing.md)

## Description

chopcolor: harden the GitHub command environment, verify ci_watch against source SASE, and stage the exact revision for live use without publishing it yet.

## Notes

[2026-08-29T00:43:37Z · sase-um.9.5.1] GitHubReader now forces GH_FORCE_TTY=0, NO_COLOR=1, CLICOLOR=0 on every gh call without dropping inherited env. Source-SASE just check: ruff/mypy clean, 113 tests passed (93% coverage), wheel+sdist twine-clean. Staged that 0.9.0 wheel into the live sase uv-tool env. Dry-run `sase axe chop run ci_watch -n -V` parsed repository metadata, PR JSON (sase #284 gating_workflow_red, sase-telegram #21 merge state not clean), and workflow job evidence with errors=0. Did not tag/publish 0.9.0; chezmoi color overlay left in place.

## Dependencies

- **Blocks:** [sase-um.9.5.4](sase-um.9.5.4.md) ◐ · ⧖ 2026-08-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-um.9.5.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-um.9.5.1/README.md) | [sase-um.9.5.1](sase-um.9.5.1.md) | 0 |
