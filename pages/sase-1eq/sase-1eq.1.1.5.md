# Bead: sase-1eq.1.1.5 — Read new artifact filenames with permanent legacy fallbacks

[Bead Pages](../README.md) / [sase-1eq.1.1](sase-1eq.1.1.md) / sase-1eq.1.1.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1eq.1.f0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.1.f0.md) · **Assignee:** `sase-1eq.1.1.5` · **Size:** medium
**Created:** 2026-10-02 07:55:53 EDT · **Closed:** 2026-10-02 12:01:54 EDT
**Plan:** [202610/finish\_core\_macro\_expand.md](https://github.com/sase-org/sase--plans/blob/main/202610/finish_core_macro_expand.md)

## Description

durable-readers: Implement new-first macros.json/raw_prompt.md selection in scans and alias history, preserve indexed storage while invalidating signatures on selection changes, and recognize renamed home state files. Verify cold/indexed scans, capacity-only behavior, and durable compatibility independent of the legacy option.

## Notes

[2026-10-02T16:01:29Z · sase-1eq.1.1.5] Implementation: new-first macros.json/raw_prompt.md selection via shared select_used_macros_path/select_raw_prompt_path in agent_scan/scanner.rs (cold scans); alias_history.rs reuses the same selectors for live snippets; record_summary.rs durable_artifact_signature folds selected macros+raw identity (filename prefix) into preserved xprompts_sig column, no schema bump, record_json keeps used_xprompts; zones.rs adds vcs_macro_mru.json/macro_save_state.json retaining legacy files. Readers ignore accept_legacy_xprompt_names. Residual xprompt hits: scanner legacy consts+fallback refs and test legacy literals = input-alias/legacy-reader (annotated); alias_history xprompts_sig SQL = preserved storage column; record_summary xprompts field/sig = preserved storage (annotated); zones legacy filenames+test paths = legacy-reader (annotated). No new root exports/prelude aliases; no bare macro identifiers. Evidence: sase tool run check e1b1283309b5b96d17f0868a4c8ff5ed succeeded; just fmt ok; just fast ok; just test -p sase_core agent_scan 167 passed; note_attachment 54 passed; new tests durable_readers_prefer_canonical_macros_and_raw_prompt, durable_canonical_selection_refreshes_indexed_record, alias_history_prefers_canonical_raw_prompt all pass.

[2026-10-02T16:01:54Z · sase-1eq.1.1.5] durable-readers verified: cold scans prefer macros.json/raw_prompt.md with legacy fallback (new-only, old-only, both-present, malformed-canonical no-fallback, late-write, source-removal); indexed refresh invalidates via filename-prefixed xprompts_sig covering macros+raw with stored used_xprompts preserved and no schema change; alias snippets share the same selection; capacity-only skips both durable reads; home zones recognize vcs_macro_mru.json/macro_save_state.json. Gates: sase tool run check e1b1283309b5b96d17f0868a4c8ff5ed green; agent_scan 167 passed; note_attachment 54 passed; epic-symbols clean.

## Dependencies

- **Depends on:** [sase-1eq.1.1.4](sase-1eq.1.1.4.md) ✓ · ⧖ 2026-10-02
- **Blocks:** [sase-1eq.1.1.6](sase-1eq.1.1.6.md) ◐ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1eq.1.1.5](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1eq.1.1.5/README.md) | [sase-1eq.1.1.5](sase-1eq.1.1.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@926edfb`](https://github.com/sase-org/sase-core/commit/926edfb8baa1d8e3ba4242156961905595d0faf9) | feat(core-expand): read new macro artifact filenames with legacy fallbacks | [sase-1eq.1.1.5](sase-1eq.1.1.5.md) | 2026-10-02 12:04:07 EDT |
