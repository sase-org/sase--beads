# Bead: sase-hn.8 — Finish the Patch/stitch terminology migration and land epic sase-hn

[Bead Pages](../README.md) / [sase-hn](README.md) / sase-hn.8

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-hn.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-hn.land/README.md) · **Assignee:** `sase-hn.8.land`
**Created:** 2026-08-09 00:10:48 EDT
**Plan:** [202608/patch\_terminology\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202608/patch_terminology_completion.md)

## Description

User-facing output and canonical-module prose everywhere say Patch and stitch, the terminology audit can actually detect a defect instead of rubber-stamping the source tree, and epic sase-hn is closed with its plan marked done.

## Notes

[2026-08-09T08:14:32Z · sase-hn.8.land] LANDING VERIFICATION (blocked, not closing yet). Verified genuinely done: canonical CLI help (sase commit --help says Branch/Patch name, Parent Patch name, Patch status; sase changespec --help dispatches to 'usage: sase patch'); user-facing strings fixed in ace/archive.py, ace/revert.py, ace/restore.py, main/commit_handler.py, workflows/commit/commit_tracking.py, core/status_wire_conversion.py, bead/work.py; garbled ChangeSpecI strings gone (only ChangeSpecInfoPanel legacy aliases remain); both DISCOVERED ISSUE notes on sase-hn resolved (commit_utils/entries.py:7 imports from sase.ace.patch.section_order; parse_timestamp_value public at ace/tui/models/patch_groups/_buckets.py:64); just _lint-symvision passes and the Justfile has no --epic-symbol entries; maintained docs clean (one legitimate legacy-parser mention at docs/change_spec.md:49). No child bead carried a PROPOSED FOLLOW-UP note, so nothing was routed through /sase_new_task. Integration review: the only two non-epic commits since the epic began (57e99f9f6, 64f9383f1, both docs-only from chop.refresh_docs) already use Patch/stitch vocabulary and the audit reports zero docs/ defects at HEAD; no integration work remains. BLOCKING DEFECTS, both introduced by sase-hn.8.5 commit cac21c867: (1) the new gate at Justfile:285-286 invokes the audit with no --allow-missing-linked-repos, and main() exits 1 when default discovery cannot find sase-github/sase-telegram/sase-nvim/chezmoi, so just lint (ci.yml:123), just check, and just check-full fail on every bare checkout and in CI; reproduced here with exit code 1. (2) _is_compatibility_test_or_fixture (patch_stitch_audit.py:333-339) was reverted from the content-aware predicate sase-hn.8.1 shipped in a4a340679 back to a blanket 'return True' for tests/ and smoke/, and test_classifier_accepts_test_tree_fixture_tokens was added to pin that behavior; restoring only that predicate surfaces 2953 hidden defects across 295 files (2709 under tests/ace/tui). This re-creates the exact structural blindness the epic existed to remove and violates the plan's 'do not silence it by loosening a path rule'. Both remain epic work; planned as epic sase_plan_patch_audit_gate_repair with land-epic as its final phase.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-hn.8.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-hn.8.land/README.md) | [sase-hn.8](sase-hn.8.md) | 0 |
