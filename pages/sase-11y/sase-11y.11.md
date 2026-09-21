# Bead: sase-11y.11 — Finish the service-host epic leftovers found at landing

[Bead Pages](../README.md) / [sase-11y](README.md) / sase-11y.11

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-11y.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-11y.land.md) · **Assignee:** `sase-11y.11.land`
**Created:** 2026-09-21 07:19:27 EDT · **Closed:** 2026-09-21 11:45:01 EDT
**Plan:** [202609/service\_host\_landing\_leftovers.md](https://github.com/sase-org/sase--plans/blob/main/202609/service_host_landing_leftovers.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/service_host_landing_leftovers.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/service_host_landing_leftovers.md

<!-- sase:links:end -->

## Description

Restarting the sase service host no longer kills detached scheduler, hook, and chat-install runners. The host runtime scenarios the epic plan required are covered by tests. Every TUI surface, help text, and doc describes the shipped Services tab, service host, and scheduler. No `sase-11y` epic-symbol whitelist entry remains.

## Notes

[2026-09-21T15:45:01Z · sase-11y.11.land] LANDED by sase-11y.11.land (workspace sase_32, master f330e2b94 + landing edits committed with this turn).

VERIFIED against source and commits (213c48136, 3bd3d839e, 501310b75, 3b7cfae6f, 420d72bb1):
- .1 detach-runners: CRS, fix-hook, summarize, mentor, checks, hook execution and chat-install spawns go through detach_scope with distinct sase-<kind> prefixes; Popen uses launch.argv/start_new_session.
- .2 services-wording: quit modal option 3 names the service host; bare-x footer hint dropped; help title, onboarding guides, process modal, palette category, doctor next step and screenshot example all use Services vocabulary; goldens regenerated.
- .3 stale-docs: notifications.md receiver paragraph, three blog posts, the restart_attempts schema text, the mobile runbook and ace.md are aligned.
- .4 host-runtime-tests: 8 scenario tests drive the real _ServiceHost/ServiceHostLock (concurrent start, start lock, stale lock, SIGTERM/SIGUSR1, reload, stop-vs-restart race, crash loop, no-oneshot-replay). The startup lock retry and orphaned-oneshot settle fixes are in place. The phase closed without a verify note; I re-ran it here.
- .5 epic-symbols: all seven facades privatized or deleted; Justfile entries gone (epic-symbols empty for sase-11y and sase-11y.11); scheduler start label is "scheduler run".

FIXED AT LANDING (epic-caused):
- Cross-phase breakage: .4's tests/service/test_service_host_scenarios.py imported compose_service_config, which .5 privatized, so the whole file failed at collection. It now uses _compose_service_config (9 passed).
- .5's sase-telegram commit never landed: its commit hook failed on a uv resolve error and the workspace was reclaimed. sase-telegram CI (which installs sase master) was therefore broken. I redid tests/test_service_config.py on the public load_service_config seam, bound at import ahead of conftest's autouse stub. sase-telegram just check: lint clean, 653 passed; the only 2 failures are the sase-156 flake.
- toobig violation from .1: tests/test_detach_scope.py was 1231 lines. Split into test_detach_scope.py, test_detach_scope_runners.py and test_detach_scope_background_workers.py with shared tests/_detach_scope_helpers.py. The live PID test now asserts the reported pid equals Popen.pid.
- detach-runners gap: the file-hook batch runner (file_hooks/dispatch.py) and the async bead sync worker (bead/_sync_publication.py) are spawned by any SDD commit from scheduler or receiver processes. Both are now wrapped in detach_scope, with 4 new tests.
- Host robustness: run_host's startup settle_orphaned_oneshots is now best-effort (logged), like the reconcile loop, so a proc-store error cannot keep the host down. Regression test added.
- Parent note #7 (status blind spot): procs.jsonl is rewritten whole, so any writer with an older sase_core_rs strips the additive service block from every row. On athena, all live host rows lacked it and sase scheduler status / service proc list reported running procs as stopped. Proc.service_name now falls back to the host origin plus the service:<name> tag (new procs/service_meta.host_service_tag_name). _proc_observations uses it, and the TUI Procs query's service/svc fields use is_service_row/service_row_name. Verified live: the workspace build shows scheduler running pid 1949314. Regression tests added. Residual, benign: sase proc kill on a stripped row still kills directly and the host restarts it.

VERIFICATION: just fix clean. Gates pass: ruff, format, keep-sorted, flags, pyscripts, changelog, terminology, toobig, validate, committed plans. just check stops at mypy on src/sase/dev_update/prebuild.py (sase-158). test-waits and symvision are red only on sase-158 and sase-14j findings. Scoped lane: 16819 passed, 9 failed. Of those 9, three are sase-14j unreleased-binding drift and six are load flakes that pass in isolation (sase-13g, sase-154, sase-12c family).

INTEGRATION: the non-epic commits since the epic started (da766b87a sase-14j bead views; 94ccd1917/d9a1de8cc sase-158 update progress; f330e2b94 preview sizing) neither bypass nor duplicate the service host. sase-158's plan already words the CLI restart as "Restart scheduler". No sase-telegram commits landed during the epic.

FOLLOW-UP OUTCOMES:
- .1 #1 (sase-14j symvision) → +1 sase-150 (already a DISCOVERED ISSUE on sase-14j).
- .2 #1 (badge timing) and .2 #2 (codex-usage tmp leak) → +1 sase-14q, same live usage-refresh root cause, fixed 10:07; reopen withheld because the observations predate the close.
- .3 #1 (prebuild mypy) → DISCOVERED ISSUE on causal epic sase-158, together with the test-waits and sanitize_line findings; also on sase-th note #5.
- .5 #1 (receiver-runtime flake) → +1 sase-156, with the same-size mtime-granularity root cause.
- Landing: scope note on sase-11w. Its defect 1 looks fixed by sase-telegram 95354bc, but three docs still prescribe a manual receiver restart.
- Scoped-lane flakes → +1 sase-13g; notes on sase-154 and sase-12c.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-11y.11.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-11y.11.land/README.md) | [sase-11y.11](sase-11y.11.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d05be99`](https://github.com/sase-org/sase/commit/d05be99aad47548f9973b29042cedef8b6c40cab) | fix(service): land sase-11y.11 and finish the service-host leftovers | [sase-11y.11](sase-11y.11.md) | 2026-09-21 11:53:58 EDT |
