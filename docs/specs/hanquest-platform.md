## Problem Statement

Người học tiếng Trung cần một sản phẩm tiếng Việt có lộ trình rõ ràng, nhiều hình thức luyện tập và động lực sử dụng hằng ngày. Website tham chiếu tại https://service-5s-ti-ng-trung.ai.studio/ thể hiện mô hình phù hợp: kết hợp HSK, tiếng Trung công sở, thi thử, luyện kỹ năng, AI Mentor, SRS và game hóa trong một trải nghiệm thống nhất.

Sản phẩm mới phải giữ cấu trúc trải nghiệm và độ phong phú chức năng nhưng không sao chép thương hiệu, hình ảnh, nội dung có bản quyền hoặc dữ liệu giả gây hiểu nhầm. Nó cần có nhận diện riêng, dữ liệu nhất quán và đặc tả đủ rõ để một agent mới có thể triển khai mà không phải khảo sát lại từ đầu.

Repository hiện là dự án mới. Tại thời điểm viết đặc tả, repository chưa có mã nguồn, kiến trúc ứng dụng hoặc test có thể tái sử dụng; chỉ có cấu hình GitHub Issues làm tracker. Công việc hiện tại chỉ tạo đặc tả, không triển khai mã nguồn.

## Solution

Xây dựng nền tảng học tiếng Trung responsive có tên làm việc **Hán Quest AI**, dùng giao diện tiếng Việt và nội dung học gồm chữ Hán, Pinyin và bản dịch tiếng Việt. Sản phẩm dùng phong cách phiêu lưu RPG, linh vật rồng mực nguyên bản và hệ thống XP, streak, huy hiệu, khóa bài, bảng xếp hạng cùng phần thưởng.

Người dùng có thể thử ngay bằng chế độ khách, đăng ký bằng email/mật khẩu hoặc Google, học nội dung mẫu trong từng nhóm chức năng, lưu tiến độ, ôn lỗi bằng SRS, làm thi thử, luyện nghe/nói/viết, nhận phản hồi AI qua custom OpenAI-compatible gateway và xem thành tích trong dashboard thống nhất.

Triển khai tương lai đi theo vertical slice. Giai đoạn đầu hoàn thành chuỗi đăng nhập → học bài → quiz → XP/streak → SRS → dashboard → AI Mentor/OCR → PK bot. Sau khi chuỗi này ổn định, mở rộng toàn bộ module và cuối cùng bổ sung phòng PK riêng cùng matchmaking realtime.

## User Stories

