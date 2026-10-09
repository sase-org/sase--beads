# Bead: sase-1if.8 — Lazy sase-listen command imports

[Bead Pages](../README.md) / [sase-1if](README.md) / sase-1if.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.apollo.research.0n.linker.w0](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.apollo.research.0n.linker.w0.md) · **Assignee:** `sase-1if.8` · **Size:** small
**Created:** 2026-10-08 15:26:27 EDT · **Closed:** 2026-10-08 16:06:36 EDT
**Plan:** [202610/plugin\_commands.md](https://github.com/sase-org/sase--plans/blob/main/202610/plugin_commands.md)

## Description

listen-fast-start: in the sase-listen repo, defer heavy imports into command handlers so building the parser and rendering help stay fast, guarded by an import-isolation test.

## Notes

[2026-10-08T20:06:36Z · sase-1if.8] Lazy imports land: render/script_cmd/lint/doctor/feed_cmd/publish_cmd defer pipeline/feed/feedhost/progress/rich into handler bodies; events.py is stdlib-only again (RetryWait via lazy __getattr__). New tests/test_fast_start.py subprocess guard passes; all 13 --help outputs byte-identical to pre-change goldens; cli.app import 1287ms->~135ms with none of numpy/PIL/mutagen/httpx/lxml/trafilatura/pdfminer/google-genai/pipeline in sys.modules; stale-env guard still exits 3; 3 existing tests re-pointed to patch defining modules; sase tool run check green (378+ passed).

## Dependencies

- **Blocks:** [sase-1if.10](sase-1if.10.md) ✓ · ⧖ 2026-10-08
- **Depends on:** [sase-1if.2](sase-1if.2.md) ✓ · ⧖ 2026-10-08

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.apollo.sase-1if.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1if.8/README.md) | [sase-1if.8](sase-1if.8.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-listen | [`sase-listen@bbaf58f`](https://github.com/sase-org/sase-listen/commit/bbaf58f7cdedecc54af5549cca1672afd71ba6e3) | perf(cli): defer heavy imports into command handlers for fast startup | [sase-1if.8](sase-1if.8.md) | 2026-10-08 16:07:42 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1if.8][1] | Need the phase scope and design file | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.apollo.sase-1if.8/README.md

<!-- sase:referenced-by:end -->
