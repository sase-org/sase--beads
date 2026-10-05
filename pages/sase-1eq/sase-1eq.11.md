# Bead: sase-1eq.11 — Cross-repo audit, guardrail, chezmoi, and machine migration

[Bead Pages](../README.md) / [sase-1eq](README.md) / sase-1eq.11

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0v4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0v4.md) · **Assignee:** `sase-1eq.11` · **Size:** medium
**Created:** 2026-10-02 06:51:34 EDT · **Closed:** 2026-10-05 08:09:51 EDT
**Plan:** [202610/xprompts\_to\_macros.md](https://github.com/sase-org/sase--plans/blob/main/202610/xprompts_to_macros.md)

## Description

audit-deploy: remove the temporary import shim and widen the guard to the whole repo. Sweep every repo, migrate the chezmoi sources and the live athena state, redeploy skills, annotate open beads, and record deferred follow-ups.

## Notes

[2026-10-05T12:08:34Z · sase-1eq.11] PROPOSED FOLLOW-UP: After a published sase release with macro support, move plugin packaged xprompts/ to macros/, drop sase_xprompts entry-point group, and raise sase floors (sase-github, sase-research-artifacts). Doctor config.retired_xprompt_names currently WARNs on those two groups; publish.yml in sase-research-artifacts still smokes sase.xprompt.* against published sase.

[2026-10-05T12:08:45Z · sase-1eq.11] PROPOSED FOLLOW-UP: Remove the mobile v1 /api/v1/xprompts/catalog route alias at the next API version.

[2026-10-05T12:08:56Z · sase-1eq.11] PROPOSED FOLLOW-UP: sase-core core-flip leftovers still emit/accept xprompt identifiers (XPromptOccurrence, xprompt_occurrences, USED_XPROMPTS_FILE, XPROMPT_PROC_ORIGIN, content-layout serializes both xprompts and macros, package:xprompts/skills). Incomplete key drop from sase-1eq.10; do not treat as this phase remaining work.

[2026-10-05T12:09:08Z · sase-1eq.11] PROPOSED FOLLOW-UP: Live athena sase update skipped: sase update -n reported 3 agent runners on the primary checkout and warned a swap can break deferred imports. Primary tree was clean. Re-run sase update when no agents are using that checkout, then sase skill init --force if skills drift.

[2026-10-05T12:09:19Z · sase-1eq.11] PROPOSED FOLLOW-UP: mac (kellys-macbook-pro) had no sase on PATH (often offline). Confirm a macros-capable sase there before relying on chezmoi apply of macros: / ~/sase/macros. After this chezmoi commit lands, chezmoi update -a --force on athena/apollo/mac so ~/.local/share/chezmoi matches the linked commit (live apply this turn used the workspace source; a later apply from the un-updated live source would revert ~/sase/macros and macros:).

[2026-10-05T12:09:51Z · sase-1eq.11] audit-deploy: deleted sase.xprompt shim; widened terminology guard to git ls-files (10 passed); env SASE_AGENT_LOCAL_MACROS; chezmoi git mv home/sase/xprompts→macros, macros: key, .chezmoiremove, sax, snips; bob-cli macro_role_binding (21+1 tests ok); athena/apollo sase path macros-dir; live apply ~/sase/macros pick_plan.md+sshot.yml, xprompts gone; sase-macro-lsp on PATH, tools.macro_lsp OK, MRU already canonical; flag sase-1fj on; skill init --check clean; core health ok; no --epic-symbol leftovers. Follow-ups noted for plugins/sase_xprompts, mobile v1 alias, core-flip identifier leftovers, sase update (agents on primary), mac/chezmoi update.

[2026-10-05T12:59:48Z · sase-1eq.11--2] PROPOSED FOLLOW-UP: just check full-suite leftovers that reproduce off this phase: tests/test_plugin_latest.py::test_enrich_with_latest_cache_only_uses_stale_hits_without_fetch_or_write (editable install missing from version inventory); tests/test_check_sase_core_rs_bindings_tool.py::test_dev_extension_exposes_every_collected_name (sase-146 — tool_adoption_report binding not on installed sase_core_rs); tests/ace/tui/widgets/test_prompt_tab_focus_steal.py FrontmatterPanel NoMatches #frontmatter-raw (sase-1fy).

## Dependencies

- **Depends on:** [sase-1eq.10](sase-1eq.10.md) ✓ · ⧖ 2026-10-02
- **Depends on:** [sase-1eq.6](sase-1eq.6.md) ✓ · ⧖ 2026-10-02

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1eq.11](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.11.md) | [sase-1eq.11](sase-1eq.11.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`17c2907`](https://github.com/sase-org/sase/commit/17c2907d3bcfd1495ff37e11217c9911bcdf2978) | feat!: drop the sase.xprompt shim and finish audit-deploy cutover | [sase-1eq.11](sase-1eq.11.md) | 2026-10-05 09:05:12 EDT |
