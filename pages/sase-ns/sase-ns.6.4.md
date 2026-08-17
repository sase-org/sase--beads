# Bead: sase-ns.6.4 — Make chezmoi's just check idempotent

[Bead Pages](../README.md) / [sase-ns.6](sase-ns.6.md) / sase-ns.6.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-ns.land--1](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-ns.land.md) · **Assignee:** `sase-ns.6.4` · **Size:** small
**Created:** 2026-08-16 21:02:35 EDT · **Closed:** 2026-08-16 21:07:07 EDT
**Plan:** [202608/task\_backlog\_top5.md](https://github.com/sase-org/sase--plans/blob/main/202608/task_backlog_top5.md)

## Description

chezmoi_check_idempotent: task bead sase-m8. Make the chezmoi repo's `just check` idempotent so a second consecutive run stops failing fmt-md-check on a pytest cache artifact.

## Notes

[2026-08-17T01:07:07Z · sase-ns.6.4] Updated linked chezmoi .prettierignore to exclude .pytest_cache/; verified an intentionally unformatted .pytest_cache/README.md is ignored by just fmt-md-check and two consecutive just check runs pass with pytest cache present.

[2026-08-17T01:08:15Z · sase-ns.6.4] Verified prettier ignores pytest cache README via fmt-md-check and two consecutive just check runs in linked chezmoi repo.
