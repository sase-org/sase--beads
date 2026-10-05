# Bead: sase-1g4.2.1 — Carry macro input metadata and finish enum assistance in the LSP

[Bead Pages](../README.md) / [sase-1g4.2](sase-1g4.2.md) / sase-1g4.2.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1g4.2](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1g4.2.md) · **Assignee:** `sase-1g4.2.1.land`
**Created:** 2026-10-05 02:19:23 EDT · **Closed:** 2026-10-05 08:58:09 EDT
**Plan:** [202610/macro\_choice\_wires\_lsp.md](https://github.com/sase-org/sase--plans/blob/main/202610/macro_choice_wires_lsp.md)

## Description

Complete the wire-lsp scope of sase-1g4.2: preserve resolved choices, named types, and value roles across catalogs and projections; share Rust choice candidates and type labels; and make enum completion, diagnostics, quick fixes, and hover agree with the runtime binder.

## Notes

[2026-10-05T12:21:05Z · sase-1g4.2.1.land] LANDING TRIAGE (sase-1g4.2.1.land, 2026-10-05). Verified: all 5 phases closed; core commits 0d27dada/57fee306/ecd2e074 and sase commits 4fd4039a5a/399b13f3ef/a6df140bcc/6fde796604/8c8c47f720 implement the plan (shared macro_argument_choice_candidates/macro_input_type_label, ENUM_MEMBER full-value edits, frontmatter type completion, diagnostic data, Replace-with quick fixes, hover tables, Python projections, golden corpus mirror). The epic's own suites pass at HEAD: 287 sase Python tests (parity, projection, terminology, cli-show, highlight, mobile, probe contracts), sase_gateway 224, and the sase_macro_lsp choice-completion/choice-diagnostics JSON-RPC suites. The pin is sase-core-revision.txt = ecd2e074 = core HEAD. Since the epic started, only f0893af93b (query-profile hash) landed in sase, unrelated, and nothing landed in core. Follow-up outcomes: (1) the 14 sase_core lib failures (.1 #1, .3 #3) plus the newly found python_wire_parity/sase_core_py/sase_macro_lsp failures and the hanging stdio_jsonrpc_frontmatter_diagnostics all reproduce on clean core 0279de6b, so they are caused by the active rename epic: recorded as a DISCOVERED ISSUE on sase-1eq, no task. (2) The host _setup probe schema 6 vs 5 (.2 #1, .3 #1, .4 #1) is already sase-1eq note #4 item 4; corroborated in that same sase-1eq note, no task. (3) Host surfaces still expecting invalid_xprompt_arg_type (.3 #4) was declined as already fixed: 8c8c47f720 updated the parity expectations, and no src/test expectation remains. (4) The core clippy -D warnings failure (.2 #2, .3 #2: type_complexity at macro_arg_choices.rs:94/126/152 and parsing.rs:651, cloned_ref_to_slice_refs at :373) still fails core check (ToolRun b4bae47dd49109560393bbb48f1e2bd2). It was caused by this epic, so it is REMAINING EPIC WORK. (5) The stale terminology pairs (.5 #3) were made stale by this epic's 8c8c47f720, so they are remaining epic work. (6) The full check never completed (.5 #2): this landing ran it, and the host is blocked by (2) while core is blocked by (4) and then (1). Also remaining epic work: 8c8c47f720 swept in the orphaned sase-146 draft files src/sase/tool/adoption.py and src/sase/core/tool_adoption.py, which call a binding no core defines (noted on sase-146). And the new code invalid_xprompt_arg_choice conflicts with the macro rename, since every sibling code is *_macro_*. Remaining work is planned as a tale.

[2026-10-05T12:58:09Z · sase-1g4.2.1.land--1] LANDING (tale 202610/land_macro_choice_wires_lsp.md). All five phases closed: .1 Rust wires/shared choice candidates/type labels, .2 enum+frontmatter type completion, .3 choice diagnostics/quick fixes/hover, .4 Python catalogs/mobile/highlight/macro show, .5 cross-surface acceptance. Commits: core 0d27dada/57fee306/ecd2e074 (=HEAD=pin in sase-core-revision.txt), sase 4fd4039a5a/399b13f3ef/a6df140bcc/6fde796604/8c8c47f720; tale fixes uncommitted in working tree for host to commit (core first). Tale fixes: (1) core clippy type_complexity/cloned_ref_to_slice_refs fixed via named structs in macro_arg_choices.rs and parsing.rs plus slice::from_ref — just clippy clean; (2) invalid_xprompt_arg_choice renamed to invalid_macro_arg_choice across core crates, sase docs/editor.md, terminology allowlist trimmed — grep returns nothing; (3) orphaned sase-146 draft files src/sase/core/tool_adoption.py and src/sase/tool/adoption.py deleted (unreferenced); (4) stale terminology pairs dropped from _pairs_a_late, _pairs_b_late, _macro_terminology_strings. Gates (monitor nmwyhv7t2ygf, ToolRun 26b14a7f50ffc041cf3af29334cfcb6b): rust-install PASS, epic pytest set (15 files incl. terminology/parity/cli-show/highlight/mobile/contracts) PASS, ruff PASS, symvision direct PASS, core just fmt PASS, core just clippy PASS. Expected NONZERO only as planned: sase tool run check dies in _setup on sase_content_layout stale-schema probe got-6-vs-5 (ToolRun 58e18e927a04fedb72c5fd0cc02f12a8); mypy 5 errors all known pre-existing (InputType input_item_modal, 3 LEGACY_XPROMPT_JINJA_SCOPE_KIND JinjaScope callers, LOCAL_XPROMPTS_ENV); core just test shows exactly the sase-1eq set with stdio_jsonrpc_frontmatter_diagnostics skipped (14 sase_core lib, proc_snapshot_json_uses_canonical_proc_keys, 6 sase_core_py pins, 2 sase_macro_lsp lib: metadata_env_prefers_macro_prefix + hover/diagnostics surfaces); core tool run check stops at the 14 lib failures (ToolRun 522dd46022369745ee202e8bf227a380). OVERALL_FAIL=none. Pre-existing blockers stay on sase-1eq (DISCOVERED ISSUE + note #4 item 4). LANDING TRIAGE follow-ups resolved: items 1-3 declined/recorded (pre-existing on clean 0279de6b, already on sase-1eq, parity already fixed by 8c8c47f720); items 4-6 plus orphan/rename/stale-pair work completed by this tale. Sibling note written on sase-1g4.4 per plan sec 2.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1g4.2.1.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1g4.2.1.land.md) | [sase-1g4.2.1](sase-1g4.2.1.md) | 2 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase-core | [`sase-core@fe2ef0e`](https://github.com/sase-org/sase-core/commit/fe2ef0e6af311dc6ae7ba7340e85d54822504f26) | fix(lsp): land choice-wire tale: clippy named structs, invalid\_macro\_arg\_choice rename | [sase-1g4.2.1](sase-1g4.2.1.md) | 2026-10-05 08:59:59 EDT |
| sase | [`0a7ccdf`](https://github.com/sase-org/sase/commit/0a7ccdf92c6c2ff6777a7d0e3032e719a21dc936) | fix(macro): land choice-wire tale: macro-spelled choice diagnostic docs, orphan removal, stale-pair cleanup | [sase-1g4.2.1](sase-1g4.2.1.md) | 2026-10-05 09:04:27 EDT |

<!-- sase:referenced-by:start -->

## Referenced By

| Relation | Artifact | Why | Uses |
| --- | --- | --- | ---: |
| read-by | [agent:sase-1g4.2.1.1][1] | Need parent epic scope | 1 |
| read-by | [agent:sase-1g4.2.1.2][2] | Need parent epic scope for phase 1g4.2.1.2 | 1 |
| read-by | [agent:sase-1g4.2.1.3][3] | Need parent epic scope and remaining work | 1 |
| read-by | [agent:sase-1g4.2.1.land--1][4] | landing-tale closeout per plan | 1 |

[1]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1g4.2.1.1/README.md
[2]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1g4.2.1.2/README.md
[3]: https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1g4.2.1.3/README.md
[4]: https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1g4.2.1.land.md

<!-- sase:referenced-by:end -->
