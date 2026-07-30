# Bead: sase-bc.4 — Configure the research-highlights hook and verify end to end

[Bead Pages](../README.md) / [sase-bc](README.md) / sase-bc.4

**Status:** ✓ closed · **Resolution:** done · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-bc.4` · **Size:** small
**Created:** 2026-07-30 17:33:40 UTC · **Closed:** 2026-07-30 19:12:33 UTC
**Plan:** [202607/commit\_file\_hooks.md](https://github.com/sase-org/sase--plans/blob/main/202607/commit_file_hooks.md)

## Description

deploy-verify: add the research-highlights file_hooks entry to the chezmoi-managed global sase.yml, apply it, install the new bob binary, run `bob highlights create` against the real 202607 beads research report, verify the PDF and then the ref note produced by `bob highlights scan`, and exercise the sase hook engine end to end including its notification.

## Dependencies

- **Depends on:** [sase-bc.1](sase-bc.1.md) ✓
- **Depends on:** [sase-bc.3](sase-bc.3.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-bc.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-bc.4/README.md) | [sase-bc.4](sase-bc.4.md) | 0 |
