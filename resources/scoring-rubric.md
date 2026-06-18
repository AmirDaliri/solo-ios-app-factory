# Scoring Rubric

Score every serious candidate 1–10 on all ten criteria. Use the anchors below so scores are comparable across ideas and sessions. When unsure between two scores, pick the lower one — this skill errs toward killing, not building.

**An idea may not be scored until its competitor scan is done** (see kill-rules.md). For a senior iOS dev who can build almost anything, the binding constraint is never effort — it is whether the competition is genuinely weak and the wedge genuinely defensible. The weights and gates below are deliberately stacked on those two axes, because that is what actually kills solo apps.

## How to compute

1. Run the **competitor scan** first. No scan → no score → kill.
2. Score each criterion 1–10 using its anchors. Apply the **caps** where they bind.
3. Apply the **hard gates**. Any gate failure kills the idea outright; do not bother with the weighted total.
4. Multiply each surviving score by its weight, sum, and divide by the max (220) → **weighted score out of 100**.
5. Map to a decision band.

### Hard gates (auto-kill, override the total)
- **Pain intensity ≤ 3** → kill. Painless = no purchase, no retention.
- **Willingness to pay ≤ 3** → kill. "Nice to have" and "free-only" don't fund a solo business.
- **MVP buildability ≤ 3** → kill for *this* user as a solo 2–4 week build.
- **Competition weakness ≤ 3** → kill. Healthy, loved, funded, or actively-updated incumbents own the space. A senior dev's time is too expensive to fight them without a real edge.
- **Differentiation ≤ 3** → kill. No wedge beyond taste means no reason to switch and nothing to defend.

Two new gates (competition, differentiation) were added because in practice these — not pain or buildability — are what sink solo apps in saturated categories. If an idea dies on one of these, say so and move on; do not reshape it three times to sneak it past.

