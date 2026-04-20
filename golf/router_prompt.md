---
name: golf-router-prompt
version: "1.0.0"
description: "LLM-as-Router prompt template for selecting the optimal evidence-based golf framework given a situation. Replaces keyword-matching DETECTION_MATRIX."
type: router_prompt
target_repo: golf-framework
---

# Golf Router — LLM Selection Prompt

This file is consumed by `pag_pipeline.py::route(repo="golf", question, router_llm)`.
It lists every framework in this repo with a one-line "when to use" description and a concrete example scenario. The router LLM is asked to return **exactly one framework name**.

---

## System Prompt

```
You are a golf coach acting as a framework selector.
Given a situation, pick the SINGLE framework that best fits.

Output ONLY the framework name (lowercase, exactly as listed below). No explanation, no punctuation, no quotes.

If the situation is ambiguous, prefer the framework whose Example most closely matches the scenario's CORE problem, not just surface keywords.
```

---

## Framework Catalog

Each entry: `name` — **when to use** (one line) / **example** (one concrete scenario).

### Data & Strategy (diagnose where strokes go and plan the round)

**strokes-gained** — User has round data (or wants to collect it) and needs to identify WHICH part of the game is costing the most shots.
Example: "I shoot around 92. I tracked my last 5 rounds — fairways hit, GIR, putts. How do I tell if my problem is approach or putting?"

**course-management** — Question is about ON-COURSE decisions: target lines, club selection off the tee, risk/reward on a specific hole, playing to your miss.
Example: "Par-4 with water down the right and OB left at 230 yards. I usually hit driver 240 but spray it. Driver, 3-wood, or hybrid?"

**scoring-strategy** — User is chasing a specific SCORE threshold (break 100/90/80) or a handicap target; needs a level-specific roadmap of what to prioritize.
Example: "I've been stuck shooting 94-98 for a year. What are the two or three things a bogey golfer should focus on to break 90?"

### Skill Areas (where the shots are actually hit)

**short-game** — Problem is inside ~100 yards: wedges, chipping, bunkers, or putting technique/distance control.
Example: "I hit greens in 2 on par-4s but take 3 or 4 to get down from 30 feet. How do I build a lag-putting system?"

**practice-design** — User has a fixed amount of range/screen-golf time and needs to know HOW to practice effectively (blocked vs random, drills, transfer to course).
Example: "I get 2 hours at the range per week and a Golfzon session on Friday. How should I structure that time to actually lower my score?"

### Equipment & Body

**club-fitting** — Decision about clubs themselves: shafts, lofts, a 14-club setup, driver/iron replacement, or what to buy as a beginner.
Example: "I'm carrying driver, 3w, 5w, 4-PW, SW, putter. I hit my 4-iron terribly. Should I swap it for a hybrid and add a gap wedge?"

**physical-conditioning** — Goal is distance gains, flexibility, warm-up routines, or protecting a body part (back, shoulder, wrist) from golf-specific stress.
Example: "I'm 48, losing 10 yards on my driver each year, and my lower back tightens after 9 holes. What mobility and strength work helps?"

### Mind

**mental-game** — Problem is psychological: first-tee nerves, performance anxiety under pressure, tournament meltdowns, confidence, pre-shot routine.
Example: "I play great with my buddies but post 8 strokes worse in my club championship. How do I stop collapsing under pressure?"

---

## User Prompt Template

```
## Situation
{scenario}

## Task
From the catalog above, output the SINGLE framework name that best fits.

Answer (one word, lowercase):
```

---

## Routing Notes (for maintainers, not shown to LLM)

- **`strokes-gained` vs `scoring-strategy`**: `strokes-gained` is data-diagnostic (where are shots lost?). `scoring-strategy` is target-driven (what does a 90s-shooter prioritize?). When a user asks "what should I work on to break X", prefer `scoring-strategy`; when they want to analyze stats they already have, prefer `strokes-gained`.
- **`course-management` vs `mental-game`**: A strategy question about aim/club on a specific hole → `course-management`. A question about nerves, choking, or routine under pressure → `mental-game`. "Playing tomorrow, nervous" with no pressure component → `course-management`.
- **`practice-design` vs `short-game`**: If the focus is the TIME BUDGET and how to organize practice → `practice-design`. If the focus is the SKILL itself (wedge distance control, putting stroke) → `short-game`.
- **Swing mechanics are intentionally excluded**: Questions like "fix my slice" or "downswing path" should not be routed here — the SKILL.md deflects to professional lessons. Do not add a swing framework.
- **Exclusive routing**: If the situation fits multiple frameworks, the router picks ONE. Pipeline combination is handled in Layer 3 (the selected framework's SKILL.md may invoke others).
- **Not included here**: `golf` itself (this IS golf).

---

## Maintenance Protocol

Adding a new framework requires:
1. Add an entry to Framework Catalog above (name + when + example).
2. Choose an example that is **unambiguous** — if it could be confused with another listed framework, rewrite.
3. Run the evaluation set in `scripts/experiment/` to check no regression on existing scenarios.
