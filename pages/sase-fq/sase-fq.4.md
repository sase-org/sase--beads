# Bead: sase-fq.4 — Stop the real-uv harness leaking lock files into the watched temp root

[Bead Pages](../README.md) / [sase-fq](README.md) / sase-fq.4

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.tq](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.tq/README.md) · **Assignee:** `sase-fq.4` · **Size:** small
**Created:** 2026-08-05 21:05:56 EDT
**Plan:** [202608/ci\_master\_red\_recovery.md](https://github.com/sase-org/sase--plans/blob/main/202608/ci_master_red_recovery.md)

## Description

uv-harness-tmpdir: give the uv_env fixture its own TMPDIR under tmp_path so real uv subprocesses stop dropping uv-setuptools-*.lock into the managed SASE temp root and tripping the session temp-leak guard.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-fq.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-fq.4/README.md) | [sase-fq.4](sase-fq.4.md) | 0 |
