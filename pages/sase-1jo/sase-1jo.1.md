# Bead: sase-1jo.1 — CV repo cleanup and PDF rebuilds

[Bead Pages](../README.md) / [sase-1jo](README.md) / sase-1jo.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.6k](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.6k.md) · **Assignee:** `sase-1jo.1` · **Size:** medium
**Created:** 2026-10-10 15:45:43 EDT · **Closed:** 2026-10-10 15:52:20 EDT
**Plan:** [202610/databricks\_followups.md](https://github.com/sase-org/sase--plans/blob/main/202610/databricks_followups.md)

## Description

cv: make the base and Batman CVs build without gutils.tex, remove stale SASE claims from the older variants, update the base CV, and rebuild and verify every changed PDF.

## Notes

[2026-10-10T19:52:00Z · sase-1jo.1] Changed BryanBugyi_CV, BryanBugyi_Batman_CV, BryanBugyi_Google_CV, and BryanBugyi_LangChain_CV .tex sources and PDFs. Removed gutils.tex inputs from base and Batman; base now explicitly loads enumitem, ulem[normalem], xparse, and the declarecommand alias; Batman explicitly loads enumitem. Updated the base CV with the approved SASE entry and corrected Google tense; removed stale CLI, telemetry, and plugin claims from the three older variants. Installed TinyTeX packages ebgaramond, fontawesome5, listings, ulem, and tocloft. Built all four PDFs twice with pdflatex; page counts remain base 3, Batman 2, Google 2, LangChain 2. mutool text extraction confirms Google ends May 2026 in each PDF, stale-claim scan is clear, and every page was visually reviewed against its saved baseline. Nothing left undone.

[2026-10-10T19:52:20Z · sase-1jo.1] Rebuilt base, Batman, Google, and LangChain PDFs successfully; page counts remain 3/2/2/2. Verified Google ends May 2026 in every PDF, stale-claim scan is clear, both base and Batman build without gutils.tex, and visually reviewed every output page against its saved baseline.

## Dependencies

- **Blocks:** [sase-1jo.4](sase-1jo.4.md) ✓ · ⧖ 2026-10-10

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1jo.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1jo.1/README.md) | [sase-1jo.1](sase-1jo.1.md) | 0 |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1jo.1][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1jo.1/README.md

<!-- sase:referenced-by:end -->
