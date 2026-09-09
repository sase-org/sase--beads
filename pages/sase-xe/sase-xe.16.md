# Bead: sase-xe.16 — Complete remote dispatch - target bootstrap, tailnet discovery, canonical machine init, and the live Apollo proof

[Bead Pages](../README.md) / [sase-xe](README.md) / sase-xe.16

**Status:** ◐ in_progress · **Type:** ▸ plan · **Tier:** epic
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.08c](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.08c.md) · **Assignee:** `sase-xe.16.land`
**Created:** 2026-09-08 10:21:31 EDT
**Plan:** [202609/remote\_dispatch\_completion.md](https://github.com/sase-org/sase--plans/blob/main/202609/remote_dispatch_completion.md)

<!-- sase:links:start -->

## Links

| Relation | Artifact | Why |
| --- | --- | --- |
| implemented-by | [plan:202609/remote_dispatch_completion.md][1] | derived from the plan's `bead_id:` frontmatter field |
| related | file:explicit:831bc61700629257ea205a90 | attached via sase artifact create --bead |

[1]: https://github.com/sase-org/sase--plans/blob/main/202609/remote_dispatch_completion.md

<!-- sase:links:end -->

## Description

Finish the remote dispatch feature epic sase-xe shipped incompletely, ending with a live proof: a normally installed Apollo that Athena discovers over the tailnet, explicitly enrolls through `sase machine init` after a target-local `sase machine bootstrap`, and immediately manages - launching 1-3 remote agents with %dispatch:apollo and driving them from Athena's TUI. Also lands the acceptance-hardening remainder (provider isolation, offline fleet fixture, PNG snapshots, fleet benches) reconciled from the sase-xe landing's stashed child plan draft.

## Notes

[2026-09-09T01:12:56Z · sase-xe.16.land] LANDING AUDIT (sase-xe.16.land): reviewed the epic record/plan, all ten children and every note, core commit 9adb209, Python phase commits 5015d76e9/18b0a91a2/ace9e2cd4/f081f2303/338e3b349/8c4f8fd22/6ae983ddc/7ee2e5177/890660e25, actual gateway/PyO3, discovery/provider runtime, machine setup, Fleet projection/fixtures/visuals/bench/fault tests and docs. Compared all commits from first child commit 8c4f8fd22 through HEAD 890660e25 plus core post-9adb209 history; fetched origin/master equals HEAD. Queue commits c235300c6/0770357cd already preserve dispatch/queue incompatibility; usage/model-alias/leader-key, sidecar/artifact-link and stitch changes do not complete the gaps below.

NOT COMPLETE: reopened sase-xe.16.10, whose own note #7 says operational proof is blocked and #8 is an automatic close. Fresh SSH confirms Apollo loopback gateway healthy/protocol 1 but No serve config. No live enrollment, dispatch launch, TUI management, or restart-resilience evidence exists yet. Ancestor sase-xe reopened with the phase and has a blocker note.

REPRODUCED GAPS: injecting a detailed tailnet_status_unavailable error into the actual candidates adapter makes canonical init return exit 0, errors=(), nothing_to_enroll=True; mocked submit_proc failure makes _run_scoped_chezmoi_apply call untracked apply_chezmoi and return success; unrelated service health {status:ok,service:unrelated} classifies unknown rather than unrelated/incompatible. Source inspection also confirms add/repair bypass activation, repair deletes the old local credential before applied-overlay verification, TUI setup guidance still teaches direct add, pure discovery/reconciliation/family-promotion decisions live in Python contrary to the core boundary, and the purported host-hang and instance-reuse tests return prewritten mocked decisions. Fleet stress scenarios share one delayed static response rather than exercising transitions during navigation. These are remaining epic work, captured in the child draft sase_plan_remote_dispatch_landing_remaining.md with parent_bead=sase-xe.16.

VERIFICATION SO FAR: just install completed (core/LSP 0.32.50); 74 focused setup/dispatch/Fleet/federation/mutation/keymap tests passed in 2.33s; 89 provider/bootstrap/doctor/parser/Fleet-model/directive contract+parity tests passed in 4.73s. No complete landing gate is claimed. Sase-y9 received the successful pin/parity evidence required by phase .2. Epic-symbol checks for both sase-xe.16 and sase-xe report none; rerun at real close.

ALL PROPOSED FOLLOW-UP OUTCOMES: .2#1 and .7#1 missing research -> both exact audited reads succeed after sanctioned research-sidecar open, so content restoration declined; independent missing-clone classification evidence corroborates existing sase-u3 (+1). .5#1 keymap failure -> current whole module passed, ref:plan o/O correctly expect no grouping, no new task without reproduction. .6#1 direct-add activation -> absorbed into remaining epic integration, extended to repair because canonical recovery depends on it. .8#1 Grok probe -> existing sase-y5 note #3, supplementary note names proposing bead; clan-summary -> +1 on existing sase-xb naming .8 and its historical unchanged rerun. .10#6 eligibility helper -> already fixed by 5b8ee98ce, new task declined. Non-proposal .9 verification failures remain already-recorded sase-j7#66 and sase-xb phase +1. No distinct new task was warranted; /sase_new_task searches and recent-task/active-epic sweeps completed.

HANDOFF: validate/revalidate/propose only the remaining-work child. Original .10 stays open until the new live phase supplies every original acceptance item, then close it normally on evidence before parent readiness. Parent closure, post-close symvision, linked plan status done and full ancestor audit stay with landing, not child implementation phases. Never force a successful close.

[2026-09-09T01:28:02Z · sase-xe.16.land--1] MONITOR COMPLETION / PLAN HANDOFF: kfbm6fy1sy53 completed just check at 2026-09-09T01:19:57Z with exit 0 in 4m46s. Every formatting/lint/SASE/committed-plan lane passed, including Symvision; scoped tests selected 64/3648 files and passed. The advisory published core-floor probe reported stale_actionable (0.32.46 lacks 13 bindings released in 0.32.47-0.32.50), not a failed just check lane. Exact retained evidence is file:explicit:831bc61700629257ea205a90. /sase_new_task searches across statuses, recent-task sweep, active-epic/child inspection and source/commit checks routed the warning to active causal epics sase-yh (six retry/origin bindings) and sase-yj (three queue bindings); the same coordinated floor bump covers four eligibility bindings introduced by dd1f829c2. Older tasks sase-wg/sase-xn cover distinct already-exceeded floors and were not corroborated; no duplicate task created. This adds no remote-dispatch implementation scope: its prepared setup-integration phase already requires a published floor carrying all consumed bindings. Scratch plan sase_plan_remote_dispatch_landing_remaining.md remains unchanged, parent_bead=sase-xe.16, five medium phases with explicit dependencies; validate --explain and revalidate both pass with zero warnings. Tracked source tree is clean. Submit this child plan now; original live phase .10 and both epics remain open. Preserve all original proposal dispositions in note #1 plus this warning outcome for the eventual close note; no full landing gate or operational completion is claimed.

[2026-09-09T16:19:52Z · sase-xe.16.11.land] LANDING BLOCKER from sase-xe.16.11.land: The child remains incomplete. Its fault phase .11.3 and live phase .11.5 were reopened after source verification: the healthy-host fixture actually fast-fails, and live receipt/visibility/output/stop were explicitly unmet before automatic commit closure. Mandatory Fleet Rust-contract, count/freshness/pagination, trust and launch-recovery gaps are recorded in .11 note LANDING AUDIT / REMAINING WORK and planned in sase_plan_remote_dispatch_contract_and_acceptance.md (parent_bead=sase-xe.16.11). Original .16.10 stays open. No ancestor or plan status has been marked done; resume only after complete child evidence and normal phase readiness checks.

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-xe.16.land](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.sase-xe.16.land.md) | [sase-xe.16](sase-xe.16.md) | 0 |
