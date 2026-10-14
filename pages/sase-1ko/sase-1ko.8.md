# Bead: sase-1ko.8 — Codex developer-instructions delivery, project-doc suppression, and shadow-home hygiene (folds sase-11s)

[Bead Pages](../README.md) / [sase-1ko](README.md) / sase-1ko.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.research.13.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.research.13.linker.w0.md) · **Assignee:** `sase-1ko.8` · **Size:** medium
**Created:** 2026-10-13 18:10:36 EDT · **Closed:** 2026-10-14 00:15:23 EDT
**Plan:** [202610/e3\_explicit\_delivery\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202610/e3_explicit_delivery_cutover.md)

## Description

codex: create the `codex_explicit_instructions` sunset flag. When it is on, deliver the whole root bundle through `developer_instructions`, add `project_doc_max_bytes=0` in SASE-managed projects only, and leave the shadow home without any SASE AGENTS.md. Rebuild the shadow home from an allowlist so shared sqlite state is never linked (closes sase-11s), and declare the subagent slot inherits_root.

## Notes

[2026-10-14T04:13:49Z · sase-1ko.8] Codex probes: codex-cli 0.162.1 rejected codex-mini-latest for this ChatGPT account (HTTP 400), so both accepted probes used gpt-6-luna and exited 0. Flag on: explicit via codex.developer_instructions, subagent inherits_root, marker 1, contract explicit 1/native 0, native-full 0, project/directive true; home.ref.obsidian and home.ref.tailnet included (observer home-H1 false). Flag off: inherits_native with flag_disabled, home/project native docs and directive true, marker 0; native contract/full counts were 0 on this host, unlike the E1 planning row. Focused Codex ToolRun: 53 passed.

[2026-10-14T04:14:18Z · sase-1ko.8] PROPOSED FOLLOW-UP: Reconcile the live Codex observer rows with E1 acceptance — 0.162.1 flag-on included home memory refs but observer home-H1 was false; flag-off loaded home/project docs yet exact contract/native-full stayed 0 rather than the planning 2×, so the acceptance phase should compare the underlying rollout evidence.

[2026-10-14T04:14:33Z · sase-1ko.8] PROPOSED FOLLOW-UP: Align the Codex small tier with ChatGPT-account support — Codex CLI 0.162.1 rejected codex-mini-latest with HTTP 400; gpt-6-luna succeeded for both acceptance probes.

[2026-10-14T04:14:45Z · sase-1ko.8] PROPOSED FOLLOW-UP: Resolve the unchanged Symvision private import _RunManifest in src/sase/instructions/show.py — final ToolRun 39e9608b1c3e4c4fb7e47a807364afac failed only at this existing lint item, reproduced by just _lint-symvision; closed phase sase-1ko.4 already records the same baseline issue. No task bead matched, and the source file is unchanged from HEAD.

[2026-10-14T04:15:23Z · sase-1ko.8] Codex explicit delivery, sunset flag, project-doc suppression, thread-id recording, and allowlist shadow home implemented; 53 focused Codex tests and both gpt-6-luna live probes passed. epic-symbols was empty. Final sase tool run check passed all prior gates and fails only on the unchanged Symvision _RunManifest private import already noted on sase-1ko.4; proposed follow-up recorded.

## Dependencies

- **Depends on:** [sase-1ko.1](sase-1ko.1.md) ✓ · ⧖ 2026-10-13
- **Blocks:** [sase-1ko.10](sase-1ko.10.md) ◐ · ⧖ 2026-10-13
- **Depends on:** [sase-1ko.5](sase-1ko.5.md) ✓ · ⧖ 2026-10-13
- **Depends on:** [sase-1ko.6](sase-1ko.6.md) ✓ · ⧖ 2026-10-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1ko.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1ko.8/README.md) | [sase-1ko.8](sase-1ko.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`429353b`](https://github.com/sase-org/sase/commit/429353b015be5e4f644a6ee5762be5dd3df64e6b) | feat(codex): deliver explicit root instructions | [sase-1ko.8](sase-1ko.8.md) | 2026-10-14 00:17:31 EDT |
