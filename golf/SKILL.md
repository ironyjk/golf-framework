---
name: golf
version: "0.3.0"
last_verified: "2026-04-17"
valid_until: "2026-10-17"
description: "Golf coaching meta-router — 8 evidence-based frameworks (Strokes Gained/Broadie, Course Management/DECADE, Mental Game/Rotella, Short Game/Pelz, Practice Design, Club Fitting, Physical Conditioning/TPI, Scoring Strategy). No swing mechanics — think your way around the course. Korean amateur context. Not a substitute for lessons."
tools: ["Read", "Write", "Edit", "Skill", "Agent"]
dependencies:
  - strokes-gained
  - course-management
  - mental-game
  - short-game
  - practice-design
  - club-fitting
  - physical-conditioning
  - scoring-strategy
---

# Golf Coaching Meta-Router

Classify golf-related questions and select 1–3 optimal sub-frameworks for execution.

## Core Principle: No Swing Corrections

This framework focuses on **"thinking golf"**:
- Data analysis (where are you losing strokes?)
- Strategy (where should you aim?)
- Mental game (how do you perform under pressure?)
- Practice design (maximum improvement per hour)
- Equipment optimization (14-club configuration)
- Physical conditioning (distance gains & injury prevention)

**Swing mechanics** (backswing angles, downswing path, impact position, etc.) require video analysis and in-person instruction; text-based corrections do more harm than good. → Recommend professional lessons.

## Detection Matrix

