# Bead: sase-sq.7.1 — Glossary migration to a core web

[Bead Pages](../README.md) / [sase-sq.7](sase-sq.7.md) / sase-sq.7.1

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-sq.7](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-sq.7.md) · **Assignee:** `sase-sq.7.1.land`
**Created:** 2026-08-24 18:15:34 EDT
**Plan:** [202608/glossary\_memory\_web.md](https://github.com/sase-org/sase--plans/blob/main/202608/glossary_memory_web.md)

## Description

The `sase` and `bob-cli` glossaries stop living in `memory.glossary` and become file-backed core memory webs: `sase/memory/glossary.md` is a user-owned descriptor with a managed roster region, each term is a strand file under `sase/memory/glossary/`, the Rust glossary source wire addresses strand files so editor go-to-definition lands on a real Markdown note, config and files can never both be live, and `sase glossary *` survives one release as a deprecating alias over `sase memory`.

## Notes

[2026-08-25T01:45:34Z · toobig-40.test_test_cost.0] DISCOVERED ISSUE: During unrelated tests/test_test_cost.py split verification on 2026-08-24T21:45:26-04:00, just check passed fmt, Ruff, mypy, feature-flag, pyscripts, test-waits, changelog, and terminology gates, then failed at lint (symvision). Symvision reported unused public symbols: add_glossary_strand and delete_glossary_strand in src/sase/glossary/web_mutation.py, and glossary_project_root in src/sase/glossary/compat.py. My diff only moves tests/test_test_cost.py into tests/test_test_cost_*.py and does not touch src/sase/glossary. This appears causally tied to active phase sase-sq.7.1.6, which is migrating the sase and bob-cli glossaries to file-backed memory webs; no new task bead created.

[2026-08-25T01:47:06Z · toobig-40.test_ratchet_core_window_tool.0] CORROBORATION: During unrelated tests/test_ratchet_core_window_tool.py split verification on 2026-08-24, just check reached the same lint (symvision) failure: unused public add_glossary_strand and delete_glossary_strand in src/sase/glossary/web_mutation.py, and glossary_project_root in src/sase/glossary/compat.py. Reproduced independently via git stash on plain master (commit f22f11307) with the identical symvision invocation, confirming it is not diff-specific. My diff only touches tests/test_ratchet_core_window_tool*.py and tests/contract_manifest.txt. No new task bead created; routing here per the existing DISCOVERED ISSUE note attributing this to active phase sase-sq.7.1.6.

[2026-08-25T02:04:32Z · toobig-41.project_mutations.0] CORROBORATION: During src/sase/bead/_project_mutations.py split cleanup verification on 2026-08-24, just check passed fmt, keep-sorted, Ruff, mypy, feature-flag, pyscripts, test-waits, changelog, and patch/stitch terminology gates, then failed at lint (symvision). Symvision reported unused public add_glossary_strand and delete_glossary_strand in src/sase/glossary/web_mutation.py plus glossary_project_root in src/sase/glossary/compat.py. The local diff only touches src/sase/bead/_project_mutations_*.py, so this corroborates the existing glossary migration blocker rather than the bead mutation split.

[2026-08-25T02:15:48Z · toobig-41.agent_chat_from_name.0] CORROBORATION: During unrelated src/sase/scripts/agent_chat_from_name.py split verification on HEAD 6ef21dc02, focused agent_chat_from_name tests passed (57 passed), and just check passed fmt, markdown fmt, keep-sorted, Ruff, mypy, feature-flag, pyscripts, test-waits, changelog, and patch/stitch terminology gates before failing at lint (symvision). After fixing the split's private-import findings, just _lint-symvision now deterministically reports unused public add_glossary_strand and delete_glossary_strand in src/sase/glossary/web_mutation.py plus glossary_project_root in src/sase/glossary/compat.py. The local diff only touches src/sase/scripts/agent_chat_from_name.py and the new src/sase/scripts/_agent_chat_from_name_*.py split modules, so this corroborates the existing glossary migration blocker rather than the chat resolver split.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-sq.7.1.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-sq.7.1.land/README.md) | [sase-sq.7.1](sase-sq.7.1.md) | 0 |
