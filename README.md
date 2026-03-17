# VC Panel Evaluator

Simulate a real venture capital investment panel evaluating your startup. Researches actual investors in your sector, builds personalized personas from their investment thesis and portfolio, runs parallel evaluations from each VC's perspective, and synthesizes a Monday partner meeting with funding verdict, feedback, and pitch coaching.

## Install

```
/plugin marketplace add JuanMarchetto/agent-skills
/plugin install vc-evaluator@agent-skills
```

Or via [skills.sh](https://skills.sh):
```bash
npx skills add JuanMarchetto/vc-evaluator-skill
```

Or manually:
```bash
git clone https://github.com/JuanMarchetto/vc-evaluator-skill.git
cp -r vc-evaluator-skill ~/.claude/skills/vc-evaluator
```

## How It Works

```
"Would VCs fund this? B2B SaaS for construction logistics, raising seed"
                            |
              Startup Discovery (code, pitch, traction, team)
                            |
              Investor Research (real VCs in sector/stage, thesis, portfolio)
                            |
              Build 3-5 Investor Personas (from real people or archetypes)
                            |
              Parallel Evaluation (each VC evaluates independently)
                            |
              Partner Meeting Synthesis (simulate Monday meeting)
                            |
              Verdict + Scorecard + Pitch Coaching
```

Each investor evaluates independently as a parallel agent, then a synthesizer simulates the Monday partner meeting — who champions the deal, what gets debated, and whether a term sheet is likely.

## What You Get

- **Funding Verdict** — PASS / PARTNER MEETING / TERM SHEET LIKELY
- **Panel Scorecard** with per-criterion scores from each investor (Team, Market, Product, Traction, Moat)
- **Individual VC Feedback** — what impressed them, deal-breakers, questions they'd ask in the pitch
- **Partner Meeting Simulation** — who champions, who passes, key debates, and the outcome
- **Funding Probability** — X% chance at your target stage with current pitch
- **What Would Change The Outcome** — max 5 specific actions to move investors from pass to proceed
- **Pitch Coaching** — tailored to this specific panel's priorities

## Example

```
VC PANEL EVALUATION
Startup: ConstructFlow
Stage: Seed
Sector: B2B SaaS / Construction Tech

VERDICT: PARTNER MEETING
Funding Probability: 35% at Seed

| Criterion        | Weight | Sarah Chen (Infra) | Marcus Webb (SaaS) | Priya Patel (Generalist) | Avg  |
|------------------|--------|--------------------|---------------------|--------------------------|------|
| Team             | 40%    | 7                  | 8                   | 6                        | 7.0  |
| Market           | 25%    | 8                  | 7                   | 8                        | 7.7  |
| Product          | 15%    | 7                  | 6                   | 7                        | 6.7  |
| Traction         | 10%    | 5                  | 6                   | 5                        | 5.3  |
| Moat             | 10%    | 6                  | 5                   | 5                        | 5.3  |
| **Overall**      |        | **7.0**            | **6.9**             | **6.5**                  | **6.8** |

PARTNER MEETING SIMULATION:
Sarah champions — she's seen the construction tech pain firsthand through her
portfolio company BuildOS. Marcus is cautiously positive but wants to see retention
data. Priya would pass — she thinks the team needs a construction industry veteran
as a co-founder. After 20 minutes of debate, they'd invite founders in for a
partner meeting, conditional on seeing 3-month cohort data.

WHAT WOULD CHANGE THE OUTCOME:
1. Add a co-founder with 10+ years in construction operations
2. Show 3-month retention cohorts from pilot customers
3. Get 3 signed LOIs from mid-size general contractors
4. Demonstrate 2x MoM growth over the next quarter
5. Secure a strategic angel from the construction industry

INDIVIDUAL FEEDBACK:
  Sarah Chen (Infra VC):
  ✓ "Construction tech is a $1.8T industry with 1990s software"
  ✗ "No construction veteran on the team — who closes enterprise deals?"

  Marcus Webb (SaaS):
  ✓ "Clean B2B metrics structure — they understand unit economics"
  ✗ "Show me retention, not signups. Where's the 3-month cohort data?"

PITCH COACHING:
  1. Lead with the pain: "GCs lose 30% of project margin to scheduling chaos"
  2. Demo the mobile app live — judges want to see the foreman UX
  3. Name-drop pilot customers (social proof > slide deck)
```

## Requirements

- WebSearch capability (for researching real investors and their thesis)
- Agent tool (for parallel investor dispatch)

## License

[MIT](LICENSE)
