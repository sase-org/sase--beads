# Bead: sase-1jx.7.1 — Complete project onboarding and sase project add

[Bead Pages](../README.md) / [sase-1jx.7](sase-1jx.7.md) / sase-1jx.7.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1jx.7](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1jx.7.md) · **Assignee:** `sase-1jx.7.1.land`
**Created:** 2026-10-11 19:14:21 EDT · **Closed:** 2026-10-12 04:21:56 EDT
**Plan:** [202610/project\_add\_engine.md](https://github.com/sase-org/sase--plans/blob/main/202610/project_add_engine.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202610/project_add_engine.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 3 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202610/project_add_engine.md

<!-- sase:links:end -->

## Description

Deliver the convergent add-existing CLI and reusable onboarding engine required by sase-1jx.7, then close that phase with verified evidence.

## Notes

[2026-10-12T08:21:56Z · sase-1jx.7.1.land] Verified the four closed phases against plan:202610/project_add_engine.md and the commits 9756adf38e, 431dfab812, 791c1797b9, and 4ccfc62c8f.

plan-documents: detect_actor honors SASE_AGENT, SASE_AGENT_NAME, discover_agent_identity, SASE_MONITOR_ID, SASE_GATE_COMMAND=1, and a nonempty SASE_PROJECT_CREATE_BYPASS. gather_facts is read-only. Journals are atomic 0o600 files under $SASE_HOME/project_onboarding/journals, matched by identity and fingerprint, and only complete records older than 30 days are pruned. build_plan_document goes through Rust plan_project_onboarding.

managed-recovery: manage.py journals marker, commit, and push evidence and reobserves Git instead of trusting a lost response. Rust facts setup_required, management_incomplete, and config_changes_owned are in sase-core 4bd08c6e, which sase-core-revision.txt pins.

convergent-apply: apply_plan locks identity then checkout, revalidates under the locks, runs checkout, reenable, identity, manage, and current, and leaves init as a handoff. create_remote is refused.

add-command: sase project add has the specified flags, check, TTY confirm, NDJSON, and PROJECT_ADD durable IO. Docs and the skill source describe preview, agent setup refusal, and the init handoff. glossary:sase-project says add registers an existing repository and that create and the wizard create one; onboarding leaves PROJECT_STATE unset. human_only_record=no was honored: no new decision record.

Integration: master commits after 9756adf38e that are not this epic are Archive TUI work, test splits, wait_checks, and the agent-display renderer. They do not add a second registration path. Their Justfile edits only dropped unrelated archive epic-symbols.

Landing: journal_path, journal_lock_path, and journal_lock are private. They had no non-test caller outside journal.py, and sase-1jx.8 and sase-1jx.10 use the higher-level journal API. Their epic-symbol rows are gone. The skill description names add. The render module docstring no longer treats plan rendering as future work.

Checks: the project_onboarding suite passed. sase tool run check 795fed0da389e11f335ab004bfa3e6f4 had green lint and symvision, then 55024 passed, 17 skipped, and 6 failed (verdict new_failures: 2 NEW, 4 KNOWN). None of those failures are in the onboarding engine.

Follow-ups: import budget 3518<3513 got +1 on sase-1ic (proposed by .1 #1, .2 #1, .3 #1, .4 #1); triage called it NEW for lack of a witness, and the count matches 791c1797b9 before the CLI commit. Project: fake and Project: tmp got +1 on sase-1k4 (proposed by .2 #1, .3 #1, .4 #1 and #2); KNOWN, root cause df61663204. project/suggest:owner is the only uncaptioned completion slot and was filed as a DISCOVERED ISSUE on sase-1jx, which still owns suggest; no new task. Marker-path audit and project-current help from .1 #1 were declined: later full-suite notes and this check did not fail them. test_explicit_provider_is_remembered (NEW) and test_options_forward_to_discovery (KNOWN, witness 0409af70242a4314f4aa519ba6c48ebb) return 2 in the suite when gh is absent from the live provider registry and pass in isolation (6 passed); DISCOVERED ISSUE on sase-1jx, not an add-engine defect. Leaving project add REF as the global ref-to-artifact completion kind was declined: the slot is captioned and the committed cli_spec snapshot records it.

[2026-10-12T08:32:09Z · sase-1jx.7.1.land] Post-close just symvision failed on --epic-symbol sase-1jm.3.1(archive_read_only_context). That bead closed at 2026-10-12T08:11:59Z during this landing's check, and the re-key its close note describes was not in this tree or on origin/master (HEAD 4ccfc62c8f). sase-1jm.4.1.3 (Lifecycle and Provenance cards) was still open and is the planned consumer named in plan:202610/agents_archive_landing_finish.md, so the Justfile row was re-keyed to sase-1jm.4.1.3(archive_read_only_context) and a comment above _lint-symvision names that consumer. just symvision then exited 0. This epic's own epic-symbols stay empty. sase-1jx remains open for the create and wizard phases.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1jx.7.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.7.1.land/README.md) | [sase-1jx.7.1](sase-1jx.7.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`8ed37c4`](https://github.com/sase-org/sase/commit/8ed37c4ef868db73fca1b870691d6f31f8846a4e) | fix(project-onboarding): retire sase-1jx.7.1 symbol exemptions | [sase-1jx.7.1](sase-1jx.7.1.md) | 2026-10-12 04:56:56 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1jx.7.1.1][1] | Need status to re-key stale epic-symbols | 2 |
| read-by | [agent:sase-1jx.7.1.3][2] | Need child epic decisions and notes | 2 |
| read-by | [agent:sase-1jx.7.1.land][3] | Need the epic scope, children, and linked plan file | 4 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.7.1.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.7.1.3/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1jx.7.1.land/README.md

<!-- sase:referenced-by:end -->
