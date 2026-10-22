# Sector Rotation — RRG Dashboard

One self-contained page, in Thai with English finance terms. No build step, no dependencies — open `index.html` or host it as-is.

**Data as of 21 Oct 2026** — Bloomberg total return, local currency. The 1-month window starts 21 Sep and the 3-month window starts 21 Jul. X = relative 3-month return (RS-Ratio) · Y = relative 1-month return (RS-Momentum) · every group is measured against its own benchmark.

**Live:** https://rakpatai.github.io/Sector_rotation/

## Contents

| § | Section |
|---|---|
| 01 | Market level — S&P 500 · SET · HSCI · CSI 300 against their equal-weight composite, local currency, with tails across five snapshots (10 Aug → 31 Aug → 4 Sep → 30 Sep → 21 Oct) and a quadrant journey table |
| 02 | Sectors by market — SET (27), Hong Kong HSCI (12) and China A CSI 300 (10), with tails |
| 03 | US sub-industry drill-down — 129 S&P 500 sub-industries, plus tails for the 41 largest movers |
| 04 | US thematic ETFs — 21 AUM-weighted themes and 260 ETFs (USD) |
| 05 | What changed since 30 Sep — quadrant crossings |
| 06 | Cross-market threads — with a rates / credit / volatility / commodities context strip |
| 07 | Data — the full table, with each group's quadrant path across all snapshots |

## Reading the quadrants

| rel 3M | rel 1M | Quadrant | Meaning |
|---|---|---|---|
| ≥0 | ≥0 | Leading | strong trend + momentum |
| <0 | ≥0 | Improving | lagging but turning up |
| ≥0 | <0 | Weakening | was leading, losing momentum — earliest rotation-out signal |
| <0 | <0 | Lagging | weak on both |

**"Lagging" does not mean "down."** Everything is relative to a benchmark, so a group can rise and still lag a strong index. Equally, when a benchmark falls the Leading bucket widens mechanically — a group can lead simply by falling less. This edition has that effect in all three Asian panels.

## Snapshot (21 Oct 2026)

The picture reversed from 30 Sep. The S&P 500 is flat over one month (−0.0%), but the median of its 129 sub-industries swung from −6.1% to +2.8% and the number of groups up over one month rose from 22 to 83. The groups sold in September — utilities, residential and tower REITs, consumer staples, insurers, managed health — bounced, while the AI hardware groups that had just moved up fell back: Semiconductors went from Leading to Lagging (−5.8% over one month), Semiconductor Equipment from Improving to Lagging (+10.6% → −12.0%), and the CSI 300 Telecom index lost 24.5% in a month. Energy is the only group Leading in all four markets; gold and metals are Weakening for a second snapshot. On the slower 3-month axis only 48 of the 129 US groups beat the index, so one month of recovery has not undone September.

At market level the US is Leading for a fifth straight snapshot with its widest lead of the series, Hong Kong dropped to Lagging for the first time (HSCI −6.5% over one month), China A is Lagging for a fifth snapshot with its sharpest month (CSI 300 −9.3%), and Thailand is Improving for a second time only because the other markets fell further. The four-market composite (3M / 1M) ran +2.2 / +2.1 → +1.0 / −0.7 → −0.7 / −0.7 → −1.1 / −2.9 → −5.3 / −4.6 across the five snapshots.

## Data & method

- Sector indices, sub-industries and ETFs: Bloomberg **total return**, local currency. The 10 Aug and 31 Aug snapshots use `CURRENT_TRR` fields; 4 Sep, 30 Sep and 21 Oct use BQL `TOTAL_RETURN` over a date range.
- **Windows differ between snapshots** (21 Oct: from 21 Jul / 21 Sep · 30 Sep: from 30 Jun / 31 Aug · 4 Sep: from 4 Jun / 4 Aug · 31 Aug: from 29 May / 31 Jul), and the snapshots are unevenly spaced (21 / 4 / 26 / 21 days) — read the direction of a tail rather than its length. Moving the 3-month base from 30 Jun to 21 Jul raised the HSCI base by about 8%, which together with the index falling 4.9% after 30 Sep turned its 3-month return from +6.9% to −6.2%.
- Market-level benchmark: the equal-weight average of the four indices at each snapshot. No FX adjustment.
- The SET Index benchmark is a **price** index computed from index closes (21 Oct 1,556.09 · 21 Sep 1,598.03 · 21 Jul 1,652.97), while Thai sectors are total return — Thai sectors therefore carry a small edge over their benchmark, most visibly the high-dividend groups.
- US sub-industries: 129 of 163 groups carry data (two more than the 30 Sep edition). US and thematic tails have four points (there is no usable 31 Aug US snapshot).
- Section 04 is in **USD**, unlike sections 01–03. Theme composites are AUM-weighted across the 156 ETFs that carry a classification; the ETF scatter plots all 260, including leveraged and inverse products.
- The context figures in section 06 (rates, HY spread, VIX, gold, copper, Brent) come from FRED and FMP, not Bloomberg. The Chinese market holiday of 1–7 Oct falls inside this edition's 1-month window.

The full list of caveats is in the footer of the page.

## Archive

| File | Edition |
|---|---|
| [`archive/260930.html`](https://rakpatai.github.io/Sector_rotation/archive/260930.html) | Data as of 30 Sep 2026 — Thai, four local-currency markets, four snapshots (10 Aug → 30 Sep), 127 US sub-industries |
| [`archive/260724.html`](https://rakpatai.github.io/Sector_rotation/archive/260724.html) | Data as of 24 Jul 2026 — bilingual (ไทย / English), 14 global markets in USD, sector tails and a macro-driver timeline |

Each new edition replaces `index.html`; the edition it replaces moves to `archive/<YYMMDD>.html`, named by its as-of date.

---

**Disclaimer:** information and education only — a statistical reading of group rotation, not investment advice. Past performance does not guarantee future results.
