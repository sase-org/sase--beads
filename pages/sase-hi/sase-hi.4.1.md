# Bead: sase-hi.4.1 — Publish and verify the compatible core binding

[Bead Pages](../README.md) / [sase-hi.4](sase-hi.4.md) / sase-hi.4.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-hi.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-hi.land/README.md) · **Assignee:** `sase-hi.4.1` · **Size:** medium
**Created:** 2026-08-08 14:50:38 EDT · **Closed:** 2026-08-08 15:13:22 EDT
**Plan:** [202608/finish\_singular\_skill\_landing.md](https://github.com/sase-org/sase--plans/blob/main/202608/finish_singular_skill_landing.md)

## Description

release_compatible_core_binding: publish the release-plz-managed binding that contains the singular skill contract and later compatible core work, then verify the exact distribution.

## Notes

[2026-08-08T19:13:22Z · sase-hi.4.1] Released and verified sase-core-rs 0.21.0 for the singular skill namespace continuation.

Core repo state: opened via sase repo and refreshed to origin/master. Release PR #97 (chore: release v0.21.0) merged at 2026-08-08T18:59:26Z as bf1998a36a5e39523de78361687c38fb0506d9cf. Tag v0.21.0 points at that release commit, and ancestry verifies inclusion of 8a0db5999a9f4dd3a64031cf31ca994151535fc8 (singular skill xprompt references), 83448690a9c54b4342482d66c1e843d290c4564d (Patch/stitch wire contract), and 4071bf083ea59e1ecdb97a64c816d272f3f5ad66 (artifact-ref contract/schema 5). GitHub release v0.21.0 is published at https://github.com/sase-org/sase-core/releases/tag/v0.21.0.

Remote release workflow: Release-plz run 31273296468 for bf1998a completed success at 2026-08-08T19:11:25Z. Jobs green: release-plz release, publish plan, release-plz PR, sdist, linux x86_64, linux aarch64, macOS universal2, windows x86_64, twine check, and publish to PyPI. Wheel smoke jobs passed for supported smoke platforms.

PyPI provenance: PyPI JSON and Simple index expose sase-core-rs 0.21.0 with requires-python >=3.12, sdist sha256 b897ce37ff7dbd4c5f57a47b04a503ee519d405517a5c2959c6ba8dc8d3098c1, manylinux_2_28_x86_64 wheel sha256 94e2978fb02d4754251995b6475ec3be8ca62412e4b214962cc4b7c7236e0a9a, manylinux_2_28_aarch64 wheel sha256 d476bfa4bb609eb811f74c6a0423d74e846b834072fb42ac9f55b029d9ff1e2e, macOS universal2 wheel sha256 930da628141b155fe2a4f2ef89de9b0bfa75b0ba5888276f54ddac5f8eb255e8, and win_amd64 wheel sha256 adf1f26a72613c80ab2a6c2f0aa97b1acf3162ff4f861d2152a47e9e5913a811.

Local source gates passed on the release source: cargo fmt --all --check; cargo clippy --workspace --all-targets -- -D warnings; cargo test --workspace --all-targets; focused cargo test -p sase_core content_layout::tests::, xprompt_catalog::tests::, editor::, artifact_ref::, --test artifact_ref_commit_budget, wire::tests::patch_wire; cargo test -p sase_gateway contract::tests::committed_contract_snapshot_is_current; cargo test -p sase_xprompt_lsp catalog_cache::tests:: and server::tests::completes_xprompt_from_static_catalog; cargo test -p sase_core_py tests::compose_snippet_catalog_binding_returns_plain_dict_shape, tests::parse_patch_project_bytes_binding_emits_canonical_shape_and_query_accepts_it, and tests::artifact_ref_bindings_round_trip_json_shapes. The Rust content-layout focused run covers the inverse split contract accepting skill/foo and app/skill/foo while rejecting skills/foo/app/skills/foo; that splitter is not exported by the Python wheel.

Installed distribution smoke: in disposable venvs with PYTHONPATH empty and no linked checkout override, first installed exact published manylinux_2_28_x86_64 wheel by PyPI JSON URL/hash while Simple index propagated, then verified normal pip install --no-cache-dir --only-binary=:all: sase-core-rs==0.21.0 succeeds. Imported module from venv site-packages, confirmed package version 0.21.0, skill_reference_name('foo') == skill/foo and skill_reference_name('foo', project='app') == app/skill/foo, sase_content_layout schema_version == 5 with plural project/home/home-project skills paths and package:xprompts/skills, Patch parsing emits stitches/stitch_id and evaluates through query, and artifact-ref parse/render/schema/scan APIs are present and working.

Worktrees clean after verification. No PROPOSED FOLLOW-UP entries were needed.

## Dependencies

- **Blocks:** [sase-hi.4.2](sase-hi.4.2.md) ✓ · ⧖ 2026-08-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-hi.4.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-hi.4.1/README.md) | [sase-hi.4.1](sase-hi.4.1.md) | 0 |
