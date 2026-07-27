# ⚾ MLB +EV DAILY PRE-ANALYSIS FRAMEWORK
### Date: `[DATE]` | Slate: `[# GAMES]` games | First pitch: `[TIME] ET`

> **Objective:** Identify bets where our projected win probability **exceeds** the sportsbook's implied probability after removing vig. We are not picking winners — we are finding mispriced lines.

---

# 🧠 LIVING MODEL RULES
> These rules are permanent and must be applied to every pick, every day, before any EV calculation is finalized. Rules are added after confirmed losses that reveal a model gap. They never expire unless explicitly superseded by a stronger rule.

---

## RULE 1 — Dual Elite Starter Total Suppression
**Confirmed:** July 21, 2026 · PHI/LAD Over 9 loss · Wheeler CG 14K, 3 total runs
- When **both starters** have a season xFIP **below 3.20**, subtract **1.5 runs** from the projected total before evaluating any Over
- Raise the minimum EV threshold to **+6.0%** for that game's total
- Reduce stake to **Quarter Kelly** regardless of other signals
- This rule applies even if one starter is a regression candidate — the elite arm creates a floor the Over cannot reliably clear

---

## RULE 2 — ERA Unknown Pitcher (Sub-8 MLB Starts)
**Confirmed:** July 21, 2026 · MIL -149 loss · NYM Thornton 2nd start, 4-0 shutout
- Any starter with **fewer than 8 MLB starts** is classified **ERA UNKNOWN**
- Reduce the **opposing team's win probability by 5%** regardless of which side they're on — this applies to favorites AND underdogs
- Recalculate EV at the adjusted probability before qualifying the pick
- At -149, MIL's true implied prob was 59.8% → minus 5% = 54.8% effective → fair line ~-121 → paying -149 for 54.8% is **negative EV** → **pass**
- Rule also applies to pitchers returning from IL with fewer than 3 post-IL starts

---

## RULE 3 — Blended ERA Formula (Rolling 4-Start Weighting)
**Confirmed:** July 21, 2026 · ATL -145 loss · Buehler season road ERA 5.36, last-4 ERA 3.05, pitched to 2ER/6IP
- Calculate every starter's **last-4-start ERA** before each pick
- **Gap < 0.75 vs season ERA:** Use season ERA (no significant trend)
- **Gap 0.75–1.50:** Use **70% season / 30% recent**
- **Gap > 1.50:** Use **45% season / 55% recent** (strong directional trend — weight recent heavily)
- Apply in **both directions**: improving pitchers get credit, declining pitchers get penalized
- Formula: `Blended ERA = (Season ERA × weight) + (Last-4 ERA × weight)`

---

## RULE 4 — No Prior-Game Score Anchoring
**Confirmed:** July 21, 2026 · CLE/MIN Over 8.5 loss · Anchored on Monday's 13-4, Tuesday total was 7
- Prior game run totals are **not a valid input** for the following day's projected total
- **Only valid carry-overs** from prior games: bullpen workload (72hr), confirmed injuries/lineup changes, pitcher velocity trends
- **Blacklisted reasoning phrases** — if these appear in the rationale, remove the input:
  - "they scored a lot yesterday"
  - "both offenses were hot Monday"
  - "carried over from the series opener"
  - "momentum from the blowout"

---

## RULE 5 — Signal Hierarchy (Confirmed Matchup Structure > Market Signals)
**Confirmed:** July 21, 2026 · MIA ML repeat loss · Imai splitter vs MIA RHB lineup confirmed Day 1, bet again Day 2 on sharp handle alone
- Signals are ranked in this order. **Higher tiers override lower tiers:**
  - **TIER 1:** Confirmed structural SP matchup (pitch-type dominance vs specific lineup composition, confirmed by actual game results)
  - **TIER 2:** Starter ERA/xFIP differential (blended, per Rule 3)
  - **TIER 3:** Sharp handle / reverse line movement / market signals
  - **TIER 4:** Momentum, narrative, streak, public sentiment
- A **Tier 3 signal cannot override a confirmed Tier 1 signal** in the same series
- Once a structural SP advantage is confirmed by a real game result, it locks in for all remaining games in that series against that arm

