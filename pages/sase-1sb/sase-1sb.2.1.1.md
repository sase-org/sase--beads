# Bead: sase-1sb.2.1.1 — Define the Rust local-command trust contract

[Bead Pages](../README.md) / [sase-1sb.2.1](sase-1sb.2.1.md) / sase-1sb.2.1.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1sb.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1sb.2.md) · **Assignee:** `sase-1sb.2.1.1` · **Size:** medium
**Created:** 2026-11-11 20:34:37 EST · **Closed:** 2026-11-11 23:06:30 EST
**Plan:** [202611/local\_config\_digest\_trust.md](https://github.com/sase-org/sase--plans/blob/main/202611/local_config_digest_trust.md)

## Description

trust-policy: Implement the pure Rust command-bearing projection, canonical
digest, filtering and trust-decision contracts described in this plan. Add
PyO3 bindings, round-trip tests and a thin Python adapter. Cover normalized
legacy macro spellings, partial overrides of executable definitions, file
hook template references, nested workflow steps and unchanged non-command
keys. Do not activate enforcement yet. Publish core changes through host
finalization and ensure the sase core revision pin contains the bindings.

## Notes

[2026-11-12T04:06:30Z · sase-1sb.2.1.1--2] trust-policy complete: Rust projection/digest/filter/decision + PyO3 bindings, Python adapter src/sase/config/local_trust.py with contract tests; symvision epic-symbols whitelisted, terminology guard fixed; sase tool run check 422a44fa1791eb6c0bb8fec19826b895 verdict pass, epic-symbols empty

## Dependencies

- **Blocks:** [sase-1sb.2.1.2](sase-1sb.2.1.2.md) ✓ · ⧖ 2026-11-11

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1sb.2.1.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1sb.2.1.1.md) | [sase-1sb.2.1.1](sase-1sb.2.1.1.md) | 3 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@e7647bf`](https://github.com/sase-org/sase-core/commit/e7647bf7a37c53ddce11726024c69a55ec877760) | feat(config): add digest-pinned local-command trust contract and bindings | [sase-1sb.2.1.1](sase-1sb.2.1.1.md) | 2026-11-11 22:01:54 EST |
| sase | [`2e7ce5c`](https://github.com/sase-org/sase/commit/2e7ce5cea11b8cd5509d3b90e5567be7a1356852) | feat(config): add local-command trust projection adapter and contract tests | [sase-1sb.2.1.1](sase-1sb.2.1.1.md) | 2026-11-11 22:03:16 EST |
| sase | [`181b213`](https://github.com/sase-org/sase/commit/181b213e8c58f8c90357d1e56cf910b5c727c0ea) | fix(trust-policy): whitelist local-trust adapter in symvision and terminology guard | [sase-1sb.2.1.1](sase-1sb.2.1.1.md) | 2026-11-11 22:53:14 EST |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1sb.2.1.1--1][1] | Check monitor failure for phase bead | 1 |
| read-by | [agent:sase-1sb.2.1.land][2] | Need the child scope and notes | 1 |
| read-by | [agent:sase-1sb.2.1.land--3][2] | Need phase notes and documented lock-race disposition for approved closeout | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1sb.2.1.1.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1sb.2.1.land.md

<!-- sase:referenced-by:end -->
