# Bead: sase-m6.6.1 — One profile-driven query engine for every Artifacts pane

[Bead Pages](../README.md) / [sase-m6.6](sase-m6.6.md) / sase-m6.6.1

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-m6.6](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-m6.6.md) · **Assignee:** `sase-m6.6.1.land`
**Created:** 2026-08-15 06:17:18 EDT
**Plan:** [202608/unified\_artifacts\_query\_1.md](https://github.com/sase-org/sase--plans/blob/main/202608/unified_artifacts_query_1.md)

## Description

Replace the Artifacts tab's Patch boolean language and four pane-local flat token languages with one profile-parameterized engine whose Rust parser, Rust batch evaluator, and Python reference evaluator agree; migrate every pane without changing its current semantics until explicitly enabled; move Patch onto the inline filter bar; and persist saved views, history, and stable selection targets independently per pane.

## Notes

[2026-08-15T14:03:04Z · 027] DISCOVERED ISSUE: During restore_agent_lane_glossary validation on 2026-08-15, a glossary/generated-memory-only diff made 'just check' escalate to the governed full suite (rules: contract-set-only, core-identity-changed) and fail 17 tests in tests/test_query_profile_corpus_facade.py after the lint/SASE/committed-plan gates passed. Representative focused repro: '.venv/bin/python -m pytest tests/test_query_profile_corpus_facade.py::test_compile_index_and_evaluate_matches_expected_rows -q' fails deterministically with 'ValueError: profile: compiled profile digest does not match payload' from src/sase/core/query_profile_corpus_facade.py:122 at compile_corpus(profile.to_wire(), wire_rows). The local diff only adds Agent Lane to sase/sase.yml and regenerated memory/instruction files, so this is unrelated to the glossary work. Routed here because this active epic owns the profile-parameterized Rust parser/corpus/Python binding parity and phase sase-m6.6.1.7 explicitly owns proving parity.

[2026-08-15T15:10:06Z · 02d] DISCOVERED ISSUE: During unrelated hyphenated prompt-word completion verification on 2026-08-15, just check passed but core-floor-probe reported declared_floor 0.27.2 stale: missing query-profile capabilities canonicalize_query_with_profile, compile_corpus_with_profile, compile_query_with_profile, parse_query_with_profile, all first published in sase-core v0.27.4. The local diff touches prompt word completion/history/docs/tests, not query-profile floor management. This belongs here because the active shared Artifacts query epic owns the profile-parameterized Rust parser/corpus/Python binding parity and its compatibility proof.

[2026-08-15T20:01:56Z · sase-mc.land] DISCOVERED ISSUE: Corroborated during sase-mc landing from proposing beads sase-mc.3 and sase-mc.4 on current master 3a31bd3b8. Targeted 'just test-visual -- <three Artifacts nodes> tests/ace/tui/visual/test_ace_png_snapshots_commits.py' reproduced 3 Artifacts failures plus 11 Commits setup errors: Beads populated/reopened cannot select typed targets ('alpha-1'/'alpha-open'), Files nested strip differs by 8,806 pixels, and Commits fixtures import removed commits_filtering.normalize_reference_time. These failures follow post-sase-mc-start unified-query commits d580a55c8/c62765eb7 and are not caused by provider disabling. Evidence: file:explicit:b511fe27a71b5834683146da

[2026-08-15T20:02:42Z · sase-mc.land] DISCOVERED ISSUE: Corroborated during sase-mc landing from proposing beads sase-mc.3 and sase-mc.4 on current master 3a31bd3b8. Targeted visual verification reproduced 3 Artifacts failures plus 11 Commits setup errors: Beads populated/reopened cannot select typed targets, Files nested strip differs by 8,806 pixels, and Commits fixtures import removed commits_filtering.normalize_reference_time. These follow post-sase-mc-start unified-query commits d580a55c8/c62765eb7 and are not caused by provider disabling. Evidence: file:explicit:b511fe27a71b5834683146da

[2026-08-15T23:47:00Z · 02w] DISCOVERED ISSUE: Independently reproduced while implementing Launch Control on 2026-08-15. Final just check passed fmt, ruff, mypy, pyscripts, test-waits, changelog, and patch/stitch terminology, then failed lint (symvision) because Justfile still passes --epic-symbol 'sase-m6.6.1.5(canonicalize_artifact_query)' after phase sase-m6.6.1.5 closed. This diff touches Launch Control/Models panel code, docs, tests, and PNG goldens, not Justfile or query-profile canonicalization. The stale whitelist is causally owned by the active one-profile Artifacts query epic.

[2026-08-15T23:48:55Z · toobig-2s.split_file.src.sase.ace.tui.modals.models_panel_providers.0] DISCOVERED ISSUE: Independently reproduced on 2026-08-15 while splitting Models-panel provider code. just check passed Python/Markdown formatting, keep-sorted, Ruff, mypy, pyscripts, test-waits, changelog, and patch/stitch terminology, then failed lint (symvision) because Justfile still passes --epic-symbol 'sase-m6.6.1.5(canonicalize_artifact_query)' after phase sase-m6.6.1.5 closed. This refactor does not touch Justfile or artifact-query canonicalization; the stale whitelist is causally owned by the active unified Artifacts query epic.

## References

- file:explicit:b511fe27a71b5834683146da

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-m6.6.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-m6.6.1.land/README.md) | [sase-m6.6.1](sase-m6.6.1.md) | 0 |
