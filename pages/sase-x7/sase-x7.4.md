# Bead: sase-x7.4 — Move Telegram to the shared pending-action API

[Bead Pages](../README.md) / [sase-x7](README.md) / sase-x7.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase · **↺ Reopened:** ↺1
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0gk](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0gk.md) · **Size:** medium
**Created:** 2026-09-05 18:55:29 EDT · **Closed:** 2026-09-07 12:40:55 EDT
**Plan:** [202609/canonical\_only\_fleet\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202609/canonical_only_fleet_cutover.md)

## Previously Closed

> ↺ Closed 2026-09-07T01:53:45Z · done
>
> (none)
>
> Reopened 2026-09-07T02:17:00Z by `sase bead open`

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| related | file:explicit:0055032c3703cd5e84e1df52 | attached via sase artifact create --bead |
| related | file:explicit:0866e26bb727d1f9ebd0b1e0 | attached via sase artifact create --bead |
| related | file:explicit:18808b952bc7f56b0ffc6178 | attached via sase artifact create --bead |
| related | file:explicit:1dc23e6db17332ca1f3d125a | attached via sase artifact create --bead |
| related | file:explicit:1e925693d40103585b71bdea | attached via sase artifact create --bead |
| related | file:explicit:3487e65f9728edeeb0e76a63 | attached via sase artifact create --bead |
| related | file:explicit:667ed72940cc689f9f1ee248 | attached via sase artifact create --bead |
| related | file:explicit:6ccbd14764372769b55e37dc | attached via sase artifact create --bead |
| related | file:explicit:77e709d6b08a824e718c5a41 | attached via sase artifact create --bead |
| related | file:explicit:84ec33cfe595b167768d5407 | attached via sase artifact create --bead |
| related | file:explicit:aa5956ebc7c9e927d01fb261 | attached via sase artifact create --bead |
| related | file:explicit:b6bf8034d5285540eeebbe64 | attached via sase artifact create --bead |
| related | file:explicit:bd4a9c08054d406064d49374 | attached via sase artifact create --bead |
| related | file:explicit:d8da212e874a2f1b3ad3a1ce | attached via sase artifact create --bead |
| related | file:explicit:e2d9beaf3705ddd7b37906e0 | attached via sase artifact create --bead |
| related | file:explicit:ed5727c5a734f4f87ef41dbe | attached via sase artifact create --bead |
| related | file:explicit:fe67ddb3cfb6b6263e489481 | attached via sase artifact create --bead |

<!-- sase:links:end -->

## Description

telegram-bridge: Implement and test the Telegram adapter to the canonical shared pending-action store, preserving existing callback identities, locking, terminal states, and transport metadata. Stage the required host/core API and publish a wheel usable by the remote machines while old host readers remain available.

## Notes

[2026-09-07T01:53:45Z · sase-x7.4] Implemented Rust-backed shared pending-action API and Telegram transport adapter; verified core just check, main just check with corrected core wheel, Telegram just check, and isolated core/host/Telegram wheel smoke.

[2026-09-07T02:15:34Z · 016--1] SUPERVISION RECOVERY / 016--1 / 2026-09-07T02:15:03.127378+00:00
The prior phase implementation did NOT finish finalization. Original run artifacts timestamp 20260906184530, PID 115011: commit finalizer started at 01:54Z and remained in just fix -> Rust LSP build at 02:06Z. Stable done.json at 02:09:30Z recorded FAILED: main stitch returned No staged changes; finalizer then reported dirty work vanished. Its input snapshot had HEAD fdfb4e238a386b5470a67025da8db1c30bc92e90 and three dirty paths (Justfile, src/sase/notifications/pending_actions.py, tests/test_pending_actions.py). Audited original workspace reflog shows reset to origin/master 09c93253dc76bb71c71ee4e855de7998172abb73 at 02:07:47Z; tree is now clean. Runtime additionally reported original workspace claim not found. Actor/root cause of the reset is not established; do not invent a code fix or overwrite another agent's work.
The source run was removed from the runtime during investigation, but these durable recovery diffs survive: CORE file:explicit:0866e26bb727d1f9ebd0b1e0 (39742 bytes, base 0ce37bfdaa0b1b6460a66c83fe779b260776c1a6; six modified Rust files), TELEGRAM file:explicit:6ccbd14764372769b55e37dc (8950 bytes, base e7582519941e733397ee593753648effa0675e7f; four files). Read through sase artifact read and open target repos through /sase_repo; adapt/apply the preserved diffs in your fresh assigned checkout after checking newer work. Reconstruct the three missing host files from the phase requirements and core API. Original tests were core just check, host just check, Telegram just check (587 passed), and isolated three-wheel smoke; rerun appropriate verification for recovered changes. Original source commit receipts contain only bead closure, no host/core/Telegram implementation commits.
Supervisor is reopening this phase because the deliverables were not committed. Retry sase-x7.4.r0 uses the unchanged original task at codex/gpt-6-astra@xhigh and should finish all repo finalizers; board sase-xu tracks it. Use the installed monitor syntax with command after -- if verification requires a monitor. Never infer success from a submitted declaration or draft final text alone.

