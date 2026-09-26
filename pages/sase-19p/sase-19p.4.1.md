# Bead: sase-19p.4.1 — Remove the stale family identifier introduced by the close-plumbing phase

[Bead Pages](../README.md) / [sase-19p.4](sase-19p.4.md) / sase-19p.4.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-19p.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-19p.land.md) · **Assignee:** `sase-19p.4.1` · **Size:** small
**Created:** 2026-09-25 21:50:32 EDT · **Closed:** 2026-09-26 06:43:23 EDT
**Plan:** [202609/agent\_closed\_bead\_landing\_cleanup.md](https://github.com/sase-org/sase--plans/blob/main/202609/agent_closed_bead_landing_cleanup.md)

## Description

terminology: remove the retired family wire-key mention from the runner-slot capacity projection docstring and verify the source terminology contract.

## Notes

[2026-09-26T01:58:46Z · sase-19p.4.1] PROPOSED FOLLOW-UP: just fix is red on the clean base tree (ruff F601 duplicate key in tests/test_agent_artifact_marker_path_passing_audit.py:266, Node Finder marker audit area already tracked on sase-19i) — unrelated to this phase

[2026-09-26T10:43:04Z · sase-19p.4.1] PROPOSED FOLLOW-UP: sase tool run check is red on the clean base tree at symvision — 4 stale --epic-symbol entries for closed bead sase-1aa.3 (ModelManifest, ProviderRecord, manifest_provider_names, provider_model_supersedes) in the Justfile _lint-symvision line; unrelated to sase-19p, no owner recorded

[2026-09-26T10:43:23Z · sase-19p.4.1] Docstring fix already on integrated tree via 22e5414a9 (legacy parallel-marker wording, no agent_family mention); verified tests/test_agent_session_terminology.py 2 passed and 4 close-feature suites 74 passed total; sase tool run check red only on pre-existing unrelated symvision stale sase-1aa.3 epic-symbols (recorded as follow-up); no epic-symbols of this phase remain

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-19p.4.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-19p.4.1.md) | [sase-19p.4.1](sase-19p.4.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`fffdaeb`](https://github.com/sase-org/sase/commit/fffdaeb3e84392178f4c7bba0344609e440c859a) | fix(agent-session): finish sase-17m landing gaps and queue capacity plumbing | [sase-19p.4.1](sase-19p.4.1.md) | 2026-09-25 23:46:09 EDT |
