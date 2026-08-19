---
name: tennis-upset-detector
description: Ruthlessly audit tennis betting tips and bookmaker favorites for upset risk using current online research. Use this skill when the user provides tennis matches, tips, bookmaker favorites, or a card and wants risky selections eliminated, the safest singles identified, or a small double shortlisted.
---

# Tennis Upset Detector

## Purpose

Identify tennis favorites that are most vulnerable to an upset and eliminate them aggressively. The goal is NOT to predict every winner and NOT to maximize the number of selections. The goal is to reduce a card to the fewest, cleanest favorite profiles after trying hard to disprove each one.

A player can be the more likely winner and still be a bad accumulator leg. Always distinguish:

- "Who is more likely to win?"
- "Is this favorite safe enough to survive a ruthless upset audit?"

The second question is the one this skill optimizes for.

## Required inputs

Minimum required input:

- one or more tennis matchups
- the supplied favorite or pick for each matchup

Optional inputs:

- bookmaker odds
- tournament and round
- date
- supplied tip narrative or reasoning

If optional information is missing, verify it online where practical. Do not invent missing context.

## Core philosophy

Do not trust the supplied tip narrative, ranking gap, player fame, or short bookmaker odds on their own. Search for the reasons the favorite could lose.

The correct mindset is adversarial:

> For every favorite, try to build the strongest credible upset case for the opponent. If that case is materially convincing, remove the match.

Short odds are not automatically safe. A 1.20-1.30 favorite can still be an automatic cut if there is a hidden injury, fatigue issue, dangerous matchup, recent opponent heater, or other material red flag.

Do not force a double. If only one selection survives, recommend one. If none survive, say so.

## The proven audit criteria

Use the following criteria. Do not add new analytical layers unless the user explicitly asks for them.

### 1. Current form

Check the player's most recent matches, not just season win-loss totals.

Look for:

- quality wins
- poor losses
- repeated three-set struggles
- recent straight-set dominance
- whether recent results are improving or deteriorating

Always consider the quality of opponents faced. A five-match winning streak against weak opposition is not equivalent to beating top-level players.

### 2. Injury, retirement, niggle, or fitness uncertainty

Search specifically for:

- recent retirements
- withdrawals
- medical timeouts
- reported injuries
- illness
- cramping
- player comments about pain or physical limitations
- recent return from injury

A meaningful unresolved physical concern is usually enough to remove a favorite from a safety-focused accumulator, even if the player is still favored by the market.

Do not overstate the evidence. "No current public injury report found" does NOT mean "confirmed fully fit." Only describe a player as fully fit when reliable current evidence supports that claim.

Do not infer the cause of a retirement, withdrawal, or poor performance unless a reliable source reports the cause. If the cause is unknown, say it is unknown.

### 3. Recent workload and fatigue

Check:

- matches played in the previous 7-10 days
- long three-set matches
- deep runs in the previous tournament
- back-to-back tournament scheduling
- recent finals or semifinals
- travel between tournaments
- limited rest days

A player can be in excellent form and still be a poor safety pick because they have accumulated too much court time.

### 4. Surface fit

Determine whether the current surface genuinely favors the selected player.

Use:

- recent performance on the same surface
- career tendencies where relevant
- whether the underdog is being unfairly dismissed as a "clay specialist" or "hard-court specialist"
- whether current tournament conditions suit both players rather than only the favorite

Do not accept generic surface narratives without checking actual recent results.

### 5. Head-to-head and matchup history

Check official or reliable H2H data.

Pay particular attention when:

- the underdog has already beaten the favorite
- the underdog won the most recent meeting
- the underdog has repeatedly kept matches close
- the supposed favorite has struggled with this exact opponent

Do not overweight very old H2H results if the players' levels have changed dramatically, but do not ignore them when they reveal a plausible matchup problem.

### 6. Ranking and class gap

Use current rankings as context, not as the prediction itself.

Ask:

- Is this actually a meaningful class mismatch?
- Is the underdog's ranking lagging behind current form?
- Is a tip portraying a near-equal matchup as if it were elite player vs journeyman?

A Top-15 vs Top-10 match is not a safety mismatch merely because one player is on a hotter run.

### 7. Dangerous underdog form

Research the opponent as seriously as the favorite.

Look for:

- recent wins over seeded or top-ranked players
- successful qualifying runs
- multiple matches already won at the same venue
- recent titles or deep runs
- strong performances hidden by a low ranking
- signs that the opponent is currently playing above their ranking

A favorite should be removed when the underdog has demonstrated the level required to produce the upset.

### 8. Tournament context, travel, qualifying, and scheduling

Check:

- whether one player came through qualifying
- whether one player has had a first-round bye and may lack court rhythm
- whether a qualifier is already fully adapted to conditions
- scheduling after a long previous match
- tournament stage
- Challenger final or semifinal volatility
- recent travel and turnaround time

These factors do not automatically decide the match, but they can expose hidden risk.

### 9. Recent vulnerability despite winning

Do not read only the W/L column.

Check whether the favorite:

- repeatedly fell behind before recovering
- saved match points
- needed multiple deciding sets
- required an opponent retirement
- barely survived lower-ranked players

A winning streak can hide instability.

### 10. Audit the supplied tip itself

Apply this criterion only when a supplied tip narrative or reasoning exists.

Fact-check the narrative line by line where practical.

Look for:

- stale rankings
- misleading surface claims
- omitted H2H results
- omitted injuries or fatigue
- cherry-picked records
- understating the opponent's recent wins
- calling a retirement "precautionary" without evidence
- presenting a close matchup as a class gulf

If the tip's framing is materially misleading, downgrade confidence aggressively.

## Explicit exclusions

Do NOT introduce serve-return modeling, first-serve percentage models, second-serve models, break-point conversion models, ace rates, double-fault rates, point-by-point physics, or custom statistical simulations as part of the default workflow.

Those were explored separately and are intentionally NOT part of this skill.

Only use such metrics if the user explicitly asks for them in a particular audit.

Do not add extra criteria merely because they sound sophisticated. Preserve the workflow above.

## Evidence discipline

Every material claim that affects a KEEP or REMOVE decision should be supported by current, reliable evidence where practical.

If reliable current information cannot be found for a criterion:

- mark that criterion as unknown or unverified
- lower confidence where the missing information matters
- do not fill the gap from memory, assumption, or inference

Distinguish clearly between:

- source-confirmed facts
- reasonable inference from confirmed facts
- information that could not be verified

Never convert lack of evidence into evidence of absence.

## Research process

### Step 1: Verify the card

Before analysis, verify:

- the match exists
- tournament and round
- correct date
- whether the match has already started or finished
- current player ranking/status where relevant

If a match has already finished, state that immediately and do not present it as a prospective pick.

### Step 2: Fast triage the entire card

For a large card, do not spend equal time on every match initially.

Quickly identify:

- obvious near-coin-flips
- doubles
- thin-data qualifying matches
- highly volatile Challenger matches
- obvious injury/fatigue flags
- favorites facing dangerous opponents
- short-priced favorites that deserve special scrutiny
- matches that could realistically survive into the final shortlist

The purpose of triage is efficiency, not pretending every match received equal research depth.

### Step 3: Deep-research the survivors and suspicious favorites

Manually research the most plausible final selections and the deceptive short-priced favorites.

For each deep audit, investigate all applicable criteria above. Do not invent or force a criterion that does not apply.

If the user explicitly asks for every match to receive equal-depth research, do that instead of triage.

### Step 4: Build the strongest upset case

For each candidate favorite, answer:

> What is the most credible way this favorite loses today?

Examples:

- unresolved injury
- accumulated fatigue
- opponent is already in excellent form at the tournament
- bad or uncomfortable H2H
- favorite recently struggling despite wins
- surface advantage is overstated
- ranking gap is misleading

If the upset case is substantial, cut the match.

### Step 5: Ruthlessly cut

Use three main verdicts:

- STRONG KEEP: no major red flag found and opponent has relatively few credible upset paths
- KEEP / BORDERLINE: favorite is preferred, but there is meaningful risk
- REMOVE / HARD REMOVE: upset pathway is too credible for a safety-focused accumulator

Do not preserve a match merely to reach a target number of legs.

### Step 6: Rank the survivors

Rank remaining selections from safest to most upset-prone.

Prefer a shortlist of 1-3 selections rather than a large accumulator.

When appropriate, identify:

- safest single
- preferred double
- optional third choice

If the second-best selection is materially weaker than the first, say that explicitly.

## Preferred source hierarchy

Prioritize current, trustworthy sources:

1. Official ATP / WTA / ITF / tournament pages
2. Official player or tournament statements where available
3. Reuters and other reputable sports reporting
4. Reliable live-score/statistical databases for H2H, results, schedules, and rankings
5. Preview sites only as supporting context, never as sole evidence for important claims

Search the web every time because injuries, rankings, schedules, results, withdrawals, and current form are time-sensitive.

## Output format

Start with a compact table:

| Match | Supplied pick | Verdict | Upset danger | Main reason |

Then explain the most important matches in depth, especially:

- final survivors
- deceptive short-priced favorites
- tips whose narratives are misleading

End with a ruthless final filter such as:

1. Safest selection
2. Second safest selection
3. Optional third
--- CUT LINE ---
Removed selections

Then give:

- Best single
- Preferred double, only if two selections genuinely survive

## Confidence discipline

Never claim that an upset chance is "near zero" or that a bet is guaranteed.

Do not confuse a successful previous pick with proof that the method cannot fail.

Use language such as:

- strongest profile on the card
- cleanest matchup I found
- lower upset risk relative to the alternatives
- still not risk-free

If the user uses phrases such as "bet your rent money," interpret that as asking for the strongest forced choice, but do not recommend risking money needed for rent, food, bills, or other essentials.

## Large-card honesty rule

If asked how many matches were deeply researched, answer accurately.

For example:

- "I screened all 50 matches, deeply researched 10 finalists/suspicious favorites, and did lighter checks on the rest."

Never imply that every match received an exhaustive dossier if the workflow used triage.

## Final validation checklist

Before returning the final recommendation, verify:

- every match is still prospective unless the user explicitly asked for retrospective analysis
- no injury, retirement, or fitness claim is stronger than the evidence supports
- every STRONG KEEP or KEEP has been challenged with a credible upset case first
- unknown or unverified information is labeled rather than guessed
- no excluded serve-return or custom statistical layer was introduced by default
- no double was forced merely to produce two selections
- the reported research depth is honest

## Key principle to preserve

The goal is not to be impressed by favorites.

The goal is to eliminate favorites until only the matches remain where, after current online research, the opponent's credible upset pathway is hardest to articulate.
