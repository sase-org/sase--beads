# Bead: sase-1ko.7 — Claude root bundle via system-prompt file, helper bundle, exact-path native exclusion

[Bead Pages](../README.md) / [sase-1ko](README.md) / sase-1ko.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.research.13.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.research.13.linker.w0.md) · **Assignee:** `sase-1ko.7` · **Size:** medium
**Created:** 2026-10-13 18:10:36 EDT · **Closed:** 2026-10-14 00:11:06 EDT
**Plan:** [202610/e3\_explicit\_delivery\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202610/e3_explicit_delivery_cutover.md)

## Description

claude: create the `claude_explicit_instructions` sunset flag. When it is on, deliver the root bundle with `--append-system-prompt-file` and the helper bundle with `--append-subagent-system-prompt-file`. Exclude SASE-owned root and home instruction files by exact path, and turn auto-memory off per decision. Flag off restores E1's after-state exactly.

## Notes

[2026-10-14T04:08:29Z · sase-1ko.7] PROPOSED FOLLOW-UP: harvest the remaining Claude auto-memory notes — scoreboard/docs still describe auto-memory as Claude foreign; MEMORY.md and # Memory operator notes should be updated now that explicit delivery sets autoMemoryEnabled: false

[2026-10-14T04:08:32Z · sase-1ko.7] Live Claude harness observer rows (haiku print-mode, invoke_with_instructions, cheapest model). Both replies were "pong".

FLAG ON (artifacts e3-claude-ckk4lgu6, session 6f42ef64-06bb-4a4f-951b-7d6b8819e876, invocation f7d34cf4-50ce-49bf-8d75-b82330812041)
- delivery: explicit, channel claude.append_system_prompt_file
- subagent: explicit, channel claude.append_subagent_system_prompt_file, helper sha 3d9017b4143e…
- native files: none
- native-full: 0
- foreign: none (auto-memory off)
- helper heading in root snapshot: false
- unique bundle marker: 1× (bb8aa409fd26 / f7d34cf4-50ce-49bf-8d75-b82330812041)
- concatenated prompt_snapshot marker count: 2 (Claude wrote two identical 27378-byte prompt_snapshot attachments; argv sent --append-system-prompt-file once)

FLAG OFF (artifacts e3-claude-t6x27i0s, session a00d8f50-9b34-4756-82ef-25514951875a, invocation 729d6392-9d20-4c1a-82a0-b421ee755428)
- delivery: inherits_native, fallback.reason flag_disabled
- natives loaded: ~/CLAUDE.md, workspace CLAUDE.md, project MEMORY.md
- native-full: 0 (print-mode attached CLAUDE.md whose contract heading is numbered `#### 1.1.4 SASE Final Declaration`, which does not match the occurrence-exact `#{1,6} SASE Final Declaration` regex; E1's 2× is from fuller agent sessions)
- foreign: auto-memory
- directive: true
- bundle markers: 0

[2026-10-14T04:08:34Z · sase-1ko.7] PROPOSED FOLLOW-UP: Claude writes two identical prompt_snapshot attachments per print-mode turn, so concatenated observer bundle_count is 2 for a single --append-system-prompt-file (unique marker is 1). Conformance may WARN until the observer uniques identical snapshots.

[2026-10-14T04:08:37Z · sase-1ko.7] PROPOSED FOLLOW-UP: test_render_failure_notifies_once patches sase.llm_provider._instruction_boundary.notify_instruction_fallback but invoke_with_instructions imports from instruction_delivery; reproduces on clean master after sase-core 0.39.1 rebuild; already noted on epic sase-1ko #7

[2026-10-14T04:10:41Z · sase-1ko.7] Also fixed test_render_failure_notifies_once patch target (instruction_delivery.notify_instruction_fallback) so the pre-existing sase-1ko.5 seam bug no longer fails scoped tests.

[2026-10-14T04:11:06Z · sase-1ko.7] Verified Claude explicit delivery: sunset flag claude_explicit_instructions (sase-1kv) default on; root via --append-system-prompt-file, helper via --append-subagent-system-prompt-file; exact-path claudeMdExcludes + autoMemoryEnabled false; flag off and no-plan path keep E1 argv. Live haiku harness: flag-on natives 0, unique bundle marker 1, auto-memory off; flag-off natives load, auto-memory on, flag_disabled. epic-symbols clean. Targeted tests 14 passed including notify-once patch-target fix.

## Dependencies

- **Depends on:** [sase-1ko.1](sase-1ko.1.md) ✓ · ⧖ 2026-10-13
- **Blocks:** [sase-1ko.10](sase-1ko.10.md) ◐ · ⧖ 2026-10-13
- **Depends on:** [sase-1ko.5](sase-1ko.5.md) ✓ · ⧖ 2026-10-13
- **Depends on:** [sase-1ko.6](sase-1ko.6.md) ✓ · ⧖ 2026-10-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1ko.7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1ko.7.md) | [sase-1ko.7](sase-1ko.7.md) | 0 |
