# Bead: sase-13t.2 — Measure and reduce per-release wheel bytes

[Bead Pages](../README.md) / [sase-13t](README.md) / sase-13t.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.11](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.11.md) · **Assignee:** `sase-13t.2` · **Size:** medium
**Created:** 2026-09-20 08:29:29 EDT · **Closed:** 2026-09-20 11:22:21 EDT
**Plan:** [202609/pypi\_quota\_and\_release\_publishing.md](https://github.com/sase-org/sase--plans/blob/main/202609/pypi_quota_and_release_publishing.md)

## Description

shrink: measure link-time options against the 36 MB extension module, land only changes that shrink it without regressing behavior, and report the macOS x86_64 slice decision rather than taking it unilaterally.

## Notes

[2026-09-20T15:18:32Z · sase-13t.2] shrink measurements (nothing landed in sase-core; all numbers reproducible from the sase-core HEAD 92cf0ca tree).

Method: maturin build --release --strip of crates/sase_core_py, one variant per build (profile knobs applied via CARGO_PROFILE_RELEASE_* env or a scratch Cargo.toml copy, never committed). Local toolchain rustc 1.95.0 / maturin 1.15 / glibc 2.39, so absolute bytes differ slightly from CI: the live PyPI 0.34.66 Linux x86_64 wheel has a 38,073,064 B .so and a 15,724,919 B wheel; the local baseline is 38,531,072 B and 16,212,682 B (+1.2% / +3.1%). Deltas are what matter.

variant                      .so raw     d      wheel        d      Rust kernel time vs base
base (thin LTO, opt 3)       38,531,072  --     16,212,682   --     1.00
lto = "fat"                  36,815,520  -4.5%  16,165,827   -0.3%  0.88-0.99 (slightly faster)
opt-level = 2                37,888,544  -1.7%  15,487,548   -4.5%  query kernels ~+5-10%, parse -3..+1%
gateway/HTTP stack opt z*    36,933,152  -4.1%  15,423,182   -4.9%  1.00 on every kernel (cold code)
opt-level = "s"              30,049,504  -22.0% 11,144,887   -31.3% +16-24% on every kernel
opt-level = "z"              25,625,184  -33.5% 9,940,431    -38.7% +56-61% on every kernel
(*) 93 per-package [profile.release.package."name@ver"] overrides for the gateway-only crates plus sase_gateway; hyper/http/socket2/base64 have two versions each, so bare names would be ambiguous.

Runtime method: focused kernel loop (evaluate_many on a compiled corpus of 100 and 1000 specs, compile_query, parse_project_bytes on the 118 KB synthetic file), variants run as separate processes interleaved and rotated over 4-6 rounds, min per-call over rounds. Base: 16.4 us, 1.15 us, 180 us, 5.67 ms. Ratios: o2 1.08/1.11/1.06/0.97; s 1.18/1.24/1.16/1.16; z 1.61/1.56/1.57/1.61; fat 0.99/0.97/0.88/0.93; gateway-z 1.00 on all. (o2 was re-run in a separate 4-round pass whose base was itself noisy, 218 vs 180 us at 1000 specs, and read 1.09/1.13/0.93/1.01; the consistent picture across both passes and the 30-scenario bench is roughly +5-10% on query evaluate/compile, neutral on parse.) Cross-check with the existing tests/perf benches (core_parse, core_query, agent_scan, notification_store; 30 Rust-path scenarios, 4 rotated rounds): geomean of min ratios o2 1.01 (max 1.12), s 1.09 (max 1.31), z 1.25 (max 1.72). The host was shared and heavily loaded, so single-pass benchmark numbers were discarded as noise; only the rotated/min-of-rounds runs are quoted. Baseline behavior check: 1320 of 1321 sase tests that touch sase_core_rs pass on the baseline wheel (the one failure, test_contract_manifest_matches_marker_selection, is a marker-manifest test unrelated to the binding).

Where the bytes are (unstripped baseline, 31.6 MB of attributable symbols): sase_core 28%, monomorphized core/alloc generics 25%, PyO3 glue (sase_core_rs) 12%, serde_json 8%, sqlite C 6.5%, sase_gateway + hyper/h2/axum/rustls/tokio/ring/reqwest ~10%. Text is 32 of 38.5 MB; .eh_frame + .gcc_except_table are 2.9 MB and must stay (PyO3 needs panic = unwind). The hot code and the bulk of the bytes are the same crates, so there is no cold/hot split available at crate granularity except the gateway stack.

Conclusion: every option that saves more than ~5% of wheel bytes costs measurable Rust speed (the plan says report, not take); the only zero-cost one (gateway stack z, -4.9%) needs ~93 versioned override sections that go stale on every dependency bump, and fat LTO saves 0.3% of wheel bytes because the extra .so shrink is absorbed by compression. Kept building the sdist.

macOS: measured on the live 0.34.67 universal2 wheel (29,358,870 B). Fat Mach-O slices: x86_64 35,274,104 B raw / 14,880,891 B deflated, arm64 30,249,280 B raw / 13,543,644 B deflated. An arm64-only wheel would be ~13.58 MB, saving ~15.78 MB per release = 53.8% of the macOS wheel and 20.2% of the 78.33 MB release. It drops Intel Mac support, so the wheel is left universal2 pending the user's decision.

[2026-09-20T15:19:32Z · sase-13t.2] PROPOSED FOLLOW-UP: DECISION NEEDED (user) - build macOS wheel arm64-only instead of universal2? Measured on 0.34.67: saves ~15.78 MB per release (20.2% of 78.33 MB), costs Intel Mac support; wheel left universal2.

[2026-09-20T15:20:22Z · sase-13t.2] PROPOSED FOLLOW-UP: DECISION NEEDED (user) - accept opt-level = "s" for [profile.release]? Measured -31.3% wheel bytes (16.21 -> 11.14 MB Linux; ~24 MB/release across 4 binary wheels) for +16-24% Rust kernel time (e.g. query evaluate 180 -> 209 us at 1000 specs, parse 118 KB 5.7 -> 6.6 ms). Not landed per the plan rule; opt-level 2 (-4.5%, query kernels +6-13%) and z (-38.7%, +56-61%) are the alternatives.

[2026-09-20T15:22:21Z · sase-13t.2] Measured all link-time options on the real extension module; landed nothing, by the plan's rule. Baseline .so 38,531,072 B / wheel 16,212,682 B (PyPI 0.34.66 linux x86_64: 38,073,064 / 15,724,919). lto=fat: .so -4.5% but wheel only -0.3%. opt-level 2: wheel -4.5%, query kernels ~+5-10%. Gateway/HTTP stack at z (93 versioned overrides): wheel -4.9%, 0% runtime, too brittle for the gain. opt-level s: wheel -31.3% for +16-24% Rust kernel time; z: -38.7% for +56-61%. Runtime from rotated min-of-rounds kernel A/B plus the tests/perf benches; behavior baseline 1320/1321 sase core tests pass. macOS universal2 quantified on live 0.34.67: arm64-only saves ~15.78 MB/release (20.2%), drops Intel Macs; left universal2 and filed as a PROPOSED FOLLOW-UP decision. sdist still built; sase-core repo untouched. No epic-symbol entries for this phase.

## Dependencies

- **Blocks:** [sase-13t.6](sase-13t.6.md) ✓ · ⧖ 2026-09-20

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-13t.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-13t.2/README.md) | [sase-13t.2](sase-13t.2.md) | 0 |
