---
name: strokes-gained
version: "0.2.0"
description: "Strokes Gained Analysis — Mark Broadie's data-driven golf analytics. Diagnose weaknesses via SG Driving/Approach/Around-the-Green/Putting. Handicap-level benchmarks."
---

# Strokes Gained Analysis (Mark Broadie)

> **Background and theory**: Read [references/foundation.md](references/foundation.md)


## One-Line Summary

**Quantify every shot's value as "strokes saved versus the average."** Diagnose "where you lose strokes" with data instead of intuition, and provide an evidence base for allocating practice time.


## Amateur Stroke-Loss Distribution by Handicap

### Scratch (0) vs. Bogey Golfer (18) Difference = 18 strokes/round

| Category | Stroke Difference | Share |
|---|---|---|
| Off-the-Tee | ~3 strokes | 17% |
| **Approach** | **~7 strokes** | **39%** |
| Around-the-Green | ~4 strokes | 22% |
| Putting | ~4 strokes | 22% |

**Key Finding**: Broadie's research shows that **approach shots create the largest gap**. Yet most amateurs spend the majority of their practice time on putting and the driver.

### Focus Areas to Drop from Handicap 20 → 10
1. **Approach accuracy** (improve GIR) — greatest impact
2. **Short game** — up-and-down probability on green misses
3. **Driver consistency** — fairway hit rate (more important than distance)
4. **Putting** — reduce three-putts


## Data Collection Methods

### Simple Method (No App)
Record on the back of your scorecard:
- Each hole: fairway hit (Y/N), GIR (Y/N), number of putts, up-and-down (Y/N)
- Post-round totals:
  - Fairway hit rate (target: 50%+ for handicap 15)
  - GIR (target: 5–7 for handicap 15)
  - Average putts (target: 32 or fewer)
  - Up-and-down success rate (target: 30%+)

### App-Based Tracking
| App | Features | Cost |
|---|---|---|
| **Arccos** (sensors) | Automatic shot tracking, SG analysis | Sensors ~$150–250 + annual subscription |
| **Shot Scope** (watch) | Automatic tracking, heat maps | Watch ~$250–350, app free |
| **Golfshot** | Manual entry, GPS distances | Free–paid |
| **TheGrint** | Handicap management + statistics | Free–paid |
| **Kakao Golf** | Korean course support, score management | Free |

### Minimum Data (5 Rounds)
- At least 5 rounds of data are needed before patterns emerge
- 1 round = noise. 5 rounds = trend


## Benchmarks by Handicap

### Key Statistics (Based on Shot Scope Data)

| Metric | Handicap 0 | Handicap 10 | Handicap 20 | Handicap 30 |
|---|---|---|---|---|
| Driver distance | 255 yd | 230 yd | 210 yd | 190 yd |
| Fairway hit rate | 65% | 50% | 40% | 30% |
| GIR | 12/18 | 7/18 | 3/18 | 1/18 |
| Up-and-down % | 55% | 30% | 15% | 8% |
| Average putts | 29 | 32 | 35 | 38 |
| Three-putt rate | 5% | 12% | 20% | 30% |


## Recommended Practice Time Allocation (Strokes Gained–Based)

### Handicap 20+
```
Driving range: 30% (contact consistency)
Short game / chips / pitches: 35% (fastest improvement area)
Putting: 20%
Course management (mental review): 15%
```

### Handicap 10–20
```
Approach (within 150 yd): 35%
Short game: 25%
Putting: 20%
Driver: 15%
Course management: 5%
```

### Handicap 0–10
```
Approach: 30%
Putting: 25%
Short game: 20%
Driver: 15%
Course management: 10%
```


## Realities for Korean Amateurs

- **Range-centric practice**: Hitting mostly driver on multi-story ranges → **least efficient** from an SG perspective
- **Screen golf data**: GolfZon statistics are reference-only (significant gap from actual field play). Use for directional insight only
- **Lack of short-game facilities**: Few dedicated short-game practice areas near Seoul → practice with a putting mat at home + wedge work at the range
- **Round frequency**: At 1–2 rounds per month, data accumulates slowly → supplement with screen golf data


## Anti-Patterns

- **Diagnosing weaknesses by feel** — Many think "putting is my problem" when approach shots are actually the issue
- **Obsession with distance** — Gaining 10 yards off the tee contributes less to scoring than improving fairway hit rate by 10%
- **Hitting only driver at the range** — "Feel-good" practice without SG data
- **Investing all time in putting** — Increasing GIR is more effective than converting three-putts into two-putts
- **Drawing conclusions from a single round** — Decisions should be based on at least 5 rounds of data


## Limitations

1. SG tells you "where" but not "how" → swing mechanics require a teaching professional
2. Cannot perfectly adjust for course difficulty differences
3. Manual data collection is burdensome for amateurs without an app
4. Psychological factors (first-tee nerves, downhill putts, etc.) are not captured in the statistics


## Complementary Frameworks

- `practice-design` — Build a practice plan based on SG analysis
- `scoring-strategy` — Improvement roadmap by handicap level
- `short-game` — Strategies to improve SG: ATG
- `course-management` — Strategic shot selection to improve SG: OTT and APP
