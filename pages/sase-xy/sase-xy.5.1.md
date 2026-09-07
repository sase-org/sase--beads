# Bead: sase-xy.5.1 — Parse document links into faithful semantic targets

[Bead Pages](../README.md) / [sase-xy.5](sase-xy.5.md) / sase-xy.5.1

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.03o--1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.03o.md) · **Assignee:** `sase-xy.5.1` · **Size:** medium
**Created:** 2026-09-07 13:01:41 EDT · **Closed:** 2026-09-07 14:14:50 EDT
**Plan:** [202609/pager\_target\_integrity.md](https://github.com/sase-org/sase--plans/blob/main/202609/pager_target_integrity.md)

## Description

document-targets: add the Rust document-link scanner and binding contract, separating painted text from normalized destinations and covering generated Markdown.

## Notes

[2026-09-07T18:13:46Z · sase-xy.5.1] PROPOSED FOLLOW-UP: repair pending_actions Symvision URI pragmas — primary just check fails because current sase-telegram no longer references upsert_transport_action, get_transport_action, list_transport_actions, remove_transport_action, or cleanup_transport_actions.

[2026-09-07T18:14:50Z · sase-xy.5.1] Implemented Rust document scanner/binding and Python pager adapter. Verified linked core just check with LD_LIBRARY_PATH for uv Python 3.14; focused Rust artifact_ref scanner and PyO3 binding tests; focused pytest artifact_refs/pager (62 passed). Primary just check clears fmt/mypy/lint lanes until unrelated pre-existing pending_actions.py symvision URI-pragma failures, recorded as PROPOSED FOLLOW-UP. epic-symbol guard clean.

[2026-09-07T23:18:31Z · 06c] RECONCILIATION UPDATE / x74_telegram_finalization_repair / 2026-09-07: The pending_actions Symvision URI pragma follow-up noted here is resolved by landing the Telegram adapter against the shared pending-action API. External Symvision with SYMVISION_EXTERNAL_REPO_PATHS=linked sase-telegram passes. Host pager cleanup was required only for current host lint gates: made GutterSection private, removed dead _measure_section_heights test hook, and split goto tests below toobig limit; focused pager tests pass. Remaining host just check failure is the unrelated sase-xe %dispatch core/host contract mismatch recorded on sase-xe, not a Telegram or pager-target regression.

## Dependencies

- **Blocks:** [sase-xy.5.2](sase-xy.5.2.md) ✓ · ⧖ 2026-09-07
- **Blocks:** [sase-xy.5.3](sase-xy.5.3.md) ✓ · ⧖ 2026-09-07