---

## RULE 6 — Weather Adjustment Table (Apply to All Totals)
**Source:** Peer-reviewed research (AMS 2013, 22,215 game dataset) + confirmed Kauffman Stadium Jul 21 miss
- Apply these adjustments to the **projected total** before EV calculation:

| Condition | Adjustment |
|---|---|
| Wind blowing OUT 10+ mph | +0.8 runs |
| Wind blowing OUT 15+ mph | +1.5 runs |
| Wind blowing IN 10+ mph | −0.8 runs |
| Wind blowing IN 15+ mph | −1.5 runs |
| Temperature below 60°F | −1.0 run |
| Temperature below 50°F | −1.8 runs |
| Temperature above 88°F | +0.5 run |
| Humidity > 80% (dense air) | −0.3 runs |
| Coors Field headwind | Flip expected: treat as pitcher's park |
| Kauffman Stadium < 62°F | −1.5 runs (confirmed threshold) |

- Weather **must be checked within 60 minutes of first pitch** — not at pick time hours earlier
- If weather adjustment changes the pick from Over to Under or vice versa, **the pick is a pass**

---

## ACTIVE TEAM INTELLIGENCE FLAGS
> Updated continuously from post-game analyses. Check these before picking any game involving these teams or pitchers.

| Flag | Team/Pitcher | Signal | Severity | Source |
|---|---|---|---|---|
| Rasmussen sinker matchup | TB | Strong lean vs low-contact offenses (bottom-third chase rate) | APPLY | Jul 21 TB 12-2 win |
| Misiorowski home dominance | MIL | Near-lock tier vs sub-.420 road teams — buy early | STRONG | Jul 21 MIL 8-3 win |
| Buehler blended ERA | SD | Use 3.05 (last-4), not 5.36 season — strong improving trend | APPLY | Jul 21 ATL loss |
| Wrobleski road regression | LAD | ERA/xFIP gap >1.00 in road starts → Over lean | WATCH | Jul 21 Wheeler CG |
| Wheeler home Under | PHI | Home starts are strong Under lean vs any top offense | STRONG | Jul 21 3-run CG |
| BOS win streak late-game | BOS | Avoid fading in 1-run late-game scenarios until streak breaks | WATCH | Jul 20-21 BAL losses |
| PIT bullpen strand rate | PIT | Bottom-quartile strand rate → subtract 4% from PIT underdog ML win prob | APPLY | Jul 21 PIT loss |
| Imai splitter vs RHB | HOU | Splitter dominates RHB-heavy lineups — overrides sharp handle in same series | TIER 1 | Jul 20-21 MIA losses |
| TEX home price inflation | TEX | Book routinely overprice TEX home edge vs run differential | WATCH | Jul 20 CWS win |
| ATH debut pitcher buy | ATH | Drake/unproven arms: apply ERA Unknown rule (Rule 2) | APPLY | Jul 20 ATH win |

---

## PRE-PICK CHECKLIST (run for every qualifying bet)
Before any pick is finalized, confirm all boxes clear:

- [ ] Vig removed and true implied probability calculated
- [ ] Blended ERA applied to both starters (Rule 3)
- [ ] ERA Unknown flag checked for both starters (Rule 2)
- [ ] Dual sub-3.20 xFIP check completed (Rule 1)
- [ ] Prior-game anchoring removed from reasoning (Rule 4)
- [ ] Signal hierarchy applied — no Tier 3 overriding Tier 1 (Rule 5)
- [ ] Weather checked and adjustments applied (Rule 6)
- [ ] Active intelligence flags cross-referenced for both teams
- [ ] Lineup confirmed (within 3 hrs of first pitch)
- [ ] EV ≥ +3.0% after all adjustments
- [ ] Confidence ≥ 6/10 after all adjustments
- [ ] Stake sizing determined (Half Kelly default / Quarter Kelly if Rules 1 or 2 triggered)

---

---

## SECTION 1 — MARKET SNAPSHOT

