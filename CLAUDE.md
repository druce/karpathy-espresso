# Espresso Machine Research Wiki

## What this is

A research wiki for purchasing an espresso machine as an upgrade from a Mr. Coffee One-Touch. Budget $300-$3,000 (machine only). Target user drinks milk drinks and espresso in roughly even measure and already owns a Eureka Mignon Specialita grinder. Standard US kitchen: 110V, no plumbing, ~16" under-cabinet clearance.

## Wiki structure

```
/
├── README.md                          # landing + comparison table
├── CLAUDE.md                          # this file
├── buyer-guide.md                     # opinionated picks
├── images/                            # local product shots (one per machine, slug-named)
├── concepts/
│   ├── espresso-basics.md
│   ├── boiler-types.md
│   ├── steam-wands-and-milk.md
│   └── pid-flow-pressure.md
├── machines/
│   ├── _template.md
│   └── [one .md per machine]
└── sources/
    └── reviewer-index.md
```

## Images

- Product shots live in `/images/` as `<slug>.jpg` (or `.png`) matching each machine page's filename.
- Machine pages reference images with the relative path `../images/<slug>.<ext>` — this works in both Obsidian and GitHub's rendered markdown.
- When adding a new machine, download the image locally (rather than hotlinking) using curl with a browser User-Agent. Don't use retailer product-page URLs; use direct image URLs (look for `og:image` meta tags or `product-image` elements).
- Images are manufacturer/retailer product shots used for personal research/reference — fair use for a non-commercial wiki. For a public repo, this is the standard norm for coffee-gear documentation but noted here for awareness.

## Editorial conventions

- **Neutral per-machine pages, opinionated buyer-guide.** Machine pages stick to facts, reviewer quotes, specs, and balanced pros/cons. The buyer-guide makes clear picks and calls out overrated/underrated machines.
- **Target length:** ~800-1,200 words per machine page.
- **Always list:** image link, price (MSRP + street), dimensions, weight, warmup, PID status, flow control, plumbable, fits-under-16"-cabinet.
- **Always link:** Whole Latte Love / Clive Coffee / Seattle Coffee Gear / Chris' Coffee / relevant retailer, plus at least 2 reviewer links and 1-2 forum threads per machine.
- **Grinder pairing note:** framed around the Specialita (won't bottleneck anything; mention when a single-dose upgrade would add meaningful value).
- **Flag counter-fit concerns:** any machine >15.5" tall gets a "Tight" or explicit "measure carefully" note.

## Research conventions

- Verify boiler architecture before categorizing. Several machines have confusing classifications:
  - **Profitec Pro 400** is an HX, not DB, despite the "Pro" naming pattern
  - **Rocket Mozzafiato Evoluzione R** is HX with rotary pump, not DB
  - **ECM Classika PID** is technically single-boiler E61 (no simultaneous brew+steam), commonly grouped with HX
  - **Lelit Elizabeth**, **Profitec Pro 300**, **Profitec Move** use saturated groups, not E61
- **Quick Mill Alexia Evo** is E61 single-boiler (despite the Alexia naming overlap with saturated-group single boilers elsewhere)
- **Quick Mill Andreja Premium Evo** is HX (1.8 L single boiler with E61 thermosiphon); at 16" height, it exceeds under-cabinet clearance
- **Quick Mill QM67 Evo** is DB E61 at 16.25" — exceeds the 16" under-cabinet constraint
- Cross-check retailer marketing copy against the actual spec sheet and forum owner reports.
- When retailers disagree on pricing, use the consistent street price; fall back to MSRP if unclear.
- Profitec is in a model transition (Pro 300 → Move, Pro 600 → Ride); some machines are being phased out.

## Machine list

### Single boiler ($300-$1,300)
- Breville Bambino Plus (thermoblock, outlier)
- Gaggia Classic Pro
- Lelit Anna PL41TEM
- Rancilio Silvia M V6
- Profitec Go
- Quick Mill Alexia Evo (saturated group)

### Heat exchanger ($1,500-$3,100)
- Lelit Mara X (PL62X)
- Profitec Pro 400
- Rocket Appartamento
- ECM Classika PID (actually single-boiler E61, convention places it here)
- Quick Mill Andreja Premium Evo
- Rocket Mozzafiato Evoluzione R

### Dual boiler ($1,600-$3,700)
- Breville Dual Boiler (BES920XL)
- Profitec Pro 300 (phase-out; being replaced by Move)
- Profitec Move (saturated group, compact DB)
- Lelit Elizabeth (PL92T V3)
- Profitec Pro 600 (phase-out; being replaced by Ride)
- Profitec Ride (E61 DB, 2024-2025 successor to Pro 600)
- Quick Mill QM67 Evo
- ECM Synchronika II
- Lelit Bianca V3
- Decent DE1Pro (software / flash heater, unique category)

## Per-machine page template

See `machines/_template.md` for the canonical template. Required sections:
1. Header image, positioning sentence
2. Quick-facts table (type, MSRP, street price, dimensions, weight, warmup, PID, flow control, steam wand, portafilter, plumbable, fits-under-16")
3. Specs (boiler, pump, group, reservoir, wattage, voltage, build)
4. Key features
5. Steam and milk workflow
6. Brew workflow and temperature stability
7. Grinder pairing (specific to Specialita)
8. Complexity and learning curve
9. Modification and upgrade potential
10. Pros and cons
11. Key reviews and references (2-3 links with 1-line summary)
12. Notable forum threads (1-2 links)
13. Who it's for (who should buy, who should look elsewhere)
14. Where to buy (retailer links)

## User context reminders

- Don't write marketing copy. Be honest about tradeoffs.
- When adding new machines, re-evaluate the buyer-guide — new entries may shift tier recommendations.
- The comparison table in README.md must stay synchronized with the machines/ directory.
- Prefer current-year street prices; flag when a machine is being phased out.
