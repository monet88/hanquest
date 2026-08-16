# 03 - Chuyển guest thành tài khoản lâu dài

**GitHub Issue:** [#4](https://github.com/monet88/hanquest/issues/4)

**Parent:** [#1 – Xây dựng nền tảng học tiếng Trung Hán Quest AI](https://github.com/monet88/hanquest/issues/1)

**What to build:** Deliver user stories 10–12 by allowing a learner to turn guest progress into a permanent email/password or Google account without losing or duplicating eligible learning data.

The slice must support both linking a new permanent identity to the current anonymous user and signing into an existing permanent account through a privileged, idempotent merge operation.

**Blocked by:** [#3 – Hoàn thiện vòng học HSK từ bài học đến tiến độ](https://github.com/monet88/hanquest/issues/3)

**Status:** ready-for-agent

## Acceptance criteria

- [ ] Email/password registration, verification where configured, login, logout and recoverable error states work in the controlled environment.
- [ ] Google authentication exposes correct callback behavior for local, preview and production environments without using personal credentials in CI.
- [ ] Converting a new anonymous user links the verified email/password or Google identity while preserving the same eligible progress.
- [ ] Signing into an existing permanent account invokes a server-side privileged merge and never exposes service-role credentials to the browser.
- [ ] Permanent profile fields win; lesson completion keeps the best score and earliest valid completion.
- [ ] XP transactions are unioned by idempotency key, streak is recomputed from unique qualifying events, and SRS keeps the most advanced valid schedule per content item.
- [ ] Attempts with distinct attempt IDs remain distinct; replaying or retrying the merge does not duplicate attempts, XP, streak, completion or SRS work.
- [ ] The is_anonymous claim is enforced so anonymous users cannot export profiles, enter public leaderboards or access permanent-user-only realtime capabilities.
- [ ] RLS negative tests prove users cannot read or mutate another account's private profile or learning data before, during or after merge.
- [ ] Playwright covers guest progress surviving both email conversion and the Google callback seam, including a repeated merge request.
