# Bead: sase-hi.4.2 — Adopt the release and integrate the latest primary tree

[Bead Pages](../README.md) / [sase-hi.4](sase-hi.4.md) / sase-hi.4.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-hi.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-hi.land/README.md) · **Assignee:** `sase-hi.4.2` · **Size:** medium
**Created:** 2026-08-08 14:50:47 EDT · **Closed:** 2026-08-08 16:12:47 EDT
**Plan:** [202608/finish\_singular\_skill\_landing.md](https://github.com/sase-org/sase--plans/blob/main/202608/finish_singular_skill_landing.md)

## Description

adopt_release_and_reconcile_primary: require the published binding, reconcile later Patch and artifact-ref adoption, and prove the combined singular-skill contract with full repository gates.

## Notes

[2026-08-08T20:12:47Z · sase-hi.4.2] Adopted and verified the published core binding in the primary tree. Current origin/master is 25be8cc68 with pyproject.toml requiring sase-core-rs>=0.21.0,<0.22.0 and uv.lock pinned to sase-core-rs 0.21.0 from PyPI. Lock provenance: sdist sha256 b897ce37ff7dbd4c5f57a47b04a503ee519d405517a5c2959c6ba8dc8d3098c1; macOS universal2 wheel 930da628141b155fe2a4f2ef89de9b0bfa75b0ba5888276f54ddac5f8eb255e8; manylinux aarch64 d476bfa4bb609eb811f74c6a0423d74e846b834072fb42ac9f55b029d9ff1e2e; manylinux x86_64 94e2978fb02d4754251995b6475ec3be8ca62412e4b214962cc4b7c7236e0a9a; win_amd64 adf1f26a72613c80ab2a6c2f0aa97b1acf3162ff4f861d2152a47e9e5913a811. Post-start audit: 3e6da8d5f landed sase-hn.2 Patch/storage adoption and 25be8cc68 landed the 0.21 launch/artifact compatibility restoration; sase-ho.2 remains in_progress and I did not recreate its Python ref-registry work. Added a release-boundary smoke to tools/validate_sase_core_rs requiring skill_reference_name to return skill/foo and app/skill/foo, content-layout schema 5, plural external skill directories, and package:xprompts/skills; tests cover stale skills/foo, schema 3, and package:skills failures. Verified local linked-core dev install with just install; tools/validate_sase_core_rs --sase-core-dir sase/repos/linked/sase-core passed; focused regression suite passed 214 tests across validator, content-layout, package resources, skill loader/expansion, editor/LSP, ACE prompt completion/jump, Patch compatibility, and artifact_refs; exact PyPI wheel smoke in a disposable venv installed sase-core-rs==0.21.0 with PYTHONPATH empty and returned skill/foo, app/skill/foo, schema 5, package:xprompts/skills, and artifact-ref schema versions 4/1/2. Stale plural-reference audit found only intentional negative assertions and external skills directory fixture paths. just docs-check passed; just build-check passed with sdist/wheel twine check; just test-visual passed 563 passed, 1 skipped; just check passed after SASE init repo refresh, with the scoped lane escalating to the full suite. just check-full passed lint, SASE validation, committed plans, and the full pytest lane, then exited 1 at selection-health --fail-on-new-flake because the known historical bd/work_task classifier issue is still reported; tests/test_bead_xprompt_tags.py passes 15/15 on the current tree and the issue is already tracked by ready task sase-hl, so no new PROPOSED FOLLOW-UP was created.

[2026-08-08T20:14:10Z · sase-hi.4.2] Verified exact PyPI wheel smoke for sase-core-rs 0.21.0, focused validator regressions, docs-check, build-check, visual tests, and just check; check-full passed full lint/SASE/pytest before the known sase-hl selection-health flake-baseline failure.

## Dependencies

- **Depends on:** [sase-hi.4.1](sase-hi.4.1.md) ✓ · ⧖ 2026-08-08
- **Blocks:** [sase-hi.4.3](sase-hi.4.3.md) ◐ · ⧖ 2026-08-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-hi.4.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-hi.4.2/README.md) | [sase-hi.4.2](sase-hi.4.2.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`5170a39`](https://github.com/sase-org/sase/commit/5170a3986737e900e2858d7a5897ac34e896a9cc) | fix: validate current skill layout binding contract | [sase-hi.4.2](sase-hi.4.2.md) | 2026-08-08 16:15:25 EDT |
