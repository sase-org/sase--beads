# Bead: sase-96.8.2 — Give the agent-launch prompt file a reapable home

[Bead Pages](../README.md) / [sase-96.8](sase-96.8.md) / sase-96.8.2

**Status:** ✓ closed · **Resolution:** (unrecorded) · **Type:** phase
**Owner:** `bryanbugyi34@gmail.com` · **Assignee:** `sase-96.8.2` · **Size:** medium
**Created:** 2026-07-25 18:15:29 UTC
**Plan:** [202607/managed\_tmp\_reaping.md](https://github.com/sase-org/sase--plans/blob/main/202607/managed_tmp_reaping.md)

## Description

'Give the agent-launch prompt file a reapable home' section: route src/sase/agent/launch_spawn.py's sase_tmpdir argument and ace_handler's profile output through a managed subdirectory instead of the bare $SASE_TMPDIR root, and decide the fate of the now-unused get_sase_tmpdir helper. This is the largest active producer (32,595 files) and a grep-driven audit of src/sase could not see it because the tempfile call lives in sase-core.

## Notes

Routed the agent-launch prompt file and the ACE profile output through managed subdirectories:

- src/sase/agent/launch_spawn.py now passes sase_tmpdir=get_sase_managed_tmpdir("launch-prompts"); the sase-core Rust side needed no edit (write_prompt_temp_file already honors an explicit dir and only falls back to the system temp dir when the argument is empty/None).
- src/sase/main/ace_handler.py writes ace_profile_<ts>.txt under get_sase_managed_tmpdir("ace-profiles"); the explicit --profile <path> override is unchanged.
- get_sase_tmpdir() is deleted (paths.py + sase.core re-exports). It had no remaining consumer in this repo, sase-core, sase-github, sase-telegram, or chezmoi. get_sase_managed_tmpdir's docstring now states that callers must always pass a subdirectory part and that no bare-root helper exists.
- Tests updated: tests/test_axe_chop_agents.py redirects the managed root via a helper and asserts the prompt file lands in <root>/launch-prompts with the sase_ace_prompt_ prefix; tests/main/test_ace_handler.py asserts the ace-profiles subdirectory.

Verification: exercised prepare_agent_launch against a scratch SASE_TMPDIR - prompt file landed in <root>/launch-prompts/sase_ace_prompt_*.md, and 0 files were added directly to the root. just check is green except the pre-existing tests/ace/tui/widgets/file_panel/test_diff_cache.py::test_get_agent_diff_invalidates_when_index_changes intra-file pollution failure the plan lists under Non-goals (passes in isolation).

## Dependencies

- **Blocks:** [sase-96.8.7](sase-96.8.7.md) ✓

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-96.8.2](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-96.8.2/README.md) | [sase-96.8.2](sase-96.8.2.md) | 1 |

## Commits

| Commit | Subject | Bead | Committed (UTC) |
|---|---|---|---|
| [`63b9d88`](https://github.com/sase-org/sase/commit/63b9d8814590ea857e4675b5b55099a0d475f3c4) | fix: give the agent-launch prompt file a reapable home (sase-96.8.2) | [sase-96.8.2](sase-96.8.2.md) | 2026-07-25 19:16:39 |
