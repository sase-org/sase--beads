# Bead: sase-b2.7 — ACE copy mode yields bead and agent references

[Bead Pages](../README.md) / [sase-b2](README.md) / sase-b2.7

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-b2.7` · **Size:** medium
**Created:** 2026-07-30 01:33:43 UTC · **Closed:** 2026-07-30 03:00:11 UTC
**Plan:** [202607/bead\_and\_agent\_artifact\_refs.md](https://github.com/sase-org/sase--plans/blob/main/202607/bead_and_agent_artifact_refs.md)

## Description

py_copy: make `%@` on an epic/phase row copy `bead:<id>`, move the design plan reference to a new `%d` key, and add `%@` to the Agents tab.

## Notes

[2026-07-30T03:00:11Z · sase-b2.7] Implemented ACE copy-mode entity references: epic/phase %@ now yields @bead:<id>, %d preserves bead design-plan copying, and Agents %@ yields canonical global @agent: refs with clan/family/workflow-step warnings. Synced default/runtime keymaps, copy palette/footer registry, help modal, docs, and tests; also fixed prerequisite entity-catalog public API names required by Symvision. Verified 123 focused tests pass; full suite ran 24,159 tests with 24,152 passed and 7 skipped, with one unrelated xdist-only xprompt highlight failure that passed on serial rerun; all format, Ruff, mypy, script, changelog, Symvision, toobig, and committed-plan gates pass. Full just check is deterministically blocked only by 8 pre-existing missing plan-prompt link errors in the clean plans sidecar.

[2026-07-30T03:01:12Z · sase-b2.7] Verified 123 focused copy/reference tests pass; repository format, Ruff, mypy, script lint, changelog lint, file-size, and Symvision gates pass; full 24,159-test run had 24,152 passes and 7 skips plus one unrelated parallel-only highlight failure that passed serially; deterministic just check blocker is eight pre-existing plan-to-prompt link errors in the clean plans sidecar.

## Dependencies

- **Depends on:** [sase-b2.6](sase-b2.6.md) ✓
- **Blocks:** [sase-b2.8](sase-b2.8.md) ✓
