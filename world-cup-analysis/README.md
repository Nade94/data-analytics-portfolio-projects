# The World Cup Through Data: 1930–2022
### *94 Years of Football's Biggest Stage — And What to Expect in 2026*

This project explores 94 years of FIFA World Cup history through data — from the 13-team inaugural tournament in Uruguay to the 32-team edition in Qatar. Using the Fjelstul World Cup Database, a research-grade open-source dataset covering all 22 tournaments, the analysis asks one central question: **how has the World Cup changed over 94 years — and what does that tell us about the first 48-team edition in 2026?**

---

## Dataset

**[Fjelstul World Cup Database](https://github.com/jfjelstul/worldcup)** — 27 CSV tables covering every match, goal, booking, and team appearance across all 22 men's World Cup tournaments (1930–2022). Featured by The Washington Post, FiveThirtyEight, and The Times.

---

## Tools

Python · pandas · sqlite3 · matplotlib · Tableau

---

## Project Structure

```
world-cup-analysis/
├── notebooks/
│   └── worldcup_analysis.ipynb   # Full analysis: SQL + visualisations
├── data/
│   ├── raw/                      # Fjelstul database CSV files (27 tables)
│   └── exports/                  # Processed CSVs exported for Tableau
```

---

## Analysis Overview

The notebook is structured in three parts across four chapters:

**Part A — Data Verification**
Schema exploration and row-count validation across the five core tables.

**Part B — SQL Analysis**
14 queries covering tournament growth, scoring trends, discipline evolution, and 2026 projections. Written in SQLite via `sqlite3` and `pd.read_sql()`, with interpretive markdown after each result.

| Chapter | Questions answered |
|---|---|
| 1: Tournament Growth | How have team count, match volume, and global reach expanded since 1930? |
| 2: Scoring Trends | How has goals per match evolved? Are modern World Cups more penalty-dependent? Do expanded tournaments produce more blowouts? |
| 3: Discipline | How have yellow and red card rates changed since 1970? What has VAR done to card patterns? |
| 4: 2026 Projections | What does the 1998 expansion tell us about 2026? How do host nations historically perform? |

**Part C — Visualisations**
8 matplotlib charts including dual-axis tournament growth, goal timing by era, blowout rate over time, and an all-time win percentage ranking.

---

## Tableau Dashboard

**[94 Years of World Cup Football](https://public.tableau.com/app/profile/nade.cvetanovska/viz/Dashboard1_17811098258810/94YearsofWorldCupFootball)** — interactive dashboard built from the exported CSVs, covering goals per match, tournament growth, card trends, top teams, and continental win share.

---

## Key Findings

- The 1954 World Cup remains the statistical outlier at 5.38 goals per match — nearly double any modern tournament
- The modern 32-team era (1998–2022) shows remarkable scoring stability at 2.23–2.69 goals per match despite doubling the number of games
- VAR's introduction in 2018 coincided with an 85% drop in red cards per match (0.13 → 0.02), suggesting a strong deterrent effect on reckless challenges
- Half of all World Cup hosts have reached at least the semi-finals; 6 of 22 won the tournament outright
- Based on the 1998 expansion precedent, 2026 is projected at ~2.65 goals per match and ~17% blowout rate — the core product looks resilient even at 48 teams
