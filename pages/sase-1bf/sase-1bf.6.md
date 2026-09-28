# Bead: sase-1bf.6 — Integrated acceptance on apollo and athena

[Bead Pages](../README.md) / [sase-1bf](README.md) / sase-1bf.6

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** `bbugyi200.kellys_mbp.1d` · **Assignee:** `sase-1bf.6` · **Size:** small
**Created:** 2026-09-27 14:23:42 EDT · **Closed:** 2026-09-27 20:13:36 EDT
**Plan:** [202609/bounded\_agent\_scratch.md](https://github.com/sase-org/sase--plans/blob/main/202609/bounded_agent_scratch.md)

## Description

host-acceptance: after deployment, prove on apollo and athena that the registry finds the agent root, runner exit removes scratch, the backstop reaps dead launches, and disk attribution matches df.

## Notes

[2026-09-28T00:11:40Z · sase-1bf.6] PROPOSED FOLLOW-UP: move sase-core-revision.txt past 90d141e — sase@96524878 requires managed-tmp reap wire schema 4 but the pin (0e8981a) builds schema 3; hosts were set to sase-core origin/master (90d141e) + rebuilt extension for acceptance

[2026-09-28T00:12:05Z · sase-1bf.6] PROPOSED FOLLOW-UP: registry enrolled per-launch dir as root on apollo (~/.cache/sase/tmp/agent-tmp/gh_sase-org__sase-ws16-260927_155334/tmputv9jf5s/managed, first seen 15:58 EDT) — consider refusing paths nested under an already-registered root

[2026-09-28T00:12:32Z · sase-1bf.6] PROPOSED FOLLOW-UP: dead-launch entries stay incomplete while any post-birth same-uid process is unreadable — apollo zombie 635512 (parent stale sase tui --restart-service from Sep 25) + each new sshd session pin old entries; consider exempting zombies since they hold no fds

[2026-09-28T00:12:58Z · sase-1bf.6] PROPOSED FOLLOW-UP: removed stale index.lock (no live holder, dated Sep 27 18:30) on athena sase-core checkout to unblock its fast-forward; watch for the process that crashed mid-fetch

[2026-09-28T00:13:36Z · sase-1bf.6] Host acceptance verified on apollo+athena after updating both to sase@96524878 / sase-core@90d141e with rebuilt schema-4 extension (normal update path: ff clean checkouts, maturin develop). (1) Registry: roots.json lists ~/.cache/sase/tmp on both while apollo service env still lacks SASE_TMPDIR (stale, unchanged); service-env-like reap pass scanned the agent root (apollo 624 scanned/208 age-removed; athena 2171/631 removed ~35GiB). (2) Runner exit: launch_scratch_cleanup status=removed, removed=2, both scratch dirs gone, both hosts. (3) Backstop: synthetic dead key dead_launch_removed=2 both hosts; production entries explained-zero (transient post-birth unreadable sshd/zombie = correct fail-closed; 7 apollo + 63 athena live-held preserved, none removed). (4) Attribution: workspace + managed_tmp + unattributed rows on both; sums within 10pct of df. (5) Buckets: apollo cargo-targets 34G/75 + agent-tmp 68M/62; athena cargo-targets 70G/272 + agent-tmp 568M/236. (6) apollo capture still stale, untouched. No epic-symbols. Follow-ups noted; no local tree changes.

## Dependencies

- **Depends on:** [sase-1bf.1](sase-1bf.1.md) ✓ · ⧖ 2026-09-27
- **Depends on:** [sase-1bf.2](sase-1bf.2.md) ✓ · ⧖ 2026-09-27
- **Depends on:** [sase-1bf.3](sase-1bf.3.md) ✓ · ⧖ 2026-09-27
- **Depends on:** [sase-1bf.4](sase-1bf.4.md) ✓ · ⧖ 2026-09-27
- **Depends on:** [sase-1bf.5](sase-1bf.5.md) ✓ · ⧖ 2026-09-27

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1bf.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1bf.6/README.md) | [sase-1bf.6](sase-1bf.6.md) | 0 |
