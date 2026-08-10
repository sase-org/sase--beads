# Bead: sase-ij — Ratchet the sase-core-rs window at the release boundary instead of on feature PRs

[Bead Pages](../README.md) / sase-ij

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.wq](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.wq/README.md) · **Assignee:** `sase-ij.land`
**Created:** 2026-08-09 15:17:19 EDT · **Closed:** 2026-08-10 10:03:26 EDT
**Plan:** [202608/core\_window\_ratchet.md](https://github.com/sase-org/sase--plans/blob/main/202608/core_window_ratchet.md)

## Description

A feature agent can call a newly landed sase-core binding or behavior without editing pyproject.toml, uv.lock, or a version literal, and without waiting on a core release; the published-floor invariant is enforced once, mechanically, on the pending sase release instead of ~1.2 times a day by a dedicated agent.

## Notes

[2026-08-10T12:00:56Z · toobig-2a.split_file.src.sase.dev_update.prebuild.0] DISCOVERED ISSUE: The full-suite escalation for an unrelated dev_update/prebuild.py refactor independently found tests/test_contract_manifest.py::{test_contract_manifest_matches_marker_selection,test_contract_set_manifest_entry_budget_has_no_hidden_headroom} failing deterministically. collect_contract_files now includes tests/test_probe_core_floor_tool.py, added by this epic's phase sase-ij.7, but tests/contract_manifest.txt still omits it and the 36-entry budget was not re-curated; the current selected set has 37 entries. This is causally linked to the active core-window-ratchet epic rather than the prebuild split.

[2026-08-10T12:24:29Z · sase-ib.land] DISCOVERED ISSUE: tests/test_contract_manifest.py fails deterministically on master (ee9603d31), blocking `just check` / `just check-full` for every agent. Phase sase-ij.7 (f43d6e4fe) added tests/test_probe_core_floor_tool.py with `pytestmark = pytest.mark.contract` but did not run `just refresh-contract-manifest` or update the entry budget. Two failures: (1) test_contract_manifest_matches_marker_selection -- marker selection now yields 37 files including tests/test_probe_core_floor_tool.py while tests/contract_manifest.txt still lists 36 without it; (2) test_contract_set_manifest_entry_budget_has_no_hidden_headroom -- refreshing the manifest alone then trips the 36-entry _MANIFEST_ENTRY_BUDGET cap, whose failure message requires re-curating the contract set by value per second and updating the cap plus its measured-cost comment per plans/202608/test_suite_tier1.md. Reproduced by sase-ib.land at ee9603d31 with a clean tree (`.venv/bin/python -m pytest tests/test_contract_manifest.py -q -p no:randomly` -> 2 failed, 1 passed); first reported by phase sase-ib.7 as a PROPOSED FOLLOW-UP. Left unfixed while landing epic sase-ib because the budget bump is a deliberate curation decision this epic owns, not a mechanical refresh.

[2026-08-10T13:48:17Z · sase-in] DISCOVERED ISSUE: Independent reproduction while verifying unrelated task bead sase-in on 2026-08-10. After the Justfile/env resolver patch, `just check` escalated to the full suite and failed tests/test_contract_manifest.py::{test_contract_manifest_matches_marker_selection,test_contract_set_manifest_entry_budget_has_no_hidden_headroom}. Current marker selection includes tests/test_probe_core_floor_tool.py while committed tests/contract_manifest.txt omits it, and the committed manifest has 38 entries against _MANIFEST_ENTRY_BUDGET=36. This matches the existing phase sase-ij.7 contract-manifest/budget gap; sase-in touches Justfile sase_core_dir resolution and the selector mirror, not contract-set curation.

[2026-08-10T13:51:45Z · wx] DISCOVERED ISSUE (independent reproduction): While verifying an unrelated PRs onboarding fix on 2026-08-10, \✓ fmt (python)
✓ fmt (markdown)
✓ lint (keep-sorted)
✓ lint (ruff)
✓ lint (mypy)
✓ lint (pyscripts)
✓ lint (test waits)
✓ lint (changelog)
✓ lint (patch/stitch terminology)
✓ lint (symvision)
✓ lint (toobig)
✓ SASE validation
✓ committed plans
✗ test (scoped)

┌───────────────────────────────────────────────────────┐
│                RUNNING: just test-scoped              │
└───────────────────────────────────────────────────────┘

---------- Running diff-scoped pytest selection... ----------
test selection escalated to the full suite (rules: context-baseline-stale, context-selection, contract-set-always, no-baseline-depth-boost, serial-budget-exceeded); 2490 test files in scope
coverage contexts: baseline 96183d71b3ef (stale, 353 commits behind HEAD) matched 3 changed file(s) and contributed 92 test file(s)
middle gear: running the over-budget selection at 4 worker(s), leased from the suite gate (ceiling 4)
============================= test session starts ==============================
platform linux -- Python 3.13.13, pytest-9.1.1, pluggy-1.6.0
rootdir: /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12
configfile: pyproject.toml
plugins: inline-snapshot-0.35.3, cov-7.1.0, asyncio-1.4.0, hypothesis-6.164.0, xdist-3.8.0, mock-3.15.1
asyncio: mode=Mode.AUTO, debug=False, asyncio_default_fixture_loop_scope=None, asyncio_default_test_loop_scope=function
created: 4/4 workers
4 workers [2451 items]

........................................................................ [  2%]
......F................................................................. [  5%]
........................................................................ [  8%]
........................................................................ [ 11%]
........................................................................ [ 14%]
........................................................................ [ 17%]
........................................................................ [ 20%]
........................................................................ [ 23%]
........................................................................ [ 26%]
........................................................................ [ 29%]
........................................................................ [ 32%]
........................................................................ [ 35%]
........................................................................ [ 38%]
........................................................................ [ 41%]
..............................................................F......... [ 44%]
........................................................................ [ 47%]
........................................................................ [ 49%]
........................................................................ [ 52%]
........................................................................ [ 55%]
........................................................................ [ 58%]
........................................................................ [ 61%]
..............................F........F.................F.............. [ 64%]
........................................................................ [ 67%]
........................................................................ [ 70%]
........................................................................ [ 73%]
........................................................................ [ 76%]
........................................................................ [ 79%]
........................................................................ [ 82%]
........................................................................ [ 85%]
........................................................................ [ 88%]
........................................................................ [ 91%]
........................................................................ [ 94%]
........................................................................ [ 96%]
........................................................................ [ 99%]
...                                                                      [100%]

═══════════════════════════════ inline-snapshot ════════════════════════════════
INFO: inline-snapshot was disabled because you used xdist. This means that tests
with snapshots will continue to run, but snapshot(x) will only return x and 
inline-snapshot will not be able to fix snapshots or generate reports.


=================================== FAILURES ===================================
_____________ test_k_on_glossary_term_pushes_glossary_preview_card _____________
[gw2] linux -- Python 3.13.13 /home/bryan/.local/state/sase/workspaces/sase-org/sase/sase_12/.venv/bin/python

monkeypatch = <_pytest.monkeypatch.MonkeyPatch object at 0x7f8cc2079320>
tmp_path = PosixPath('/var/tmp/sase-3573d744/pytest-of-bryan/pytest-4/popen-gw2/test_k_on_glossary_term_pushes0')

    async def test_k_on_glossary_term_pushes_glossary_preview_card(
        monkeypatch: pytest.MonkeyPatch,
        tmp_path: Path,
    ) -> None:
        text = "Ask Agent Clan to coordinate"
        catalog = catalog_for_text(text, tmp_path, "Agent Clan")
    
        async with PromptPage(text, cursor=(0, 6), size=(80, 24)) as page:
            install_warm_glossary(monkeypatch, page.ta.app, catalog)
            monkeypatch.setattr(
                page.ta,
                "_lookup_word_under_cursor",
                lambda: (_ for _ in ()).throw(
                    AssertionError("word lookup must not run for glossary terms")
                ),
            )
    
            await page.press("K")
            await _wait_for(page, lambda: _top_is_preview(page))
    
            modal = page.ta.app.screen_stack[-1]
            assert isinstance(modal, GlossaryPreviewModal)
            assert modal._entry.term == "Agent Clan"
            assert modal._matched_text == "Agent Clan"
            assert modal._source_action_path() == str(tmp_path / "sase.yml")
            assert modal._source_action_position() == (8, 5)
            title_text = _render_text(modal._build_title())
            meta_text = _render_text(modal._build_meta())
            assert "GLOSSARY" in title_text
            assert "Agent Clan" in title_text
            assert "matched" not in title_text
            assert "A named, rootless container for coordinated agents." in (
                modal._definition_markdown()
            )
            assert "ALSO KNOWN AS" in meta_text
            assert "clan" in meta_text
            assert "agent clans" not in meta_text
            assert "Project" in meta_text
            assert "sase" in meta_text
            assert "Source" in meta_text
>           assert str(tmp_path / "sase.yml") in meta_text
E           AssertionError: assert '/var/tmp/sase-3573d744/pytest-of-bryan/pytest-4/popen-gw2/test_k_on_glossary_term_pushes0/sase.yml' in 'ALSO KNOWN AS   clan                                                                                \n---------------...              \nMatch

… and 24569 more characters

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-ij.1](sase-ij.1.md) | Derive the telemetry smoke test's expected minimum from pyproject | ✓ closed | small | 2026-08-09 | 1 | 1 |
| [sase-ij.2](sase-ij.2.md) | Build the window ratchet tool | ✓ closed | medium | 2026-08-09 | 1 | 1 |
| [sase-ij.3](sase-ij.3.md) | Enforce the published floor on the release branch and at publish time | ✓ closed | medium | 2026-08-09 | 1 | 1 |
| [sase-ij.4](sase-ij.4.md) | Ratchet the window on the pending release branch in report-only mode | ✓ closed | medium | 2026-08-09 | 1 | 1 |
| [sase-ij.5](sase-ij.5.md) | Verify one report-only run and switch the ratchet to apply | ✓ closed | small | 2026-08-09 | 1 | 1 |
| [sase-ij.6](sase-ij.6.md) | Stop conscripting feature agents into the floor bump | ✓ closed | small | 2026-08-09 | 1 | 1 |
| [sase-ij.7](sase-ij.7.md) | Add a non-fatal core-floor probe to just check | ✓ closed | medium | 2026-08-09 | 1 | 1 |
| [sase-ij.8](sase-ij.8.md) | Merge sase-core release PRs from the release-plz workflow | ✓ closed | small | 2026-08-09 | 1 | 2 |

