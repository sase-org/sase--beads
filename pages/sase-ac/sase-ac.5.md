# Bead: sase-ac.5 — Mirror the identity fix in the Rust core catalog

[Bead Pages](../README.md) / [sase-ac](README.md) / sase-ac.5

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-ac.5` · **Size:** medium
**Created:** 2026-07-28 11:41:49 UTC · **Closed:** 2026-07-28 12:41:06 UTC
**Plan:** [202607/xprompt\_project\_identity.md](https://github.com/sase-org/sase--plans/blob/main/202607/xprompt_project_identity.md)

## Description

core_parity: apply the same canonical-name namespacing and filtering to the Rust xprompt catalog in the sase-core repo so the LSP and gateway agree with Python.

## Notes

[2026-07-28T12:38:54Z · sase-ac.5] Implemented Rust xprompt catalog canonical project identity in sase-core: lifecycle records now key enabled workspaces by PROJECT_NAME fallback, resolve directory-key/name/alias refs, namespace and tag project entries canonically, normalize requested filters, and deduplicate root-plus-registry discovery. Added Rust coverage for PROJECT_NAME, aliases, legacy fallback, canonical namespace/tag, no directory-key entry, and key/name/alias filtering. Verified with cargo fmt --all -- --check, cargo clippy --workspace --all-targets -- -D warnings, and cargo test --workspace.

[2026-07-28T12:40:07Z · sase-ac.5] Implemented Rust xprompt catalog canonical project identity in sase-core: lifecycle records now key enabled workspaces by PROJECT_NAME fallback, resolve directory-key/name/alias refs, namespace and tag project entries canonically, normalize requested filters, and deduplicate root-plus-registry discovery. Added Rust coverage for PROJECT_NAME, aliases, legacy fallback, canonical namespace/tag, no directory-key entry, and key/name/alias filtering. Verified with cargo fmt --all -- --check, cargo clippy --workspace --all-targets -- -D warnings, and cargo test --workspace.

## Dependencies

- **Depends on:** [sase-ac.2](sase-ac.2.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ac.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ac.5/README.md) | [sase-ac.5](sase-ac.5.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`sase-core@2034123`](https://github.com/sase-org/sase-core/commit/20341233d36bd492497a715fe0ac25985dd4eb28) | fix(xprompt): canonicalize project identities in catalog (sase-ac.5) | [sase-ac.5](sase-ac.5.md) | 2026-07-28 12:43:17 |
