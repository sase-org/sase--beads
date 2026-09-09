# Bead: sase-z2.2 — Protect unpushed sidecar commits from workspace re-provisioning

[Bead Pages](../README.md) / [sase-z2](README.md) / sase-z2.2

**Status:** ◐ in_progress · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.0i2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.0i2.md) · **Assignee:** `sase-z2.2` · **Size:** medium
**Created:** 2026-09-09 18:25:00 EDT
**Plan:** [202609/durable\_plan\_archive\_publication.md](https://github.com/sase-org/sase--plans/blob/main/202609/durable_plan_archive_publication.md)

## Description

prep-clone-protection: find the code path that deletes and re-creates a workspace's sase/repos/<role> sidecar clones, and extend the existing publish-or-rescue protection (today bead-store-only) to every sidecar role so an unpushed plans commit can never be silently destroyed.

## Notes

[2026-09-09T23:06:59Z · sase-z2.2] Identified destruction path: src/sase/axe/runner_workspace.py:prepare_launch_workspace_repos calls sase.linked_repos.clear_workspace_repos, which renames numbered-workspace sase/repos to .sase/trash and schedules deletion before rematerializing sidecars with ensure_workspace_sdd_clone. The new guard runs immediately before clear_workspace_repos and checks every direct sase/repos/<role> Git sidecar clone, preserving the existing managed bead-store sync first.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-z2.2](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-z2.2.md) | [sase-z2.2](sase-z2.2.md) | 0 |
