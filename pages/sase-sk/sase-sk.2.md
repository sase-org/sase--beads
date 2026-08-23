# Bead: sase-sk.2 — Admission-gate toobig\_split at the configured line floor

[Bead Pages](../README.md) / [sase-sk](README.md) / sase-sk.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0c1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0c1.md) · **Assignee:** `sase-sk.2` · **Size:** medium
**Created:** 2026-08-23 16:21:06 EDT · **Closed:** 2026-08-23 17:49:40 EDT
**Plan:** [202608/toobig\_split\_conditional\_admission.md](https://github.com/sase-org/sase--plans/blob/main/202608/toobig_split_conditional_admission.md)

## Description

toobig-if-guard: remove repository-HEAD and proposal-dedupe behavior from bugyi-chops, emit a safe per-file %if Bash fence that rechecks the configured minimum line limit, and prove stale files skip while eligible files still launch.

## Notes

[2026-08-23T21:49:07Z · sase-sk.2] PROPOSED FOLLOW-UP: SASE release/version gap — PyPI sase 0.16.0 lacks the typed_launch_units/feature_flags modules used by the guarded bugyi-chops tests; before publishing bugyi-chops 0.7.0, release or version-bump the SASE package that contains the completed AXE typed-admission contract, then tighten the dependency floor if needed.

[2026-08-23T21:49:40Z · sase-sk.2] Implemented toobig_split conditional %if admission in bugyi-chops; verified uv lock resolves away from SASE 0.13 to SASE 0.16/core 0.19, installed against current SASE source venv, focused toobig_split tests passed (44), just check passed (ruff, mypy, 93 pytest with 92.76% coverage, build, twine), and epic-symbols reported no entries.

## Dependencies

- **Depends on:** [sase-sk.1](sase-sk.1.md) ✓ · ⧖ 2026-08-23
- **Blocks:** [sase-sk.3](sase-sk.3.md) ✓ · ⧖ 2026-08-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-sk.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-sk.2/README.md) | [sase-sk.2](sase-sk.2.md) | 0 |
