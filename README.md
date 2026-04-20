# Espresso Machine Research Wiki

Example research flow usinng Karpathy's wiki methodology
- Create a CLAUDE.md with Claude's  (15 minutes)
  - Prompt: help me make a CLAUDE.md to research <detailed question> using Karpathy's methodology, see https://x.com/karpathy/status/2039805659525644595 and https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f and https://www.mindstudio.ai/blog/andrej-karpathy-llm-wiki-knowledge-base-claude-code 
- Claude Code: Please ask any additional questions and create the wiki per @Claude.md (Claude crunches for 30 minutes)
- Edit wiki in Obsidian, ask Claude Code to fix any issues, answer additional questions (see `transcript.md` - 15 minutes)

Task: research moving from a Mr. Coffee One-Touch to a prosumer espresso machine. Budget $300-$3000, even split between milk drinks and espresso, grinder already sorted (Eureka Mignon Specialita). Standard US kitchen: 110V, no plumbing, ~16" under-cabinet clearance.

## Start here

- [Buyer's guide](buyer-guide.md) — opinionated picks by tier, skill, and priority
- [Espresso basics](concepts/espresso-basics.md) — pressure, temperature, extraction
- [Boiler types explained](concepts/boiler-types.md) — single boiler vs heat exchanger vs dual boiler
- [Steam wands and milk](concepts/steam-wands-and-milk.md) — panarello vs single-hole vs commercial
- [PID, flow, pressure](concepts/pid-flow-pressure.md) — what they control and why it matters

## Machines

### Single boiler (entry prosumer, $400-$1,600)

One boiler heats both brew water and steam — not at the same time. Fine for solo drinkers making one or two milk drinks in sequence; tedious for back-to-back lattes.

- [Breville Bambino Plus](machines/breville-bambino-plus.md) — thermoblock outlier, auto-steam
- [Gaggia Classic Pro](machines/gaggia-classic-pro.md)
- [Lelit Anna PL41TEM](machines/lelit-anna.md)
- [Rancilio Silvia](machines/rancilio-silvia.md)
- [Profitec Go](machines/profitec-go.md)
- [Quick Mill Alexia Evo](machines/quick-mill-alexia-evo.md) — single-boiler with stock E61 group

### Heat exchanger ($1,700-$3,100)

One boiler serves steam continuously; brew water passes through a heat exchanger inside it. Simultaneous brew+steam, but brew-temp stability depends on flushing / idle time.

- [Profitec Pro 400](machines/profitec-pro-400.md)
- [Lelit Mara X (PL62X)](machines/lelit-mara-x.md)
- [ECM Classika PID](machines/ecm-classika.md) — actually a single-boiler E61, grouped here per convention
- [Rocket Appartamento](machines/rocket-appartamento.md)
- [Quick Mill Andreja Premium Evo](machines/quick-mill-andreja-premium-evo.md) — 16" height, tight under-cabinet fit
- [Rocket Mozzafiato Evoluzione R](machines/rocket-mozzafiato-r.md)

### Dual boiler ($1,600-$3,700)

Separate boilers for brew and steam. Best brew-temperature stability plus instant simultaneous steaming. Bigger, heavier, more expensive, but the workflow is strictly better once you're here.

- [Breville Dual Boiler (BES920XL)](machines/breville-bes920xl.md)
- [Lelit Elizabeth (V3)](machines/lelit-elizabeth.md)
- [Profitec Pro 300](machines/profitec-pro-300.md) — phase-out; succeeded by Move
- [Profitec Move](machines/profitec-move.md) — 2024-2025 successor to Pro 300, saturated group
- [Profitec Pro 600](machines/profitec-pro-600.md) — phase-out; succeeded by Ride
- [Quick Mill QM67 Evo](machines/quick-mill-qm67-evo.md) — **16.25" height, exceeds under-cabinet clearance**
- [Profitec Ride](machines/profitec-ride.md) — 2024-2025 successor to Pro 600, E61
- [Lelit Bianca (V3)](machines/lelit-bianca.md)
- [ECM Synchronika (II)](machines/ecm-synchronika.md)
- [Decent DE1Pro](machines/decent-de1pro.md)

## Comparison table

Prices are April 2026 street (USD). All machines listed are 110V US variants. "**Tight**" in the height column means 15.5"+ — verify your cabinet clearance before buying.

| Machine | Type | Street | Warmup | W×D×H (in) | Weight | PID | Flow control | Plumb |
|---|---|---|---|---|---|---|---|---|
| [Breville Bambino Plus](machines/breville-bambino-plus.md) | Thermoblock | $399-499 | 3 sec | 7.7×12.6×12.2 | 11 lb | Yes | — | No |
| [Gaggia Classic Pro](machines/gaggia-classic-pro.md) | Single boiler | $449-549 | 5-10 min | 9.5×8.0×14.2 | 19 lb | Mod | Mod | No |
| [Lelit Anna](machines/lelit-anna.md) | Single boiler | $599-649 | 3-5 min | 9.0×10.3×13.4 | 16.5 lb | Yes | — | No |
| [Rancilio Silvia](machines/rancilio-silvia.md) | Single boiler | $900-995 | ~25 min | 9.2×11.0×13.4 | 30 lb | Mod | Mod | No |
| [Profitec Go](machines/profitec-go.md) | Single boiler (rotary) | $1,199 | 5-6 min | 8.3×14.5×14.9 | 29 lb | Yes | — | No |
| [Quick Mill Alexia Evo](machines/quick-mill-alexia-evo.md) | Single boiler (E61) | $1,550 | 10-12 min | 9.5×17.5×15.9 | 38 lb | Yes | FC kit | No |
| [Breville BES920XL](machines/breville-bes920xl.md) | Dual boiler | $1,599 | 15-20 min | 16.3×15.0×15.0 | 30 lb | Yes (dual) | Slayer Mod | No |
| [Profitec Pro 400](machines/profitec-pro-400.md) | HX (E61) | $1,699 | 5-10 min | 9.0×17.6×14.7 | 41 lb | Yes (3-preset) | FCD kit | No |
| [Lelit Mara X](machines/lelit-mara-x.md) | HX (E61, dual PID) | $1,699 | 8-10 min | 8.9×20.5×14.0 | 42 lb | Yes (3-preset) | X3 variant | Yes |
| [ECM Classika PID](machines/ecm-classika.md) | SB (E61) | $1,699-1,899 | 11-15 min | 9.8×17.8×15.8 | 46 lb | Yes (1°C) | FCD kit | Yes |
| [Lelit Elizabeth V3](machines/lelit-elizabeth.md) | Dual boiler (saturated) | $1,799 | ~15 min | 12.0×11.0×15.0 | 27 lb | Yes (dual) | Electronic PI | No |
| [Profitec Pro 300](machines/profitec-pro-300.md) | Dual boiler (saturated) | $1,799-1,929 | 8.5-10 min | 10.0×16.3×15.2 | 40 lb | Yes (dual) | Kit | No |
| [Rocket Appartamento](machines/rocket-appartamento.md) | HX (E61) | $1,850-2,050 | ~20 min | 10.8×16.7×14.2 | 48 lb | TCA only | Aftermarket | Yes |
| [Quick Mill Andreja Prem. Evo](machines/quick-mill-andreja-premium-evo.md) | HX (E61) | $1,850 | 10-15 min | 11.0×17.0×**16.0 Tight** | 46 lb | Optional | FC kit | Aftermarket |
| [Profitec Move](machines/profitec-move.md) | Dual boiler (saturated) | $1,999 | 9 min | 10.6×17.5×14.8 | 41 lb | Yes (dual) | — | No |
| [Profitec Pro 600](machines/profitec-pro-600.md) | Dual boiler (E61) | $2,399 | 10 min | 12.0×17.6×15.6 | 53 lb | Yes (dual) | FCD kit | No |
| [Quick Mill QM67 Evo](machines/quick-mill-qm67-evo.md) | Dual boiler (E61) | $2,395-2,495 | 12-15 min | 11.3×17.8×**16.25 Exceeds** | 50 lb | Yes (dual) | FC kit | No |
| [Profitec Ride](machines/profitec-ride.md) | Dual boiler (E61) | $2,599 | 8-10 min | 11.8×22.0×14.6 | 62 lb | Yes (dual) | FCD kit | No |
| [Lelit Bianca V3](machines/lelit-bianca.md) | Dual boiler (E61, paddle) | $2,999 | 10-12 min | 11.4×19.1×15.75 | 58 lb | Yes (dual) | **Paddle (stock)** | Yes |
| [Rocket Mozzafiato R](machines/rocket-mozzafiato-r.md) | HX (E61, rotary) | $3,100 | ~20 min | 11.0×16.75×15.75 | 67 lb | Yes | Aftermarket | Yes |
| [ECM Synchronika II](machines/ecm-synchronika.md) | Dual boiler (E61, rotary) | $3,599 | 6.5 min | 13.8×18.3×**16.3 Tight** | 55 lb | Yes (dual) | Aftermarket | Yes |
| [Decent DE1Pro](machines/decent-de1pro.md) | Software / flash heater | $3,699 | <5 min | 9.0×14.5×16.5 (w/ tablet) | 30 lb | Yes (software) | **Software** | Yes |

"—" = not available / not relevant. "Mod" = common aftermarket modification. "Tight" = at or above 16" height; confirm cabinet clearance. "**Exceeds**" = does not fit a standard 16" under-cabinet space; only buy if your counter has more clearance.

## Sources and reviewers

- [Reviewer index](sources/reviewer-index.md) — channels and outlets referenced throughout the wiki
