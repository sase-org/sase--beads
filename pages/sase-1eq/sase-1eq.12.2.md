# Bead: sase-1eq.12.2 — Drop leftover pre-flip xprompt wire keys in sase-core and sase

[Bead Pages](../README.md) / [sase-1eq.12](sase-1eq.12.md) / sase-1eq.12.2

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1eq.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.land.md) · **Assignee:** `sase-1eq.12.2` · **Size:** medium
**Created:** 2026-10-05 10:21:56 EDT · **Closed:** 2026-10-06 08:09:42 EDT
**Plan:** [202610/land\_xprompts\_to\_macros.md](https://github.com/sase-org/sase--plans/blob/main/202610/land_xprompts_to_macros.md)

## Description

key-flip: Stop emitting the remaining pre-flip xprompt keys and values (content layout, snippet entries, launch units, proc and highlight labels). Rename leftover core identifiers, bump the content-layout schema, and update the sase mirrors, validator, and terminology guard in the same declared turn so the host moves the pin. Follow the key-flip section.

## Notes

[2026-10-06T12:08:49Z · sase-1eq.12.2] PROPOSED FOLLOW-UP: test_delete_rich_format_prints_restore_and_removed_path fails identically on the clean base tree in this environment (rich truncates the config path under long agent TMPDIR); environment-only, not caused by the key-flip.

[2026-10-06T12:09:05Z · sase-1eq.12.2] PROPOSED FOLLOW-UP: test_macro_docs_and_memory_avoid_xprompt_terms infographic failure (docs/images/macro-resolution-infographic.prompt.md) reproduces on the clean base tree; owned by the sase-1eq.6 docs phase, not this bead.

[2026-10-06T12:09:19Z · sase-1eq.12.2] PROPOSED FOLLOW-UP: sase tool run check core-floor-probe stays blocked_unpublished until the flipped sase-core is committed/released and sase-core-revision.txt ratcheted (load_macro_input_type_registry at af5df61 has no containing release); land-agent work, host moves pin.

[2026-10-06T12:09:42Z · sase-1eq.12.2] Key-flip done and verified: sase-core emits macro-only wire keys (EditorSnippetEntryWire.macro_name, kind/source macro, sase/macros paths, /api/v1/macros/catalog, content-layout schema 7 with xprompt legacy source ids, retired catalog options removed with deny_unknown_fields, leftover core identifiers renamed); sase mirrors updated (launch swarm_macros/macro: groups/prompt-proc, snippet kind/name keys incl. cli_common contribution JSON, continuation source_ref macro:, content_layout_wire>=7, validator schema 7, macro-only LSP env, terminology guard repruned). Verified: sase-core lib 4450 passed; parity_fixture fixed and green; sase targeted 94 passed (browserHelpers/highlight/snippetCLI/contentLayout/editorHelper/snippetCatalog/mutation/capturePrompt) + terminology 9 passed + LSP 20 passed + validator contracts green; just fmt/ruff/mypy clean; no epic-symbols. Known non-blocking: check-run triage undetermined from pre-existing symvision KNOWNs + core-floor-probe blocked_unpublished until core release/pin ratchet (land-agent work, follow-ups noted); rich-format delete + docs infographic failures reproduce on clean base (follow-ups noted); grok stream flakes pass on retry.

## Dependencies

- **Depends on:** [sase-1eq.12.1](sase-1eq.12.1.md) ✓ · ⧖ 2026-10-05

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1eq.12.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1eq.12.2/README.md) | [sase-1eq.12.2](sase-1eq.12.2.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@b19690e`](https://github.com/sase-org/sase-core/commit/b19690e3913233a4f73d7e67db6e1a16db6e7d1a) | feat(macros): flip remaining xprompt wire keys to macro spellings | [sase-1eq.12.2](sase-1eq.12.2.md) | 2026-10-06 08:10:54 EDT |
| sase | [`312f17d`](https://github.com/sase-org/sase/commit/312f17dc3f3ad83fcd57578c9b243098297768c0) | feat(macros): drop remaining pre-flip xprompt wire keys and finish key-flip mirrors | [sase-1eq.12.2](sase-1eq.12.2.md) | 2026-10-06 08:16:06 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1eq.12.2][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1eq.12.2/README.md

<!-- sase:referenced-by:end -->
