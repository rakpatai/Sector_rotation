# Sector Rotation — RRG Dashboard

One self-contained page, **bilingual (ไทย / English)**. No build step, no dependencies — open `index.html` or host it as-is. The language switch sits at the left of the sticky nav and re-renders the charts as well as the text.

**Data as of 24 Jul 2026.** X = relative 3-month return (RS-Ratio) · Y = relative 1-month return (RS-Momentum) · every group measured against its own benchmark.

**Live:** https://rakpatai.github.io/sector_rotation/

## Contents

| § | Section |
|---|---|
| 01 | Market level — 14 global markets (USD) |
| 02 | Market tails — path across three snapshots (30 Jun → 8 Jul → 24 Jul), full range and zoomed |
| 03 | What the market tails reveal |
| 04 | Sector RRG — SET · Hong Kong · China A (local currency) |
| 05 | Sector tails — SET, 27 sectors |
| 06 | Sector tails — Hong Kong (12) and China A (10) |
| 07 | What the sector tails reveal |
| 08 | US deep dive — 126 S&P 500 sub-industries |
| 09 | US sub-industry tails — 40 biggest movers (2 snapshots) |
| 10 | Cross-market threads |
| 11 | Data tables — full returns plus the market journey table |
| 12 | Macro drivers — timeline and watchlist |

## Reading the quadrants

| rel 3M | rel 1M | Quadrant | Meaning |
|---|---|---|---|
| ≥0 | ≥0 | Leading | strong trend + momentum |
| <0 | ≥0 | Improving | lagging but turning up |
| ≥0 | <0 | Weakening | was leading, losing momentum — earliest rotation-out signal |
| <0 | <0 | Lagging | weak on both |

**"Lagging" does not mean "down."** Everything is relative to a benchmark, so a group can rise and still lag a strong index. Equally, when a benchmark cools the Leading bucket widens mechanically — arithmetic, not broadening strength.

## Snapshot (24 Jul 2026)

The global composite cooled to roughly flat over 3M, from +11% at end-June. AI/tech leaders (Taiwan, Nasdaq, Japan) rotated into **Weakening**; value/defensive plus Southeast Asia (Singapore, Dow, Thailand, US, Europe) took the lead; Hong Kong, Indonesia and Malaysia turned **Improving**. In the US, semis rolled over — Semiconductor Equipment fell 16.6% over 1M while still up 18% over 3M — as leadership passed to refining and healthcare.

The tails add the path rather than the snapshot. China A walked the full textbook clockwise route (Leading → Weakening → Lagging); Thailand jumped from Lagging straight to Leading without passing through Improving; the Dow never changed quadrant. At sector level China A moved all ten groups, Thai Electronics decayed Weakening → Weakening → Lagging, and Thai Banking held Leading while its relative 3M climbed from +4 to +18. The largest single journey on the board is US Semiconductor Equipment, whose relative 3M fell from +96 to +15.

## Data & method

- Sector and sub-industry data: Bloomberg official sector indices, trailing 1M/3M, local currency
- Market level: US-listed country ETFs — returns are in **USD and include FX**, deliberately a different basis from the sector panels, flagged on the page
- Market-level benchmark: equal-weight average of the 14 markets, recomputed each snapshot (+11.3% → +7.3% → −0.2%)
- Return basis differs across snapshots (30 Jun and 8 Jul price return; 24 Jul total return) — read tail direction rather than exact distance
- US tails use **two** snapshots (30 Jun → 24 Jul) and show the 40 largest movers of the 124 groups matched across both dates

## Publish to GitHub Pages

Remote is preset to `https://github.com/rakpatai/sector_rotation.git` and a commit is ready.

```bash
git push -u origin main --force   # --force only needed if the repo already has history
```

Then **Settings → Pages → Deploy from a branch → `main` / `/ (root)` → Save**. Live after ~1 minute.

---

**Disclaimer:** information and education only — a statistical reading of group rotation, not investment advice. Past performance does not guarantee future results.
