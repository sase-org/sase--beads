# Bead: sase-1rq.5 — Turn dotfiles CI green

[Bead Pages](../README.md) / [sase-1rq](README.md) / sase-1rq.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.19h](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.19h.md) · **Assignee:** `sase-1rq.5` · **Size:** xlarge
**Created:** 2026-11-07 07:46:43 EST · **Closed:** 2026-11-07 09:40:52 EST
**Plan:** [202611/red\_ci\_repair.md](https://github.com/sase-org/sase--plans/blob/main/202611/red_ci_repair.md)

## Description

dotfiles: remove the ripgrep dependency (or provision it) behind the "rg: command not found" failure in tests/bash/doctl_login_test.sh that has kept the test job red since 2026-11-05.

## Notes

[2026-11-07T14:40:52Z · sase-1rq.5--1] Verified CI run 42378990324 (https://github.com/bbugyi200/dotfiles/actions/runs/42378990324) completed successfully at master tip f1da6b641eca9616d687689a30e62eba12553f47; lint (ubuntu-latest) and test (ubuntu-latest) succeeded. The fix run 42375253106 also passed both jobs on attempt 1. Local bashunit tests/bash/doctl_login_test.sh passed all 17 tests with rg removed from PATH; just test, just lint, and just fmt-check passed. chezmoi apply was skipped because tests/ is outside the source root. CI evidence is attached as ci_evidence.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1rq.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.5.md) | [sase-1rq.5](sase-1rq.5.md) | 0 |