1. As a new learner, I want a short onboarding tour, so that I understand pronunciation, HSK vocabulary, workplace learning and AI support before starting.
2. As a returning learner, I want onboarding completion remembered, so that the tour does not interrupt every visit.
3. As a learner, I want to skip or revisit onboarding, so that I control the guidance I receive.
4. As a visitor, I want a clear homepage hero and learning calls to action, so that I can choose HSK, workplace Chinese or PK quickly.
5. As a visitor, I want the same navigation hierarchy on desktop and mobile, so that every module remains discoverable.
6. As a learner, I want complete light and dark themes, so that I can learn comfortably in different environments.
7. As a learner, I want current streak and XP visible globally, so that progress feels continuous across modules.
8. As a learner, I want a floating AI Mentor, so that I can ask questions without leaving the current lesson.
9. As a visitor, I want guest mode, so that I can evaluate the product without creating an account.
10. As a learner, I want email/password registration and login, so that my progress is synchronized.
11. As a learner, I want Google login, so that account creation requires fewer steps.
12. As a guest who later registers, I want supported local progress merged idempotently, so that trial activity is not lost or duplicated.
13. As a learner, I want to switch between HSK Standard and textbook-style programs, so that I can follow my preferred curriculum.
14. As a learner, I want to browse HSK levels 1–6, so that I can see the full progression even when only representative lessons are seeded initially.
15. As a learner, I want RPG map and compact list views, so that I can choose a motivational or efficient presentation.
16. As a learner, I want nodes to show rewards, completion and lock conditions, so that the next action is obvious.
17. As a learner, I want lessons with Hanzi, Pinyin, Vietnamese meaning, examples and audio, so that multiple learning modes reinforce one another.
18. As a learner, I want immediate quiz feedback and explanations, so that errors become learning moments.
19. As a learner, I want successful completion to award XP exactly once, so that rewards cannot be duplicated by refresh or resubmission.
20. As a learner, I want streak changes to follow one documented day boundary, so that the header and dashboard agree.
21. As a learner, I want workplace scenarios filtered by negotiation, meetings, email and interviews, so that practice matches my needs.
22. As a learner, I want a workplace scenario to start with listening and comprehension, so that I understand the conversation before responding.
23. As a learner, I want playback, mute, speed, loop, Hanzi, Pinyin and translation controls, so that listening difficulty is adjustable.
24. As a learner, I want a comprehension gate before the response stage, so that progression proves basic understanding.
25. As a learner, I want to compose either a WeChat-style message or a business email, so that tone matches the channel.
26. As a learner, I want optional sentence suggestions without automatic submission, so that AI does not replace my work.
27. As a learner, I want AI feedback on politeness, business tone and grammar, so that I can improve professional communication.
28. As a learner, I want to choose an HSK 1–6 mock exam, so that I can practise at my target level.
29. As an exam taker, I want a timer, section progress and question matrix, so that I can manage time and unanswered questions.
30. As an exam taker, I want listening playback rules enforced per level, so that the simulation is credible.
31. As an exam taker, I want previous/next navigation without losing answers, so that I can review strategically.
32. As an exam taker, I want a warning before abandoning an unfinished attempt, so that accidental exits do not destroy progress.
33. As an exam taker, I want one immutable attempt to produce section and overall scores, so that results are auditable.
34. As an exam taker, I want a shareable practice-result certificate, so that I can demonstrate progress without implying official HSK certification.
35. As a learner, I want to search and filter grammar by HSK level and category, so that I can find a pattern quickly.
36. As a learner, I want grammar formulas, explanations, examples, translations and audio, so that usage is clear.
37. As a learner, I want to mark grammar as understood and complete basic exercises, so that progress feeds my review plan.
38. As a learner, I want Lego Syntax modes for ordering, fill-in-the-blank and error correction, so that I manipulate sentence structure actively.
39. As a learner, I want semantic blocks, reset and XP-costing hints, so that assistance has a visible game tradeoff.
40. As a beginner, I want an interactive initials/finals table with IPA and example syllables, so that pronunciation components are discoverable.
41. As a beginner, I want tone cards with pitch contours, examples and listening controls, so that Mandarin tones are distinguishable.
42. As a learner, I want a speaking room with reference audio, recording and feedback, so that pronunciation practice is actionable.
43. As a learner, I want a listening room with quiz and dictation modes, so that recognition and transcription are trained separately.
44. As a learner, I want to browse and search 214 radicals by category, so that character composition is easier to understand.
45. As a learner, I want radical stories and composition explanations, so that shapes have memorable associations.
46. As a learner, I want to select Hanzi and practise strokes on configurable grids, so that handwriting can be rehearsed.
47. As a learner, I want stroke order, demo, reset and brush choices, so that writing supports instruction and practice.
48. As a learner, I want incorrect answers to enter an SRS notebook, so that mistakes are reviewed rather than forgotten.
49. As a learner, I want SRS items grouped as due, waiting or mastered with search, TTS and retry, so that review is efficient.
50. As a learner, I want AI Mentor personas for classical explanation, Gen Z coaching and workplace advice, so that tone fits the question.
51. As a learner, I want AI answers to include Hanzi, Pinyin, Vietnamese explanation and examples when relevant, so that responses are instructional.
52. As a learner, I want to upload or capture an image for OCR, so that printed Chinese can be explained.
53. As a learner, I want to copy or listen to AI responses and see pending, retry, timeout and quota states, so that provider failures remain understandable.
54. As a learner, I want karaoke with lyrics, Pinyin, translation, playback speed and line practice, so that music supports pronunciation.
55. As a learner, I want to challenge a deterministic bot with visible rules, so that PK is available and feels fair without another player.
56. As an authenticated learner in a later phase, I want private PK rooms with shareable codes, so that I can challenge a friend.
57. As an authenticated learner in a later phase, I want matchmaking with timeout and cancellation, so that I can find an opponent safely.
58. As a realtime player, I want reconnect, forfeit and server-authoritative timing rules, so that network interruptions do not corrupt matches.
59. As a learner, I want one dashboard for XP, level, streak, rank, HSK target, SRS and course progress, so that statistics share one source of truth.
60. As a learner, I want to edit my display name, HSK target, occupation badge and avatar, so that my profile reflects my goals.
61. As a learner, I want leaderboard filters by HSK level, so that comparison remains relevant.
62. As a learner, I want achievements and reward chests unlocked from recorded events, so that rewards are reproducible across screens.
63. As a learner, I want 9:16 story and certificate-style exports, so that I can share achievements without exposing private data.
64. As a visitor, I want legal, support and real social links in the footer, so that the product is complete without fake live counters.
65. As a keyboard or assistive-technology user, I want semantic controls, focus states, labels and sufficient contrast, so that the app works without a mouse.
66. As a mobile learner, I want touch targets, menus, media controls and exercises adapted to a narrow viewport, so that features are not desktop-only.
67. As a learner on a slow connection, I want skeletons, lazy-loaded modules and clear network errors, so that loading remains understandable.
68. As a privacy-conscious learner, I want OCR images and speaking audio discarded after analysis unless saved explicitly, so that sensitive material is not retained.

