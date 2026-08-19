# Tennis Upset Detector Skill

A reusable research skill for **ruthlessly auditing tennis betting favorites for upset risk**.

Instead of asking only _“Who is more likely to win?”_, this skill asks a stricter question:

> **Is this favorite clean enough to survive a ruthless upset audit?**

The goal is not to predict every match correctly or build large accumulators. The goal is to start with a card of bookmaker favorites or supplied tennis tips, actively search for reasons each favorite could lose, eliminate the risky ones, and reduce the card to the **fewest, cleanest selections**.

The full methodology lives in [`SKILL.md`](./SKILL.md).

## Why this exists

Short odds do not automatically mean low upset risk.

A 1.20–1.30 favorite can still be a poor accumulator leg because of factors the headline price or tip narrative may hide, such as:

- a recent injury, retirement, illness, or unresolved niggle
- accumulated fatigue from deep tournament runs or long three-set matches
- a dangerous underdog already playing above their ranking
- a misleading ranking or class gap
- poor or uncomfortable head-to-head history
- a surface narrative that does not match recent results
- qualifying rhythm, travel, scheduling, or tournament-stage volatility
- recent wins that were much shakier than the final result suggests
- stale, cherry-picked, or incomplete reasoning in the supplied tip

The skill is intentionally adversarial: **try to disprove the favorite before trusting the favorite**.

## Core audit criteria

The default workflow uses the same ten criteria defined in `SKILL.md`:

1. **Current form** — recent results and the quality of opponents faced.
2. **Injury / fitness uncertainty** — retirements, withdrawals, medical timeouts, illness, cramping, pain, or recent return from injury.
3. **Recent workload and fatigue** — court time, long matches, deep runs, travel, and limited rest.
4. **Surface fit** — whether the current surface genuinely favors the selected player.
5. **Head-to-head and matchup history** — especially evidence that the underdog has already solved the matchup.
6. **Ranking and class gap** — used as context, not as the prediction itself.
7. **Dangerous underdog form** — recent upsets, qualifying runs, titles, deep runs, and evidence the ranking understates current level.
8. **Tournament context, travel, qualifying, and scheduling** — including court acclimatization and Challenger-stage volatility.
9. **Recent vulnerability despite winning** — repeated deciding sets, saved match points, frequent deficits, or narrow escapes.
10. **Audit of the supplied tip itself** — fact-check stale rankings, omitted injuries, misleading H2H, cherry-picked records, and exaggerated class gaps.

## What the skill intentionally does not do

The default process **does not add extra statistical layers simply because they sound sophisticated**.

In particular, it does not default to:

- first-serve or second-serve models
- serve/return probability models
- ace-rate or double-fault models
- break-point conversion models
- point-by-point physics
- custom match simulations

Those can be explored separately if explicitly requested, but they are **not part of the baseline upset-detector workflow**.

This constraint is deliberate: the purpose of the repository is to preserve a repeatable process rather than continually changing the methodology.

## Workflow

### 1. Verify the card

Confirm the match, tournament, round, date, status, and current player context. If a match has already started or finished, say so immediately.

### 2. Fast-triage the full card

For large cards, eliminate obviously unattractive profiles early and identify:

- near-coin-flip matches
- thin-data qualifiers
- volatile Challenger matches
- obvious injury or fatigue concerns
- dangerous underdogs
- suspicious short-priced favorites
- matches that could realistically survive into the final shortlist

Triage is an efficiency mechanism. It must **not** be described later as equal-depth research on every match.

### 3. Deep-research survivors and suspicious favorites

Manually investigate the matches that could realistically make the final shortlist, plus deceptive short-priced favorites that deserve extra scrutiny.

### 4. Build the strongest upset case

For every candidate favorite, answer:

> **What is the most credible way this favorite loses today?**

If that case is materially convincing, remove the match.

### 5. Ruthlessly cut

Use three broad verdicts:

- **STRONG KEEP** — no major red flag found and relatively few credible upset paths.
- **KEEP / BORDERLINE** — favorite is preferred, but meaningful risk remains.
- **REMOVE / HARD REMOVE** — the upset pathway is too credible for a safety-focused accumulator.

Do not preserve matches merely to reach a target number of selections.

### 6. Rank the survivors

Prefer a shortlist of **1–3 selections**, then identify when appropriate:

- safest single
- preferred double
- optional third choice

If only one match genuinely survives, recommend one. If none survive, say so.

## Preferred research sources

The skill prioritizes current sources in roughly this order:

1. Official ATP / WTA / ITF / tournament sources
2. Official player or tournament statements
3. Reuters and other reputable sports reporting
4. Reliable live-score and statistical databases for results, schedules, rankings, and H2H
5. Preview sites only as supporting context

Because injuries, rankings, schedules, withdrawals, and current form change quickly, the workflow assumes **fresh online research for every audit**.

## Expected output

A typical result starts with a compact table:

| Match | Supplied pick | Verdict | Upset danger | Main reason |
|---|---|---|---|---|
| Player A vs Player B | Player A | STRONG KEEP | Low–medium | Clean current profile; no major red flag found |
| Player C vs Player D | Player C | REMOVE | High | Dangerous underdog + recent fatigue |

Then the analysis explains the most important survivors, deceptive favorites, and misleading tip narratives before finishing with a ruthless final filter:

```text
1. Safest selection
2. Second safest selection
3. Optional third
--- CUT LINE ---
Removed selections
```

The skill should also identify a **best single** and a **preferred double only when two selections genuinely survive**.

## Example prompts

```text
Use the tennis-upset-detector skill on these matches. Research them online, challenge every favorite, eliminate anything with a credible upset pathway, and give me the safest single and double if one genuinely exists.
```

For a bookmaker card:

```text
Use the tennis-upset-detector skill on this card. Treat the bookmaker favorites as hypotheses, not truths. Triage the full card, deeply research the realistic survivors and suspicious short-priced favorites, then ruthlessly cut the risky legs.
```

For exhaustive research instead of triage:

```text
Use the tennis-upset-detector skill, but give every match equal-depth research rather than using the normal triage workflow.
```

## Confidence discipline

This skill is designed to reduce risk, **not eliminate it**.

It should never describe an upset probability as “near zero,” call a bet guaranteed, or treat a previous successful pick as proof that the method cannot fail.

Preferred language includes:

- “strongest profile on the card”
- “cleanest matchup I found”
- “lower upset risk relative to the alternatives”
- “still not risk-free”

If someone asks for the choice they would “bet rent money on,” interpret that as asking for the strongest forced selection — **not as advice to risk money needed for rent, food, bills, or other essentials**.

## Research honesty

If a large card is triaged, be explicit about the research depth.

For example:

> “I screened all 50 matches, deeply researched 10 finalists or suspicious favorites, and did lighter checks on the rest.”

Do not imply that every match received an exhaustive dossier when it did not.

## Repository structure

```text
tennis-upset-detector-skill/
├── README.md
└── SKILL.md
```

- **`SKILL.md`** — canonical instructions for the reusable skill.
- **`README.md`** — human-readable explanation of the methodology, intended use, workflow, and constraints.

## Guiding principle

> **The goal is not to be impressed by favorites. The goal is to eliminate favorites until only the matches remain where, after current online research, the opponent’s credible upset pathway is hardest to articulate.**

---

This repository is a research methodology for evaluating tennis upset risk. It is not a guarantee of betting outcomes and should not be treated as financial advice.