### Caps (ceilings, not kills)
- **Differentiation is capped at 4** if the only edge is positioning, taste, price, privacy, or "local-first" that a competent team copies in one sprint. A 7+ requires a *structural* moat (proprietary/accumulated data, an on-device capability rivals can't match, a real integration, switching cost, or format lock-in). Privacy and local-first are good defaults, not a moat.
- **Willingness to pay is capped at 5** if demand is unverified [ASSUMPTION] — no paid precedent and no search evidence. Unverified demand is also auto-named as the riskiest assumption.
- **Competition weakness is capped at 5** if you did not actually search the App Store / web for rivals. You cannot call competition weak from your armchair.

## Criteria, weights, and anchors

Max raw per criterion = 10. Weighted max = sum(weight × 10) = 220.

### 1. Pain intensity — weight ×3
How much the target actually hurts without this.
- **1–3**: Mild annoyance, easily ignored or worked around.
- **4–6**: Real friction, recurring grumble, current workaround is clumsy.
- **7–8**: Painful enough that people already pay, hack spreadsheets, or complain publicly.
- **9–10**: Acute, repeated pain with money or time visibly on the line.

### 2. Frequency of use — weight ×2
How often the moment of need recurs.
- **1–3**: Once or a few times ever (one-shot, then deleted).
- **4–6**: Occasional — monthly-ish, event-driven.
- **7–8**: Weekly, tied to a routine.
- **9–10**: Daily or near-daily, habitual.

### 3. Willingness to pay — weight ×3 *(capped at 5 if unverified)*
Evidence that the target spends money on this class of problem.
- **1–3**: Expects it free; no paid precedent.
- **4–6**: Might pay a little; weak or indirect precedent.
- **7–8**: Comparable paid apps/tools exist and sell.
- **9–10**: People already pay real money (subscriptions, pricey alternatives, or it touches their income).

### 4. Competition weakness — weight ×3 *(capped at 5 without a real search)*
How exploitable the incumbents are. This is now triple-weighted and gated — treat it as the make-or-break criterion.
- **1–3**: Strong, loved, funded, or freshly-updated incumbents own the keywords. (Auto-kill.)
- **4–5**: Crowded; a competent incumbent exists and is maintained, even if not beloved.
- **6–7**: Few players, several stale or abandoned, visible review complaints, no clear leader.
- **8–10**: Verified gap — existing options are bad, absent on iOS, or a frustrated audience has fallen back to spreadsheets/notebooks.

### 5. Differentiation — weight ×3 *(capped at 4 if positioning-only)*
The defensible wedge. Positioning is not a moat.
- **1–3**: Me-too; only difference is taste. (Auto-kill.)
- **4**: A positioning angle only — privacy, local-first, price, cleaner UI. Copyable in a sprint; cannot score higher.
- **5–6**: A genuinely sharp angle incumbents structurally won't or can't follow (their cloud/community model, their bloat, their business model).
- **7–8**: A structural wedge that's hard to copy quickly — on-device capability, integration, format, or workflow lock-in.
- **9–10**: Compounding structural edge (accumulating proprietary data, a moat that widens with use).

### 6. MVP buildability — weight ×2
Shippable by this solo senior iOS dev in 2–4 weeks.
- **1–3**: Needs a team, months, or unproven tech.
- **4–6**: 4–6 weeks solo; tight.
- **7–8**: 2–4 weeks solo with known frameworks.
- **9–10**: ~2 weeks; standard SwiftUI + local storage + StoreKit.

### 7. Backend simplicity — weight ×1
Lower infra = better for a solo operator.
- **1–3**: Heavy backend, servers, sync infra, ops burden.
- **4–6**: Light backend or a managed BaaS dependency.
- **7–8**: Minimal — maybe one API or push.
- **9–10**: Fully local-first / on-device; zero servers to run.

### 8. App Store search potential — weight ×2
Can it be discovered organically via search?
- **1–3**: No clear keywords, or keywords owned by giants.
- **4–6**: Some keyword room but contested.
- **7–8**: Identifiable mid-volume keywords with weak competition.
- **9–10**: Clear, searchable intent keywords with rankable competition.

### 9. Retention potential — weight ×2
Reason to come back (or to keep paying).
- **1–3**: Use once, delete. No recurring hook.
- **4–6**: Returns occasionally; retention is fragile.
- **7–8**: Built-in recurring trigger or accumulating value (data, history, habit).
- **9–10**: Strong lock-in via accumulated data, routine, or ongoing utility.

### 10. Founder fit (senior iOS solo dev) — weight ×1
Match to this specific builder. Note: domain ignorance (building for a hobby/profession the founder doesn't live in) caps this at 6 and raises validation importance.
- **1–3**: Outside core skills (heavy ML training, web app, hardware).
- **4–6**: Doable but stretches into unfamiliar territory, or the founder is a tourist in the domain.
- **7–8**: Squarely in Swift/SwiftUI/iOS wheelhouse.
- **9–10**: Plays directly to native iOS, on-device, App Store strengths *and* a domain the founder understands.

## Decision bands (weighted score /100)

- **≥ 80** — Build candidate. Proceed to the full pipeline.
- **70–79** — Conditional. Build *only* after both: (a) the riskiest assumption is cheaply validated, and (b) a specific, hard-to-fix incumbent weakness is confirmed. Until then it is a no.
- **55–69** — Weak. Default no. The wedge isn't there; reshape into a sharper vertical or move on.
- **< 55** — Kill.

The build threshold was raised from 75 to 80 and the bands compressed because the previous version let merely-okay ideas read as "promising." An 80 now requires genuinely weak competition *and* a structural wedge, not a high score propped up by easy buildability and proven WTP.

## Verdict classification (four buckets)

After scoring, every candidate resolves to exactly one verdict:

- **Build-ready** — Lane A score **≥80** with strong evidence. Proceed to the full plan.
- **Research-only** — Lane A score **70–79**, *or* an execution-play candidate whose teardown leaves a material assumption unresolved. Validate the riskiest assumption before building.
- **Execution-play candidate** — **Lane B** activated: Competition-weakness is **4–5** (fragmented field, no dominant loved incumbent), there are repeated severe user complaints, and all eight Lane B conditions hold (see kill-rules.md / SKILL.md). Routed to the mandatory **Execution Teardown**, whose verdict from scan/desk research can only be **research-only or killed** — never build-ready. It reaches build-ready only by passing the real-world promotion gate (SKILL.md §4c).
- **Killed** — structural weakness, a dominant incumbent (Comp▼ ≤3), weak WTP, poor retention, no wedge, or no feasible 2–4 week MVP.

**The gates, weights, caps, and 80 threshold above are unchanged by the execution-play lane.** An execution-play candidate is still scored normally; the score is simply *informational* for it, because the rubric's Differentiation cap deliberately undercounts execution edges. An execution-play candidate is **never** build-ready from the scan or desk teardown — at most research-only. The single path from a sub-80 Lane B idea to build-ready is the **execution-play promotion gate** (SKILL.md §4c): manual top-3 teardown + repeated complaints confirmed + 10–15 real user reactions + a clear willingness-to-pay signal + the narrow workflow proven beatable in 2–4 weeks. All five, or it stays research-only. A Comp▼ ≤3 idea gate-kills and can never enter Lane B.

## Winner discipline

If the top-scoring idea is **below 80**, the Winner section must say **"No winner"** outright. Never label a sub-80 idea a "winner" or "conditional winner." A sub-80 idea may be mentioned only as the **"closest miss — still a no,"** stating its point gap to 80 and the single criterion that capped it. The user can build anything; do not tempt him toward a flawed idea by dressing it up.

## Presentation

Show a compact table with all ten raw scores, any caps applied, the weighted total /100, gate status (PASS / KILLED + which gate), and the band. Never round a low score up to be kind.
