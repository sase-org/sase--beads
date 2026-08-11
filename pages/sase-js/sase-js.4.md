# Bead: sase-js.4 — Builtin refs and prompt ref context

[Bead Pages](../README.md) / [sase-js](README.md) / sase-js.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.athena.y2` · **Assignee:** `sase-js.4` · **Size:** large
**Created:** 2026-08-11 13:21:59 EDT · **Closed:** 2026-08-11 18:09:31 EDT
**Plan:** [202608/artifact\_ref\_contract.md](https://github.com/sase-org/sase--plans/blob/main/202608/artifact_ref_contract.md)

## Description

builtins: thread an explicit per-segment `PromptRefContext` through late prompt processing, implement `@stitch`, `@patch`, `@bead`, and `@agent` resolution on it, record one immutable use row per ref occurrence, and land the legacy parse aliases.

## Notes

[2026-08-11T21:52:48Z · sase-js.4] PROPOSED FOLLOW-UP: Migrate stitch/patch entry resolution from Python into sase-core in a dedicated Rust phase, replacing the unknown_kind placeholder arms, so the LSP and any future frontend share one resolver.

[2026-08-11T21:53:03Z · sase-js.4] PROPOSED FOLLOW-UP: Extend the artifact-ref use wire to schema 2 with the S3.7 field set (span, project, provider, origin, properties, captured_revision, captured_digest); phase 4 can only persist what schema 1 accepts.

[2026-08-11T21:53:16Z · sase-js.4] PROPOSED FOLLOW-UP: Add a cheap sha-to-Patch/stitch-number mapping so @stitch entries can carry the patch and stitch_number properties S3.4 lists.

[2026-08-11T22:09:31Z · sase-js.4] Verified 2026-08-11: 'just install' succeeded (sase-core-rs 0.25.0 built from linked checkout). 'just lint' fully clean (ruff, mypy across 3019 src files, pyscripts, test-wait helpers, changelog, patch/stitch terminology audit, symvision with no stale epic-symbol entries, toobig line limits), exit 0. Targeted suite (tests/artifact_refs tests/artifact_providers tests/test_artifact_ref_uses.py tests/main/test_artifact_cli_show.py): 96 passed. 'just check-full': every lint gate, SASE validation, committed-plans validation, and the full pytest test-cost lane all passed; the only failing gate was the pre-existing cross-workspace flake-baseline gate (test_contract_manifest.py + test_core_vcs_log.py nodes, unrelated to this diff, root cause already tracked on sase-iu/sase-jq), corroborated with an independent +1 on sase-jq rather than re-filed. All three PROPOSED FOLLOW-UP notes from plan S8 are recorded on this bead. Implementation matches plan sase/repos/plans/202608/builtin_refs_and_prompt_ref_context.md: PromptRefContext threading, @stitch/@patch/@bead/@agent builtin resolvers, ref-uses.jsonl manifest, alias/kind-catalog wiring (fixes the @plans: silent-drop regression), and CLI parity in artifact_cli/references.py.

## Dependencies

- **Depends on:** [sase-js.3](sase-js.3.md) ✓ · ⧖ 2026-08-11
- **Blocks:** [sase-js.6](sase-js.6.md) ◐ · ⧖ 2026-08-11
- **Blocks:** [sase-js.7](sase-js.7.md) ◐ · ⧖ 2026-08-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| bbugyi200.athena.sase-js.4 | [sase-js.4](sase-js.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| gh\_sase-org\_\_sase | [`0f3569c`](https://github.com/sase-org/sase/commit/0f3569cb4c46a1bee1629ab64ef831a3535b64d2) | feat(artifact-ref)!: resolve @stitch/@patch/@bead/@agent through an explicit prompt ref context | [sase-js.4](sase-js.4.md) | 2026-08-11 18:14:02 EDT |