[2026-09-07T02:21:19Z · 016--1] RECOVERY ADDENDUM / 016--1 / 2026-09-07T02:21Z: A separately initiated same-name rerun at artifacts 20260906221416 failed at 02:16:57Z solely because this phase was still closed. Its exact raw task matches the original phase assignment; our prepared sase-x7.4.r0 now uses that latest stored raw prompt. The supervisor has since successfully run sase bead open sase-x7.4, so this claim blocker is repaired. No live phase replacement exists yet; the queued monitor launch will create it. Preserved core/Telegram diff refs in the preceding note remain the recovery source.

[2026-09-07T02:34:56Z · 016--2] MONITOR COMMAND CORRECTION / 016--2 / 2026-09-07T02:34:32.430306+00:00
The installed CLI joins all command words after -- with spaces, then executes sh -c. Passing separate argv entries for python -c <multiline code> or sh -c <compound script> loses their original argument grouping. Epoch016 monitor p71c3z676v1n failed before any retry launched for this reason. The safe prepared recovery uses an actual Python script file and its interpreter as the monitor command; nested sase run calls use subprocess argv. For your own verification monitor use one correctly shell-quoted command string or a script file, not the earlier unquoted sh -c example. Explicitly pass -m codex/gpt-6-astra@xhigh with --next. The x7/xq retries remain pending and will launch from the cycle2 monitor after a fresh duplicate check.

[2026-09-07T02:51:07Z · sase-x7.4.r0] Recovery implementation restored in the assigned checkout and extended with Rust-owned atomic transport operations, collision refusal, terminal-state/deadline preservation, legacy callback tombstones, and concurrency/corruption regressions. Three pre-verification source diff snapshots are attached to this bead for recovery. Verification is now staged in /tmp/sase-x7.4-verify.py: core just check, host just install/check, Telegram just install/check, three wheel builds, and isolated Python 3.12/3.14 wheel smoke. No phase closure or implementation finalization has occurred yet.

[2026-09-07T03:03:05Z · sase-x7.4.r0--1] Verification attempt rwebsqxq2jfc stopped with exit 127 because the Rust binding test could not load uv Python 3.14 libpython; earlier Rust suites reported no assertions failing. Confirmed the library exists and ldd resolves all dependencies with the selected interpreter LIBDIR on LD_LIBRARY_PATH. The revised scratch harness pins PYO3_PYTHON and the loader path, preserves original failed logs, and writes the next attempt to /tmp/sase-x7.4-verification-r2. Isolated wheel smoke removes that loader override and checks imports originate inside each fresh virtualenv. A fresh source archive including untracked Rust transport modules and the latest legacy-menu regression is attached. PROPOSED FOLLOW-UP: Make sase-core scripts/check.sh configure the selected interpreter LIBDIR for binding tests on uv-managed Python installs; root just check currently chooses Python 3.14 without making its shared library discoverable.

[2026-09-07T03:14:32Z · sase-x7.4.r0--2] Verification attempt k59m605bnp2x failed at imports that exist in the recovered source. Global Cargo configuration uses /mnt/poseidon/cargo-target; recent core dep-info files omit the new transport module, consistent with cross-checkout stale artifact reuse. The r3 scratch harness now uses a checkout-specific Cargo target, retains the Python loader fix, and compares source HEADs and dirty-file hashes after every step. Review also found and repaired overlap between an available host record and an old callback: merge the legacy callback view without writing either source on reads, retain original expiry and metadata on promotion, refuse mismatched full IDs, and preserve terminal masking after removal. Two Rust regressions added; Rust formatting and Python targeted static checks passed, full verification remains pending. New complete source archive file:explicit:bd4a9c08054d406064d49374 includes all three repositories, untracked transport files, r2 failure logs, and the r3 harness. No implementation commits or phase closure yet.

