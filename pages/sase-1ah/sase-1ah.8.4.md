# Bead: sase-1ah.8.4 — Publish the receipt-capable core wheel and raise the sase floor

[Bead Pages](../README.md) / [sase-1ah.8](sase-1ah.8.md) / sase-1ah.8.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-1ah.8.land](https://github.com/sase-org/sase--agents/blob/main/sessions/bbugyi200.athena.sase-1ah.8.land.md) · **Assignee:** `sase-1ah.8.4.land`
**Created:** 2026-09-26 18:37:47 EDT · **Closed:** 2026-09-27 07:45:35 EDT
**Plan:** [202609/receipt\_capable\_wheel.md](https://github.com/sase-org/sase--plans/blob/main/202609/receipt_capable_wheel.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/receipt_capable_wheel.md][1] | derived from the plan's `bead_id:` frontmatter field |

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/receipt_capable_wheel.md

<!-- sase:links:end -->

## Description

Unblock the sase-core release that contains the receipt report binding, publish a complete sase-core-rs wheel, and raise sase's declared floor so a fresh wheel install accepts the catalog receipt policy.

## Notes

[2026-09-27T11:45:35Z · sase-1ah.8.4.land] Verified: phase 1 (sase-1ah.8.4.1) change is on sase-core origin/master, where Cargo.toml has sase_gateway = { path = "crates/sase_gateway" } with no caret pin. release-plz then cut v0.35.0 (PR #313, fe1e065), which descends from 0cf5147/9f86897/e654e7c (receipt binding) plus f55c63b and eef7ca4. pypi_release_files.py status 0.35.0 = complete. Phase 2 (sase-1ah.8.4.2): sase bc7144574 ratcheted the floor to sase-core-rs>=0.35.0,<0.36.0 through just ratchet-core-window (pyproject+uv.lock), with the phase recording a fresh-venv PyPI-wheel proof: receipt catalog loads, receipt check/test give typed refusals, receipts exits 0. Integration: no commits after bc7144574. The 39 commits since the epic started do not conflict with the floor. The finalizers/prepare.py fail-closed accept guard is kept on purpose. sase-17t (drop awaits fallbacks) is now unblocked by the 0.35.0 floor, so I noted it there. Phase 2 had not recorded the published version on sase-10d, so I added that note (it also covers raising the research-artifacts floor), and sase-10d stays open for the sase PyPI publish. Follow-ups: 8.4.2 #2 (check_sase_core_rs_bindings missing proc_wire_schema_version, which no sase-core commit defines; the call site came from sase-1ab's 55e9e96de) and #3 (base-tree check failures from proc-shell->named-proc rename drift, snapshot test re-failing at HEAD) are both caused by active epic sase-1ab, so I recorded each as a DISCOVERED ISSUE on sase-1ab instead of opening new tasks. Epic-symbols: none.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-1ah.8.4.land](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-1ah.8.4.land/README.md) | [sase-1ah.8.4](sase-1ah.8.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase--plans | [`sase--plans@ac25e18`](https://github.com/sase-org/sase--plans/commit/ac25e1820c4bc41056e02969ba5caba3761b2745) | chore(plans): mark receipt\_capable\_wheel and e4\_landing\_remainder done | [sase-1ah.8.4](sase-1ah.8.4.md) | 2026-09-27 07:57:39 EDT |
