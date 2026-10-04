# Bead: sase-1g4.1 — One input-type vocabulary and strict enum declarations

[Bead Pages](../README.md) / [sase-1g4](README.md) / sase-1g4.1

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0wj](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0wj.md) · **Assignee:** `sase-1g4.1` · **Size:** large
**Created:** 2026-10-04 18:19:28 EDT
**Plan:** [202610/macro\_named\_input\_types.md](https://github.com/sase-org/sase--plans/blob/main/202610/macro_named_input_types.md)

## Description

vocab: add the sase-core macro_input_types module (type catalog, resolver, did-you-mean, choice value rules, PyYAML-parity quoting check, enum value check), move every Rust and Python type parser onto it, fix the seven existing enum defects, isolate bad macros, add the strict_macro_input_types sunset flag, generate the JSON schemas, add the config.macro_input_types doctor check, and make #pr's status a real enum.

## Dependencies

- **Blocks:** [sase-1g4.2](sase-1g4.2.md) ◐ · ⧖ 2026-10-04

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1g4.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1g4.1.md) | [sase-1g4.1](sase-1g4.1.md) | 0 |
