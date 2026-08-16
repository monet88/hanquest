# 05 - Xây dựng PK bot end-to-end

**GitHub Issue:** [#6](https://github.com/monet88/hanquest/issues/6)

**Parent:** [#1 – Xây dựng nền tảng học tiếng Trung Hán Quest AI](https://github.com/monet88/hanquest/issues/1)

**What to build:** Deliver user story 55 as a complete single-player PK challenge against a deterministic bot, reusing the canonical identity and reward sources established by the learning loop.

The learner must understand the rules and difficulty, complete a versioned question set, see reproducible scoring and receive any eligible reward exactly once. Private rooms, matchmaking and realtime reconnect behavior remain outside this ticket.

**Blocked by:** [#3 – Hoàn thiện vòng học HSK từ bài học đến tiến độ](https://github.com/monet88/hanquest/issues/3)

**Status:** ready-for-agent

## Acceptance criteria

- [ ] The PK entry clearly identifies bot mode, exposes the scoring rules and lets the learner select at least two seeded difficulty profiles.
- [ ] The seed contains 20 versioned questions suitable for deterministic selection and replayable test fixtures.
- [ ] The same question-set version, learner answers and difficulty produce the same bot behavior, score events and final result.
- [ ] The experience has explicit waiting, countdown, active and completed states with useful cancellation and error handling; it does not present private-room or matchmaking controls as functional.
- [ ] Match records retain match type, participant identity, question-set version, start time, bounded answers, score events and final result.
- [ ] The trusted operation owns score and final-result calculation; the browser cannot directly mutate scores or rewards.
- [ ] Refresh, replay, repeated answer submission or repeated completion cannot duplicate score events, XP transactions or PK rewards.
- [ ] Match data is visible only to its participant under RLS, and PK operations are rate-limited.
- [ ] The completed result reads canonical XP/streak values consistently with the header and dashboard.
- [ ] Contract tests prove deterministic and idempotent bot scoring, and Playwright covers a full bot match at both canonical viewports.
