# Bead: sase-vw.3 — Links in the closure walk

[Bead Pages](../README.md) / [sase-vw](README.md) / sase-vw.3

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-vk.land.w1.w0](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-vk.land.w1.w0.md) · **Assignee:** `sase-vw.3` · **Size:** medium
**Created:** 2026-08-30 10:02:17 EDT · **Closed:** 2026-08-30 11:31:28 EDT
**Plan:** [202608/memory\_link\_strategies.md](https://github.com/sase-org/sase--plans/blob/main/202608/memory_link_strategies.md)

## Description

closure: classify each detected link as an inline or reference edge from the effective strategies, feed inline edges into the existing BFS through `precomputed_spans`, add cross-unit inline targets as extra roots, and make ACE strand relations follow the same rules.

## Notes

[2026-08-30T15:30:31Z · sase-vw.3] PROPOSED FOLLOW-UP: just test-scoped has 5 pre-existing failures unrelated to this phase (tests/main/test_init_memory_managed_agents_descriptions.py::test_init_memory_managed_agents_renders_block_long_memory_descriptions, ::test_init_memory_allows_fenced_hash_in_long_memory_description, test_init_memory_managed_agents_frontmatter.py::test_tier2_section_heading_keeps_top_level_long_note_reachable, test_init_memory_plan.py::test_memory_plan_missing_tree_reports_create_actions_without_writing, test_init_onboarding_memory.py::test_bare_init_yes_repairs_unreferenced_long_memory); confirmed via git stash that they fail identically on a clean master HEAD (7c8117b17), so this is pre-existing repo/environment drift, not something sase-vw.1/.2/.3 introduced. just check also fails at the "SASE validation" step (init memory --check reports 6 chezmoi-deployed home dotfiles out of sync) on a clean checkout too - same root cause category, unrelated to this epic.

[2026-08-30T15:30:56Z · sase-vw.3] PROPOSED FOLLOW-UP: scope decisions worth reviewing in phase render/migrate. (1) A flat notes own ![[...]] links never trigger cross-unit inline expansion - notes have no pre-existing closure/BFS concept, so every note-sourced link (bang or not) always lands in resolved_links as a reference entry; only strand-sourced links get the same-web-span / cross-unit-extra-root treatment. (2) The ACE memory panel only builds a StrandMentionCatalog (and therefore SEE ALSO/REFERENCED BY relation chips) for webs whose effective link_reference is implicit, matching the pre-existing closure:mentions gate 1:1; an explicit-only web that authors [[...]] links still gets no panel relations, to avoid an unconditional catalog build (phrase-matcher-adjacent cost) for every ordinary web on load. The CLI (sase memory read/show) does not have this restriction - it always resolves and classifies authored links regardless of web strategy.

[2026-08-30T15:31:28Z · sase-vw.3] Implemented the link-closure integration: closure.py classifies each scanned strand link (same-web inline -> synthetic GlossarySpan merged into the existing BFS via precomputed_spans; cross-web/cross-note inline -> extra related root on the owning unit; everything else -> resolved_links) per strand's effective link_reference/link_rendering, honoring -d 0 by forcing every link to reference-only. selector.py resolves links against the full project+home notes/webs universe (resolve_memory_link_target), adds cross-web strand targets as extra MemoryWebReadSection roots and cross-note targets as extra ResolvedMemoryNote units (graceful fallback to reference on failure), and gives flat notes the same scan+resolve treatment (always reference-style, no note-triggered inlining). MemoryWebReadNode.referrer now carries a mention/link kind so selector_render.py prints 'linked from X' instead of faking a matched phrase. ACE memory_panel_catalog.py/_web_rendering.py keep the catalog-build gate on link_reference==implicit (parity with the old closure==mentions gate) and now also fold same-web authored links into the panel's SEE ALSO/REFERENCED BY relations via the new strand_link_spans() local resolver. Verified: full targeted pytest sweep (memory/, ace/tui memory-panel suites, glossary relations/resolution, main memory-read selectors) all green; just check's lint/mypy/symvision/toobig gates all green; just test-scoped run in full (38216 passed) with only 5 pre-existing, pre-my-change failures (confirmed via git stash against clean master) unrelated to this phase; end-to-end check against the real repo's sase/memory/decisions content (with closure:none temporarily lifted) reproduces the epic's stated acceptance case exactly - gates-never-block renders single-turn-agents inline with link provenance, and reverts to no expansion with the repo's current closure:none (untouched, that migration is phase sase-vw.5's job).

## Dependencies

- **Depends on:** [sase-vw.1](sase-vw.1.md) ✓ · ⧖ 2026-08-30
- **Depends on:** [sase-vw.2](sase-vw.2.md) ✓ · ⧖ 2026-08-30
- **Blocks:** [sase-vw.4](sase-vw.4.md) ✓ · ⧖ 2026-08-30

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-vw.3](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-vw.3/README.md) | [sase-vw.3](sase-vw.3.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`90e3a38`](https://github.com/sase-org/sase/commit/90e3a385c526e7659b93b29a5ce599d1e6deade6) | feat(memory): fold authored links into the closure walk | [sase-vw.3](sase-vw.3.md) | 2026-08-30 11:32:44 EDT |
