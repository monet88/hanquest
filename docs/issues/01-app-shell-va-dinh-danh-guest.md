# 01 - Khởi tạo app shell và định danh guest

**GitHub Issue:** [#2](https://github.com/monet88/hanquest/issues/2)

**Parent:** [#1 – Xây dựng nền tảng học tiếng Trung Hán Quest AI](https://github.com/monet88/hanquest/issues/1)

**What to build:** Deliver the first usable Hán Quest AI shell for user stories 1–7 and 9: a Vietnamese responsive homepage and onboarding experience, consistent desktop/mobile navigation, complete light/dark themes, canonical XP/streak header state, and a protected Supabase anonymous identity created only when the learner performs the first persistent action.

This slice must be independently demoable without Phase 2 or Phase 3 features appearing functional.

**Blocked by:** None - can start immediately

**Status:** ready-for-agent

## Acceptance criteria

- [ ] The three-slide onboarding can be completed, skipped and revisited; completion remains remembered on later visits.
- [ ] The homepage exposes clear calls to action for HSK, workplace learning and PK while unimplemented later-phase destinations are hidden or visibly marked coming soon.
- [ ] Desktop and mobile expose the same navigation hierarchy at the canonical 1440×900 and 390×844 viewports.
- [ ] Light and dark themes cover the full shell and persist without a flash of the wrong theme.
- [ ] The global header reads XP and streak from the canonical user statistics source and displays valid initial values for a new identity; it does not use fake counters.
- [ ] Browsing alone does not create a guest account; the first persistent action creates one Supabase Anonymous Auth identity and subsequent sessions reuse it.
- [ ] LocalStorage is limited to theme, onboarding, pending offline UI state and the temporary pre-auth handoff token; progress is not treated as canonical there.
- [ ] Anonymous signup is rate-limited and bot-protected, and the 30-day inactive-anonymous cleanup policy is documented and verifiable.
- [ ] Browser tests cover onboarding persistence, shell navigation, theme persistence and anonymous-identity creation at the approved Playwright seam.
- [ ] No service-role key, AI key or private gateway value is exposed to the browser or committed.
