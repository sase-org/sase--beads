# Bead: sase-4e.5 — Phase 5: Add release-plz To sase-core

[Bead Pages](../README.md) / [sase-4e](README.md) / sase-4e.5

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-4e.5`
**Created:** 2026-06-08 16:31:55 UTC · **Closed:** 2026-06-08 17:10:16 UTC
**Plan:** [202606/automated\_semver\_releases.md](https://github.com/sase-org/sase--plans/blob/main/202606/automated_semver_releases.md)

## Notes

COMMIT: 3e815658c

[2026-07-27T21:32:27Z · sase-a1.land] [2026-06-08T17:06:09Z · bryanbugyi34@gmail.com] (restored 2026-07-27) Phase 5 complete in sibling workspace /home/bryan/.local/state/sase/workspaces/sase-org/sase-core/sase-core_11: added release-plz.toml for git-only vX.Y.Z release management, moved sase-core-rs Python metadata to dynamic Cargo-derived versioning, replaced the tag/PYPI_API_TOKEN wheel workflow with release-plz.yml that runs release first, release-pr second, preserves the wheel/sdist matrix and smoke tests, and publishes via PyPI Trusted Publishing. Validation: actionlint .github/workflows/release-plz.yml; TOML/YAML parser checks; cargo fmt --all -- --check; cargo clippy --workspace --all-targets -- -D warnings; cargo test --workspace; uvx maturin build --manifest-path crates/sase_core_py/Cargo.toml --release --out crates/sase_core_py/dist --strip; fresh-venv wheel import/query/error smoke; uvx twine check crates/sase_core_py/dist/*; release-plz release --dry-run --allow-dirty with gh token; release-plz update check in temporary worktree.

## Dependencies

- **Depends on:** [sase-4e.1](sase-4e.1.md) ✓
- **Blocks:** [sase-4e.6](sase-4e.6.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-4e.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-4e.5/README.md) | [sase-4e.5](sase-4e.5.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`sase-core@74f5e97`](https://github.com/sase-org/sase-core/commit/74f5e97c768aa2200881fb43634ecf03ca243878) | chore: add release-plz release automation (sase-4e.5) | [sase-4e.5](sase-4e.5.md) | 2026-06-08 17:11:36 |
