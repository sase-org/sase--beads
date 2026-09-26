# Bead: sase-1ah.1 — Recheck E3 precision and verification inputs

[Bead Pages](../README.md) / [sase-1ah](README.md) / sase-1ah.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0st](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0st.md) · **Assignee:** `sase-1ah.1` · **Size:** medium
**Created:** 2026-09-26 07:29:30 EDT · **Closed:** 2026-09-26 07:55:40 EDT
**Plan:** [202609/tool\_e4\_verified\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_e4_verified_completion.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| related | file:explicit:3f5a47aa2857ef19cbfacdd3 | attached via sase artifact create --bead |

<!-- sase:links:end -->

## Description

hermetic-baseline: re-run the KNOWN precision gate, inventory changing lint and bead inputs, and make check fingerprints complete within bounded probe cost.

## Notes

[2026-09-26T11:55:01Z · sase-1ah.1] PROPOSED FOLLOW-UP: stale Justfile --epic-symbol entries for closed bead sase-19x.4 (phase_card_block, block_meta_for_session_shell, session_reply_heading) keep just check lint-symvision red with 8 KNOWN items; owned by that epic land agent, blocks E4 live-demo greenness

[2026-09-26T11:55:16Z · sase-1ah.1] PROPOSED FOLLOW-UP: apollo tool ledger too small for an independent KNOWN precision gate (92 check runs, 29 triaged items: 13 known/12 new/2 flaky/1 unknown); keep no-new receipts athena-only until apollo corpus grows; no mac machine configured so mac rollout is unassessed

[2026-09-26T11:55:40Z · sase-1ah.1] hermetic-baseline done. Backtest re-run (seed 1, default knobs MIN_WITNESSES=1): 718 runs, 3240 KNOWN, known_on_added_or_untracked=0, attribution none=48/718; all 60 sampled KNOWN mechanically re-verified (locator exists at base, unchanged-since-witness recomputed, 0 mismatches), 18 hand-dispositioned pre-existing (Y), incl. all 3 changed-since-witness rows; report retained as file:explicit:3f5a47aa2857ef19cbfacdd3. Apollo read-only: online, 92 check runs too small for independent gate; no mac machine configured. sase-vr left open deliberately: new ruff/mypy/symvision/prettier version probes on check+check-full capture install drift instead of fixing provenance. Probes measured 13/158/79/89ms (total fingerprint 0.49s, within 1s-each/2s-total budget); absent probe yields complete=False/absent-executable (proven, never old-looking success); version change moves canonical digest. Bead/flag state choice documented in docs/tool.md: not fingerprinted (external state), receipts get TTL<=2h enforced in later phases. Tests: 27 passed incl. 2 new (absent-probe incompleteness, check-tools probe lint toolchain). just fix clean. sase tool run check: all file-relevant stages green (fmt, ruff, mypy, flags, keep-sorted, validation, committed-plans); run killed by 9-min transport cap during test-scoped with only 8 KNOWN symvision items from another epic stale symbols (sase-19x.4), none mine; epic-symbols for this phase clean.

## Dependencies

- **Blocks:** [sase-1ah.2](sase-1ah.2.md) ◐ · ⧖ 2026-09-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ah.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ah.1/README.md) | [sase-1ah.1](sase-1ah.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`0b5fc65`](https://github.com/sase-org/sase/commit/0b5fc652b0933891525879b16e16259969d90052) | feat(tool): add hermetic-baseline lint version probes and KNOWN precision recheck | [sase-1ah.1](sase-1ah.1.md) | 2026-09-26 07:57:48 EDT |