| User Signal | Primary | Secondary |
|---|---|---|
| "I want to lower my score", "I don't know where I'm losing strokes", "data analysis" | **strokes-gained** | scoring-strategy |
| "On-course decisions", "where should I aim", "course strategy", "risk management" | **course-management** | strokes-gained |
| "I'm nervous", "first-tee jitters", "meltdown", "confidence", "focus" | **mental-game** | course-management |
| "Approach shots", "putting", "bunkers", "wedge distances", "short game" | **short-game** | practice-design |
| "How to practice", "driving range", "limited time", "effective practice" | **practice-design** | strokes-gained |
| "Club recommendations", "fitting", "driver", "should I change irons", "14-club setup" | **club-fitting** | strokes-gained |
| "Distance", "flexibility", "back pain", "warm-up", "fitness" | **physical-conditioning** | injury → `/fit` |
| "I want to break 90", "80s", "lower my handicap", "bogey golfer" | **scoring-strategy** | strokes-gained / course-management |
| "Screen golf", "Golfzon", "winter practice" | **practice-design + indoor context** | — |
| "Just starting out", "beginner", "what equipment should I buy" | **club-fitting + scoring-strategy (Starter 2)** | — |
| "Preparing for a round", "playing tomorrow" | **course-management + mental-game** | nutrition → `/fit` |
| "My swing isn't working", "slice", "hook" | **→ Recommend professional lessons** (outside this framework's scope) | mental-game (if psychological factors are involved) |

## Routing by Handicap

| Handicap | Key Frameworks | Rationale |
|---|---|---|
| **100+ (Beginner)** | scoring-strategy + club-fitting | Consistent contact, equipment fundamentals |
| **90–100** | short-game + course-management | Short game yields fastest improvement; eliminate penalties |
| **80–90** | strokes-gained + practice-design | Data-driven weakness identification, efficient practice |
| **70–80 (Single digit)** | course-management + mental-game | Strategy optimization, pressure management |
| **Sub-70 (Scratch+)** | course-management + mental-game + strokes-gained | Fine-tuning across all areas |

## Multi-Framework Combinations

| Scenario | Framework Combination |
|---|---|
| **Comprehensive handicap diagnosis** | strokes-gained (data analysis) + scoring-strategy (level-specific roadmap) + practice-design (practice plan) |
| **Breaking 90** | short-game (wedge & putting focus) + course-management (bogey avoidance) + scoring-strategy (90s tactics) |
| **Tournament/competition prep** | course-management (course strategy) + mental-game (pressure management) + nutrition (on-course fueling → `/fit`) |
| **Winter off-season** | practice-design (screen golf/indoor utilization) + physical-conditioning (flexibility & strength) + short-game (short game drills) |
| **Equipment upgrade cycle** | club-fitting (analysis) + strokes-gained (data-driven prioritization) |
| **Gaining distance** | physical-conditioning (rotational power & strength) + club-fitting (driver optimization) — swing changes go to a pro |
| **Day before a round** | course-management (course strategy) + mental-game (pre-shot routine review) |

## Goal / Level / Context Checklist

Confirm or ask before analysis:

- **Handicap / average score**: Current level (e.g., "I usually shoot 95–100")
- **Goal**: Target handicap? By when?
- **Round frequency**: 1× / 2× / 4×+ per month
- **Practice time**: Available hours per week
- **Practice environment**: Outdoor range / screen golf / putting green / short game area
- **Lessons**: Currently taking professional lessons?
- **Equipment**: Current club setup (driver loft, iron type, wedge configuration)
- **Primary concern**: Driver / irons / short game / putting / mental — which is the biggest issue?
- **Physical**: Age, injury history (back, elbow, wrist)

## Korean Amateur Golf Context

- **Cost structure**: Green fees ₩150K–300K (weekday/weekend); memberships range from tens of millions to hundreds of millions of won. Public course utilization strategy is important
- **Screen golf (시뮬레이터)**: Golfzon, Kakao VX. Field access limited 4–5 months in winter → screen golf becomes the primary practice environment. Awareness of differences from actual field play is essential
- **Driving ranges**: Multi-story (2F/3F) ranges are standard. Difficult to verify actual ball flight. Launch monitors (SkyTrak, Garmin R10) gaining traction
- **Four-player group culture (4인 1팀)**: Must match pace with playing partners. Pace-of-play management is important
- **Caddie system**: Most courses require caddies. Leveraging caddie advice (vs. trusting your own judgment)
- **Business golf culture (접대 골프)**: Manners > score > relationships. Behavioral strategy in corporate golf settings
- **Season**: March–May and September–November are peak season. Summer means early-morning tee times; winter means screen golf
- **Key events**: Club championships, amateur tournaments, corporate golf outings

## Evidence Strength

- **Strong evidence**: Strokes Gained analysis (PGA Tour data-based), random/interleaved practice > blocked practice (motor learning research), pre-shot routine effectiveness
- **Moderate evidence**: DECADE course management, Pelz wedge system, TPI golf fitness
- **Weak evidence**: Specific putter head shapes and putting accuracy, most golf gadgets/training aids

## Exclusion Principles

- **Swing mechanics corrections** — No text-based swing instruction. Always recommend professional lessons + video analysis
- Brand-promotional equipment recommendations
- Unscientific advice packaged as "secrets" or "hacks"
- Unrealistic promises such as "drop 10 strokes in one month"
- Betting/gambling-related content


## Execution Strategy

1. **Route** -- classify the problem, select 1-3 sub-skills
2. **Confirm** -- verify goal/level/context with the user before analysis
3. **Execute** -- call sub-skills via the Skill tool (read their SKILL.md for execution protocol)
4. **Synthesize** -- combine results, expose conflicts, give concrete next steps
5. **Measure** -- propose 1-2 metrics to track over 4-12 weeks

When a sub-skill needs background theory, read its `references/foundation.md`. Execute using its `SKILL.md`.

## Output Format

```
## Situation Assessment
- Handicap / average score: [current level]
- Goal: [target handicap/score]
- Round frequency: [N× per month]
- Practice time / environment: [Xh per week, range/screen/short game area]
- Primary concern: [driver/irons/short game/putting/mental]

## Selected Frameworks
1. [Framework] — Selection rationale (evidence strength)
2. ...

## Framework Analysis
### [Framework 1]
[Analysis results]

## Summary
- Points of agreement across frameworks: [summary]
- Top 1–2 priorities at current stage: [specific actions]
- What NOT to do: [anti-patterns]
- Measurement metrics (4–12 weeks): [handicap/GIR/putts per round/up-and-down % etc.]

## Professional Lesson Recommendation
- [Recommend lessons if swing-related issues are present]
```

## Related Domains

- **`/fit`** — Golf fitness & flexibility connects to `strength-basics`, `progressive-overload`. On-course nutrition connects to `macro-tracking`
- **`/ride`** — For those combining cycling and golf, time allocation guidance (primarily overlapping fitness base)
- **`/counsel`** — Severe performance anxiety, yips, etc. → Recommend a sports psychologist
- **`/learn`** — Directly applicable to efficient practice: `deliberate-practice`, `interleaving`, `active-recall`
