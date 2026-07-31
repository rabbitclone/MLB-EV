# ⚾ MLB INTELLIGENCE FLAGS
> Pitcher and team-specific edges confirmed by real game results.
> This file is filtered by today's confirmed starters before being sent to the AI.
> Only flags matching today's pitchers/teams are included in the prompt.
> Last updated: July 31, 2026

---

## HOW FLAGS WORK
- **Tier 1** — Confirmed structural edge. Overrides Tier 3 sharp handle signals per Rule 5.
- **Strong** — Confirmed multiple times. Apply automatically.
- **Apply** — Confirmed once. Apply with normal confidence.
- **Watch** — Observed but not confirmed. Track only, do not bet on alone.
- **Expired** — Condition no longer exists. Ignore.

New flags start as Watch. Promoted to Apply after first confirmation. Promoted to Strong/Tier 1 after multiple confirmations. Retired when the triggering condition resolves.

---

## 🟢 PITCHER FLAGS

### Wheeler — PHI
**Trigger:** Any game Wheeler starts at home
**Signal:** Strong Under lean vs any offense regardless of opponent ERA
**Detail:** Home ERA 1.35, 10-1 Under record in home starts. Wheeler generates elite groundball rate (58%) and limits hard contact to 28%. When Wheeler starts at home, project total 1.5 runs lower than market line before evaluating.
**Action:** Lean Under. If Under is already priced below -135, seek alternate lines.
**Severity:** STRONG ✅ ACTIVE
**Confirmed:** Jul 21, 2026 — 14K CG shutout, PHI/LAD total 3 runs

---

### Misiorowski — MIL
**Trigger:** Misiorowski home start vs road team with win% below .420
**Signal:** Near-lock tier. Buy early before market adjusts.
**Detail:** Misiorowski's home ERA is 2.18 vs road teams under .420. The market systematically underprices MIL in these matchups, typically offering -130 to -145 when the true line should be -170 to -185.
**Action:** Buy MIL ML early in the morning line. Line moves significantly by game time.
**Severity:** STRONG ✅ ACTIVE
**Confirmed:** Jul 21-22, 2026 — MIL 2-0 in Misiorowski home starts vs sub-.420 road teams

---

### Rasmussen — TB
**Trigger:** Rasmussen vs any lineup ranking bottom-third in chase rate vs sinkers
**Signal:** Tier 1 structural matchup. Sinker generates exceptional weak contact.
**Detail:** Rasmussen's sinker produces 34% chase rate vs lineups that rank bottom-third in sinker recognition. This translates directly to weak contact and low run totals. TB is typically underpriced in these matchups.
**Action:** TB ML + consider TB team Under (opponents). Raise confidence to 8/10.
**Severity:** TIER 1 ✅ ACTIVE
**Confirmed:** Jul 21-22, 2026 — TB 3-0 in series, 23-5 run differential

---

### Imai — HOU
**Trigger:** Imai starting vs lineup >60% RHB OR >50% LHB
**Signal (RHB):** Tier 1 structural — splitter generates 32% chase rate vs RHB. Reduce opposing win prob ~4%.
**Signal (LHB):** FLAG NEUTRALIZED — treat as standard ERA matchup only. Neutralization does NOT create a counter-edge toward the opposing ML. Evaluate ERA differential alone.
**Detail:** Imai's splitter is a Tier 1 weapon vs right-handed hitters specifically. The platoon split is confirmed across 3 games. When facing LHB-heavy lineups the structural advantage disappears entirely.
**Action (RHB):** HOU ML with elevated confidence. Apply Tier 1 to override Tier 3 signals.
**Action (LHB):** Evaluate HOU ML on ERA differential alone. Do not bet solely because the flag fired.
**Severity:** TIER 1 ✅ ACTIVE (amended Jul 27)
**Confirmed:** Jul 20-22, 2026 — HOU 3-0 vs MIA RHB lineup. Jul 27 — LHB neutralization test confirmed flag correctly neutralized (LAA won).

---

### Buehler — SD
**Trigger:** Any Buehler start
**Signal:** Always apply blended ERA (~4.09), never season ERA (5.36). Do not use 5.36.
**Detail:** Buehler's last-4 ERA is 3.05 vs season ERA of 5.36 — a gap of 2.31, well above the >1.50 threshold in Rule 3. Blended ERA = (5.36 × 0.45) + (3.05 × 0.55) = 4.09. The market often prices Buehler at his season ERA, creating value when he's in a strong recent stretch.
**Action:** Use blended 4.09 for all EV calculations. If market is pricing SD as a bigger dog than the 4.09 ERA warrants, evaluate SD ML.
**Severity:** APPLY ✅ ACTIVE
**Confirmed:** Jul 21, 2026 — Buehler pitched to 2 ER/6 IP despite season ERA of 5.36

