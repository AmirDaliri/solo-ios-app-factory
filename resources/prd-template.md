# PRD Template

A solo-builder PRD: enough to build from, no ceremony. If a section would be empty, write "N/A — why" rather than padding.

## [App name] — Product Requirements

### 1. Problem & goal
- **Problem statement.** One paragraph. Who, when, what hurts.
- **Goal.** What success looks like in plain terms.
- **Non-goals.** What this explicitly does not do (protect the scope).

### 2. Target user & primary job-to-be-done
- Primary persona (one).
- The core job: "When [situation], I want to [action], so I can [outcome]."

### 3. Success metrics
- **Activation:** the first-session action that signals the user "got it".
- **Retention:** the recurring action that signals value (tie to the retention hook).
- **Monetization:** trial→paid or free→paid conversion signal.
- Keep to 3–5 metrics. No vanity metrics.

### 4. MVP feature list (in scope)
Numbered, each with a one-line acceptance criterion. This list must be buildable solo in 2–4 weeks. If it isn't, cut here.

### 5. Out of scope (v2+)
The honest parking lot. Everything tempting that does not ship in v1.

### 6. User flows
The 2–3 critical flows as short step lists (first run / onboarding, the core loop, the paywall moment).

### 7. Data model (high level)
The few entities the app stores and their key relationships. Note local-first vs any sync.

### 8. Monetization in-product
Where the paywall sits, what's free vs paid, the trigger, and the price. Reference the monetization section.

### 9. Edge cases & failure states
Empty states, permission denials (Photos/Notifications/etc.), offline behavior, large data, migration. The boring stuff that decides review ratings.

### 10. Risks & open questions
The riskiest assumption restated, plus anything unresolved. Mark each [FACT]/[ASSUMPTION].

### 11. Release criteria
The checklist that must be true to submit: core loop works, paywall works, no data loss on relaunch, privacy strings present, screenshots/keywords ready.

### 12. Execution-play focus (only if this is a Lane B candidate)
If the idea came through the execution-play lane, the MVP is not a smaller clone of the incumbents — it is the **one narrow workflow** done dramatically better. State:
- **The workflow you win.** The single job the MVP beats incumbents on; everything in section 4 (in-scope) must serve it.
- **The execution metric.** The measurable promise on that workflow (e.g. "log an entry in <5 s vs the incumbent's ~20 s", "works fully offline", "no account required"). This is the activation/retention signal that matters.
- **The switch test.** What proves a user would drop incumbent X for this on that workflow — the bar the teardown's validation step must clear.
- **Out of scope, loudly.** The incumbent features you are deliberately *not* matching (the moat you conceded). Listing them protects the 2–4 week window.
