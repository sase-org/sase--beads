# Bead: sase-1df.6 — Python adapter, single source of truth, lint, and parity tests

[Bead Pages](../README.md) / [sase-1df](README.md) / sase-1df.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.3g](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.3g.md) · **Assignee:** `sase-1df.6` · **Size:** medium
**Created:** 2026-09-30 08:47:26 EDT · **Closed:** 2026-09-30 12:52:53 EDT
**Plan:** [202609/jinja\_variable\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202609/jinja_variable_completion.md)

## Description

python: add the sase Jinja adapter and move the core pin. Delete the Python builtin-name mirrors in favor of the Rust catalog. Switch the unknown-variable lint and gL/save-as-xprompt input inference to engine scope variables. Add runtime/catalog parity tests and update the docs/xprompt.md template-context reference.

## Notes

[2026-09-30T16:46:21Z · sase-1df.6--2] PROPOSED FOLLOW-UP: just check _setup fails on clean base too — validate_sase_core_rs prompt-prediction probe expects confident=True/ghost=[the] for "help me implement" but sase-core@9074b2a wheel returns confident=False/ghost=[]; core/python skew unrelated to Jinja phase

[2026-09-30T16:52:53Z · sase-1df.6--3] Verified: fresh wheel exposes jinja_completion, jinja_catalog, jinja_scope_variables. Targeted suites pass: test_xprompt_jinja_inspect + catalog_parity (25), test_local_xprompt_conversion + test_prompt_jinja (39), search/todo/yank highlight (25). Ruff clean on all touched files; mypy clean on xprompt adapter files. sase bead epic-symbols reports none. just check still fails at _setup on the pre-existing sase-core skew probe (predict expects confident=True/ghost=[the], wheel@9074b2a returns False/[]) already recorded as PROPOSED FOLLOW-UP; validator and Rust wheel untouched by this phase.

## Dependencies

- **Depends on:** [sase-1df.4](sase-1df.4.md) ✓ · ⧖ 2026-09-30
- **Blocks:** [sase-1df.7](sase-1df.7.md) ✓ · ⧖ 2026-09-30
- **Blocks:** [sase-1df.9](sase-1df.9.md) ✓ · ⧖ 2026-09-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1df.6](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1df.6.md) | [sase-1df.6](sase-1df.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`85b2ce1`](https://github.com/sase-org/sase/commit/85b2ce10385b7809a96f8ca72fe80405934afa56) | feat(xprompt): add Jinja adapter over engine scope variables with parity tests | [sase-1df.6](sase-1df.6.md) | 2026-09-30 13:03:26 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1df.6--3][1] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-1df.7][2] | check python phase done state | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1df.6.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1df.7/README.md

<!-- sase:referenced-by:end -->
