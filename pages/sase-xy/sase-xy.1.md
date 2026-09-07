# Bead: sase-xy.1 — Context-aware hard search in the resolver

[Bead Pages](../README.md) / [sase-xy](README.md) / sase-xy.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.01q](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.01q.md) · **Assignee:** `sase-xy.1` · **Size:** medium
**Created:** 2026-09-07 10:02:20 EDT · **Closed:** 2026-09-07 10:42:58 EDT
**Plan:** [202609/pager\_link\_reliability.md](https://github.com/sase-org/sase--plans/blob/main/202609/pager_link_reliability.md)

## Description

resolve-search: add LinkResolutionContext with ordered workspace anchors, rework file-path resolution into a candidate/probe ladder (line suffixes, trailing-dot and diff-prefix candidates, stale-workspace re-rooting, bounded unique-suffix git ls-files search), walk anchors for typed refs through resolve_cli_reference contexts, and thread context through resolve_ref and copy_text_for_target.

## Notes

[2026-09-07T14:42:24Z · sase-xy.1] PROPOSED FOLLOW-UP: test_wipe_does_not_delete_under_the_allocation_lock patches _wipe.shutil but shutil.rmtree lives in sase.agent.names._wipe_execute — AttributeError on full-suite just check (unrelated to pager resolve-search)

[2026-09-07T14:42:58Z · sase-xy.1] Added LinkResolutionContext with ordered workspace anchors and reworked pager file-path/typed-ref resolution. Verified: just check lint gates passed (ruff, mypy, symvision, toobig); tests/pager/test_resolve.py and test_link_context.py 40 passed; just check escalated to the full suite because of Justfile --epic-symbol entries (39098 passed, 1 unrelated failure in test_wipe_does_not_delete_under_the_allocation_lock recorded as PROPOSED FOLLOW-UP). Phase-2 helpers are whitelisted as sase-xy.2 epic-symbols; sase-xy.1 has none.

## Dependencies

- **Blocks:** [sase-xy.2](sase-xy.2.md) ◐ · ⧖ 2026-09-07
- **Blocks:** [sase-xy.3](sase-xy.3.md) ✓ · ⧖ 2026-09-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xy.1](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-xy.1/README.md) | [sase-xy.1](sase-xy.1.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase | [`4bb47fc`](https://github.com/sase-org/sase/commit/4bb47fc987541c33386ee508024a956c44cbb79d) | feat(pager): resolve links against ordered workspace anchors | [sase-xy.1](sase-xy.1.md) | 2026-09-07 10:44:14 EDT |
