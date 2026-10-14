# Bead: sase-1ko.7 — Claude root bundle via system-prompt file, helper bundle, exact-path native exclusion

[Bead Pages](../README.md) / [sase-1ko](README.md) / sase-1ko.7

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase · **↺ Reopened:** ↺1
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.research.13.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.research.13.linker.w0.md) · **Assignee:** `sase-1ko.7` · **Size:** medium
**Created:** 2026-10-13 18:10:36 EDT · **Closed:** 2026-10-14 07:40:48 EDT
**Plan:** [202610/e3\_explicit\_delivery\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202610/e3_explicit_delivery_cutover.md)

## Previously Closed

> ↺ Closed 2026-10-14T04:11:06Z · done
>
> (none)
>
> Reopened 2026-10-14T10:32:20Z by a status update

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

[2026-10-14T06:54:09Z · sase-1ko.7--2] PROPOSED FOLLOW-UP: just check NEW TUI hint failures reproduce on clean origin/master and are tracked by sase-1hy — test_changed_reply_invalidates_hint_document_and_mappings, test_hinted_raw_prompt_moves_to_identity_and_keeps_its_markers (duplicate identity raw-prompt hint), and test_agent_session_content_hints_are_full_at_both_levels_and_use_phase_workspace (prompt paths missing from body mappings).

[2026-10-14T08:25:56Z · sase-1ko.7--3] PROPOSED FOLLOW-UP: just check NEW TUI raw-prompt failures reproduce on clean origin/master and are tracked by sase-1ia — test_collapsed_preview_shows_quote_bar_and_body_omits_raw_prompt (AGENT RAW PROMPT substring in expanded body) and TestAgentRawPromptRendering.test_done_agent_renders_raw_prompt (compact AGENT PROMPT spacing).

[2026-10-14T08:26:05Z · sase-1ko.7--3] PROPOSED FOLLOW-UP: just check NEW ImportError for _RunManifest in test_conformance_warns_for_duplicate_root_and_leaked_helper_markers reproduces on clean origin/master (dead private import after the class was renamed RunManifest); this phase dropped the unused import so the node passes. Remaining unused public instruction symbols (claude_helper_sources, contains_contract, count_contract_sources, human_rules_blocks, prompt_prefixes, prompt_texts, rules_texts) also reproduce on master and are owned by sase-1ko.10 per epic notes 8-9.

[2026-10-14T09:44:04Z · sase-1ko.7--4] PROPOSED FOLLOW-UP: just check NEW TUI failures reproduce on clean origin/master after sase-1ko.9 — test_agent_session_conversation_sections_are_always_full (truncated plan prompt), test_agent_macro_and_prompt_receive_roles_replies_do_not (substring not found), and TestAgentRawPromptRendering.test_done_agent_renders_raw_prompt (sase-1ia). The schema.json flag entry escalates test-scoped to the full suite, so these origin-red tests surface as NEW.

[2026-10-14T10:32:20Z · bryanbugyi34@gmail.com] I'm not sure if this work is completed or not.

[2026-10-14T10:43:09Z · sase-1ko.7] Fresh real Claude haiku probes through invoke_with_instructions, ToolRun ef6de7a7cf2db82dee3402a063846241. Both returned pong. Enabled: explicit root/helper, one root-file argv, one marker per unique prompt snapshot, no native files, auto-memory absent. Disabled: flag_disabled, both home/workspace CLAUDE.md files load, auto-memory present. Observer limitations reproduce prior notes: duplicate identical snapshots double the raw marker/contract count; numbered native contract headings count as zero.

🔒 sase-1ko.7-live-results.json

[2026-10-14T10:43:49Z · sase-1ko.7] PROPOSED FOLLOW-UP: explicit Claude home-layer observation misses included home references — fresh probe invocation 3bd4ac46-1ea0-4cee-ab95-c11e123b6b4d has home.ref.obsidian and home.ref.tailnet included in the archived bundle, but observe_claude_session reports home=false because it looks for the native home H1. Acceptance phase sase-1ko.10 should reconcile this alongside duplicate prompt snapshots and numbered native contract headings (notes 2-3); adapter delivery itself is verified.

