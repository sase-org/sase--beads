# Bead: sase-um.9.5.5 — Ratchet and publish bugyi-chops 0.9.0 against released SASE v0.17.0

[Bead Pages](../README.md) / [sase-um.9.5](sase-um.9.5.md) / sase-um.9.5.5

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-um.9.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-um.9.land.md) · **Assignee:** `sase-um.9.5.5` · **Size:** medium
**Created:** 2026-08-28 20:17:51 EDT · **Closed:** 2026-08-29 13:58:31 EDT
**Plan:** [202608/finish\_release\_gate\_landing.md](https://github.com/sase-org/sase--plans/blob/main/202608/finish_release_gate_landing.md)

## Description

choppublish: update bugyi-chops to the released SASE 0.17 dependency window, prove a clean public-index install, publish 0.9.0, and verify the released wheel live.

## Notes

[2026-08-29T17:58:31Z · sase-um.9.5.5--1] Completed bugyi-chops 0.9.0 release: annotated tag v0.9.0 was pushed at b0f66983f4bacee8f3722b9e4d03d249317ff208 and Publish to PyPI run 33266707738 completed success. PyPI has bugyi-chops 0.9.0; metadata Requires-Dist includes sase<0.18.0,>=0.17.0 and toobig<0.2.0,>=0.1.0. Installed version: live SASE uv tool env now has bugyi-chops 0.9.0 from the files.pythonhosted.org wheel, while sase, sase-core-rs, sase-github, sase-telegram, and sase-research-artifacts remain editable/source-backed. Prior public-index verification passed in fresh Python 3.12: env -u BUGYI_CHOPS_VENV_BIN UV_PYTHON=3.12 uv sync --group dev --refresh; env -u BUGYI_CHOPS_VENV_BIN just check passed ruff format/check, mypy, 113 pytest cases with coverage, build, and twine check; direct import checked sase.feature_flags and sase.xprompt.directives.extract_prompt_directives -> directives.if_code. Current verification commands: gh run view 33266707738 --repo bbugyi200/bugyi-chops --json databaseId,status,conclusion,event,headBranch,headSha,displayTitle,workflowName,createdAt,updatedAt,url returned completed/success for workflow Publish to PyPI; uv pip install --python /home/bryan/.local/share/uv/tools/sase/bin/python3 --reinstall --no-deps --only-binary :all: https://files.pythonhosted.org/packages/42/e5/df580467d9886985174c371e8810bd85dddfd8034b333dfb8cb93b751a50/bugyi_chops-0.9.0-py3-none-any.whl replaced the GitHub snapshot with the PyPI wheel; importlib.metadata showed bugyi-chops 0.9.0 from that wheel with Requires-Dist sase<0.18.0,>=0.17.0; sase axe chop run ci_watch --dry-run --force --chop-verbose completed no_op. Dry-run release reasons for configured release repos: sase-org/sase-github: no release PR; sase-org/sase-telegram: PR #21 merge state not clean; sase-org/sase: PR #298 gating workflow red. Final cleanup: sase bead epic-symbols sase-um.9.5.5 reported no --epic-symbol entries.

## Dependencies

- **Depends on:** [sase-um.9.5.4](sase-um.9.5.4.md) ✓ · ⧖ 2026-08-28

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-um.9.5.5](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-um.9.5.5.md) | [sase-um.9.5.5](sase-um.9.5.5.md) | 0 |
