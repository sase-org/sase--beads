# Bead: sase-1rq.5 — Turn dotfiles CI green

[Bead Pages](../README.md) / [sase-1rq](README.md) / sase-1rq.5

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.19h](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.19h.md) · **Assignee:** `sase-1rq.5` · **Size:** xlarge
**Created:** 2026-11-07 07:46:43 EST
**Plan:** [202611/red\_ci\_repair.md](https://github.com/sase-org/sase--plans/blob/main/202611/red_ci_repair.md)

## Description

dotfiles: remove the ripgrep dependency (or provision it) behind the "rg: command not found" failure in tests/bash/doctl_login_test.sh that has kept the test job red since 2026-11-05.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1rq.5](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1rq.5.md) | [sase-1rq.5](sase-1rq.5.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| chezmoi | [`chezmoi@28fd5c7`](https://github.com/bbugyi200/dotfiles/commit/28fd5c78dac932cb948121b71823a3887a69a9aa) | fix(tests): use grep instead of rg in doctl\_login\_test | [sase-1rq.5](sase-1rq.5.md) | 2026-11-07 08:04:09 EST |
