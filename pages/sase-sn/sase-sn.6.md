# Bead: sase-sn.6 — End-to-end regression coverage and documentation

[Bead Pages](../README.md) / [sase-sn](README.md) / sase-sn.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0c5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0c5.md) · **Assignee:** `sase-sn.6` · **Size:** small
**Created:** 2026-08-24 06:11:49 EDT · **Closed:** 2026-08-24 09:26:57 EDT
**Plan:** [202608/xprompt\_text\_block\_args.md](https://github.com/sase-org/sase--plans/blob/main/202608/xprompt_text_block_args.md)

## Description

regression: add a launch-level regression test built from the real failing prompt, add a shared cross-language corpus, and update the xprompt grammar documentation.

## Notes

[2026-08-24T13:26:32Z · sase-sn.6] PROPOSED FOLLOW-UP: document the [[...]] terminator-position closing rule in sase/memory/xprompts.md Invoke section — needs explicit user permission plus sase memory init

[2026-08-24T13:26:57Z · sase-sn.6] Launch-level #name:: prose-with-]] fixture binds one positional, expands into %clan summary=[[...]] without DirectiveError, and the launch pre-scan emits nothing; shared Python/Rust xprompt_args_corpus.json (8 cases) is consumed by parse_args, ArgScanner, and parse_directive_args_with_names; docs/xprompt.md states the terminator-position closing rule, structural shorthand binding, and trailing-]] workaround. just check passed (scoped escalated full suite, core-identity-changed). sase-core cargo test --lib corpus: 8 passed. Epic-symbols empty.

## Dependencies

- **Depends on:** [sase-sn.1](sase-sn.1.md) ✓ · ⧖ 2026-08-24
- **Depends on:** [sase-sn.2](sase-sn.2.md) ✓ · ⧖ 2026-08-24
- **Depends on:** [sase-sn.3](sase-sn.3.md) ✓ · ⧖ 2026-08-24
- **Depends on:** [sase-sn.4](sase-sn.4.md) ✓ · ⧖ 2026-08-24
- **Depends on:** [sase-sn.5](sase-sn.5.md) ✓ · ⧖ 2026-08-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-sn.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-sn.6/README.md) | [sase-sn.6](sase-sn.6.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`1907346`](https://github.com/sase-org/sase/commit/1907346f8e4170ee31f639db9fe452930bff9ce5) | test(xprompt): add text-block launch regression and shared corpus | [sase-sn.6](sase-sn.6.md) | 2026-08-24 09:28:05 EDT |
| sase-core | [`sase-core@81f114a`](https://github.com/sase-org/sase-core/commit/81f114a2ac7f1f01d1ffa4e0988fcedada214236) | test(xprompt): parse the shared text-block argument corpus | [sase-sn.6](sase-sn.6.md) | 2026-08-24 09:30:35 EDT |
