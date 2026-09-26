# Bead: sase-1ah.5 — Measure content-equivalent verification repeats

[Bead Pages](../README.md) / [sase-1ah](README.md) / sase-1ah.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0st](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0st.md) · **Assignee:** `sase-1ah.5` · **Size:** medium
**Created:** 2026-09-26 07:29:35 EDT · **Closed:** 2026-09-26 11:06:19 EDT
**Plan:** [202609/tool\_e4\_verified\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202609/tool_e4_verified_completion.md)

## Description

opportunity-report: list receipts and report content-addressed repeat opportunities, including dirty-tree-to-commit equivalence, without changing run behavior.

## Notes

[2026-09-26T15:05:34Z · sase-1ah.5] PROPOSED FOLLOW-UP: installed sase-core-rs 0.34.73 wheel rejects catalog receipt: field so sase tool run check cannot load sase/sase.yml; reproduces identically on clean base tree, needs rebuild/ratchet via just install

[2026-09-26T15:05:45Z · sase-1ah.5] PROPOSED FOLLOW-UP: Justfile symvision carries stale --epic-symbol entries for closed sase-19x.4 (and missing sase-18i), turning just check red repo-wide independent of this phase

[2026-09-26T15:05:55Z · sase-1ah.5] PROPOSED FOLLOW-UP: receipts opportunity report reads the ledger via read-only Python SQLite; migrate to a Rust tool_run_receipts_report binding if E4b needs cross-frontend parity

[2026-09-26T15:06:19Z · sase-1ah.5] Added sase tool receipts [-d/--days N] [-j/--json]: lists retained receipts (receipt/run/verdict/age/status) and content-addressed repeat opportunities (counts, summed duration/hours, top tools, observation window, schema_version 1). Equivalence keys on tool/definition/extra-args/toolchain/env/inputs plus Git-blob content comparison (dirty sha256 vs git show HEAD:path, diff coverage), so a dirty tree committed and rechecked at a new HEAD counts; missing objects/incomplete fingerprints are uncomparable, never guessed. Read-only ledger access; run behavior unchanged. Verified: 5 new report tests (incl. dirty-to-commit fixture, uncomparable case) + 2 parser tests pass, full receipts+parser suite 32 passed, ruff and mypy clean, no new symvision findings. sase tool run check and just symvision fail identically on the clean base tree (stale core wheel vs catalog receipt: field; stale sase-19x.4 epic-symbols) — recorded as PROPOSED FOLLOW-UP entries.

## Dependencies

- **Depends on:** [sase-1ah.4](sase-1ah.4.md) ✓ · ⧖ 2026-09-26
- **Blocks:** [sase-1ah.7](sase-1ah.7.md) ◐ · ⧖ 2026-09-26

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ah.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ah.5/README.md) | [sase-1ah.5](sase-1ah.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`473871c`](https://github.com/sase-org/sase/commit/473871ceea6b68748793875bca1daef39ca68558) | feat(tool): add receipts opportunity report for content-equivalent repeats | [sase-1ah.5](sase-1ah.5.md) | 2026-09-26 11:08:37 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1ah.5][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ah.5/README.md

<!-- sase:referenced-by:end -->
