# Bead: sase-ha.8 — Live end-to-end verification

[Bead Pages](../README.md) / [sase-ha](README.md) / sase-ha.8

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.ve](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.ve/README.md) · **Assignee:** `sase-ha.8` · **Size:** small
**Created:** 2026-08-07 20:46:17 EDT · **Closed:** 2026-08-08 09:41:15 EDT
**Plan:** [202608/muse\_provider.md](https://github.com/sase-org/sase--plans/blob/main/202608/muse_provider.md)

## Description

verify: run real SASE agents on Muse, confirm the artifacts and skill rendering on disk, exercise `sase agent-cli` install/update against the live channel, and land the tree green under `just check-full`.

## Notes

[2026-08-08T14:00:07Z · sase-ha.land] Completed by epic land agent sase-ha.land on 2026-08-08. This phase closed at 13:41:15Z with no note; its transcript (sase chat show --agent sase-ha.8) shows plan steps 1-5 verified live — agent-cli list/update/install against the live channel (muse 0.1.0-R708.1, latest matches), skills rendered to ~/.config/muse/skills/<name>/SKILL.md with provider_name 'Muse Code' and 'muse skills list --json' picking them over the shadowed ~/.claude/skills copies, a real SASE agent (agent 'vi', muse-spark-1.2-contributor) producing every expected artifact, sandbox-off in-run commit succeeding with real session-log usage and sandbox-on failing clearly with 'Read-only file system' on .git/index.lock, both tiers resolving to muse-spark-1.2, the advisory rendering on only the Contributor row in the ACE model picker, and 'sase doctor -C llm.model_advisory -v' silent — but its response ends waiting on a backgrounded 'just check-full' that never reported. Step 6 is now done: 'just check-full' on clean master 204537c97 passes every lint gate (fmt python/markdown, keep-sorted, ruff, mypy, pyscripts, changelog, symvision, toobig, SASE validation, committed plans) and runs 27601 passed / 10 skipped / 1 failed, the single failure being tests/test_content_layout.py::test_project_home_and_chezmoi_named_paths_are_canonical (schema_version 3 vs 2), which is cross-repo skew from the in-progress sase-hf epic and is recorded there as a DISCOVERED ISSUE.

## Dependencies

- **Depends on:** [sase-ha.7](sase-ha.7.md) ✓ · ⧖ 2026-08-07

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ha.8](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ha.8/README.md) | [sase-ha.8](sase-ha.8.md) | 0 |
