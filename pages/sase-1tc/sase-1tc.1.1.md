# Bead: sase-1tc.1.1 — Keep workflow data out of host command substitution

[Bead Pages](../README.md) / [sase-1tc.1](sase-1tc.1.md) / sase-1tc.1.1

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1tc.1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tc.1.md) · **Assignee:** `sase-1tc.1.1.land`
**Created:** 2026-11-17 11:31:49 EST
**Plan:** [202611/cmdsub\_source\_provenance.md](https://github.com/sase-org/sase--plans/blob/main/202611/cmdsub_source_provenance.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202611/cmdsub_source_provenance.md][1] | derived from the plan's `bead_id:` frontmatter field |

_Plus 3 automatic references — see [Referenced By](#referenced-by)._

[1]: https://github.com/sase-org/sase--plans/blob/main/202611/cmdsub_source_provenance.md

<!-- sase:links:end -->

## Description

Fix sase-1tc.1 and sase-1sn while preserving authored commands, macro expansion, and Jinja value semantics.

## Notes

[2026-11-17T20:59:57Z · 1dn] DISCOVERED ISSUE: efc66a420b (phase sase-1tc.1.1.2) silently drops #research_swarm segments. Repro: expand_macro_swarms_with_metadata on a #research_swarm(...,image=true,...) prompt yields 6 segments (cdx cld grk mus gem final) at efc66a420b vs 8 (+image +linker) at parent 71f0060927; hit live on apollo as research.58/research.59 (6 agents each). Root cause: _marking_finalize in src/sase/macro/_jinja.py marks every {{ }} output, so a Jinja macro called inside {{ }} (research_swarm's {{ tree(lead_files) }}, whose body prints fences via {{ }}) is marked twice; GeneratedTextGuard.hide_marked_spans' non-greedy START(.*?)END regex pairs the outer START with an inner END, leaving NUL SJSMARK markers before the opening fence and after the closing fence. The closing fence is then read as an unclosed opener, hiding the last two --- separators from split_segments_protecting_fences, so the image and linker prompts are merged into the .final lead prompt. %if(should_run=...) itself evaluates correctly. Tested fix on a scratch copy: strip inner markers in _marking_finalize (text = str(value).replace(start, '').replace(end, '')) -> 8 segments, 0 stray markers. Suggested: regression test for macro-in-{{ }} round-trip and research_swarm(image=true) == 8 segments, plus fail loudly when SJSMARK/SASEDATA survives guard.unwrap. Second symptom, same commit, not fixed by that one-liner: sase macro expand on the same prompt fails with "Macro '#research' argument error: Argument 'suffix' expects word ... got '\x00SASEDATA_<nonce>_18\x00'" because validate_and_convert_args sees the guard token from #research(suffix={{ r.short }}). Report: research:202611/research_swarm_missing_image_linker_agents.md (file:explicit:c1798ebb9b8fdad85a57743d).

[2026-11-17T21:23:20Z · 1do] DISCOVERED ISSUE (beyond the research_swarm note above; found while planning its fix on be6adc20d0): efc66a420b's nested local-helper boundaries leak in two ways. (1) Security gap: command stdout minted inside a local helper is unwrapped to plain text when the nested process_macro_references_with_catalog call returns (its ephemeral guard unwraps at the end), so the outer first pass treats it as source and runs $(...) inside it. Repro in a human launch (SASE_PROMPT_AUTHORSHIP unset): catalog {main: Macro(content='#_h', local_macros={'_h': Macro(content='$(cat payload.txt)')}), echo: Macro(content='{{ _1 }}')}, payload.txt = '#echo($(touch pwn_local))'; process_macro_references_with_catalog('#main', ..., aliases_resolved=True, raise_on_error=True) creates pwn_local. The same flow through a global (non-local) macro stays literal. (2) Regression: typed local-helper args fed by a parent interpolation fail validation, e.g. main content '#_h(suffix={{ v }})' with _h input suffix: word raises "Argument 'suffix' expects word ... got '\\x00SASEDATA_<nonce>_0\\x00'", and untyped helper Jinja comparisons on such args see the token (works at parent 71f0060927). Both stem from nested helpers minting an isolated guard that can neither see nor keep hiding the parent guard's spans. The planned tale for the research_swarm fix covers same-guard (global macro) arg reveal only and leaves these to this epic.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1tc.1.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tc.1.1.land/README.md) | [sase-1tc.1.1](sase-1tc.1.1.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:1dn][1] | Check whether the in-progress epic that produced efc66a420b owns the macro-guard regression | 1 |
| read-by | [agent:sase-1tc.1.1.1][2] | Need parent epic DECISIONS and design | 1 |
| read-by | [agent:sase-1tc.1.1.2--1][3] | Check ancestor status before deciding on reopen | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.1dn/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1tc.1.1.1/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1tc.1.1.2.md

<!-- sase:referenced-by:end -->
