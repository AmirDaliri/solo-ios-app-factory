# Claude Code Starter Prompt Template

This closes every full run. It is a single, paste-ready prompt the user can drop into Claude Code to scaffold the MVP. Fill the brackets from the proposal, PRD, and architecture sections — do not leave placeholders. Keep it self-contained: someone with no other context should be able to act on it.

---

## Output format (produce this verbatim, filled in)

```
You are helping build the MVP of [App name], a native iOS app, with me — a senior solo iOS developer. Build production-quality, not a toy.

## Product
[One-line description]. Target user: [persona]. Core job: [JTBD].

## Constraints
- Native SwiftUI, iOS [min version]+.
- Modern Swift: async/await, structured concurrency. MVVM[, + Coordinator if used].
- [Local-first / persistence choice]. [Networking stance.] StoreKit 2 for monetization.
- Minimize dependencies; justify any SPM package.
- Clean, maintainable, production-ready. No unnecessary abstraction.

## MVP scope (build only this)
[Numbered in-scope feature list from the PRD, each with its acceptance criterion.]

## Explicitly out of scope
[Out-of-scope list — do not build these.]

## Architecture
[Layer/module breakdown, persistence model, concurrency boundaries, monetization integration — from the architecture section.]

## Data model
[Entities and relationships.]

## Monetization
[Model, free vs paid line, paywall trigger, price.]

## Build order
1. Project scaffold + folder structure + data model.
2. Core loop (the one flow that delivers the value) end to end.
3. Persistence wired and verified (no data loss on relaunch).
4. Paywall + StoreKit 2 entitlement.
5. Onboarding/empty states, permission paths, polish.

## Working agreement
- Start by proposing the project structure and data model, then wait for my OK before generating screens.
- When editing existing code, change only what's necessary — no wholesale rewrites.
- Explain non-obvious tradeoffs in one or two lines; skip the lecture.
- Flag the riskiest part of the build: [riskiest assumption / technical long pole].

Begin with the project structure and data model.
```

---

Notes when filling it:
- Pull every value from the actual run — the prompt should be specific to this app, not generic.
- The "Working agreement" matters: it makes Claude Code propose-then-build and edit surgically, which suits a senior dev who wants control.
- Keep the build order honest to the 2–4 week MVP. If it doesn't fit, the scope above it is wrong.
- **Execution-play (Lane B) adaptation.** If the winner came through the execution-play lane, adapt the prompt so the *one narrow workflow* is unmistakably the priority:
  - In **## Product**, state the single workflow the app wins and the execution promise on it (e.g. "log an entry in under 5 seconds, fully offline, no account").
  - Make **build step 2 (core loop)** that exact workflow, and add an explicit performance/offline acceptance bar for it.
  - Add a line under constraints: **"Do not try to match [incumbent]'s [conceded moat] — out of scope."** Naming what *not* to build protects the window.
  - In the riskiest-part flag, name the execution metric as the thing that must hold (if it doesn't beat the incumbent on that workflow, there is no product).
