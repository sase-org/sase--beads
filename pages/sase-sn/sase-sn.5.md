# Bead: sase-sn.5 — Rust core parity for the shared argument grammar

[Bead Pages](../README.md) / [sase-sn](README.md) / sase-sn.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0c5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0c5.md) · **Assignee:** `sase-sn.5` · **Size:** medium
**Created:** 2026-08-24 06:11:48 EDT · **Closed:** 2026-08-24 08:51:25 EDT
**Plan:** [202608/xprompt\_text\_block\_args.md](https://github.com/sase-org/sase--plans/blob/main/202608/xprompt_text_block_args.md)

## Description

rust: mirror the text-block closing rule and the narrowed `+` decoding in the sase-core editor and agent-launch argument scanners, and reconcile their divergent dialects against one shared corpus.

## Notes

[2026-08-24T12:50:36Z · sase-sn.5] PROPOSED FOLLOW-UP: unify remaining argument-scanner dialects — editor ArgScanner quotes only '/" (no backticks, no extra bracket depth), QuoteState also treats backticks as quotes, and agent-launch parsers quote only `/` " plus keep `([{`/`)]}` depth outside text blocks; none of the Rust scanners implement alt_inspect-style backslash escapes

[2026-08-24T12:50:55Z · sase-sn.5] PROPOSED FOLLOW-UP: axe_chop still rejects `+` in clan summaries as unrepresentable because it assumed xprompt decoding always turned `+` into a space — that is now false for [[...]] text blocks; editor colon completion also still aborts when the typed suffix contains `+`

[2026-08-24T12:51:25Z · sase-sn.5] Mirrored the terminator-position [[...]] closer and narrowed + decoding in sase-core ArgScanner, QuoteState, and agent-launch parsers; shared helper tests, Python corpus rows, %clan summary=[[...]] with inner ]], and + decode cases pass; sase-core ./scripts/check.sh all passed; just rust-install then just check passed in sase (scoped escalated full suite, core-identity-changed); Python xprompt/clan/typed-launch tests 152 passed. Epic-symbols empty.

## Dependencies

- **Depends on:** [sase-sn.1](sase-sn.1.md) ✓ · ⧖ 2026-08-24
- **Depends on:** [sase-sn.4](sase-sn.4.md) ✓ · ⧖ 2026-08-24
- **Blocks:** [sase-sn.6](sase-sn.6.md) ✓ · ⧖ 2026-08-24

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-sn.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-sn.5/README.md) | [sase-sn.5](sase-sn.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@1d3c9c6`](https://github.com/sase-org/sase-core/commit/1d3c9c6e5b7bcb408932b31d99473eeb99e49cd2) | fix(xprompt): close \[\[...\]\] blocks at terminator-position \]\] | [sase-sn.5](sase-sn.5.md) | 2026-08-24 08:52:31 EDT |