## Implementation Decisions

### Product identity and interface

- Use the working brand **Hán Quest AI** with an original ink-dragon mascot. The name remains configurable and is not trademark-cleared.
- Preserve the motivational learning model, not the protected identity of the reference. Do not reuse the 5S name, logo, photographs, copy, social links, audio or proprietary learning content.
- Use a red-to-amber primary gradient, dark slate neutrals, light surfaces and restrained gold accents. Recommended anchors are red 600, amber 600 and slate 900 with accessible light/dark variants.
- Use a system UI font stack for Vietnamese and a CJK-capable fallback such as Noto Sans SC for Chinese.
- Use a sticky header, grouped desktop navigation, mobile drawer, XP/streak indicator, auth entry point, floating AI Mentor and structured footer.
- Use 12–16 px rounded surfaces, clear focus rings, restrained shadows and short motion. Respect reduced-motion settings.
- Implement dark mode from shared semantic tokens across every module. Do not reproduce the reference site's incomplete theme.
- Use original AI-generated or commissioned visuals and audio subject to human review.

### Application architecture

- Use React, Vite, TypeScript and Tailwind CSS.
- Use explicit client-side routes for deep-linkable modules inside one cohesive SPA shell.
- Organize by domains: identity, curriculum, assessments, SRS, gamification, AI, media practice, PK and reporting.
- Use a server-state library such as TanStack Query. Keep transient UI state local and prevent duplicate XP/profile state in components.
- Deploy the frontend and server-side AI proxy on Vercel.
- Use Supabase for Auth, PostgreSQL, Storage and later Realtime. Row Level Security is mandatory for user-owned data.
- Keep content separate from progress so seed material can expand without migrating learner state.
- Lazy-load major modules and media; provide responsive images and defer non-critical audio.

### Authentication and identity

