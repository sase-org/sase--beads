# Bead: sase-1au.2 — Python contract, configuration, and upgrade boundary

[Bead Pages](../README.md) / [sase-1au](README.md) / sase-1au.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0sy](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0sy.md) · **Assignee:** `sase-1au.2` · **Size:** medium
**Created:** 2026-09-26 14:44:22 EDT · **Closed:** 2026-09-26 16:06:43 EDT
**Plan:** [202609/prompt\_recall\_tabs\_and\_stash\_trash.md](https://github.com/sase-org/sase--plans/blob/main/202609/prompt_recall_tabs_and_stash_trash.md)

## Description

python_contract: expose strict Python wires and config, then pin a core revision with the new binding.

## Notes

[2026-09-26T19:54:44Z · sase-1au.2] PROPOSED FOLLOW-UP: just check symvision gate fails on clean base tree (private _legacy_sase_shell_syntax_enabled imported by src/sase/config/_settings_system.py); identical failure with changes stashed; needs owner triage

[2026-09-26T20:05:19Z · sase-1au.2] PROPOSED FOLLOW-UP: symvision private-import failure (_legacy_sase_shell_syntax_enabled in agent/legacy_sase_shell_syntax.py, imported by config/_settings_system.py) is pre-existing on clean HEAD and likely owned by open retirement bead sase-1ar; needs owner triage there

[2026-09-26T20:06:20Z · sase-1au.2] PROPOSED FOLLOW-UP: test_validate_proc_lifecycle_contract_passes_for_schema_v3_transitions fails identically on clean HEAD (tool expects lifecycle proc-shell, test fake uses named-proc); needs owner triage

[2026-09-26T20:06:43Z · sase-1au.2] python_contract done: strict lifecycle wires (schema v1, snapshot/outcome incl. changed/evicted) + facade (read/trash/restore/purge/reconcile, limit passed to Rust, stale wheel fails naming binding) with v1 shape intact; ace.prompt_stash.trash_limit=20 in default_config.yml + schema (int, min 0) with bool-rejecting accessor defaulting 20; validator parity (6 bindings, schema + behavior probes) and pin e44af7d. Verified: 375 passed in dependent subset incl. real-extension trash/restore/purge/limit-0/reconcile round trips, ruff/mypy/format clean, validate_sase_core_rs + binding scan exit 0. Two pre-existing failures proven identical on clean HEAD via stash round-trips, recorded as PROPOSED FOLLOW-UP (symvision private _legacy_sase_shell_syntax_enabled import, likely owned by sase-1ar; proc-lifecycle named-proc vs proc-shell test/tool mismatch). Full just check/test-scoped not completable inline (escalates to 48k-test full suite).

## Dependencies

- **Depends on:** [sase-1au.1](sase-1au.1.md) ✓ · ⧖ 2026-09-26
- **Blocks:** [sase-1au.4](sase-1au.4.md) ✓ · ⧖ 2026-09-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1au.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1au.2/README.md) | [sase-1au.2](sase-1au.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e7dc4be`](https://github.com/sase-org/sase/commit/e7dc4be959ecc5f773424673166e3dac5b51d601) | feat(prompt-stash): Python contract, config, and core pin for stash trash (sase-1au.2) | [sase-1au.2](sase-1au.2.md) | 2026-09-26 16:14:01 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1au.2][1] | Need the phase scope and design file | 3 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1au.2/README.md

<!-- sase:referenced-by:end -->