| Sportsbook | Status | Notes |
|---|---|---|
| DraftKings | ✅ Live | Primary reference |
| FanDuel | ✅ Live | Cross-reference |
| BetMGM | ✅ Live | Odds comparison |
| Caesars | ✅ Live | Line movement check |
| ESPN BET | ✅ Live | Public % reference |
| Fanatics | ✅ Live | Best-price shop |

**Opening line timestamp:** `[TIME]`
**Analysis timestamp:** `[TIME]` *(≥3 hrs before first pitch)*
**Lineup confirmation:** ☐ Pending / ✅ Confirmed *(~3–4 hrs before first pitch)*

---

## SECTION 2 — VIG REMOVAL WORKSHEET

Before any probability comparison, strip the bookmaker's margin.

**Formula:**
```
Implied Prob (side A) = |odds_A| / (|odds_A| + |odds_B|)   [for negative odds]
Implied Prob (side B) = 100 / (odds_B + 100)                [for positive odds]
Hold % = (Implied Prob A + Implied Prob B) - 1.00
True Prob A = Implied Prob A / (Implied Prob A + Implied Prob B)
```

**Example:**
```
Team A: -150  →  150/250 = 60.0% implied
Team B: +130  →  100/230 = 43.5% implied
Hold   = 60.0% + 43.5% - 100% = 3.5%
True A = 60.0% / 103.5% = 57.97%
True B = 43.5% / 103.5% = 42.03%
```

> ⚠️ Never compare your model probability directly against the raw implied odds. Always remove the vig first.

---

## SECTION 3 — STARTING PITCHER CHECKLIST

*Complete for every starter on today's slate. Flag any with ⚠️ before including in a recommendation.*

### Pitcher: `[NAME]` — `[TEAM]` vs `[OPP]`

| Metric | Value | League Avg | Flag? |
|---|---|---|---|
| ERA | | ~4.20 | |
| xFIP | | ~4.20 | |
| SIERA | | ~4.20 | |
| ERA vs xFIP gap | | <0.50 ideal | ⚠️ if >1.00 |
| WHIP | | ~1.30 | |
| K% | | ~22% | |
| BB% | | ~8% | |
| K-BB% | | ~14% | |
| SwStr% | | ~11% | |
| GB% | | ~45% | |
| Barrel% allowed | | ~8% | |
| Hard Hit% allowed | | ~36% | |
| Home ERA | | | |
| Away ERA | | | |
| Day ERA | | | |
| Night ERA | | | |
| Last start: IP / ER / K | | | |
| L3 starts avg ERA | | | |
| L10 starts avg ERA | | | |
| Pitch count last start | | <100 ideal | |
| Velo trend (vs season avg) | | ±1 mph normal | ⚠️ if -2+ |
| Pitch mix changes? | ☐ Yes / ☐ No | | |
| Injury history concern? | ☐ Yes / ☐ No | | |

**Pitcher Summary:** `[2-3 sentence assessment]`

---

## SECTION 4 — BULLPEN STATUS REPORT

*Check this within 2 hours of first pitch. Bullpen fatigue is the #1 late-breaking edge.*

### `[TEAM]` Bullpen

| Factor | Value | Threshold | Flag? |
|---|---|---|---|
| Bullpen ERA (season) | | <4.00 good | |
| Bullpen xFIP | | <4.00 good | |
| Bullpen WHIP | | <1.30 good | |
| Pitches thrown last 3 days | | <150 healthy | |
| Pitches thrown last 7 days | | <300 healthy | |
| Back-to-back appearances (key arms) | | 0 ideal | |
| Closer available? | ☐ Yes / ☐ No | | |
| Setup arm available? | ☐ Yes / ☐ No | | |
| Inherited runner strand % | | >75% good | |
| Leverage Index rank | | Top 10 good | |
| Rest days for top 3 arms | | | |

**Bullpen Summary:** `[2-3 sentence assessment]`

---

## SECTION 5 — OFFENSIVE MATCHUP MATRIX

*Rate each team's offense vs today's opposing starter.*

