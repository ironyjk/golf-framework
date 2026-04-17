[한국어](README.ko.md) | **English**

# Golf Framework

A data-driven golf coaching system built on 8 evidence-based frameworks. No swing mechanics — this is golf played with your head. Routes your strategy, mental game, short game, and equipment questions to the right expert framework automatically. Powered by Broadie's Strokes Gained, DECADE course management, Rotella's mental game, Pelz's short game research, and TPI physical conditioning. Built with Korean amateur golf context (골프존/Golfzon screen golf, Korean handicap system) built in.

> Not a replacement for professional instruction. Consult a certified instructor for swing coaching.

## Installation

```bash
claude plugin install ironyjk/golf-framework
```

## Short Command Setup

After installation, add a wrapper command for `/golf`:

```markdown
# ~/.claude/commands/golf.md
---
description: "Golf coaching — 8 frameworks. Shortcut for /golf-framework:golf"
---
Invoke the skill `golf-framework:golf` with these arguments: $ARGUMENTS
```

See the [marketplace wrapper guide](https://github.com/ironyjk/claude-frameworks-marketplace) for details.

## Frameworks

| Command | Framework | Author / Method |
|---------|-----------|-----------------|
| `/golf` | Meta-router | Routes to the best 1–3 sub-frameworks |
| `strokes-gained` | Strokes Gained Analysis | Broadie SG model, SG Driving/Approach/ATG/Putting |
| `course-management` | Course Management | DECADE decision framework, miss bias strategy |
| `mental-game` | Mental Game | Rotella, pre-shot routine, pressure management |
| `short-game` | Short Game | Pelz research, chipping, pitching, bunker play |
| `practice-design` | Practice Design | Deliberate practice, blocked vs. random, skill transfer |
| `club-fitting` | Club Fitting | Static and dynamic fitting, 14-club optimization |
| `physical-conditioning` | Physical Conditioning | TPI (Titleist Performance Institute) movement screening |
| `scoring-strategy` | Scoring Strategy | Risk-reward, par management, round planning |

## Usage

```
/golf  I'm a 15-handicap. Where should I focus my practice time?
/golf  I always choke on the 18th hole. How do I manage pressure?
/golf  Should I hit driver or iron on a 380-yard dogleg left?
```

## License

[CC-BY-NC 4.0](LICENSE) — Free for personal/educational use. Commercial use requires permission: ironyjk@gmail.com

## Related

- `/fit` ([health-framework](https://github.com/ironyjk/health-framework)) for general fitness and conditioning
- `/think` ([strategy-frameworks](https://github.com/ironyjk/strategy-frameworks)) for decision-making frameworks
- [claude-frameworks-marketplace](https://github.com/ironyjk/claude-frameworks-marketplace) — all available frameworks
