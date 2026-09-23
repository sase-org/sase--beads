# Bead: sase-16z.3 — Probe and runner robustness fixes

[Bead Pages](../README.md) / [sase-16z](README.md) / sase-16z.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0q3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0q3.md) · **Assignee:** `sase-16z.3` · **Size:** medium
**Created:** 2026-09-23 11:06:12 EDT · **Closed:** 2026-09-23 13:15:57 EDT
**Plan:** [202609/usage\_window\_collection\_service\_tree.md](https://github.com/sase-org/sase--plans/blob/main/202609/usage_window_collection_service_tree.md)

## Description

probe-robustness: fix the runner's batch-deadline double-record, the probe TypeError re-run, the process-tree kill gap, the worker env allowlist, the 2 s agy/grok version timeouts, Muse's missed-mint blanking, and Codex's best-effort `account/read` poisoning the session. Each fix gets a regression test. This phase is pure Python and needs no core change.

## Notes

[2026-09-23T17:15:57Z · sase-16z.3--4] 7 probe-robustness fixes with regression tests, check green: runner keeps finished-probe records, probe TypeError calls hook once, snapshot SIGKILL for escaping descendants, env allowlist gains proxies/CLAUDE_CONFIG_DIR/NODE_EXTRA_CA_CERTS, agy/grok version timeout 4s, muse missed-mint is timeout, codex reconnects after account/read transport failure

## Dependencies

- **Blocks:** [sase-16z.4](sase-16z.4.md) ✓ · ⧖ 2026-09-23

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-16z.3](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-16z.3.md) | [sase-16z.3](sase-16z.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`caca6b6`](https://github.com/sase-org/sase/commit/caca6b60f9a2263ea29073be42fee94c1b88c52f) | fix(llm-provider): harden usage probe and refresh-runner robustness | [sase-16z.3](sase-16z.3.md) | 2026-09-23 13:18:02 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-16z.3--4][1] | Check whether phase close completed | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-16z.3.md

<!-- sase:referenced-by:end -->
