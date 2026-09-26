# Bead: sase-1ah.4 — Mint and query receipts on both execution paths

[Bead Pages](../README.md) / [sase-1ah](README.md) / sase-1ah.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0st](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0st.md) · **Assignee:** `sase-1ah.4` · **Size:** medium
**Created:** 2026-09-26 07:29:34 EDT · **Closed:** 2026-09-26 10:41:35 EDT
**Plan:** [202609/tool\_e4\_verified\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_e4_verified_completion.md)

## Description

receipt-execution-cli: wire foreground and handed-off settlement to Rust minting and expose a truthful receipt query with versioned JSON and exact exit codes.

## Notes

[2026-09-26T14:41:12Z · sase-1ah.4] PROPOSED FOLLOW-UP: Justfile symvision lint fails on stale --epic-symbol entries for closed bead sase-19x.4 (phase_card_block, block_meta_for_session_shell, session_reply_heading); reproduces on clean base tree, triaged KNOWN with no owner — needs a task bead and Justfile cleanup.

[2026-09-26T14:41:35Z · sase-1ah.4] receipt-execution-cli done: Rust settle wired after E3 triage on both foreground and adopted worker paths (shared run_recorded_body); sase tool receipt TOOL [-a/--accept {pass,no-new}] [-j/--json] exits 0 covered / 1 typed refusal / 2 usage with versioned JSON; every run still spawns. Verified: 15 new tests/tool/test_receipts.py pass (mint+query, drift refusal with path, handoff parity, no-skip, ad-hoc/bypass/flag-off negatives, partial-write and missing-binding fail-open, no landing-gate language); 64 related tests pass (parser, executor, handoff, query, catalog); just check lint gates pass (ruff, mypy, fmt, keep-sorted, flags) except pre-existing stale sase-19x.4 epic-symbols symvision failure (recorded as PROPOSED FOLLOW-UP, reproduces on clean base). No epic-symbols for sase-1ah.4.

## Dependencies

- **Depends on:** [sase-1ah.3](sase-1ah.3.md) ✓ · ⧖ 2026-09-26
- **Blocks:** [sase-1ah.5](sase-1ah.5.md) ✓ · ⧖ 2026-09-26
- **Blocks:** [sase-1ah.6](sase-1ah.6.md) ✓ · ⧖ 2026-09-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ah.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ah.4/README.md) | [sase-1ah.4](sase-1ah.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`2811476`](https://github.com/sase-org/sase/commit/281147666b7ce353cb46fc1031870e72c9c7cd6d) | feat(tool): add receipt execution CLI with settle adapter and receipt query | [sase-1ah.4](sase-1ah.4.md) | 2026-09-26 10:43:44 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ah.3][1] | Need to avoid overlapping receipt-execution-cli work | 1 |
| read-by | [agent:sase-1ah.4][2] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-1ah.7][3] | Need sibling phase close evidence for landing-proof | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ah.3/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ah.4/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ah.7/README.md

<!-- sase:referenced-by:end -->
