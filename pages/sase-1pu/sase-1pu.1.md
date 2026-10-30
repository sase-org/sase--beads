# Bead: sase-1pu.1 — Scan and safely recover prompt migrations into the agents sidecar (sase-1os)

[Bead Pages](../README.md) / [sase-1pu](README.md) / sase-1pu.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1pn.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1pn.land.md) · **Assignee:** `sase-1pu.1` · **Size:** medium
**Created:** 2026-10-29 19:19:00 EDT · **Closed:** 2026-10-29 20:58:46 EDT
**Plan:** [202610/task\_backlog\_epic\_3.md](https://github.com/sase-org/sase--plans/blob/main/202610/task_backlog_epic_3.md)

## Description

prompt-migration-protection: route the one-time legacy prompt migration through the shared publication-protection scanner before staging, and stop recommending a raw push after a GH013 rejection. Preserve the existing private/quarantine behavior and sanitized diagnostics. Add regression coverage for clean migration, a detected secret, and a rejected push; ensure no secret value is emitted or replayed.

## Notes

[2026-10-30T00:58:35Z · sase-1pu.1] TASK RESOLVED: sase-1os — migration now scans rewritten prompt text and the generated month index through scan_archive_text_bytes before staging; withheld files stay in the plans sidecar with PROMPT_PROTECTION_BLOCKED. Agents GH013/repo-rule push rejections call recover_publication_push and the recovery message omits git push origin HEAD (no replay). Evidence: tests/agents_sync/test_prompt_archive_migration.py (clean/idempotent, secret withheld + clean sibling, GH013 no re-push) all pass; secret marker absent from agents files and JSON; tool run b01a142d4b6bcde810ca712dfa9de510 lint/docs green, scoped tests no_new_failures with 1 FLAKY contract-manifest mismatch already recorded on sase-1pu.3.

[2026-10-30T00:58:40Z · sase-1pu.1] PROPOSED FOLLOW-UP: test_contract_manifest_matches_marker_selection FLAKY on this tree (committed manifest lists tests/test_core_finalizer_handoff.py which has no pytest.mark.contract) — reproduces on the clean base tree and is already recorded on sase-1pu.3; not caused by this phase.

[2026-10-30T00:58:46Z · sase-1pu.1] Scanned migrated prompts before staging; withheld secrets stay in plans; GH013 recovery does not advise or execute a raw re-push. Verified by test_prompt_archive_migration (clean, secret withheld, GH013) and sase tool run check b01a142d4b6bcde810ca712dfa9de510 (no_new_failures; 1 pre-existing FLAKY contract_manifest cited on sase-1pu.3).

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1pu.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pu.1/README.md) | [sase-1pu.1](sase-1pu.1.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1pu.1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1pu.1/README.md

<!-- sase:referenced-by:end -->
