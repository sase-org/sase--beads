# Bead: sase-12w.4 — Detached execution for remote sudo targets

[Bead Pages](../README.md) / [sase-12w](README.md) / sase-12w.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0ms](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0ms.md) · **Assignee:** `sase-12w.4` · **Size:** medium
**Created:** 2026-09-18 08:50:41 EDT · **Closed:** 2026-09-18 12:46:50 EDT
**Plan:** [202609/sudo\_proc\_execution.md](https://github.com/sase-org/sase--plans/blob/main/202609/sudo_proc_execution.md)

## Description

remote: extend `sase sudo exec` and the SSH relay so a remote target authenticates interactively, spawns its own detached executor, and the local finalize proc polls for and fetches the remote ledger; gate the path on an additive contract capability with a synchronous fallback.

## Notes

[2026-09-18T16:46:03Z · sase-12w.4] PROPOSED FOLLOW-UP: investigate unrelated full-suite sidecar failures after sudo remote-detach work — `just check` escalated to the full suite after core binding refresh and failed linked-repo/sidecar materialization tests with staged clones lacking resolvable HEAD plus one linked-repo staging assertion; focused sudo and completion tests pass.

[2026-09-18T16:46:50Z · sase-12w.4] Implemented remote detached sudo target flow; verified focused sudo/completion suite passes (uv run pytest -q tests/completion/test_snapshot.py tests/test_sudo_parser.py tests/test_sudo_ssh.py tests/test_sudo_detach.py tests/test_sudo_execution.py tests/test_sudo_runner.py). Ran just check; it escalated to full suite after core binding refresh and failed unrelated linked-repo/sidecar materialization tests, recorded as PROPOSED FOLLOW-UP.

## Dependencies

- **Depends on:** [sase-12w.2](sase-12w.2.md) ✓ · ⧖ 2026-09-18
- **Blocks:** [sase-12w.5](sase-12w.5.md) ✓ · ⧖ 2026-09-18

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-12w.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-12w.4/README.md) | [sase-12w.4](sase-12w.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`e0f1a8d`](https://github.com/sase-org/sase/commit/e0f1a8d43ad803f64477f73609426409b0c426a7) | feat(sudo): detach remote sudo execution | [sase-12w.4](sase-12w.4.md) | 2026-09-18 12:48:39 EDT |
