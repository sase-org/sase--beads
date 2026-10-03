# Bead: sase-1eq.4.1.3 — Macro directory, plugin, and LSP discovery

[Bead Pages](../README.md) / [sase-1eq.4.1](sase-1eq.4.1.md) / sase-1eq.4.1.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1eq.4](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1eq.4.md) · **Assignee:** `sase-1eq.4.1.3` · **Size:** medium
**Created:** 2026-10-03 06:00:01 EDT · **Closed:** 2026-10-03 09:42:25 EDT
**Plan:** [202610/macro\_syntax\_cutover.md](https://github.com/sase-org/sase--plans/blob/main/202610/macro_syntax_cutover.md)

## Description

discovery: use the content-layout macro source order and write paths, share deduplicated plugin discovery, gate legacy directories and public environment aliases, and propagate the policy to Rust and LSP.

## Notes

[2026-10-03T13:40:57Z · sase-1eq.4.1.3] PROPOSED FOLLOW-UP: symvision NEW PublicationPayloadFile in src/sase/core/publication_payload_facade.py reproduces identically on clean base HEAD 6eaa8df521 (verified via scratch worktree); check red is pre-existing, not from discovery phase

[2026-10-03T13:42:25Z · sase-1eq.4.1.3] Discovery implemented and verified: consolidated plugin discovery around main/plugin_discovery (sase_macros first, retired group only when flag on, dedup by entry-point value, both-env collision and retired-off errors); legacy macro dirs gated via resolve_macro_file_sources role filter in both flag states; writers on macros.write_path (cli_export, TUI location modal, agent-workflow editor); LSP uses SASE_MACRO_LSP_CMD first with legacy gated, canonical-first binary preference, SASE_ACCEPT_LEGACY_XPROMPT_NAMES exec transport; facade/snippet bindings pass accept_legacy explicitly with real macros/default_macros dirs; sase/xprompts/{reads,sync}.md moved to sase/macros/ (reads frontmatter canonicalized). Tests: new tests/macro/test_macro_discovery_policy.py (18 pass); affected suites 412 passed 1 skipped. sase tool run check: fmt+mypy clean; single symvision NEW (PublicationPayloadFile) reproduces identically on base 6eaa8df521, recorded as PROPOSED FOLLOW-UP. No epic-symbols.

## Dependencies

- **Depends on:** [sase-1eq.4.1.2](sase-1eq.4.1.2.md) ✓ · ⧖ 2026-10-03
- **Blocks:** [sase-1eq.4.1.4](sase-1eq.4.1.4.md) ✓ · ⧖ 2026-10-03

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1eq.4.1.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1eq.4.1.3/README.md) | [sase-1eq.4.1.3](sase-1eq.4.1.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`6d0d8a0`](https://github.com/sase-org/sase/commit/6d0d8a0a2d7321a4bc89a892cbb572bfac13f98e) | feat(macros): consolidate plugin discovery on canonical sase\_macros group | [sase-1eq.4.1.3](sase-1eq.4.1.3.md) | 2026-10-03 09:44:04 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1eq.4.1.3][1] | Need the phase scope and design file | 2 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1eq.4.1.3/README.md

<!-- sase:referenced-by:end -->
