# 06 - Đạt quality gate tích hợp cho Phase 1

**GitHub Issue:** [#7](https://github.com/monet88/hanquest/issues/7)

**Parent:** [#1 – Xây dựng nền tảng học tiếng Trung Hán Quest AI](https://github.com/monet88/hanquest/issues/1)

**What to build:** Deliver user stories 65–67 and the integrated Phase 1 quality gate across the completed shell, learning, account-conversion, AI/OCR and PK bot slices.

This ticket closes only the verification and hardening gaps needed to prove that the complete Phase 1 journey is accessible, responsive, deterministic, secure and performant. It must not expand into Phase 2 or Phase 3 product breadth.

**Blocked by:** [#3 – Hoàn thiện vòng học HSK từ bài học đến tiến độ](https://github.com/monet88/hanquest/issues/3), [#4 – Chuyển guest thành tài khoản lâu dài](https://github.com/monet88/hanquest/issues/4), [#5 – Tích hợp AI Mentor và OCR qua custom gateway](https://github.com/monet88/hanquest/issues/5), [#6 – Xây dựng PK bot end-to-end](https://github.com/monet88/hanquest/issues/6)

**Status:** ready-for-agent

## Acceptance criteria

- [ ] Every Phase 1 route and documented loading, empty, ready and error state is reachable at 1440×900 and 390×844 without console-blocking errors.
- [ ] The complete guest → lesson → quiz → XP/streak → SRS → dashboard → account conversion → AI Mentor/OCR → PK bot journey passes in Chromium at both canonical viewports.
- [ ] A WebKit smoke suite passes for auth shell, navigation, media capability fallbacks and the Phase 1 happy path.
- [ ] Playwright visual baselines cover homepage, onboarding, HSK map, lesson/quiz, SRS, AI Mentor, PK bot and dashboard in light and dark themes at both canonical viewports.
- [ ] Visual baselines are generated only in the pinned CI environment and use deterministic timestamps, avatars and progress fixtures.
- [ ] Automated accessibility checks and manual keyboard, accessible-name, screen-reader-label and contrast review satisfy WCAG 2.2 AA; touch targets and narrow-screen controls remain operable.
- [ ] Slow and failed network states provide skeletons or clear recoverable errors, and noncritical modules/media are lazy-loaded appropriately.
- [ ] Performance gates cover initial shell, homepage and lesson; lab regressions are budgeted and deployed field monitoring is prepared for LCP ≤2.5 s, INP ≤200 ms and CLS ≤0.1 at the 75th percentile.
- [ ] Database tests pass for Phase 1 RLS allow/deny behavior, idempotent rewards, guest-merge conflicts and streak boundaries around midnight in Asia/Ho_Chi_Minh.
- [ ] Replaying, refreshing or double-submitting cannot duplicate lesson completion, XP, streak, SRS updates or PK rewards.
- [ ] Deterministic AI fixtures pass in CI and the credential-gated real-gateway text/vision smoke seam passes in its configured environment without exposing secrets.
- [ ] Required deployment variables and verification steps are documented without credentials or private gateway URLs.
- [ ] Phase 2 and Phase 3 controls are hidden or visibly marked coming soon and do not appear functional.
- [ ] The complete Phase 1 Definition of Done in #1 is checked against evidence before this ticket is closed.
