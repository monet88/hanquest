# 04 - Tích hợp AI Mentor và OCR qua custom gateway

**GitHub Issue:** [#5](https://github.com/monet88/hanquest/issues/5)

**Parent:** [#1 – Xây dựng nền tảng học tiếng Trung Hán Quest AI](https://github.com/monet88/hanquest/issues/1)

**What to build:** Deliver user stories 8, 50–53 and 68 as an end-to-end AI Mentor and OCR slice backed by the user's custom OpenAI-compatible gateway through a server-side adapter.

Learners must be able to open the mentor from the current context, choose a persona, receive instructional Chinese responses, submit a supported image for OCR/explanation, and understand every pending, success and failure state without exposing provider secrets or retaining sensitive media by default.

**Blocked by:** [#2 – Khởi tạo app shell và định danh guest](https://github.com/monet88/hanquest/issues/2)

**Status:** ready-for-agent

## Acceptance criteria

- [ ] A floating AI Mentor is reachable from the approved Phase 1 screens without discarding the learner's current context.
- [ ] The three seeded personas and six suggested prompts are available, and relevant normalized answers can include Hanzi, Pinyin, Vietnamese explanation and examples.
- [ ] Phase 1 uses the configured OpenAI-compatible /v1 chat-completions contract through a server-side adapter with separate text and vision model identifiers.
- [ ] No AI base URL, API key, private gateway response body or provider credential is exposed to the browser or committed.
- [ ] Text requests are non-streaming, cancelable, time out after 20 seconds, and retry 429/5xx at most once with jitter while respecting provider retry headers.
- [ ] OCR accepts JPEG, PNG or WebP up to 5 MB, strips EXIF, uses the vision message contract, and times out after 30 seconds.
- [ ] Raw OCR images and captured speaking audio are discarded after analysis unless the learner explicitly chooses a supported save behavior.
- [ ] Provider failures normalize to validation, unauthorized, rate_limited, timeout, unavailable or malformed_response without leaking upstream details.
- [ ] Default configurable quotas enforce 20 text and five vision requests per Supabase identity per hour.
- [ ] The interface supports pending, success, retry, timeout, quota and provider-error states plus copy and capability-aware TTS controls.
- [ ] AI output cannot directly award XP or official scores, and private conversations are owner-readable only under RLS.
- [ ] Deterministic text/vision fixtures pass at the server-adapter test seam, and a credential-gated real-gateway smoke test verifies text, vision, authentication and normalized failures.
