# Bead: sase-zw.8 — Finish disk retention safety and integrated footprint acceptance

[Bead Pages](../README.md) / [sase-zw](README.md) / sase-zw.8

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.sase-zw.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-zw.land.md) · **Assignee:** `sase-zw.8.land`
**Created:** 2026-09-13 18:40:37 EDT
**Plan:** [202609/disk\_footprint\_remaining\_work.md](https://github.com/sase-org/sase--plans/blob/main/202609/disk_footprint_remaining_work.md)

## Description

SASE disk owners enforce bounded, safe retention through Rust core, disk pressure reports and invokes the same policies, and the remaining host acceptance is measured.

## Notes

[2026-09-14T15:29:22Z · 0kk--code] COORDINATION from sase-10r: managed-tmp pressure now takes additive wire field `pressure_low_free_space_min_age_seconds` (config `managed_tmp.pressure.low_free_space_min_age_seconds`, default 1h) and reports `pressure_effective_min_age_seconds`. Whenever the free-space floor is breached, regardless of trigger, the effective pressure min age is `min(base, low-space)`. Please preserve this and its tests while completing disk-pressure owner delegation.

[2026-09-14T20:44:42Z · sase-zw.8.land] LANDING AUDIT at main 00acd607f / core 3566872 (v0.34.28), 2026-09-14: read this epic, all six children and every note/close reason, linked remaining-work plan, original disk/sharing plans, prior parent audit and .6 acceptance artifact; reviewed actual main/Rust owners and six main/five core epic commits plus subsequent main/core changes. NOT COMPLETE. Durable audit: file:explicit:1b136cd32d914b18447bed0a. Snapshot creation succeeded; automatic attachment failed on the dirty hidden plans clone (existing sase-10y), so preserve the clone and use this explicit reference.

ISOLATED REPRODUCTIONS on installed v0.34.28, no live deletion: missing proc store and malformed not-json store each delete a stale valid runtime directory (removed=1); run retention follows an in-root symlink ancestor and deletes its real target; an empty referenced run is counted protected=1 yet removed by the shard pass (three directories); artifact apply errors and proc step exit_code=1 both yield CLI exit 0; ordinary-age scratch preview selects 512-byte payload but reports zero bytes; configured 7d handoff is displayed as 3d; pressure chop samples only sase_home then forwards that filesystem's free bytes to managed_tmp; healthy dirty borrower reuse against replacement primary lacking borrowed objects returns successfully after alternate rewrite, then git status fails with 128. All fixture paths were disposable; local retained state was untouched.

Other unfinished approved requirements: actionable deduplicated hourly artifact preview is absent (logs only); per-root rather than whole-pass inventory budgets, eager listings and unbounded effects remain; missing owners silently disappear, primary versus recipe targets and overlaps are not fully accounted; owner orchestration still scrapes workspace output and shared inventory policy remains Python; new launch-exit scratch cleanup duplicates liveness/deletion policy. These are epic work, not standalone follow-ups. Integration must preserve 59dde523c/core 5ea49f5 low-space configurable 1h age for free_space and size_and_free_space, exact launch assignment/handoff/live protection, df5fbbacc test scratch owner, core continuation/forced-reuse contracts, and cc91c0aa4 plus 6b4bee96d Git-identity/detector fixes. Epic #1 and .5 #1/#2 coordination are addressed in current Rust/config/tests; preserve them.

VERIFICATION: just install succeeded, core and LSP 0.34.28; managed tmp wire2 and proc/runtime/run/pressure wire1 checked. 101 focused retention/proc/workspace tests passed in 13.23s. 46 targeted tests passed in 27.17s, including exact terminology, Justfile incremental, shell writer checks plus artifact directory operation audit, artifact capture policy and global leak detector. Existing green tests omit the reproduced safety cases. No new full-suite success claimed; rerun just check-full through sase_monitor only after the repairs. Prior .6 41665 passed bodies then detector failure is not a passing combined gate.

EVERY PROPOSED FOLLOW-UP: .2 #1 orphan logs -> used sase_new_task, independently measured 459 canonical rowless logs / 60063 bytes / oldest31.9d against103 durable rows, searched every task status/type and last-week sweep, reviewed active epics; created large ready bug sase-115. No independent causal active epic or duplicate found; no log deletion authorized. .2 #2 historical eight-check bundle -> decline duplicate blanket task, now-passing exact checks/audit and existing historical tasks/green-CI ownership supersede it. .4 #1 Symvision/artifact/clippy bundle -> decline new blanket task; monitor repairs and artifact checks now pass, core signature uses context struct and .6 reports complete core success; new safety gaps remain here. .6 #1 post-fix monitored full rerun -> required epic acceptance, not independent task, retained in child plan. All completion/evidence notes were read; manually closed .1/.3 caveats are not accepted as proof of missing tests.

No --epic-symbol entries for sase-zw.8. Prepared remaining-only child epic sase_plan_disk_retention_final_safety.md with parent_bead sase-zw.8, seven explicitly serial medium phases: scratch results/liveness, proc protection coverage, run protection/preview, borrower reuse, bounded inventory, filesystem pressure/results, combined acceptance. Ran validate --explain, edited schema/phase descriptions and exact audit ref, then revalidated successfully with zero warnings. Submission is the required planning handoff. Keep this epic and its linked plan in progress. No closure/post-close Symvision/ancestor plan status actions are child phases. Resumed landing must review new notes/descendants and drift, pass combined verification and readiness/symbol checks, close normally, then recheck directly parented plan sase-zw.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-zw.8.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-zw.8.land.md) | [sase-zw.8](sase-zw.8.md) | 0 |
