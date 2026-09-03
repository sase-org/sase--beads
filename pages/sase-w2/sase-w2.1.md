# Bead: sase-w2.1 — Persist the full durable record through TUI dismissal

[Bead Pages](../README.md) / [sase-w2](README.md) / sase-w2.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.8--1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.apollo.8.md) · **Assignee:** `sase-w2.1` · **Size:** medium
**Created:** 2026-09-03 12:31:54 EDT · **Closed:** 2026-09-03 15:40:37 EDT
**Plan:** [202609/athena\_agent\_sync\_repair.md](https://github.com/sase-org/sase--plans/blob/main/202609/athena_agent_sync_repair.md)

## Description

cleanup-serializer: make the cleanup subprocess payload carry every bundle-relevant Agent field (family, model, provider, effort, response path, effective artifacts dir) so manual dismissal stops nulling revival data.

## Notes

[2026-09-03T19:39:41Z · sase-w2.1] PROPOSED FOLLOW-UP: sase/task_types.json snapshot omits the project-local flag task type, so `sase validate` / `just check` fail init memory --check with "`flag` is not in the committed snapshot"; run `sase memory init` to regenerate the snapshot (pre-existing, not caused by this phase).

[2026-09-03T19:40:37Z · sase-w2.1] Cleanup serialize_agent now emits a versioned archive DTO that shares the dismissed-bundle writer field set, resolving effective artifacts_dir from get_artifacts_dir()/index_record_dir before the subprocess. Verified: DTO keys match to_bundle_dict; local and imported/index-projected dismiss through _apply_cleanup_payload_for_result persist family/model/provider/effort/response_path/artifacts_dir; unsupported archive versions raise; legacy unversioned payloads still load; cleanup_payload, bundle, dismiss-persistence, kill/cleanup, and revival e2e tests passed. Lint gates in just check passed; sase validate still fails pre-existing on the missing flag task-type snapshot.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-w2.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-w2.1/README.md) | [sase-w2.1](sase-w2.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`9e2d95b`](https://github.com/sase-org/sase/commit/9e2d95bb0e85eb546502a069c1a0d7d773d715bf) | fix(ace): persist the full durable record through TUI dismissal | [sase-w2.1](sase-w2.1.md) | 2026-09-03 15:42:21 EDT |