[2026-10-14T10:49:51Z · sase-1ko.7] Recovered the missing Claude implementation on base 8847d07a086b9e930f1a787425ec4c3272ea6824: registered the existing sunset flag sase-1kv, added per-invocation root/helper file lifetimes, exact exclusions plus auto-memory off, independent slot fallbacks, session-id recording, regression tests, and provider docs. Focused suite: 60 passed, 1 skipped in 17.20s. Fresh real haiku flag-on/off probes succeeded (ToolRun ef6de7a7cf2db82dee3402a063846241; attached observer rows). Required check is running as 77e759d13d5e5d73518ed7c4c3a1cdfc; no phase epic-symbol entries remain. Any clean-base check failures must be recorded and this phase closed per the launch instruction.

[2026-10-14T11:10:36Z · sase-1ko.7] PROPOSED FOLLOW-UP: harvest the remaining Claude auto-memory notes — the approved design identifies two non-empty auto-memory directories containing five files, none newer than September 25. With autoMemoryEnabled=false now delivered per invocation, the land agent should triage their migration into reviewed SASE memory; this phase edits no memory notes.

[2026-10-14T11:40:18Z · sase-1ko.7] PROPOSED FOLLOW-UP: required check retains known TUI rendering/hint failures and the stale scoreboard _RunManifest import — ToolRun 77e759d13d5e5d73518ed7c4c3a1cdfc passed all lint/validation, then reported 55694 passed, 19 failed, 31 skipped; verdict no_new_failures (15 KNOWN signatures with independent witnesses). Clean base 8847d07a086b9e930f1a787425ec4c3272ea6824 reproduced 16 failures in ToolRun 9b1d1725316001f985e9f7e048685ec6; the same serial set on this tree produced 17 in 859225b2eab2b571fe50a71ffdaa0314, with all failures confined to the original set and intermittent TUI passes. Relevant existing tasks are sase-1hy and sase-1ia; the scoreboard import is already assigned to acceptance phase sase-1ko.10 in epic notes. Exact comparisons are attached; these pre-existing failures do not keep this phase open.

[2026-10-14T11:40:26Z · sase-1ko.7] Final verification evidence and clean-base/current-tree failure comparison.

🔒 sase-1ko.7-verification.md

[2026-10-14T11:40:48Z · sase-1ko.7] Implemented Claude explicit root/helper file delivery using existing sunset flag sase-1kv, exact SASE-owned exclusions, auto-memory off, atomic per-slot fallback, session tracking, file cleanup, and docs. Verified 60 focused tests (1 skipped) and real haiku flag-on/off probes. Required check 77e759d13d5e5d73518ed7c4c3a1cdfc passed lint/validation; 55694 tests passed, with 19 independently KNOWN failures and no_new_failures verdict. Clean-base/current serial comparisons and proposed follow-ups attached. No epic-symbol entries remain.

## Attachments

- 🔒 sase-1ko.7-live-results.json · application/json · 4.85938 KiB (private attachment)
- 🔒 sase-1ko.7-verification.md · text/markdown · 4.79688 KiB (private attachment)

## Dependencies

- **Depends on:** [sase-1ko.1](sase-1ko.1.md) ✓ · ⧖ 2026-10-13
- **Blocks:** [sase-1ko.10](sase-1ko.10.md) ✓ · ⧖ 2026-10-13
- **Depends on:** [sase-1ko.5](sase-1ko.5.md) ✓ · ⧖ 2026-10-13
- **Depends on:** [sase-1ko.6](sase-1ko.6.md) ✓ · ⧖ 2026-10-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1ko.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1ko.7/README.md) | [sase-1ko.7](sase-1ko.7.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`d265233`](https://github.com/sase-org/sase/commit/d2652334910952f8c244b58d3d32f1ae4ed8d0fd) | feat(claude): deliver explicit root and helper instruction bundles | [sase-1ko.7](sase-1ko.7.md) | 2026-10-14 07:42:50 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1kl.4--1][1] | Verify epic-symbol bead for lint allowlist on master tip | 1 |
| read-by | [agent:sase-1ko.7][2] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-1ko.9--1][3] | Determine whether the stale epic whitelist still protects an unused public symbol | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1kl.4.md
[2]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1ko.7.md
[3]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.sase-1ko.9.md

<!-- sase:referenced-by:end -->
