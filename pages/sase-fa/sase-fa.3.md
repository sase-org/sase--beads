# Bead: sase-fa.3 — Narrow the durable outbox back to agent-hood retries

[Bead Pages](../README.md) / [sase-fa](README.md) / sase-fa.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.t4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.t4/README.md) · **Assignee:** `sase-fa.3` · **Size:** medium
**Created:** 2026-08-05 14:26:37 EDT · **Closed:** 2026-08-05 17:08:34 EDT
**Plan:** [202608/revert\_async\_sidecar\_publication.md](https://github.com/sase-org/sase--plans/blob/main/202608/revert_async_sidecar_publication.md)

## Description

queue: drop the `bead_pages`, `plan_header`, and `sidecar_push` request kinds, bump the outbox schema so existing v4 files load without resurrecting them, and revert doctor, ACE, status, and prompt-archive validation to agent-hood-only semantics.

## Notes

[2026-08-05T21:08:34Z · sase-fa.3] queue phase done: outbox narrowed to agent-hood retries.

Models: dropped PublicationKind/PUBLICATION_KIND_RANK/ordering_rank/SidecarPublicationRequest, the bead_pages/plan_header/sidecar_push constructors, and the kind-specific fields (bead_id, lineage_root, plan_ref, commit_message, sidecar_kind). AgentPublicationOutboxItem is back to its v3 field set with the (global_agent, primary_revision) logical key and pre-epic id/to_json_dict payload.

Schema: PUBLICATION_OUTBOX_SCHEMA_VERSION bumped 4 -> 5; readers accept 1-5. A v4 file loads cleanly with every non-agent_hood record dropped (not resurrected, not raising) and returns a PublicationOutboxDocument carrying a notice naming the count and per-kind breakdown. New snapshot_publication_document_from_path surfaces it; sase doctor renders it as a WARN detail + next step, so the drop is visible rather than silent. Preserved: flock read-modify-write, atomic_write_json, per-item attempts/last_error/quarantined/terminal, duplicate-logical-key rejection at read time, and the lock-free non-mutating snapshot (test asserts the v4 file is byte-identical after a snapshot read).

Reverted to agent-hood-only: operations (multi-kind enqueue helpers, rank ordering, publication_status_diagnostics), diagnostics (publication_request_subject, no publications-lane text), facade exports, git_sync's tautological kind filter, commit_publication's three kind filters, chat_catalog_provenance/sidecars, agents_sync/status (back to publication_quarantine_diagnostics), ace agents_sync_format + agents_sync_indicator (attention_count and the queue-diagnostics tooltip block), and doctor checks_agent_publication (multi-kind data + the not-draining/publications-lumberjack diagnostic). Preserved 0e40decdc's unreadable-local-owner-manifest diagnostic. prompt_archive/validation: deleted _queued_agent_hood_publications and the 'publication is queued' arm plus the now-unused project_key parameter (and its cli_prompts caller); prompt-unpublished and plan-unresolved stay at warning severity. _link_validation/_link_support/parser_plan/plan_links_handler/--strict left untouched per the plan.

Verified: new test writes a v4 outbox with one agent_hood + one bead_pages + one plan_header + one sidecar_push, asserts the agent-hood request survives with an unchanged logical key, the other three drop with the diagnostic, the file is not rewritten by the read, and a later mutation persists schema 5 with no kind field. v1/v2/v3 round-trip tests and the two-process concurrency test pass unchanged. Doctor tests cover the dropped-request WARN and still cover quarantined/retired/stalled agent-hood requests. just lint clean (ruff, mypy over 2748 files, symvision, toobig). Targeted pytest green: tests/agents_sync (all), tests/doctor, tests/history, tests/test_bead, tests/test_commit_workflow_{publication,resume,checkpointing}.py, tests/test_sdd_commit_store.py, tests/test_axe_run_agent_exec_plan_followup_approvals.py, tests/test_committed_plan_validation.py, tests/test_commit_publication_inline.py, and the agents-sync ace tests (1396 + 769 + 59 passed). Live sase doctor runs clean through the new reader; this machine's gh_sase-org__sase outbox is already empty at v4, so no live records needed dropping.

Full 'just test' was not run: the whole-suite run is SIGTERM-killed (exit 144) in this sandbox, so coverage was taken via the targeted subsets above plus the complete static gate.

Not in scope, left to phase land: docs/agents_sidecar.md:360 and docs/beads.md:534 still mention 'sidecar_publication'/the publications lane.

## Dependencies

- **Depends on:** [sase-fa.2](sase-fa.2.md) ✓
- **Blocks:** [sase-fa.5](sase-fa.5.md) ◐

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-fa.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fa.3/README.md) | [sase-fa.3](sase-fa.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`ccf4d77`](https://github.com/sase-org/sase/commit/ccf4d77a9b1ffe83936e81c082040d61d2b8af60) | feat!: narrow the durable publication outbox back to agent-hood retries | [sase-fa.3](sase-fa.3.md) | 2026-08-05 17:10:00 EDT |