| Metric | `[TEAM A]` | `[TEAM B]` | Edge |
|---|---|---|---|
| wRC+ | | | |
| OPS | | | |
| ISO | | | |
| OBP | | | |
| SLG | | | |
| Hard Hit% | | | |
| Barrel% | | | |
| K% | | | |
| BB% | | | |
| xBA | | | |
| xSLG | | | |
| RISP AVG | | | |
| Home wRC+ | | | |
| Away wRC+ | | | |
| vs LHP wRC+ | | | |
| vs RHP wRC+ | | | |
| Last 7 days OPS | | | |
| Last 14 days wRC+ | | | |

**Platoon advantage:** `[TEAM]` — `[explain]`
**Offensive edge:** `[TEAM]` — `[explain]`

---

## SECTION 6 — LINEUP QUALITY SCAN

*Confirm within 3 hours of first pitch.*

### `[TEAM]` Lineup

| Position | Player | Status | Notes |
|---|---|---|---|
| 1 | | ✅ In / ⚠️ Out | |
| 2 | | | |
| 3 | | | |
| 4 | | | |
| 5 | | | |
| 6 | | | |
| 7 | | | |
| 8 | | | |
| 9 | | | |
| SP | | | |

- **Stars confirmed?** ☐ Yes / ☐ No → `[who is out]`
- **Rest day?** ☐ Yes / ☐ No → `[who]`
- **IL moves today?** ☐ Yes / ☐ No → `[details]`
- **Call-ups?** ☐ Yes / ☐ No → `[details]`
- **Projected lineup WAR:** `[value]`

---

## SECTION 7 — BALLPARK & WEATHER CONDITIONS

*Refresh within 60 minutes of first pitch.*

### Ballpark

| Factor | Value | Impact |
|---|---|---|
| Park run factor | | >105 = hitter friendly |
| Park HR factor | | >110 = hitter friendly |
| Dimensions (LF/CF/RF) | | |
| Surface | ☐ Grass / ☐ Turf | |
| Altitude | | >3,000 ft = ball carries |
| Roof | ☐ Open / ☐ Closed / ☐ N/A | |

### Weather *(update 60 min before first pitch)*

| Factor | Value | Impact threshold |
|---|---|---|
| Wind speed | mph | >10 mph matters |
| Wind direction | | Out = Over; In = Under |
| Temperature | °F | <50°F suppresses offense |
| Humidity | % | High = ball dies |
| Rain probability | % | >30% = delay risk |
| Air density | | High alt / hot = ball flies |

**Weather impact on total:** ☐ Push Over / ☐ Push Under / ☐ Neutral
**Delay risk:** ☐ Low / ☐ Medium / ☐ High

---

## SECTION 8 — UMPIRE REPORT

**HP Umpire:** `[NAME]`

| Metric | Value | vs Average |
|---|---|---|
| Strike zone size (career) | | |
| Runs per game (career) | | |
| Over% (career) | | |
| Home team win% | | |
| Walk rate induced | | |
| K rate induced | | |
| Recent tendencies (last 10) | | |

**Umpire impact on total:** ☐ Push Over / ☐ Push Under / ☐ Neutral
**Umpire impact on favorite:** ☐ Helps / ☐ Hurts / ☐ Neutral

---

## SECTION 9 — TEAM MOMENTUM & SCHEDULE FACTORS

### `[TEAM A]`

| Factor | Value | Flag? |
|---|---|---|
| Last 5 record | | |
| Last 10 record | | |
| Last 30 record | | |
| Current streak | | |
| Run differential L10 | | |
| Cross-country travel? | ☐ Yes / ☐ No | ⚠️ if yes |
| Time zone change? | ☐ Yes / ☐ No | ⚠️ if yes |
| Day game after night game? | ☐ Yes / ☐ No | ⚠️ if yes |
| Rest advantage (days off) | | |
| Series game # | Game `[ ]` of `[ ]` | |
| Getaway game? | ☐ Yes / ☐ No | |
| Pythagorean record | | vs actual |
| BaseRuns record | | vs actual |
| BABIP (luck factor) | | .300 = neutral |
| LOB% | | >75% = may regress |
| Clutch rating | | |

---

## SECTION 10 — SHARP MONEY & MARKET SIGNALS

*This section separates recreational from professional betting action.*

