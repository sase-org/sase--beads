# Bead: sase-h7.9 — sase gate answer, act, and show

[Bead Pages](../README.md) / [sase-h7](README.md) / sase-h7.9

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.v2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.v2/README.md) · **Assignee:** `sase-h7.9` · **Size:** medium
**Created:** 2026-08-07 17:08:13 EDT · **Closed:** 2026-08-07 19:21:00 EDT
**Plan:** [202608/gate\_input\_collection.md](https://github.com/sase-org/sase--plans/blob/main/202608/gate_input_collection.md)

## Description

gate-cli: add headless `answer`, `act`, and `show` subcommands to `sase gate` and build the cross-surface conformance fixture matrix that runs the same input cases through ACE, the mobile bridge, and the CLI.

## Notes

[2026-08-07T23:19:20Z · sase-h7.9] PROPOSED FOLLOW-UP: flip ACE/mobile conformance capabilities when inputs-ace and inputs-remote land — tests/gate_conformance/_surfaces.py declares CAP_OPTION_INPUTS (and mobile CAP_SHARED_INPUT/CAP_RETRY) as unsupported, so 17 of 42 matrix cases skip today; sase-h7.6 and sase-h7.8 should add the capability to SURFACES and drop the entry from PENDING_CAPABILITY_PHASES so those cases start asserting.

[2026-08-07T23:21:00Z · sase-h7.9] Added headless sase gate answer/act/show and the cross-surface conformance matrix. answer: repeatable --option, --set typed by the declared inputs field (int/float/bool/enum/repeatable coercion, broadcast to every selected option that accepts the key, unknown key names the accepted keys), --option-input OPT=@file|-|literal, --input for the legacy shared value, mutual-exclusion errors, --resume/--restart mapped to the executor retry parameter with a partial_attempt error naming both flags, exit codes 0/1/3. act: runs run_command actions (repeatable, gate stays pending, --input, display-aware output, --json) and edit_file actions via $VISUAL/$EDITOR with resolve_edit_path/accept_edited_origin and a rejected draft kept in the origin file. show: branches, per-option declared fields with type/required/default/choices/secret, raw-schema summary, and declared actions, human + --json. gate_operation_from_envelope gained kind=None for kind-agnostic lookup. Verified: new tests/gate_conformance/ matrix (14 cases x cli/ace/mobile drivers calling each surface's real entry point; 25 pass, 17 skip with the capability declared as pending sase-h7.6/sase-h7.8) plus 32 per-subcommand CLI tests; full 'just check' green (every lint gate, SASE validation, scoped test lane), and an earlier full-suite run passed 3712 tests after updating the gate-subparser assertion in tests/main/test_notify_handler.py.

## Dependencies

- **Blocks:** [sase-h7.12](sase-h7.12.md) ◐ · ⧖ 2026-08-07
- **Depends on:** [sase-h7.3](sase-h7.3.md) ✓ · ⧖ 2026-08-07
- **Depends on:** [sase-h7.4](sase-h7.4.md) ✓ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-h7.9](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-h7.9/README.md) | [sase-h7.9](sase-h7.9.md) | 0 |
