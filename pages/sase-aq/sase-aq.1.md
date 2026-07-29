# Bead: sase-aq.1 — Keyed marker grammar in sase-core

[Bead Pages](../README.md) / [sase-aq](README.md) / sase-aq.1

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-aq.1` · **Size:** medium
**Created:** 2026-07-29 13:07:25 UTC · **Closed:** 2026-07-29 13:16:53 UTC
**Plan:** [202607/agent\_name\_key\_markers.md](https://github.com/sase-org/sase--plans/blob/main/202607/agent_name_key_markers.md)

## Description

grammar: teach `sase_core::agent_name_template` the `{@<id>}` / `{@<id>!}` marker, add a lexical marker scanner and key accessor, and expose both through the `sase_core_py` bindings.

## Notes

[2026-07-29T13:16:53Z · sase-aq.1] Implemented keyed {@<id>} / {@<id>!} template parsing, marker scanning with byte spans, key access, namespace preservation, and Python bindings. Verified cargo fmt --all -- --check, cargo clippy --workspace --all-targets --all-features -- -D warnings, cargo test --workspace --all-features (995 core tests plus all workspace/integration/doc tests), and git diff --check.

[2026-07-29T13:18:20Z · sase-aq.1] Verified cargo fmt --all -- --check, strict workspace clippy, full workspace tests, and git diff --check.

## Dependencies

- **Blocks:** [sase-aq.2](sase-aq.2.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| bbugyi200.athena.sase-aq.1 | [sase-aq.1](sase-aq.1.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`8facc89`](https://github.com/sase-org/sase-core/commit/8facc89d62a65a932adaa9020749f2042f1b06b4) | feat: add keyed agent name template markers | [sase-aq.1](sase-aq.1.md) | 2026-07-29 13:18:36 |