- Support guest, email/password and Google authentication.
- Guest activity uses a generated local identity. Registration merges eligible records through an idempotent server operation.
- Configure Google OAuth callbacks separately for local, preview and production environments.
- Never expose Supabase service-role or AI gateway secrets to the browser.
- Profile fields include display name, avatar reference, target HSK level, occupation badge, locale and onboarding state.

### Core data and consistency

- Curriculum entities include programs, levels, units, lessons, lesson blocks, vocabulary, grammar, exercises, answer choices and media.
- Progress entities include attempts, completion records, XP transactions, streak events, achievements, unlocks and SRS schedules.
- XP is ledger-based; header, dashboard, leaderboard and rewards derive from one transaction source.
- Streaks are event-based with one documented timezone policy. Replays cannot duplicate daily or completion rewards.
- SRS records store source content, due time, interval, difficulty/ease, attempt count and mastery. Use a deterministic SM-2-inspired policy.
- Exam definitions are immutable and separate from timed attempts, answers, section scores and proof records.
- AI storage is minimal. Raw OCR images and speaking audio are ephemeral by default.
- PK records include match type, participants, question-set version, server start time, answers, score events, result and disconnect/forfeit state.

### Learning and assessment

- Seed at least one high-quality, self-authored example for every major module. The UI may show the full HSK 1–6 structure, but unavailable content must be labeled clearly.
- Lesson unlocks come from data-defined prerequisites and XP rules.
- Exercise scoring and rewards use idempotent operations.
- Workplace Simulator has two stages: listening/comprehension, then channel-aware writing with AI feedback.
- Mock exams preserve answers, enforce timers and warn before abandoning unfinished work.
- Certificates must say they are Hán Quest AI practice results, not official HSK credentials.
- Lego Syntax supports ordering, fill-in-the-blank and error correction with optional XP-costing hints.
- Speaking feedback is educational, not certified phoneme assessment. Unsupported browsers receive a manual/text fallback.
- Karaoke must disclose whether scoring is timing/text-based or AI-assisted and cannot use random scores.

### AI, OCR and media contracts

- Integrate the custom OpenAI-compatible gateway only through a server-side adapter.
- Configure `AI_BASE_URL`, `AI_API_KEY`, `AI_TEXT_MODEL` and `AI_VISION_MODEL` as deployment variables; never commit real values.
- Text requests support chat messages, system instructions, bounded output and normalized provider errors.
- Vision requests support image plus instruction and return structured OCR/explanation output.
- Validate media type and size before transmission and strip unnecessary metadata where practical.
- Apply timeouts, cancellation, rate limits and per-user quotas at the server boundary.
- Use MediaRecorder for recording and browser speech synthesis for basic TTS with capability detection and fallbacks.
- AI grading returns criteria-level feedback and suggestions. AI output cannot directly award XP or official scores.

### Gamification and delivery phases

- **Phase 1 — Vertical slice:** responsive shell, original homepage/onboarding, full theme, guest/email/Google auth, one HSK path and lesson, quiz, XP/streak, SRS, dashboard/profile, AI Mentor text/vision and PK bot.
- **Phase 2 — Module breadth:** workplace simulator, HSK mock exams, grammar/basic exercises/Lego Syntax, Pinyin/tones, speaking/listening, radicals, Hanzi writing, karaoke, certificate/story export and representative content.
- **Phase 3 — Realtime:** private PK rooms, matchmaking, reconnect/forfeit behavior, realtime leaderboard hardening and small-demo abuse controls.
- Phase 1 leaderboards use real stored values; never display fabricated online users, visitors or learner identities.
- Realtime rules define join timeout, answer timeout, reconnect window, cancellation, forfeit and duplicate-event handling.
- Each phase must satisfy its browser-level acceptance tests before breadth is added.

### Security, privacy and observability

