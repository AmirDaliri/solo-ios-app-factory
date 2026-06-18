# Kill Rules

Apply these before scoring. The point is to delete most ideas quickly so attention goes only to survivors. When an idea hits a rule, state the rule and move on — do not argue the idea back to life. Reshaping a killed idea two or three times to slip it past the gate is itself a failure mode; if it took that much rescuing, it's a kill.

## Mandatory competitor scan (run before the gate)

For any idea that isn't killed by rules 1–5 on sight, you **must** actually search the App Store / web before it earns a score. The scan must produce, in writing:

- the **top 1–3 incumbents** by name;
- their **visible traction** (rating + rough review count, last-update recency) and **pricing**;
- the **single most exploitable weakness** — and whether it's something the incumbent is *unlikely or structurally unable to fix*.

If you cannot name a specific incumbent weakness from a real scan, the idea is killed under Rule 11. "Competition feels weak" without evidence is not a finding. A scan that turns up a healthy, maintained, or loved incumbent (e.g. a 4.5★+ app with thousands of ratings, updated this year) is grounds to kill unless the wedge is structural — not merely cleaner UI, privacy, or local-first.

## Instant-disqualifier gate

If any of these is true, the idea is dead. No score, no rescue.

1. **Requires network effects** — value depends on other users already being there (social graphs, "it's empty until everyone joins"). A solo dev cannot manufacture a cold-start network.
2. **Requires marketplace liquidity** — needs both supply and demand sides present at once (buyers + sellers, renters + listers). Chicken-and-egg you can't bootstrap alone.
3. **Requires enterprise sales** — value is gated behind procurement, contracts, demos, or a sales motion. Not a solo App Store play.
4. **Requires heavy backend infrastructure** — real-time sync fabric, large media pipelines, always-on servers, ops you'd have to run and pay for indefinitely.
5. **Generic AI wrapper** — a thin shell over a chat model with no proprietary data, workflow, or on-device edge. Trivially cloned, and you don't own the moat.
6. **Saturated commodity with no wedge** — generic habit tracker, todo, journal, notes, budget, recipe, or fitness app *without a pre-stated, specific, structural wedge*. These categories are graveyards. The wedge must be named in the same breath as the idea, and "nicer/cleaner/private" does not count.
7. **Unclear monetization** — no honest path to subscription, lifetime unlock, paid upfront, or freemium. "We'll figure out money later" = killed.
8. **Weak retention** — used once and deleted, with no recurring trigger or accumulating value. One-shot novelty.
9. **Regulated / claim-dependent** — depends on legal, medical, financial, or other regulated advice or claims (diagnosis, dosage, tax/legal guidance, investment advice). Liability and App Store review risk outweigh a solo upside.
10. **Interesting but not painful** — clever, fun to build, demos well, but nobody hurts without it. The most seductive kill of all. Kill it harder for being tempting.
11. **Unverified or copyable wedge** — after the competitor scan, you cannot name a specific incumbent weakness the incumbent won't fix, OR the only edge is positioning (privacy, local-first, price, cleaner UI) that a competent team copies in a sprint. No verified, defensible wedge = no product. This is the rule that catches "legitimate category, healthy incumbents, no real angle."

## How a wedge survives rule 6

The saturated-category rule is not "never touch these categories" — it's "the bar is brutal." A wedge survives only if it is **structural** and at least one of:

- **A narrow, underserved audience** the generic apps ignore (e.g. not "budget app" but a budgeting tool for a specific irregular-income profession).
- **A format or input the incumbents lack** (on-device scan, voice, a specific import/export, a workflow they can't bolt on without breaking their model).
- **A capability rivals can't match** — an on-device model, an integration, or accumulating data that compounds.
- **A verified keyword + competition gap** you can actually rank for, confirmed by the scan.

Privacy, local-first, lower price, and nicer design are good defaults but are **not** wedges — they're copyable in a sprint. If that's all you have, it does not survive. Restate it as a Rule 11 kill.

## Soft flags (don't auto-kill, but lower the score)

These don't end the idea, but they should drag the relevant rubric criterion down and be named explicitly:

- Discovery depends entirely on paid acquisition (no organic App Store search path) → tank **App Store search potential**.
- Differentiation is only aesthetic → tank **Differentiation**.
- "People probably want this" with zero evidence → treat demand as **[ASSUMPTION]**, raise it as the riskiest assumption, and lower **Willingness to pay** until validated.
- Needs a content library you must create and maintain → lower **Backend simplicity** and **MVP buildability**.
- Platform-policy fragile (rides on a single API/ToS that can change) → name the dependency risk.

## Output format for rejected ideas

For each killed idea: `Idea name — Rule N (short rule name): one-line specific reason.` Keep it terse. The user wants the body count and the cause of death, not a eulogy.