| Signal | `[GAME]` | Reading |
|---|---|---|
| Public bet % (side A) | | |
| Handle % (side A) | | |
| Bet/Handle gap | | >10pts = sharp signal |
| Opening ML | | |
| Current ML | | |
| Line movement direction | | |
| Reverse line movement? | ☐ Yes / ☐ No | |
| Steam move detected? | ☐ Yes / ☐ No | |
| CLV projection | | |
| Best available price | Book: `[ ]` | |

**Sharp signal summary:** `[narrative]`

> 🔑 **Key rule:** When the public heavily backs one side but the line moves the other way, that is reverse line movement — the clearest footprint of sharp money.

---

## SECTION 11 — INJURY & LATE-SCRATCH MONITOR

*Check 90 minutes before first pitch. Recalculate projections if key player scratched.*

| Player | Team | Role | Status | Impact if out |
|---|---|---|---|---|
| | | SP | ☐ In / ⚠️ Out | Recalculate all lines |
| | | Bullpen | ☐ In / ⚠️ Out | Adjust total, run line |
| | | Everyday | ☐ In / ⚠️ Out | Adjust lineup WAR |
| | | Catcher | ☐ In / ⚠️ Out | Adjust framing, defense |

**Manager comments logged?** ☐ Yes / ☐ No
**Last injury report timestamp:** `[TIME]`

---

## SECTION 12 — PROJECTION MODEL OUTPUT

*Complete this section after Sections 1–11 are filled in. This is the model's final verdict.*

### `[AWAY]` @ `[HOME]` — `[TIME] ET`

| Market | Sportsbook Line | My Fair Line | Edge | EV% | Confidence |
|---|---|---|---|---|---|
| Moneyline (Away) | | | | | /10 |
| Moneyline (Home) | | | | | /10 |
| Run Line (Away -1.5) | | | | | /10 |
| Run Line (Home +1.5) | | | | | /10 |
| Total (Over) | | | | | /10 |
| Total (Under) | | | | | /10 |
| F5 ML (Away) | | | | | /10 |
| F5 ML (Home) | | | | | /10 |
| F5 Total (Over) | | | | | /10 |
| F5 Total (Under) | | | | | /10 |
| Away Team Total | | | | | /10 |
| Home Team Total | | | | | /10 |

**Win probability:** Away `[ ]%` · Home `[ ]%`
**Projected score:** Away `[ ]` – Home `[ ]`
**Risk rating:** ☐ Low / ☐ Medium / ☐ High
**Luck factor concern:** ☐ Yes / ☐ No → `[explain]`

---

## SECTION 13 — EV CALCULATION & KELLY CRITERION

**EV Formula:**
```
EV = (Win Probability × Profit per unit) − (Loss Probability × Stake)

Example at +150:
EV = (0.42 × 1.50) − (0.58 × 1.00)
EV = 0.63 − 0.58 = +0.05 → +5.0% EV
```

**Kelly Criterion:**
```
Kelly % = (bp - q) / b
  b = decimal odds - 1
  p = your win probability
  q = 1 - p

Example: +150 odds, 42% win probability
  b = 1.50, p = 0.42, q = 0.58
  Kelly = ((1.50 × 0.42) - 0.58) / 1.50
  Kelly = (0.63 - 0.58) / 1.50 = 3.3%
```

> ⚠️ **Never bet full Kelly.** Default to Half Kelly for recreational bankrolls, Quarter Kelly for aggressive risk management. Only bet when EV ≥ +3.0%.

| Bet | Odds | Win Prob | EV% | Full Kelly | Half Kelly | Quarter Kelly |
|---|---|---|---|---|---|---|
| | | | | | | |
| | | | | | | |
| | | | | | | |

---

## SECTION 14 — PROJECTION CONSENSUS CHECK

*Compare your model against publicly available projections. Explain any major divergence.*

| Source | Projected Winner | Win Prob | Total |
|---|---|---|---|
| **My Model** | | | |
| FanGraphs Steamer | | | |
| THE BAT | | | |
| ZiPS | | | |
| Dimers | | | |
| NumberFire | | | |
| Vegas consensus | | | |

