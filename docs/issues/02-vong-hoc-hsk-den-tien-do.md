# 02 - Hoàn thiện vòng học HSK từ bài học đến tiến độ

**GitHub Issue:** [#3](https://github.com/monet88/hanquest/issues/3)

**Parent:** [#1 – Xây dựng nền tảng học tiếng Trung Hán Quest AI](https://github.com/monet88/hanquest/issues/1)

**What to build:** Deliver the Phase 1 learning loop for user stories 13–20, 48–49 and 59–60: browse the HSK curriculum, complete the seeded lesson and quiz, receive idempotent XP/streak progress, review mistakes through SRS, and see the same canonical state in the header, dashboard and profile.

The complete guest → lesson → quiz → XP/streak → SRS → dashboard journey must be independently demoable on desktop and mobile.

**Blocked by:** [#2 – Khởi tạo app shell và định danh guest](https://github.com/monet88/hanquest/issues/2)

**Status:** ready-for-agent

## Acceptance criteria

- [ ] Learners can switch supported programs, browse HSK 1–6, and use both RPG map and compact list views; unavailable content is clearly labeled rather than simulated.
- [ ] The Phase 1 seed exposes the specified three-node HSK 1 map and the complete representative lesson with 12 vocabulary items, one dialogue and five scored questions.
- [ ] Nodes show completion, rewards and data-defined lock prerequisites, and locked/unlocked behavior remains correct after reload.
- [ ] Lesson content displays Hanzi, Pinyin, Vietnamese meaning, examples and available audio with useful media fallbacks.
- [ ] Quiz answers receive immediate deterministic feedback and explanations.
- [ ] A valid lesson completion is recorded once; refresh, replay and double submission cannot duplicate completion or XP.
- [ ] Streak events use the Asia/Ho_Chi_Minh product-day boundary and cannot be duplicated by replay.
- [ ] Incorrect answers create or update SRS work; due, waiting and mastered states, search, TTS and retry operate using the documented deterministic SM-2-inspired policy.
- [ ] Dashboard and global header derive XP and streak from the same ledger/event sources and remain consistent after reload.
- [ ] Profile editing supports display name, avatar reference, target HSK level and occupation badge without exposing private identity fields.
- [ ] RLS and negative authorization tests prove one identity cannot read or mutate another identity's attempts, progress, XP, streak or SRS data.
- [ ] Playwright covers the complete guest learning loop at both canonical viewports, including idempotency and persistence after reload.
