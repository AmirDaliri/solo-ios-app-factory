# iOS Technical Architecture Template

Target: modern, native, solo-maintainable. Defaults below — deviate only with a stated reason. Prefer the simplest thing that ships; avoid abstraction the app doesn't yet need.

## Defaults (change only with justification)

- **Min iOS:** latest − 1 (state it; affects available APIs).
- **UI:** SwiftUI-first. UIKit only where SwiftUI genuinely falls short (state it).
- **Concurrency:** async/await + structured concurrency. No completion-handler soup, no Combine unless a stream genuinely needs it.
- **Pattern:** MVVM. Add a Coordinator only if navigation is non-trivial (multiple flows); for a small app, SwiftUI navigation state may be enough — don't add a Coordinator by reflex.
- **Persistence:** local-first. SwiftData (modern, simple) or Core Data (if you need its maturity); UserDefaults only for small prefs; Keychain for secrets.
- **Networking:** none if possible. If needed, a thin async URLSession client — no heavyweight networking dependency for a couple of endpoints.
- **Monetization:** StoreKit 2.
- **Dependencies:** minimize. Every SPM package is a maintenance liability for a solo dev. Justify each one.

## Architecture sketch (fill in)

### Module / layer breakdown
- **App / entry:** app lifecycle, root state, dependency wiring.
- **Features:** one folder per feature, each with its View(s) + ViewModel.
- **Domain:** models and the small business-logic types.
- **Data:** persistence layer + (optional) network client, behind a protocol the ViewModels depend on.
- **Shared:** design system, reusable components, extensions.

### Data flow
One paragraph: View → ViewModel (intent) → Data layer (async) → ViewModel (state) → View. Note where state lives and how it's observed (@Observable / @State / @Environment).

### Persistence model
The entities, their store (SwiftData/Core Data), and migration stance. Confirm: does the app lose data on relaunch? (Must be no.)

### Concurrency & threading
What runs off the main actor, what's @MainActor, and where the boundaries are. Image/file/heavy work off-main.

### Permissions & system integration
Which capabilities (Photos, Camera, Notifications, etc.), the usage-description strings, and graceful denial paths.

### Monetization integration
StoreKit 2 products, the entitlement check, where it's enforced, and offline entitlement behavior.

### Testing stance
What actually gets tested for a solo MVP: the ViewModel logic and the data layer. Don't over-test glue UI. Name the few high-value tests.

### Risk / complexity flags
Anything in the architecture that's the long pole or the part most likely to leak time. Be honest about where the build will hurt.

### Execution-play emphasis (only if this is a Lane B candidate)
If the wedge is an execution advantage, the architecture must be organized to *deliver that advantage*, not just to be tidy. Name how the chosen edge drives technical decisions, e.g.:
- **Faster capture/input** → optimize the entry path for latency: pre-warmed views, minimal taps, no network on the critical path, instant local persist.
- **Better offline** → local-first is non-negotiable; define exactly what works with zero connectivity and how/if it later syncs.
- **Tighter Apple-ecosystem integration** → call out the specific surfaces (Widgets, App Intents/Shortcuts, Apple Watch, Live Activities, Handoff, share extension) that are part of the wedge, not nice-to-haves.
- **Fewer bloated features / one-job focus** → the architecture should make the narrow workflow trivially fast and refuse scope that doesn't serve it.
State which one criterion the architecture is being tuned for; if everything is "balanced," the execution edge probably isn't real.