[2026-09-07T03:26:45Z · sase-x7.4.r0--3] Attempt 4ykg1vfmrap2 reached the actual pending-action tests: 2119 passed and one legacy-menu timestamp regression failed. Fixed compatibility reads resetting a reused menu to the retired callback creation time, and retained tombstones when removing/expiring that reused menu while its old key remains in the legacy store. Extended the regression through reuse, removal, reuse again, and expiry. Rust formatting and diff whitespace checks pass; full verification is pending. Source snapshot file:explicit:18808b952bc7f56b0ffc6178 preserves all 14 dirty source files across host/core/Telegram, tracked diffs, r3 failed logs, and the r4 verification harness. Next attempt writes /tmp/sase-x7.4-verification-r4. No implementation commits or phase closure yet.

[2026-09-07T03:48:32Z · sase-x7.4.r0--4] Attempt 4x3wth6wx16b passed the complete core root check (including the repaired legacy-menu regression and PyO3 binding tests) and host just install, then failed host mypy because reconstructed pending_actions.py omitted PENDING_ACTION_PREFIX_LEN. Restored the existing public value 8; 15 pending-action tests and 19 plan inventory/show tests pass, as do targeted Python formatting/lint and diff whitespace checks. Source manifests match r4 exactly except for that one restored host constant. The r5 harness reuses the passing core-check and host-install receipts only after asserting that provenance, then resumes host-check, Telegram install/check, wheel builds and isolated Python 3.12/3.14 smoke. The smoke now also imports both affected plan views and tests legacy callback retirement without changing the old store. Complete 14-file source recovery archive file:explicit:b6bf8034d5285540eeebbe64 (sha256 67911d909053c2100746a055fe274cbb30d068c28e840146b5e4441061b37b26) includes all three repos and r4 receipts/logs. Draft deployment note is /tmp/sase-x7.4-deployment-note.md; fill verified evidence and actual wheel refs before publication. No implementation commits or phase closure yet.

[2026-09-07T04:08:47Z · sase-x7.4.r0--5] Verification r5 passed all host lint gates and 6,185 tests, with one failure in test_config_schema_validates_dispatch_machine_records. Base commit 09c93253d defines dispatch twice in both the public JSON schema and default YAML; later federation entries hide enrollment entries. Consolidated both pairs without changing their declared values, added duplicate-key regressions, and exercised federation plus enrollment in one config. All 10 config-schema tests pass; targeted Python formatting/lint and whitespace checks pass. The r6 harness reuses unchanged core-check/host-install evidence, runs the required host check-full after the default-config repair, and collects Telegram checks, wheel builds and isolated Python 3.12/3.14 smoke even if an independent check fails. No implementation commits or phase closure yet.

[2026-09-07T06:22:07Z · 016--5] RECOVERY CHECKPOINT / supervisor 016--5 / 2026-09-07: sase-x7.4.r0--6 failed before doing any work because the full-family fork grew to 1,316,146 characters, exceeding the provider 1,048,576 input limit. It has no response/finalizer and no active continuation. Previewing restart of the shell is refused because -- is reserved; nothing killed or wiped. We will retry the exact ORIGINAL phase raw task (no recursive fork) as allocated hood child sase-x7.4.r0.r0, codex/gpt-6-astra@xhigh, pres

… and 10021 more characters

## Dependencies

- **Depends on:** [sase-x7.1](sase-x7.1.md) ✓ · ⧖ 2026-09-05
- **Depends on:** [sase-x7.2](sase-x7.2.md) ✓ · ⧖ 2026-09-05
- **Depends on:** [sase-x7.3](sase-x7.3.md) ✓ · ⧖ 2026-09-05
- **Blocks:** [sase-x7.5](sase-x7.5.md) ◐ · ⧖ 2026-09-05
- **Blocks:** [sase-x7.7](sase-x7.7.md) ◐ · ⧖ 2026-09-05

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-x7.4](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-x7.4.md) | [sase-x7.4](sase-x7.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e0c5755`](https://github.com/sase-org/sase/commit/e0c5755033ff0e17c5b306a6c703901ada67b1f4) | feat(notifications): expose Rust-backed shared pending-action transport API | [sase-x7.4](sase-x7.4.md) | 2026-09-07 16:50:21 EDT |
| sase-core | [`sase-core@f7852f5`](https://github.com/sase-org/sase-core/commit/f7852f54f2b2962b71b7692f71d3ef699ddafd1d) | feat: Move Telegram to the shared pending-action API (sase-x7.4) | [sase-x7.4](sase-x7.4.md) | 2026-09-07 16:54:26 EDT |
