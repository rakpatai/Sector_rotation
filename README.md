# Sector Rotation — RRG Dashboard

One self-contained page, in Thai with English finance terms. No build step, no dependencies — open `index.html` or host it as-is.

**Data as of 30 Sep 2026** — Bloomberg total return, local currency. The 1-month window starts 31 Aug and the 3-month window starts 30 Jun. X = relative 3-month return (RS-Ratio) · Y = relative 1-month return (RS-Momentum) · every group is measured against its own benchmark.

**Live:** https://rakpatai.github.io/Sector_rotation/

## Contents

| § | Section |
|---|---|
| 01 | Market level — S&P 500 · SET · HSCI · CSI 300 against their equal-weight composite, local currency, with tails across four snapshots (10 Aug → 31 Aug → 4 Sep → 30 Sep) and a quadrant journey table |
| 02 | Sectors by market — SET (27), Hong Kong HSCI (12) and China A CSI 300 (10), with tails |
| 03 | US sub-industry drill-down — 127 S&P 500 sub-industries, plus tails for the 36 largest movers |
| 04 | US thematic ETFs — 21 AUM-weighted themes and 260 ETFs (USD) |
| 05 | What changed since 4 Sep — quadrant crossings |
| 06 | Cross-market threads — with a rates / credit / commodities context strip |
| 07 | Data — the full table, with each group's quadrant path |

## Reading the quadrants

| rel 3M | rel 1M | Quadrant | Meaning |
|---|---|---|---|
| ≥0 | ≥0 | Leading | strong trend + momentum |
| <0 | ≥0 | Improving | lagging but turning up |
| ≥0 | <0 | Weakening | was leading, losing momentum — earliest rotation-out signal |
| <0 | <0 | Lagging | weak on both |

**"Lagging" does not mean "down."** Everything is relative to a benchmark, so a group can rise and still lag a strong index. Equally, when a benchmark falls the Leading bucket widens mechanically — a group can lead simply by falling less.

## Snapshot (30 Sep 2026)

The index and what sits inside it parted ways. The S&P 500 is −0.3% over one month, but the median of its 127 sub-industries is −6.1% and only 22 groups are up. Mega-cap tech and AI hardware carried the index — Semiconductors moved into Leading, and Semiconductor Equipment gained 10.6% over one month while still down 28.3% over three — as rate-sensitive groups, US banks and consumer names were sold in a month when the Fed raised rates and the 10-year Treasury yield rose 54bp. Gold and materials reversed: the one-month return of the S&P 500 Gold sub-industry swung from +31.3% at the 4 Sep snapshot to −8.3%.

At market level the US is Leading for a fourth straight snapshot, Hong Kong slipped to Weakening, Thailand moved to Improving only because China and Hong Kong fell further, and China A is the deepest Lagging (CSI 300 −11.7% over three months). The four-market composite (3M / 1M) went +2.2 / +2.1 → +1.0 / −0.7 → −0.7 / −0.7 → −1.1 / −2.9 across the four snapshots.

## Data & method

- Sector indices, sub-industries and ETFs: Bloomberg **total return**, local currency. The 10 Aug and 31 Aug snapshots use `CURRENT_TRR` fields; 4 Sep and 30 Sep use BQL `TOTAL_RETURN` over a date range.
- **Windows differ between snapshots** (30 Sep: from 30 Jun / 31 Aug · 4 Sep: from 4 Jun / 4 Aug · 31 Aug: from 29 May / 31 Jul), and the snapshots are unevenly spaced — read the direction of a tail rather than its length.
- Market-level benchmark: the equal-weight average of the four indices at each snapshot. No FX adjustment.
- The SET Index benchmark is a **price** index computed from index closes, while Thai sectors are total return — Thai sectors therefore carry a small edge over their benchmark, most visibly the high-dividend groups.
- US sub-industries: 127 of 163 groups carry data. US and thematic tails have three points (there is no usable 31 Aug US snapshot).
- Section 04 is in **USD**, unlike sections 01–03. Theme composites are AUM-weighted across the 160 ETFs that carry a classification; the ETF scatter plots all 260, including leveraged and inverse products.
- The context figures in section 06 (rates, HY spread, gold, copper, Brent) come from FRED and FMP, not Bloomberg.

The full list of caveats is in the footer of the page.

## Archive

| File | Edition |
|---|---|
| [`archive/260724.html`](https://rakpatai.github.io/Sector_rotation/archive/260724.html) | Data as of 24 Jul 2026 — bilingual (ไทย / English), 14 global markets in USD, sector tails and a macro-driver timeline |

Each new edition replaces `index.html`; the edition it replaces moves to `archive/<YYMMDD>.html`, named by its as-of date.

---

**Disclaimer:** information and education only — a statistical reading of group rotation, not investment advice. Past performance does not guarantee future results.