---

### Wrobleski — LAD
**Trigger:** Wrobleski ROAD starts only where ERA/xFIP gap exceeds 1.00
**Signal:** Over lean in road starts with large ERA/xFIP gap. Home starts are NEUTRAL — flag does not apply.
**Detail:** Wrobleski's road ERA regresses significantly relative to his xFIP when the gap exceeds 1.00. In these starts, the Over is the primary play. His home starts do not exhibit the same regression pattern.
**Action:** Road start + gap >1.00 → lean Over. Home start → neutral, no flag.
**Severity:** APPLY ✅ ACTIVE (road only)
**Confirmed:** Jul 22, 2026 — Wrobleski road start, 9 ER. LAD 9-5 win, Over confirmed.

---

### Thornton — NYM
**Trigger:** Any Thornton start (while sub-8 MLB starts)
**Signal:** ERA Unknown flag (Rule 2) — reduce opposing team win prob by 5%
**Detail:** Thornton is in his first several MLB starts. Rule 2 applies regardless of his ERA. The market systematically misprices pitchers in their first 8 starts. NYM has been offered at generous odds in Thornton starts.
**Action:** Apply Rule 2 — reduce opposing team win prob 5%, recalculate EV. If opposing team is a big favorite, check whether the -5% adjustment makes the NYM ML +EV.
**Severity:** APPLY ✅ ACTIVE
**Expires:** ~August 1 at 8th start — retire this flag when Thornton reaches 8 MLB starts
**Confirmed:** Jul 21, 2026 — Thornton 2nd start, NYM shut out MIL 4-0 (Rule 2 confirmed). Jul 27, 2026 — Thornton 5th start, NYM won 14-3.

---

### Melton — DET
**Trigger:** Any Melton start
**Signal:** DET ML at -140 or better is the target. Melton is significantly mispriced.
**Detail:** Melton's current season ERA is 1.95 — elite by any measure. The market has not fully adjusted to his quality, frequently offering DET in the -130 to -145 range when his ERA warrants -160 to -175. Buy DET when Melton starts.
**Action:** DET ML at -140 or better. Do not pay worse than -155. Check Comerica wind for totals secondary play.
**Severity:** APPLY ✅ ACTIVE
**Confirmed:** Jul 28, 2026 — DET 14-0 vs BAL. Melton dominant. DET ML -139 won.

---

## 🟡 TEAM / PARK FLAGS

### TEX Home Price Inflation
**Trigger:** Any game where TEX is a home favorite
**Signal:** Books consistently overprice TEX home edge relative to run differential. Fade TEX home line by ~5-8 cents.
**Detail:** TEX home win% is inflated in public perception vs their actual run differential metrics. Books shade the line toward TEX at home knowing public bets them. The away team is typically 5-8 cents better value than the listed price.
**Action:** When evaluating any TEX home game, reduce TEX implied win prob by ~4% before calculating EV. The away team ML is often +EV as a result.
**Severity:** APPLY ✅ ACTIVE
**Confirmed:** Jul 20, 2026 — CWS +109 won 10-3. Jul 22, 2026 — CWS won again.

---

### PIT Bullpen Strand Rate
**Trigger:** Any game where PIT is involved, especially as an underdog
**Signal:** Subtract 4% from PIT underdog win probability to account for bullpen vulnerability.
**Detail:** PIT bullpen ranks bottom-quartile in strand rate — inherited runners score at an elevated rate vs league average. This creates a persistent late-inning vulnerability. When PIT is an underdog, the market already discounts them, but not enough for the bullpen bleed.
**Action:** Reduce PIT win prob by 4% in all ML calculations. This makes PIT underdogs slightly less attractive than they appear.
**Severity:** APPLY ✅ ACTIVE
**Confirmed:** Jul 21, 2026 — PIT bullpen blew leads multiple times in series.

---

