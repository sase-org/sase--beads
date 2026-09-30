# Bead: sase-1co.3 — sase grammar mirror, highlight adapter, pin, and docs

[Bead Pages](../README.md) / [sase-1co](README.md) / sase-1co.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0u1](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.0u1.md) · **Assignee:** `sase-1co.3` · **Size:** medium
**Created:** 2026-09-29 16:22:05 EDT · **Closed:** 2026-09-29 17:56:25 EDT
**Plan:** [202609/midword\_alternation.md](https://github.com/sase-org/sase--plans/blob/main/202609/midword_alternation.md)

## Description

sase-grammar-highlight: in sase, bump the core pin, relax `_ALT_DIRECTIVE_RE` for the brace form, and turn `alt_inspect.tokenize` into a memoized thin adapter over the binding. Also route project-tag alt groups through that adapter, add correctness and performance tests, and document the rule in `docs/xprompt.md`.

## Notes

[2026-09-29T21:40:01Z · sase-1co.3] PROPOSED FOLLOW-UP: core alternation_scan misses %{/%(/%alt( immediately preceded by `{` (e.g. `{%{a | b}`, `{%(a,b)`) while launch fans out — highlight/LSP and launch disagree there; fix in sase-core scanner and re-pin

[2026-09-29T21:55:53Z · sase-1co.3] PROPOSED FOLLOW-UP: `just check` lint (patch/stitch terminology) fails on 14 lines in linked sase-core fixtures (note_attachment/at_bearing_notes.jsonl), byte-identical on clean base tree; no tracking bead found

[2026-09-29T21:56:25Z · sase-1co.3] sase-grammar-highlight done. Pin 43f744b->1e51ff3 (remote HEAD, has core-grammar+core-scan-lsp); _ALT_DIRECTIVE_RE brace-anywhere/paren-boundary with one marker group (end()-1 audit clean); alt_inspect.tokenize/groups() are memoized adapters over alternation_scan (fast path + 128-LRU, fail-open callers unchanged); project-tag groups routed via adapter with depth re-rooting for nested validation; docs/xprompt.md position/glued/Jinja rule documented (llms.md needed no change). Verified: 309 focused tests green (alt_inspect, has_helpers, split alternatives/models, extract, jinja, project tags, highlight incl. new binding-call-count test); slow bench_alt_inspect green (before p95 26.64/med 26.38ms, after p95 15.63/med 12.62ms, ceilings 26/16ms); ruff/mypy/fmt/keep-sorted/flags/pyscripts/waits/changelog green; full suite 73% zero-fail when time-boxed (scoped lane escalated on pin change). just-check patch/stitch-terminology gate fails byte-identically on clean base (14 sase-core fixture lines) — recorded as follow-up, as is the core scanner miss of openers right after `{` (launch fans out, scanner silent). No epic-symbols left.

## Dependencies

- **Depends on:** [sase-1co.2](sase-1co.2.md) ✓ · ⧖ 2026-09-29
- **Blocks:** [sase-1co.4](sase-1co.4.md) ✓ · ⧖ 2026-09-29

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1co.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1co.3/README.md) | [sase-1co.3](sase-1co.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`0266fe4`](https://github.com/sase-org/sase/commit/0266fe4a1227c2a96293828b520b5cd0f1d54a15) | feat(xprompt): mid-word alternation grammar mirror, highlight adapter, and docs | [sase-1co.3](sase-1co.3.md) | 2026-09-29 17:59:08 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1co.3][1] | Need the phase scope and design file | 1 |
| read-by | [agent:sase-1co.land][2] | Need the child scope and notes | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1co.3/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1co.land/README.md

<!-- sase:referenced-by:end -->
