# Bead: sase-ru.4 — Measure inherited planner chat value and cost

[Bead Pages](../README.md) / [sase-ru](README.md) / sase-ru.4

**Status:** ✓ closed · **Resolution:** done · **Type:** ↳ phase
**Owner:** `bryanbugyi34@gmail.com` · **Created by:** [bbugyi200.athena.09i](https://github.com/sase-org/sase--agents/blob/main/families/bbugyi200.athena.09i.md) · **Assignee:** `sase-ru.4` · **Size:** medium
**Created:** 2026-08-21 10:44:27 EDT · **Closed:** 2026-08-21 11:05:08 EDT
**Plan:** [202608/open\_feature\_flag\_closeout.md](https://github.com/sase-org/sase--plans/blob/main/202608/open_feature_flag_closeout.md)

## Description

planner_chat_trial: compare paired coder handoffs with and without coder_inherits_planner_chat and produce an evidence-backed product recommendation.

## Notes

[2026-08-21T15:04:37Z · sase-ru.4] Measured matched Off vs On coder handoffs from stored artifacts and production sase xprompt expand. Recommendation: abandon coder_inherits_planner_chat; keep plan-file-only. Full matrix on sase-qe and file:explicit:0b50eb32321cc48fb8e48e7b. Sampled: sase-m7 (small, fork 1627B), 09f (small, 1834B), sase-lk (medium, 1580B), sase-js.7 (medium, 1931B), 04l.f1 (noisy, 58704B), 001.f1 (noisy, 168938B). All Off followup_prompt.md; all sampled Off coders completed.

[2026-08-21T15:05:08Z · sase-ru.4] Verified matched Off vs On coder handoffs from stored artifacts plus production sase xprompt expand. 0/676 followup prompts used #fork. Planner chats are 10-line stubs for 811/820 pairs so #fork does not carry planner reasoning. Typical On add-on is ~400-480 tokens of duplication; noisy feedback planners inject 15k-42k tokens of prior family/coder context (001.f1 fork=168938B, 18.7x plan) while Off still completed. Recommend abandon beta / keep plan-file-only; matrix on sase-qe and file:explicit:0b50eb32321cc48fb8e48e7b. No leftover --epic-symbol entries.

## References

- file:explicit:0b50eb32321cc48fb8e48e7b

## Dependencies

- **Blocks:** [sase-ru.9](sase-ru.9.md) ✓ · ⧖ 2026-08-21

## Agents

| Agent | Bead | Commits |
|---|---|---:|
| [bbugyi200.athena.sase-ru.4](https://github.com/sase-org/sase--agents/blob/main/agents/bbugyi200.athena.sase-ru.4/README.md) | [sase-ru.4](sase-ru.4.md) | 1 |

## Commits

| Repo | Commit | Subject | Bead | Committed |
|---|---|---|---|---|
| sase--plans | [`sase--plans@661460d`](https://github.com/sase-org/sase--plans/commit/661460d5bd91ec44d7fe7d820476b98e7e60c000) | docs(plan): link planner-chat trial evidence to the flag closeout plan | [sase-ru.4](sase-ru.4.md) | 2026-08-21 11:07:36 EDT |