## Lineage

```mermaid
flowchart TD
    n0["sase-ij: Ratchet the sase-core-rs window at the release boundary instead of on feature PRs [closed]"]
    n1["sase-ij.1: Derive the telemetry smoke test's expected minimum from pyproject [closed]"]
    n2["sase-ij.2: Build the window ratchet tool [closed]"]
    n3["sase-ij.3: Enforce the published floor on the release branch and at publish time [closed]"]
    n4["sase-ij.4: Ratchet the window on the pending release branch in report-only mode [closed]"]
    n5["sase-ij.5: Verify one report-only run and switch the ratchet to apply [closed]"]
    n6["sase-ij.6: Stop conscripting feature agents into the floor bump [closed]"]
    n7["sase-ij.7: Add a non-fatal core-floor probe to just check [closed]"]
    n8["sase-ij.8: Merge sase-core release PRs from the release-plz workflow [closed]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n0 --> n6
    n0 --> n7
    n0 --> n8
    n1 -.-> n2
    n2 -.-> n4
    n3 -.-> n5
    n4 -.-> n5
    n5 -.-> n6
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ij.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ij.1/README.md) | [sase-ij.1](sase-ij.1.md) | 1 |
| [bbugyi200.athena.sase-ij.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ij.2/README.md) | [sase-ij.2](sase-ij.2.md) | 1 |
| [bbugyi200.athena.sase-ij.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ij.3/README.md) | [sase-ij.3](sase-ij.3.md) | 1 |
| [bbugyi200.athena.sase-ij.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ij.4/README.md) | [sase-ij.4](sase-ij.4.md) | 1 |
| [bbugyi200.athena.sase-ij.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ij.5/README.md) | [sase-ij.5](sase-ij.5.md) | 1 |
| [bbugyi200.athena.sase-ij.6](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ij.6/README.md) | [sase-ij.6](sase-ij.6.md) | 1 |
| [bbugyi200.athena.sase-ij.7](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ij.7/README.md) | [sase-ij.7](sase-ij.7.md) | 1 |
| [bbugyi200.athena.sase-ij.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ij.8/README.md) | [sase-ij.8](sase-ij.8.md) | 2 |
| [bbugyi200.athena.sase-ij.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ij.land/README.md) | [sase-ij](README.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@735a01b`](https://github.com/sase-org/sase-core/commit/735a01b35143a5208af83451af31996a325fd755) | ci(release-plz): auto-merge release PRs once checks pass | [sase-ij.8](sase-ij.8.md) | 2026-08-09 15:31:05 EDT |
| sase | [`755987f`](https://github.com/sase-org/sase/commit/755987ff5b42418f6d411eec7373ce524184a0b3) | test: derive telemetry smoke core floor from pyproject | [sase-ij.1](sase-ij.1.md) | 2026-08-09 15:33:31 EDT |
| sase | [`48d5bcd`](https://github.com/sase-org/sase/commit/48d5bcdf1e9c59a9a6dea498e3eb7a08b1c1a7d8) | ci: enforce published core floor in release workflows | [sase-ij.3](sase-ij.3.md) | 2026-08-09 15:42:12 EDT |
| sase-core | [`sase-core@443f1aa`](https://github.com/sase-org/sase-core/commit/443f1aa16994eb840c032e99df449170f22c722e) | fix(release-plz): set GH\_REPO in the merge job's gh commands | [sase-ij.8](sase-ij.8.md) | 2026-08-09 15:44:57 EDT |
| sase | [`f43d6e4`](https://github.com/sase-org/sase/commit/f43d6e4fea2423cea0e164962e4d86ffaea12aee) | feat(check): add advisory core floor probe | [sase-ij.7](sase-ij.7.md) | 2026-08-09 15:49:17 EDT |
| sase | [`ca2dbcb`](https://github.com/sase-org/sase/commit/ca2dbcb0fd8d4fee7a9df8f449a943a5683f8d70) | feat: add core window ratchet tool | [sase-ij.2](sase-ij.2.md) | 2026-08-09 16:15:34 EDT |
| sase | [`dfa07fb`](https://github.com/sase-org/sase/commit/dfa07fb48e7c215c6470ea9364b9f118a62bd50e) | ci: reconcile release metadata on pending branch | [sase-ij.4](sase-ij.4.md) | 2026-08-09 16:30:31 EDT |
| sase | [`419a81b`](https://github.com/sase-org/sase/commit/419a81b7b5530e700cb176acf2a888ba3c267e19) | ci: apply release metadata ratchet | [sase-ij.5](sase-ij.5.md) | 2026-08-09 16:48:00 EDT |
| sase | [`0968318`](https://github.com/sase-org/sase/commit/0968318b17a35e13e539758191cc4ff8f2511478) | ci: retire published-core-minimum-smoke now enforced at release boundary | [sase-ij.6](sase-ij.6.md) | 2026-08-10 09:17:02 EDT |
| sase | [`90912ad`](https://github.com/sase-org/sase/commit/90912ad7d6cad2807ec86d6dbc98e60a33ec421d) | fix: stop conscripting agents into manual core-window bumps | [sase-ij](README.md) | 2026-08-10 10:08:01 EDT |
| sase--plans | [`sase--plans@024f221`](https://github.com/sase-org/sase--plans/commit/024f22159c124e0381564b61bfb418f288bf1f9d) | docs(plans): mark core window ratchet epic done | [sase-ij](README.md) | 2026-08-10 10:10:29 EDT |
