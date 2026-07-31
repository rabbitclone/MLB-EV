# ⚾ MLB +EV MODEL BRAIN
> Rules, flags, and lessons only. Pick history lives in MLB_LEDGER.md.
> Last updated: July 31, 2026 · Repository: rabbitclone/MLB-EV

---

## SYSTEM CONFIG

| Setting | Value |
|---|---|
| Dashboard repo | `rabbitclone/MLB-EV` |
| Live URL | `https://mlb.beclutch.me` |
| Default password | `ev2026` |
| Simulated stake | $10 per pick |
| Kelly default | Half Kelly |
| Minimum EV | +3.0% after vig removal |
| Minimum confidence | 6/10 |
| Ledger file | `MLB_LEDGER.md` |

---

## 🧠 PERMANENT MODEL RULES

### RULE 1 — Dual Elite Starter Total Suppression
**Confirmed:** July 21, 2026 · PHI/LAD Over 9 loss
- Both starters xFIP < 3.20 → subtract 1.5 runs from projected total
- Raise EV threshold to +6.0% · Reduce stake to Quarter Kelly

### RULE 2 — ERA Unknown Pitcher (Sub-8 MLB Starts)
**Confirmed:** July 21, 2026 · MIL -149 loss · Thornton 2nd start
- Sub-8 starts → reduce opposing team win prob by 5% · Recalculate EV · Pass if no longer +EV
- Applies to IL returnees with fewer than 3 post-IL starts

### RULE 3 — Blended ERA Formula
**Confirmed:** July 21, 2026 · ATL loss · Buehler season 5.36, last-4 3.05
```
Gap < 0.75   → Use season ERA
Gap 0.75–1.50 → 70% season / 30% recent
Gap > 1.50   → 45% season / 55% recent
```

### RULE 4 — No Prior-Game Score Anchoring
**Confirmed:** July 21, 2026 · CLE/MIN Over loss
- Prior game run totals are NOT valid inputs for next-day totals
- Blacklisted: "they scored a lot yesterday", "hot offense", "carried over momentum"

### RULE 5 — Signal Hierarchy
**Confirmed:** July 21, 2026 · MIA ML repeat loss
- Tier 1: Confirmed structural SP matchup > Tier 2: ERA differential > Tier 3: Sharp handle > Tier 4: Narrative
- Tier 3 cannot override confirmed Tier 1 in same series

### RULE 6 — Weather Adjustments
**Confirmed:** July 21, 2026 · SF/KC Over loss · Kauffman 58°F

| Condition | Adjustment |
|---|---|
| Wind out 10+ mph | +0.8 runs |
| Wind out 15+ mph | +1.5 runs |
| Wind in 10+ mph | −0.8 runs |
| Wind in 15+ mph | −1.5 runs |
| Temp < 60°F | −1.0 run |
| Temp < 50°F | −1.8 runs |
| Temp > 88°F | +0.5 run |
| Kauffman < 62°F | −1.5 runs |
| Coors headwind | Treat as pitcher's park |

Weather must be checked within 60 min of first pitch.

### RULE 7 — Imai Splitter Platoon Adjustment
**Confirmed:** July 20–22, 2026 · HOU 3-0 vs MIA
- >60% RHB lineup → Tier 1 structural (−4% opposing win prob)
- >50% LHB lineup → flag NEUTRALIZED — evaluate ERA differential only. Neutralization ≠ counter-signal.

### RULE 8 — Coors Field Bilateral Scoring
**Confirmed:** July 22, 2026 · WSH 8-0 at Coors · Over failed
- Over requires both offenses to contribute · Headwind = neutral park

### RULE 9 — Starter Identity Verification
**Confirmed:** July 27–28, 2026 · PHI ML misattributed to Wheeler (Nola was starting)
- Confirm starter by name before applying any pitcher-specific flag
- If starter unconfirmed → conditional pass until confirmed

---

## 📊 ACTIVE INTELLIGENCE FLAGS
> Flags live in **MLB_FLAGS.md** — filtered by today's confirmed starters before being sent to the AI.
> Only flags matching today's pitchers/teams are injected into the picks prompt.
> To add/retire a flag: edit MLB_FLAGS.md directly.

---

## ✅ PRE-PICK CHECKLIST

- [ ] Starter identity verified by NAME (Rule 9)
- [ ] Vig removed — true implied probability calculated
- [ ] Blended ERA applied to both starters (Rule 3)
- [ ] ERA Unknown flag checked for both starters (Rule 2)
- [ ] Dual sub-3.20 xFIP check (Rule 1)
- [ ] Prior-game anchoring scrubbed (Rule 4)
- [ ] Signal hierarchy applied (Rule 5)
- [ ] Weather checked within 60 min of first pitch (Rule 6)
- [ ] Imai platoon flag checked if Imai starting (Rule 7)
- [ ] Coors bilateral check for Overs (Rule 8)
- [ ] All active intelligence flags cross-referenced
- [ ] Lineup confirmed within 3 hrs of first pitch
- [ ] EV ≥ +3.0% (Overs ≥ +5.0%) after all adjustments
- [ ] Confidence ≥ 6/10
- [ ] Stake: Half Kelly default / Quarter Kelly if Rule 1 or 2 triggered
- [ ] Sharp signal is NOT the sole reason for pick

---

## 📚 RECENT LESSONS — LAST 10
> Rolling window — 10 most recent lessons only. Full history in MLB_LEDGER.md.
> When a new lesson is added, the oldest entry drops off this list automatically.
> Format: **L[n] ([date]):** [lesson] — [action taken]

**L12 (Jul 22):** BOS streak broke in series finale. Finales are highest-probability break point for active streaks.
**L13 (Jul 22):** Rasmussen 3-0 vs TOR, 23-5 run diff. Sinker vs contact-weak lineups = Tier 1 confirmed.
**L14 (Jul 22):** Wrobleski road regression confirmed with 9 ER. Flag applies to ROAD starts only — home starts are neutral.
**L15 (Jul 22):** DH split confirmed — NYY lost G1 to PIT, won G2. Track in all future doubleheaders.
**L16 (Jul 23):** Trust +8%+ EV plays even at large underdog prices. KC +190 won 3-2. Model is calibrated.
**L17 (Jul 23):** Bieber blended ERA confirmed. Rule 3 applies to improving starters too, not just declining ones.
**L18 (Jul 27):** Rule 7 amended — Imai LHB neutralization does NOT create a counter-edge. ERA diff only when neutralized.
**L19 (Jul 27):** Rule 9 born — Wheeler flag misapplied when Nola was starting. Always verify starter by name.
**L20 (Jul 28):** 4W-0L. Melton 1.95 ERA (DET 14-0), Comerica wind +1.5 (14 total), Lambert vs Detmers, King vs Lorenzen. All signals confirmed in one day.
**L21 (Jul 29):** 4W-0L. STL -101, HOU -133 (Rodriguez 8.54 ERA), SD -142 Day 2, BOS -154. Eight consecutive wins Jul 28-29. High-EV picks (+8%+) continue to outperform.

---

## ⚠️ ONGOING WATCH LIST

| Pattern | Status |
|---|---|
| ML favorites above −140 (30.8% win rate) | Consider −130 ceiling |
| Totals Over minimum EV raised to +5.0% | IMPLEMENTED |
| CLV tracking — compare pick odds to closing line | Add as manual field (future) |
| Series finale underdog value | Watch |
| Comerica wind-out totals | Promoted to active flag |

---

*MLB Brain · v2.0 · Lean file — pick history in MLB_LEDGER.md*