**Divergence note:** `[Where does my model differ and why? A divergence of >5% win probability is worth investigating before betting.]`

---

## SECTION 15 — BET FILTER (MINIMUM THRESHOLDS)

*A bet only qualifies for recommendation if it clears ALL of the following:*

| Filter | Threshold | Pass? |
|---|---|---|
| EV% | ≥ +3.0% | ☐ |
| Edge (My Prob vs True Implied) | ≥ +3.0% | ☐ |
| Confidence score | ≥ 6/10 | ☐ |
| Lineup confirmed | Yes | ☐ |
| Weather checked | <60 min ago | ☐ |
| Injury report clear | Yes | ☐ |
| Sharp money alignment | Neutral or favorable | ☐ |
| Vig removed before comparison | Yes | ☐ |

> ❌ If any filter fails, **do not bet.** There will be another game tomorrow.

---

## SECTION 16 — FINAL PICK CARD

*Only bets that passed Section 15 appear here.*

### ✅ Recommended Bets — `[DATE]`

| # | Game | Market | Book | Odds | My Prob | True Implied | Edge | EV% | Stake | Confidence |
|---|---|---|---|---|---|---|---|---|---|---|
| 1 | | | | | | | | | | /10 |
| 2 | | | | | | | | | | /10 |
| 3 | | | | | | | | | | /10 |
| 4 | | | | | | | | | | /10 |
| 5 | | | | | | | | | | /10 |

**Total units at risk today:** `[ ]`
**Projected bankroll impact (EV-weighted):** `[ ]`

---

## SECTION 17 — RISK REGISTER

*For each recommended bet, list the top 3 things that would invalidate the wager.*

| Bet | Risk #1 | Risk #2 | Risk #3 |
|---|---|---|---|
| | | | |
| | | | |
| | | | |

---

## SECTION 18 — POST-GAME RESULTS LOG

*Complete after the last game of the night concludes.*

| # | Game | Market | Odds | Stake | Result | P&L (units) | Notes |
|---|---|---|---|---|---|---|---|
| 1 | | | | | ☐ Win / ☐ Loss / ☐ Push | | |
| 2 | | | | | ☐ Win / ☐ Loss / ☐ Push | | |
| 3 | | | | | ☐ Win / ☐ Loss / ☐ Push | | |
| 4 | | | | | ☐ Win / ☐ Loss / ☐ Push | | |
| 5 | | | | | ☐ Win / ☐ Loss / ☐ Push | | |

**Day record:** `W-L-P`
**Day P&L:** `+/- [ ] units`
**Running season record:** `W-L-P`
**Running season P&L:** `+/- [ ] units`
**CLV achieved?** ☐ Yes (beat closing line) / ☐ No / ☐ Push

---

## SECTION 19 — DAILY NOTES & MODEL ADJUSTMENTS

*Use this section to log anything that should inform tomorrow's analysis.*

- **What the model got right:**
- **What the model missed:**
- **Line movement we should have caught earlier:**
- **Weather/injury that moved after our pick:**
- **Model adjustment for tomorrow:**
- **Books showing sharp movement to watch:**

---

## QUICK REFERENCE — EDGE THRESHOLDS

| EV Range | Action |
|---|---|
| Below +3.0% | ❌ No bet — insufficient edge |
| +3.0% to +5.0% | 🟡 Quarter Kelly — marginal edge |
| +5.0% to +8.0% | 🟢 Half Kelly — solid edge |
| +8.0% to +12.0% | 🟢 Full Kelly — strong edge |
| Above +12.0% | ⚠️ Cap at Full Kelly — verify model, line may have moved |

## QUICK REFERENCE — CONFIDENCE SCALE

| Score | Meaning |
|---|---|
| 9–10 | Elite edge — multiple confirming signals, sharp money aligned, no injury concerns |
| 7–8 | Strong edge — model and market aligned, one minor uncertainty |
| 6 | Minimum threshold — edge present but one key unknown remains |
| 5 or below | ❌ Do not bet — too many open questions |

---

*Template version 1.0 · For use with the MLB +EV Oddsmaker System · Update Sections 4, 7, 11 within 60–90 minutes of first pitch*
