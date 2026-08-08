# Bead: sase-h7.3 — Declarative per-option inputs and per-option submission

[Bead Pages](../README.md) / [sase-h7](README.md) / sase-h7.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase · **↺ Reopened:** ↺2
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.v2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.v2/README.md) · **Assignee:** `sase-h7.3--code` · **Size:** large
**Created:** 2026-08-07 17:07:30 EDT · **Closed:** 2026-08-07 18:23:33 EDT
**Plan:** [202608/gate\_input\_collection.md](https://github.com/sase-org/sase--plans/blob/main/202608/gate_input_collection.md)

## Previously Closed

> ↺ Closed 2026-08-07T22:07:49Z · done
>
> (none)
>
> Reopened 2026-08-07T22:08:20Z by `sase bead open`

> ↺ Closed 2026-08-07T21:41:32Z · done
>
> (none)
>
> Reopened 2026-08-07T21:47:05Z by `sase bead open`

## Description

inputs-core: add the closed per-option `inputs:` authoring vocabulary built on `InputArg`/`InputType` (plus a new `enum` type), compile it into the option's `input_schema` at creation, and teach the executor to accept and persist one input value per selected option instead of one shared blob.

## Notes

[2026-08-07T21:47:44Z · sase-h7.3] PROPOSED FOLLOW-UP: sase commit auto-closes the workspace's assigned phase bead too eagerly for multi-repo phases — after committing the sase-core (linked-repo) half of this phase's Rust changes via sase_git_commit, the tool's before-commit hook (sase_git_fix) immediately closed sase-h7.3 with resolution=done, even though this phase's primary-repo (sase) implementation, tests, just check-full verification, and primary commit were all still in progress. Reopened via 'sase bead open sase-h7.3' and continued work. Suggest the auto-close heuristic should not fire on a linked/sidecar-repo commit alone, or should confirm the primary repo's working tree is also clean/committed before closing the workspace's assigned bead.

[2026-08-07T22:05:52Z · sase-h7.3] PROPOSED FOLLOW-UP: just check-full's 'SASE validation' step (sase plan links validate) fails by default in this phase-worker's ephemeral workspace because only the phase's own plan file (sase/repos/plans/202608/gate_inputs_core.md) was materialized locally, not its PARENT epic plan (202608/gate_input_collection.md), even though the parent exists in the canonical global store at ~/.sase/plans/202608/gate_input_collection.md. Worked around by manually copying the parent file into the local (gitignored) plan-store mirror so validation could resolve the PARENT link; 'sase plan links repair' did not detect or fix the gap. If every single-phase workspace hits this, the workspace setup (or 'sase init'/'sase repo open') should sync each plan file's PARENT chain into the local plan store alongside the phase file itself, or 'sase plan links repair' should detect and offer to fetch a missing PARENT target from the global store.

[2026-08-07T22:06:33Z · sase-h7.3] PROPOSED FOLLOW-UP: for custom-validation (sase-h7.5) — the compiled 'pattern' anchors in compile_gate_input_schema (src/sase/notification_gates/model_inputs.py) are approximate under Python's re: '$' matches before a single trailing newline, so 'ab\n' satisfies the compiled word ('^\S+$') and line ('^[^\n]*$') fragments even though InputArg.validate_and_convert rejects the same value. The table is implemented verbatim from the plan because it is portable ECMA-262, where $ has no such leniency; sase-h7.5 is the phase that pins the JSON Schema dialect/validator and should close this gap (e.g. anchor with \z or a validator configured for ECMA-262 semantics).

[2026-08-07T22:06:53Z · sase-h7.3] PROPOSED FOLLOW-UP: for inputs-remote (sase-h7.8) — MobileXpromptInputWire.type is a free-form String, so the new 'enum' xprompt input type (added in sase-h7.3 to src/sase/xprompt/models.py's InputType) reaches the mobile app as an unrecognized type and renders as plain text instead of a proper choice picker. Not fixed here per the gate_inputs_core plan's explicit scope boundary; inputs-remote owns the mobile wire and Telegram step flow for declared inputs.

[2026-08-07T22:23:33Z · sase-h7.3] Implementation complete: enum InputType+choices in shared xprompt vocabulary (models.py, loader_parsing.py, prompt_frontmatter.py); GateInputField/compile_gate_input_schema authoring layer (model_inputs.py); GateOption.inputs with exact-equality conflict detection against input_schema; per-option submission via resolve_option_inputs/redact_option_inputs (executor_inputs.py) wired into execute_gate_selection; response["input"] reader gap closed via effective_response_input in adapters.py; Rust sase-core enum support committed separately (a35fe9180e2d4dc756b08019a9951cec9088c0d2). Resolved a rebase conflict in executor.py against concurrent journal/feedback-input-injection work that landed upstream, preserving both the resolve-then-validate loop and the error-recording wrap. Verified with 'just check-full': fmt, all lint gates (ruff, mypy, pyscripts, changelog, symvision, toobig), SASE validation, and the full test suite all pass (exit 0). Commit 8e52e4638 on master.

## Dependencies

- **Blocks:** [sase-h7.10](sase-h7.10.md) ✓ · ⧖ 2026-08-07
- **Blocks:** [sase-h7.5](sase-h7.5.md) ✓ · ⧖ 2026-08-07
- **Blocks:** [sase-h7.6](sase-h7.6.md) ✓ · ⧖ 2026-08-07
- **Blocks:** [sase-h7.8](sase-h7.8.md) ✓ · ⧖ 2026-08-07
- **Blocks:** [sase-h7.9](sase-h7.9.md) ✓ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-h7.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-h7.3.md) | [sase-h7.3](sase-h7.3.md) | 3 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@a35fe91`](https://github.com/sase-org/sase-core/commit/a35fe9180e2d4dc756b08019a9951cec9088c0d2) | feat(xprompt): add enum input type with declared choices | [sase-h7.3](sase-h7.3.md) | 2026-08-07 17:41:48 EDT |
| sase | [`8e52e46`](https://github.com/sase-org/sase/commit/8e52e46386c7a7950f3335e6e9ae58d8c388df90) | feat(notification-gates): add declarative per-option inputs and per-option submission | [sase-h7.3](sase-h7.3.md) | 2026-08-07 18:17:17 EDT |
| sase--plans | [`sase--plans@2f213a1`](https://github.com/sase-org/sase--plans/commit/2f213a1ed034a10a36ae9fe333a42c37b05c1d8a) | docs: add SDD plan for gate\_input\_collection epic | [sase-h7.3](sase-h7.3.md) | 2026-08-07 18:28:17 EDT |
