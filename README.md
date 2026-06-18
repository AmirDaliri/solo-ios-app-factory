# solo-ios-app-factory

A Claude Skill that turns vague "what should I build next" energy into a defensible build decision for a **solo senior iOS developer**. It generates app opportunities, kills the weak ones aggressively, scores the survivors against an anchored rubric, picks a winner, and produces the full plan — proposal, MVP scope, PRD, App Store positioning, monetization, validation plan, iOS architecture, 30-day roadmap, and a paste-ready Claude Code starter prompt.

It is deliberately harsh. It does not flatter, it does not invent market demand, and it recommends *not* building when nothing clears the bar. Every candidate resolves to one of four verdicts — **build-ready, research-only, execution-play candidate, or killed** — via two lanes: a strict **gap-hunting** default and a narrow **execution-play** exception (see below).

## What it does

- **Discovery** — give it a domain (or nothing) and it produces scored candidates and a winner.
- **Single-idea audit** — paste one idea and it scores it, applies kill rules, and either kills it or builds out the full plan.
- **Artifact** — ask for just a PRD, architecture, roadmap, monetization plan, positioning, or Claude Code prompt and it produces that one thing.

## Folder structure

```
solo-ios-app-factory/
├── SKILL.md                                  # orchestrator: persona, modes, pipeline
├── README.md
└── resources/
    ├── scoring-rubric.md                     # anchored 1–10 scoring, weights, decision bands, hard gates
    ├── kill-rules.md                         # instant-disqualifier gate + full rejection ruleset
    ├── product-proposal-template.md
    ├── prd-template.md
    ├── ios-architecture-template.md
    └── claude-code-starter-template.md
```

## Install

**Claude.ai / Claude app (Skills):** Settings → Capabilities/Skills → upload the packaged `solo-ios-app-factory.skill` file (or the zipped folder, depending on your client's importer).

**Claude Code:** drop the `solo-ios-app-factory/` folder into your skills directory (e.g. `~/.claude/skills/solo-ios-app-factory/`). It loads automatically; `SKILL.md` frontmatter handles triggering.

**Manual / other:** keep the folder intact. `SKILL.md` references the files in `resources/` by relative path, so the structure must stay as-is.

## Use

Just talk to it. It triggers on things like:

- "Give me iOS app ideas I could actually ship solo."
- "Is this idea any good: [idea]?"
- "Score this against your rubric."
- "Write the PRD / architecture / Claude Code prompt for it."
- "What should I build next?"

For discovery, anchoring it helps but isn't required:

> Give me solo-buildable iOS app ideas around [domain/itch]. Local-first, App Store search-driven, monetizable.

## How scoring works

Each serious idea is scored 1–10 on ten criteria — pain intensity, frequency, willingness to pay, competition weakness, differentiation, MVP buildability, backend simplicity, App Store search potential, retention, and founder fit — then weighted to a score out of 100 with decision bands. Competition weakness and differentiation are triple-weighted, because for a developer who can build anything those are the criteria that actually decide success. **Five hard gates** (pain, willingness to pay, buildability, competition weakness, differentiation) auto-kill at ≤3 regardless of total, and three caps prevent gaming: unverified demand can't exceed WTP 5, an un-scanned market can't exceed competition-weakness 5, and a positioning-only edge (privacy, local-first, price, UI) can't exceed differentiation 4. The build threshold is **80/100**; below it, the verdict is "no winner." See `resources/scoring-rubric.md`.

## How kill rules work

Ideas are filtered *before* scoring through an instant-disqualifier gate: network effects, marketplace liquidity, enterprise sales, heavy backend, generic AI wrappers, saturated commodity categories without a structural wedge, unclear monetization, weak retention, regulated/claim-dependent ideas, "interesting but not painful," and — the catch-all that does most of the work — an **unverified or copyable wedge**. Anything that isn't killed on sight gets a **mandatory competitor scan** (name the top incumbents, their traction and pricing, and a specific weakness they can't easily fix) before it's allowed a score. Most ideas die here, by design. See `resources/kill-rules.md`.

## Two lanes and four verdicts

Every candidate resolves to one verdict through one of two lanes:

- **Lane A — gap-hunting (default).** The strict path. An idea earns **build-ready** only by scoring ≥80, which needs genuinely weak competition *and* a structural wedge. **70–79** is **research-only**; below that is **killed**.
- **Lane B — execution-play (narrow exception).** For markets that aren't empty but are fragmented, mediocre, outdated, bloated, overpriced, or poorly executed — no dominant loved incumbent (competition-weakness 4–5), several weak players, **repeated severe user complaints**. Such an idea is classified **execution-play candidate** and routed to a mandatory **Execution Teardown** (download and tear apart the top 3; identify the one narrow workflow the MVP can win 10x; name what can't be beaten). The teardown — not the score — produces the terminal verdict.

Lane B **never weakens Lane A**: a dominant incumbent still gate-kills (competition-weakness ≤3) and is never eligible. And Lane B is not a loophole — if the only wedge is vague "cleaner UI," if winning needs out-spending incumbents on marketing, if the MVP can't clearly win one narrow workflow, if complaints aren't repeated/severe, or if a domain-tourist user can't reach the audience, it's killed or downgraded.

## Design intent

Built for one person who can ship native iOS fast and wants the truth, not encouragement. Every demand or competition claim is tagged `[FACT]` (verifiable, ideally searched) or `[ASSUMPTION]`. Every run names the single riskiest assumption and the cheapest way to test it before writing code. Every full run ends with a Claude Code implementation prompt.

## Tuning it

The behavior lives in editable Markdown:
- Loosen or tighten the bar → edit weights, anchors, and decision bands in `scoring-rubric.md`.
- Add/remove disqualifiers → edit `kill-rules.md`.
- Change deliverable shape → edit the templates in `resources/`.
- Change persona, modes, or pipeline order → edit `SKILL.md`.