- Apply Row Level Security to every user-owned Supabase table and bucket.
- Validate user input at the server boundary; sanitize AI/Markdown output and prevent arbitrary HTML execution.
- Store secrets only in deployment configuration and document non-secret variable names.
- Rate-limit auth-sensitive, AI, OCR, export and PK operations.
- Do not log raw images, recordings, tokens or full prompts containing user data.
- Use structured error categories for authentication, database, media, AI provider and realtime failures.
- Analytics, if enabled, must be consent-aware and cannot fabricate live-user statistics.

## Testing Decisions

The approved primary seam is Playwright end-to-end testing through the browser-visible application boundary. Tests use an isolated Supabase test project or Supabase local environment and exercise the same routes and domain operations as the deployed app.

Run E2E tests at representative desktop and mobile viewports. They must prove:

- onboarding completes, skips and remains remembered;
- guest mode works and eligible progress survives registration merge;
- email auth works in a controlled environment and Google auth exposes correct callback behavior without real personal credentials in CI;
- a lesson awards XP exactly once, updates streak, creates SRS work and remains consistent after reload;
- locked/unlocked nodes follow configured prerequisites;
- workplace listening, comprehension gate and AI-writing states behave correctly;
- HSK attempts preserve answers, warn on exit, expire and produce deterministic practice results;
- grammar filters, standard exercises and Lego Syntax work with keyboard and touch;
- media modules expose useful fallbacks when browser APIs are unavailable;
- AI text/OCR shows pending, success, timeout, quota and provider-error states;
- dashboard, leaderboard, rewards and exports use consistent data without leaking private fields;
- PK bot scoring is deterministic and idempotent;
- later realtime tests cover room join, answer sync, reconnect, timeout, forfeit and matchmaking cancellation;
- critical flows work on desktop/mobile with keyboard focus, accessible names and automated accessibility checks.

For deterministic E2E, replace the gateway at the server-adapter boundary with controlled text and vision fixtures. A separate credential-gated contract smoke seam calls the real gateway and proves:

- authentication and configured model identifiers are accepted;
- the text model returns a normalized assistant response;
- the vision model accepts a representative image and returns parseable OCR/explanation;
- timeout, invalid credentials, unsupported media and provider errors are normalized without exposing secrets.

There are no prior-art tests in the repository. The repository contained no product code or test configuration when this specification was written.

## Out of Scope

### Initial vertical slice

- Full HSK 1–6 corpus, 5,000-word catalog or hundreds of workplace scenarios.
- Private-room and matchmaking PK; Phase 1 uses a deterministic bot.
- Production-scale load tests, sophisticated anti-cheat and large-community moderation.
- Certified phoneme-level pronunciation assessment.
- Full analytics provider integration beyond a consent-aware event interface.

### Entire product

- Copying the 5S name, logo, people, proprietary text, audio, social links or protected assets.
- A pixel-for-pixel clone presented as the original service.
- Official HSK certification claims.
- Native iOS or Android applications.
- Payment processing, subscriptions and commerce flows.
- Fabricated online-user counts, visitor counts, rankings or testimonials.
- Production launch guarantees, trademark clearance and legal review.
- Source-code implementation in the current To Spec task.

## Further Notes

- The public reference was inspected as a stateful SPA. React/Vite/Tailwind is an inference from root, bundle and CSS patterns, not verified source access.
- The reference has observable inconsistencies: header and dashboard XP disagree, some profile values appear seeded, dark mode is incomplete and the public login control did not react. Treat these as defects to avoid.
- The reference AI Mentor returned a real generated answer in a harmless text test. Camera, microphone, file upload, exam submission, PK-room creation and destructive exit confirmation were not exercised.
- Mobile layout was not visually verified at every reference breakpoint. Build and test an original responsive layout rather than claiming mobile pixel parity.
- Generated visuals must be reviewed for legibility, cultural appropriateness and accidental resemblance to the reference brand.
- Gateway implementation later requires the non-secret base URL shape and text/vision model identifiers. Secrets belong only in deployment configuration.
- The repository is public at specification time. Never commit credentials, private gateway URLs or proprietary datasets.
