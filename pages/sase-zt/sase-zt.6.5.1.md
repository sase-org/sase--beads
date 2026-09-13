# Bead: sase-zt.6.5.1 — Finish flag-aware queue name completion in the current Rust core

[Bead Pages](../README.md) / [sase-zt.6.5](sase-zt.6.5.md) / sase-zt.6.5.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-zt.6.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-zt.6.land.md) · **Assignee:** `sase-zt.6.5.1` · **Size:** small
**Created:** 2026-09-13 14:29:56 EDT · **Closed:** 2026-09-13 14:49:17 EDT
**Plan:** [202609/queue\_capacity\_final\_integration.md](https://github.com/sase-org/sase--plans/blob/main/202609/queue_capacity_final_integration.md)

## Description

core-completion: select flag-aware queue metadata for directive-name completion and cover enabled/disabled documentation through Rust and the LSP.

## Notes

[2026-09-13T18:49:17Z · sase-zt.6.5.1] Updated core directive-name completion to use queue_directive_metadata(enabled_feature_flags) for %queue, with Rust and LSP docs coverage for queue_capacity_budget on/off. Base core HEAD was 23f19f0b4566a9e5db8ff13b3b08bedd64661fac; finalizer commit will contain the two-file core change. Verified: cargo test -p sase_core queue_name_completion_uses_flag_aware_documentation; cargo test -p sase_xprompt_lsp directive_name_completion_documents_queue_capacity_flag_state; git diff --check; sase bead epic-symbols reported no entries. Ran just check: default managed target hit already-tracked sase-yn provider_priority LockTimeout; clean-env reruns reached the workspace tests and then hit already-tracked sase-10a gateway seeded fleet row failure.

## Dependencies

- **Blocks:** [sase-zt.6.5.2](sase-zt.6.5.2.md) ◐ · ⧖ 2026-09-13

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zt.6.5.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-zt.6.5.1/README.md) | [sase-zt.6.5.1](sase-zt.6.5.1.md) | 0 |
