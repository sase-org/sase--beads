# Bead: sase-h7.13.1 — Model what a surface can really submit at creation

[Bead Pages](../README.md) / [sase-h7.13](sase-h7.13.md) / sase-h7.13.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-h7.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-h7.land/README.md) · **Assignee:** `sase-h7.13.1` · **Size:** medium
**Created:** 2026-08-07 23:12:02 EDT · **Closed:** 2026-08-07 23:36:53 EDT
**Plan:** [202608/gate\_inputs\_landing.md](https://github.com/sase-org/sase--plans/blob/main/202608/gate_inputs_landing.md)

## Description

answerability: teach the creation-time answerability probe about the raw-schema escape hatch every surface gained later in the epic, so an option declaring a required property under `properties` is creatable again, while a required name with no control behind it still fails closed.

## Notes

[2026-08-08T03:36:53Z · sase-h7.13.1] answerability: the creation-time probe now credits the raw-schema escape hatch. _client_producible_input builds the probe from input_schema.properties (default/const/enum/type-derived values) when an option declares no inputs, and the raw branch rejects only required names nothing renders a control for — a name absent from properties, or host-collected 'feedback' with feedback mode disabled. Options declaring inputs keep the exact prior behavior (full schema validation of the compiled probe). Value-level constraints (pattern/minLength/type) on declared raw properties no longer reject at creation, since the reviewer types the value into ACE's YAML editor, --option-input, or the mobile bridge. Verified: all six previously failing tests pass UNCHANGED (tests/test_gate_cli_show.py x4, gate_conformance cli/ace-legacy_shared_input); tests/gate_conformance 32 passed 10 skipped. tests/test_gate_custom_validation.py updated where its premise inverted: the unanswerable case now uses a required name absent from properties, plus new tests for a raw required property being creatable+answerable end to end and a pattern-constrained raw property staying creatable; the format test now proves 'format' is annotation-only at both creation and submission (the dead _requires_format remedy branch was removed since no missing name can carry a format). docs/notifications.md answerability paragraph rewritten to state the two shapes. 'just check' green: every lint gate (ruff, mypy, symvision, keep-sorted, changelog, toobig, sase validate) plus the test lane, which escalated to and passed the full suite (core-identity-changed). Changes left uncommitted in the workspace tree.

[2026-08-08T03:37:36Z · sase-h7.13.1] Verified: just check green (all lint gates + full suite escalation); gate conformance 32 passed/10 skipped; six previously failing tests pass unchanged.

## Dependencies

- **Blocks:** [sase-h7.13.4](sase-h7.13.4.md) ✓ · ⧖ 2026-08-07
- **Blocks:** [sase-h7.13.5](sase-h7.13.5.md) ✓ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-h7.13.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-h7.13.1/README.md) | [sase-h7.13.1](sase-h7.13.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f2c6f18`](https://github.com/sase-org/sase/commit/f2c6f1889dce19dac2a34ecfc9b543315a19b241) | fix(gate): credit the raw-schema escape hatch in the answerability probe | [sase-h7.13.1](sase-h7.13.1.md) | 2026-08-07 23:38:18 EDT |
