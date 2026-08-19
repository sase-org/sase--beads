# Bead: sase-qn — Scale the Admin Center Updates \> Plugins sub-tab to 1000+ community plugins

[Bead Pages](../README.md) / sase-qn

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.075](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.075.md) · **Assignee:** `sase-qn.land`
**Created:** 2026-08-18 20:12:38 EDT
**Plan:** [202608/plugin\_catalog\_scale.md](https://github.com/sase-org/sase--plans/blob/main/202608/plugin_catalog_scale.md)

## Description

The Updates tab's Plugins sub-tab loads, filters, and navigates a catalog of 1000+ community plugins without silent truncation, without a per-catalog-entry network storm, and with j/k key-to-paint p95 under 16 ms.

## Notes

[2026-08-19T02:30:05Z · toobig-34.split_file.tests.test_config_schema.0] DISCOVERED ISSUE: tests/ace/tui/test_plugins_browser_pane_detail.py::test_plugins_pane_lazy_fetches_highlighted_latest_when_flag_on fails reproducibly on clean master (17592d904), not a flake: 3/3 serial isolated runs failed under '.venv/bin/python -m pytest <node> -q -p no:randomly', and it also failed inside a full 'just check' run. It fails on a stashed, unmodified tree, so it is not caused by the in-flight test-file split that found it.

Symptom: the lazy worker does run (the test's wait_for on 'calls' passes), but pane._entry_by_name('nvim').latest is still LatestInfo(checked=False, version=None) instead of the fetched '2.0.0'.

Root cause: phase sase-qn.2 (664180532) added _apply_plugin_latest in src/sase/ace/tui/modals/plugins_browser_latest.py, which rewrites self._catalog and self._grouped with the enriched entry. Phase sase-qn.4 (41d9f9141) then added the name-keyed identity map self._plugin_entry_by_name, built only in _rebuild_plugin_identity_maps (src/sase/ace/tui/modals/plugins_browser_rendering.py:212-231) and read by _entry_by_name (line 587). _apply_plugin_latest never refreshes that map, so the map keeps the pre-enrichment entry.

Impact is user-visible, not test-only: _current_entry -> _entry_by_name (line 585) feeds _render_detail_now, so the Updates > Plugins detail panel re-renders from the stale entry after a lazy fetch completes and never shows the fetched latest version while the plugin_catalog_scoped_latest flag is on. Fix belongs with phase sase-qn.5's close-out: have _apply_plugin_latest update _plugin_entry_by_name (and any sibling identity map keyed on the replaced entry) alongside _catalog and _grouped.

## Phases

| Bead | Title | Status | Size | Created | Agents | Commits |
|---|---|---|---|---|---:|---:|
| [sase-qn.1](sase-qn.1.md) | Large-catalog bench harness and recorded baselines | ✓ closed | small | 2026-08-18 | 1 | 1 |
| [sase-qn.2](sase-qn.2.md) | Latest-version enrichment that scales with installed count, not catalog size | ✓ closed | medium | 2026-08-18 | 1 | 1 |
| [sase-qn.3](sase-qn.3.md) | Catalog fetch past GitHub search's 1000-result cap | ✓ closed | medium | 2026-08-18 | 1 | 1 |
| [sase-qn.4](sase-qn.4.md) | Constant-time render, filter, and navigation paths | ✓ closed | medium | 2026-08-18 | 1 | 1 |
| [sase-qn.5](sase-qn.5.md) | Enforce the budgets and close out the epic | ✓ closed | small | 2026-08-18 | 1 | 2 |

## Lineage

```mermaid
flowchart TD
    n0["sase-qn: Scale the Admin Center Updates &gt; Plugins sub-tab to 1000+ community plugins [in_progress]"]
    n1["sase-qn.1: Large-catalog bench harness and recorded baselines [closed]"]
    n2["sase-qn.2: Latest-version enrichment that scales with installed count, not catalog size [closed]"]
    n3["sase-qn.3: Catalog fetch past GitHub search's 1000-result cap [closed]"]
    n4["sase-qn.4: Constant-time render, filter, and navigation paths [closed]"]
    n5["sase-qn.5: Enforce the budgets and close out the epic [closed]"]
    n0 --> n1
    n0 --> n2
    n0 --> n3
    n0 --> n4
    n0 --> n5
    n1 -.-> n2
    n1 -.-> n3
    n1 -.-> n4
    n1 -.-> n5
    n2 -.-> n5
    n3 -.-> n5
    n4 -.-> n5
```

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-qn.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-qn.1/README.md) | [sase-qn.1](sase-qn.1.md) | 1 |
| [bbugyi200.athena.sase-qn.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-qn.2/README.md) | [sase-qn.2](sase-qn.2.md) | 1 |
| [bbugyi200.athena.sase-qn.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-qn.3/README.md) | [sase-qn.3](sase-qn.3.md) | 1 |
| [bbugyi200.athena.sase-qn.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-qn.4/README.md) | [sase-qn.4](sase-qn.4.md) | 1 |
| [bbugyi200.athena.sase-qn.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-qn.5.md) | [sase-qn.5](sase-qn.5.md) | 2 |
| [bbugyi200.athena.sase-qn.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-qn.land/README.md) | [sase-qn](README.md) | 0 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`42a8193`](https://github.com/sase-org/sase/commit/42a81937b9dedd61eb8a77b3d691565e793acb0e) | test(perf): add plugins catalog scale bench harness | [sase-qn.1](sase-qn.1.md) | 2026-08-18 20:52:44 EDT |
| sase | [`ea95b16`](https://github.com/sase-org/sase/commit/ea95b16ce2ba58101b805f65cd6f628577696517) | feat(plugins): shard GitHub catalog search past the 1000-result cap | [sase-qn.3](sase-qn.3.md) | 2026-08-18 21:32:42 EDT |
| sase | [`41d9f91`](https://github.com/sase-org/sase/commit/41d9f9141b537785164d83ca665c6c30cf81d211) | perf(tui): make plugins-browser render, filter, and navigation paths constant-time | [sase-qn.4](sase-qn.4.md) | 2026-08-18 21:37:23 EDT |
| sase | [`6641805`](https://github.com/sase-org/sase/commit/66418053282c2937c4ca79a179e5c9a21bea02a8) | feat(plugins): scale latest-version enrichment to installed count | [sase-qn.2](sase-qn.2.md) | 2026-08-18 21:53:45 EDT |
| sase | [`ce5ddf1`](https://github.com/sase-org/sase/commit/ce5ddf13cd8030b385c430da1a5909b07849a3c1) | perf(plugins): enforce catalog-scale budgets and keep lazy latest | [sase-qn.5](sase-qn.5.md) | 2026-08-18 23:02:02 EDT |
| sase | [`0e36971`](https://github.com/sase-org/sase/commit/0e36971e0ba2b75ffa9cc09d33ff2a00c6bcce65) | chore(perf): ignore plugin catalog scale floor-check report | [sase-qn.5](sase-qn.5.md) | 2026-08-18 23:06:15 EDT |
