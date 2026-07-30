# Bead: sase-al.1 — Fix sase-core clippy lints and release 0.12.5

[Bead Pages](../README.md) / [sase-al](README.md) / sase-al.1

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-al.1` · **Size:** small
**Created:** 2026-07-28 21:37:18 UTC · **Closed:** 2026-07-28 21:45:24 UTC
**Plan:** [202607/fix\_ci\_core\_clippy\_and\_minimum.md](https://github.com/sase-org/sase--plans/blob/main/202607/fix_ci_core_clippy_and_minimum.md)

## Description

fix-core-clippy-and-release: allow too_many_arguments on close_issues_with_note, drop two clone-on-Copy calls in tests, land the fix on sase-core master, then merge the release-plz PR and verify sase-core-rs 0.12.5 reaches PyPI with plan-header schema 2.

## Notes

[2026-07-28T22:20:34Z · sase-al.1] Fixed sase-core clippy lints and released 0.12.5. Added #[allow(clippy::too_many_arguments)] to close_issues_with_note (mutation.rs) and to the py_bead_close pyo3 binding (sase_core_py/src/lib.rs, an extra 9-arg violation not listed in the plan), and dropped the two clone_on_copy calls in the close-note tests (mutation.rs, bead/cli.rs). Verified locally with just rust-check (cargo fmt --check + clippy --workspace --all-targets -D warnings + cargo test --workspace) all clean. Landed as sase-core master 461c7f1 via sase commit; master CI run 30402012749 green. release-plz refreshed PR #42 to head 04aab77, its CI run 30402752940 went green, merged (squash) as a7a3121. Release-plz run 30403013933 succeeded with all publish jobs green and tag v0.12.5 pushed. Confirmed via PyPI JSON that sase-core-rs latest is 0.12.5 (5 files), and installed sase-core-rs==0.12.5 into a throwaway venv where tools/smoke_sase_core_rs_plan_header exits 0 reporting schema_version 2. No changes made in the sase repo, so just check was not applicable.

## Dependencies

- **Blocks:** [sase-al.2](sase-al.2.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-al.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-al.1/README.md) | [sase-al.1](sase-al.1.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`sase-core@461c7f1`](https://github.com/sase-org/sase-core/commit/461c7f1b410c1c3a979ef7fbc21a64db30451a91) | fix(beads): resolve clippy lints in close-note support | [sase-al.1](sase-al.1.md) | 2026-07-28 21:46:19 |
