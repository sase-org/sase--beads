# Bead: sase-s9.6 — Mirror the shared grammar extensions in sase-core

[Bead Pages](../README.md) / [sase-s9](README.md) / sase-s9.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0bh](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0bh.md) · **Assignee:** `sase-s9.6` · **Size:** medium
**Created:** 2026-08-23 08:01:39 EDT · **Closed:** 2026-08-23 09:39:37 EDT
**Plan:** [202608/procs\_filter.md](https://github.com/sase-org/sase--plans/blob/main/202608/procs_filter.md)

## Description

rust: port the bare-boolean shorthand and the host bound-key registry into the `sase-core` Rust flat parser, canonicalizer, and evaluator so both implementations of the shared grammar stay byte-identical.

## Notes

[2026-08-23T13:38:31Z · sase-s9.6] PROPOSED FOLLOW-UP: Align flat AND operand order — Python emits field terms in compiled profile order while Rust still emits in first-seen clause order; canonicalize already matches, so parse-AST equality fails for multi-field queries like min:30s max:2h.

[2026-08-23T13:38:48Z · sase-s9.6] PROPOSED FOLLOW-UP: just check fmt/symvision fail independently of this phase — ruff format wants a blank line before _dispatch_result in src/sase/agent/launch_admission.py; symvision reports unused public wait_watch/cli_duration helpers.

[2026-08-23T13:39:05Z · sase-s9.6] PROPOSED FOLLOW-UP: core-identity-changed full suite had 8 unrelated failures — xprompt directive completion parity, CLI completion snapshot key-order drift, agents help wrapping, and a TUI sase-update confirm timeout.

[2026-08-23T13:39:37Z · sase-s9.6] Ported bare-boolean flags and HOST_DATE/DURATION_BOUND_KEYS into the sase-core flat parser, canonicalizer, and evaluator. Verified cargo test -p sase_core (all pass, including new grammar tests); pytest tests/test_query_profile_corpus_facade.py (31 pass: sidecar/flag parse+canonicalize and bound-key eval parity through Rust); just rust-install. just check lint besides pre-existing fmt-py (launch_admission.py) and symvision unused-public reports; core-identity-changed full suite 36256 passed / 8 unrelated failures recorded as follow-up. No --epic-symbol leftovers.

## Dependencies

- **Depends on:** [sase-s9.1](sase-s9.1.md) ✓ · ⧖ 2026-08-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-s9.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-s9.6/README.md) | [sase-s9.6](sase-s9.6.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`f0b932c`](https://github.com/sase-org/sase/commit/f0b932c9d5ce3880cc793f9252a7b4eb56f22c30) | test(query): cover Rust parity for bare flags and bound keys | [sase-s9.6](sase-s9.6.md) | 2026-08-23 09:41:27 EDT |