### Kauffman Stadium Cold Weather
**Trigger:** Any KC home game (Kauffman Stadium) where temp is below 62°F at first pitch
**Signal:** Subtract 1.5 runs from projected total. This threshold is confirmed — stronger than standard Rule 6.
**Detail:** Kauffman plays extremely cold below 62°F due to its open design and proximity to the Missouri River. The cold weather suppression is reliably 1.5 runs more than other parks at the same temperature.
**Action:** Check temp at Kauffman within 60 min of first pitch. If below 62°F → subtract 1.5 from projected total in addition to any wind adjustments.
**Severity:** STRONG ✅ ACTIVE
**Confirmed:** Jul 21, 2026 — SF/KC Over 9.5 loss. 58°F at Kauffman, 5-run total.

---

### Comerica Park Wind-Out Totals
**Trigger:** Any DET home game (Comerica Park) where wind is 15+ mph blowing out
**Signal:** Add 1.5 runs to projected total per Rule 6. Comerica plays dramatically differently in wind.
**Detail:** Comerica's open design amplifies wind effects more than most parks. When wind is 15+ mph out, fly balls carry significantly further. The market often underestimates this at Comerica specifically.
**Action:** Check wind at Comerica within 60 min of first pitch. If 15+ mph out → add 1.5 to projected total → evaluate Over.
**Severity:** APPLY ✅ ACTIVE
**Confirmed:** Jul 28, 2026 — 18 mph wind out, Over 9.5 +100 won. Total was 14 runs. DET 14-0.

---

### Coors Field Bilateral Scoring
**Trigger:** Any COL home game (Coors Field) with an Over in play
**Signal:** Over requires BOTH offenses to contribute. Check wind direction — headwind neutralizes Coors entirely.
**Detail:** Coors altitude inflates scoring but only when both teams contribute. A unilateral blowout (one team shut out or held to 1 run) frequently fails the Over even when the other team scores big. Additionally headwind at Coors completely neutralizes the altitude effect.
**Action:** Before betting any Coors Over — confirm both lineups have reasonable scoring upside. Check wind direction. If headwind 10+ mph → treat Coors as a neutral park, not a hitter's park.
**Severity:** APPLY ✅ ACTIVE
**Confirmed:** Jul 22, 2026 — WSH 8-0 at Coors. Over was 10.5, total was 8. Bilateral scoring rule created.

---

### Doubleheader Split Tendency
**Trigger:** Any doubleheader Game 2 where the team lost Game 1
**Signal:** Team that lost G1 wins G2 at an elevated rate vs expectation.
**Detail:** Teams that lose G1 of a doubleheader show elevated motivation and often start a rested arm or turn to their best available reliever earlier in G2. The market often anchors on G1 result and under-adjusts for G2.
**Action:** In G2 of any doubleheader — if one team lost G1 badly, consider that team's G2 ML as a potential value play. Requires separate ERA/EV analysis to confirm.
**Severity:** APPLY ✅ ACTIVE
**Confirmed:** Jul 22, 2026 — NYY lost PIT G1 5-3, won G2 2-0.

---

### Post-Shutout Rebound Tendency
**Trigger:** Any team with above-average road wRC+ that was shut out the previous game
**Signal:** Above-average road offenses score more the game after a shutout vs expectation.
**Detail:** The market slightly over-discounts strong offensive teams after a shutout, treating the shutout as evidence of offensive weakness when it's more often a one-game pitcher-specific result.
**Action:** When a team with above-avg road wRC+ was shut out yesterday, their offensive upside is slightly underpriced today. Factor into totals analysis, not ML.
**Severity:** APPLY ✅ ACTIVE
**Confirmed:** Jul 22, 2026 — CIN shut out previous game, scored 5 in Over 7.5 win.

---

## 🔴 EXPIRED FLAGS

### BOS Win Streak
**Was:** Avoid fading BOS during active long win streaks in close games
**Retired:** July 22, 2026 — BAL won 5-1 in series finale, streak broken
**Status:** ❌ EXPIRED — no longer apply

---

## 👀 WATCH LIST — Not yet confirmed

| Pattern | Observation | Games tracked | Promote when |
|---|---|---|---|
| Series finale underdog value | Teams trailing in series push hard in finales | 2 | 3rd confirmation |
| ATL home offense vs 5.00+ road ERA | Lopez home starts with run support | 2 | 3rd confirmation |
| Bieber improving form | Last-2 starts 0 ER, 1 ER — blended ERA well below season | 1 | 2nd confirmation |
| MIN underdog vs CLE | Rojas starts neutralize CLE pull-heavy lineup | 1 | 2nd confirmation |
| CLV tracking | Compare pick odds to closing line for model health | 0 | Future implementation |

---

*MLB Flags · v1.0 · July 31, 2026 · Filtered by today's slate before AI prompt*
