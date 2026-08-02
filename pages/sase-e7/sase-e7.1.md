# Bead: sase-e7.1 — Restrict plan-header parsing to the leading block

[Bead Pages](../README.md) / [sase-e7](README.md) / sase-e7.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.rt](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.rt/README.md) · **Assignee:** `sase-e7.1` · **Size:** medium
**Created:** 2026-08-02 13:28:27 UTC · **Closed:** 2026-08-02 13:40:34 UTC
**Plan:** [202608/finish\_dh\_canonical\_archive.md](https://github.com/sase-org/sase--plans/blob/main/202608/finish_dh_canonical_archive.md)

## Description

header-block: stop the Rust plan-header parser from scanning the whole document body, so an ordinary known-label bullet no longer invalidates a plan; publish the fix in a core release, raise the Python floor to it, and drop the plans-sidecar wording workaround.

## Dependencies

- **Blocks:** [sase-e7.5](sase-e7.5.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-e7.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-e7.1/README.md) | [sase-e7.1](sase-e7.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|---|
| sase-core | [`sase-core@d7cfed8`](https://github.com/sase-org/sase-core/commit/d7cfed84d5d7ea0584baa326f5c25abaf94a9293) | fix(plan): restrict header parsing to leading block | [sase-e7.1](sase-e7.1.md) | 2026-08-02 13:41:33 |
| sase--plans | [`sase--plans@f3696ca`](https://github.com/sase-org/sase--plans/commit/f3696ca8bd9f8ee9b9dbe8dacaf7b8d17f867ea6) | docs: restore natural artifacts body label | [sase-e7.1](sase-e7.1.md) | 2026-08-02 14:17:58 |
