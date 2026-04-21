# Brew groups: E61, saturated, thermoblock, and others

The brew group is the business end of an espresso machine — where hot, pressurized water meets the coffee puck. After the boiler architecture, it's the second-most consequential design choice. The group determines warmup time, temperature-stability behavior, pre-infusion character, whether flow-control mods are possible, and how the machine *feels* to use.

## The Faema E61 — the group that defined the category

The E61 brew group was designed by **Ernesto Valente** and released by **Faema** of Milan in 1961. Its name commemorates the total solar eclipse of **February 15, 1961** (*eclissi*, abbreviated E61) — a bit of mid-century Italian industrial romance that stuck.

What made the E61 revolutionary at launch:

- **First commercial use of an electric volumetric pump** (9 bar) instead of spring-lever or manual piston pressure. Before the E61, espresso was a lever-pulled drink; the E61 is why the pump machine exists.
- **Integrated heat exchanger** — cold water from the reservoir passes through a coil immersed in the steam boiler, heating to brew temp on its way to the group. This was the first practical HX implementation.
- **Mechanical pre-infusion chamber** — a small internal cavity with a spring-loaded valve. When the lever is raised, line pressure (~1-3 bar) first fills the chamber and gently wets the puck. Only when the chamber fills does full 9-bar pump pressure engage. This pre-infusion happens purely by mechanical design, no electronics required.
- **Thermosiphon circulation** — a passive convection loop that continuously pulls hot water from the boiler through the group head and back. This keeps the heavy brass group at brew temperature without needing its own heater.
- **Three-way solenoid valve** — releases pressure from the puck into a drain line when the shot ends, producing a dry puck instead of a slurry.

Faema didn't tightly license the design, and over 65 years the E61 group became a de facto industry standard. Dozens of manufacturers (Profitec, ECM, Rocket, Quick Mill, Lelit, Bezzera, Vibiemme, and many more) build machines around E61-compatible groups, either sourced from Faema or from third-party Italian foundries. Shower screens, gaskets, mushrooms, and flow-control kits are interchangeable across brands. The original design is essentially unchanged — buy a Profitec Pro 600 in 2026 and the group head is mechanically equivalent to a 1961 Faema.

**In this wiki, E61 machines include:** Profitec Pro 400, Pro 600, Ride; ECM Classika PID, Synchronika II; Rocket Appartamento, Mozzafiato R; Quick Mill Alexia Evo, Andreja Premium Evo, QM67 Evo; Lelit Bianca.

**Characteristics of the E61:**

- **~4 kg of chromed brass** — massive thermal mass, slow warmup (15-25 min from cold), excellent idle stability once hot.
- **Thermosiphon feed means the group has no heater of its own** — it takes its temperature from the boiler via convection. On HX machines this produces the characteristic cooling-flush ritual; on DB machines a properly designed thermosiphon largely eliminates it.
- **Mechanical pre-infusion is built in** — soft wet-up for 3-4 seconds on every shot, no programming needed. This is a big part of why E61 shots "feel" different than saturated-group shots.
- **Massive modding ecosystem** — flow-control kits (Slayer-style needle valves, paddle conversions), pressure gauges, aftermarket shower screens (IMS), bottomless portafilters, steam tip upgrades.
- **Serviceable for decades** — E61 gaskets are a $10 replacement you'll do every few years; groups are rebuildable indefinitely.

## Saturated groups

A saturated group is directly bolted to (or integrated into) the brew boiler, so the group body itself is always full of brew-temperature water. There's no thermosiphon loop and no independent group-heating mechanism — the group simply *is* part of the boiler.

The saturated architecture was pioneered by **La Marzocco** (founded 1927 in Florence by the Bambi brothers) and popularized by the **Linea** commercial machine in the 1990s. La Marzocco's insight was that the thermosiphon — while elegant — introduces thermal lag between the boiler and the group. Putting the group *inside* the thermal loop eliminates that lag entirely.

**Characteristics of saturated groups:**

- **Faster warmup** (8-15 min) because there's less independent mass to bring up to temp.
- **No cooling flush needed**, ever. Temperature at the screen equals temperature in the boiler.
- **No mechanical pre-infusion** — the design doesn't have a spring-chamber, so pre-infusion must be provided electronically (programmable pump ramp) or via a paddle/valve.
- **Simpler plumbing** — fewer parts, fewer potential failure points.
- **Smaller modding ecosystem** — saturated groups tend to be manufacturer-specific, so you can't cross-fit aftermarket parts the way you can on E61.
- **Often smaller and lighter** than E61 machines of equivalent capability — the saturated group itself is more compact than a freestanding E61 head.

**In this wiki, saturated-group machines include:** Lelit Elizabeth V3, Profitec Pro 300, Profitec Move. The Breville Dual Boiler (BES920XL) uses a similar-in-spirit arrangement, though Breville doesn't market it with the "saturated" terminology.

## Thermoblocks

A thermoblock is a small aluminum or brass block with serpentine channels machined through it and electric heating elements bonded to it. Water flows through on demand and is heated as it passes — there is effectively no "boiler," only a heated block with a tiny water volume inside at any moment.

**Characteristics:**

- **Near-instant warmup** (seconds to a few minutes) because there's no water reservoir to heat.
- **Near-instant transitions** between brew and steam modes — the block can change setpoint in seconds.
- **Temperature stability depends on flow rate and timing** — a fast-flowing shot can cool the block faster than it can keep up, producing a temperature slope during extraction.
- **No thermal buffer** — idle behavior and recovery are fundamentally different from boiler-based machines.
- **Very compact** — the whole heating apparatus can be the size of a paperback book.

**In this wiki, thermoblock machines include:** Breville Bambino Plus. It's the one "outlier" architecture in the single-boiler tier.

Thermoblocks dominate the sub-$500 consumer segment (Breville, De'Longhi, Philips) because they're cheap to manufacture and solve the warmup problem users care about. Prosumer machines almost universally avoid them because the temperature-stability compromise matters at the quality level prosumer buyers are targeting.

## Proprietary / "ring" groups

A newer category that blurs the saturated/thermoblock boundary. These are small, purpose-designed direct-heated groups paired with compact boilers, unique to each manufacturer and not cross-compatible with E61 accessories.

- **Profitec Go** uses a proprietary "ring" group with a small integrated pre-infusion chamber.
- **Quick Mill Pop Up** uses a "ring" brew group that Clive Coffee and other US retailers describe as saturated — the terminology overlap suggests the design sits in the saturated family but isn't a La Marzocco-style integrated group.

These groups prioritize compactness, lower manufacturing cost, and faster warmup over modding potential. If you own one, you're mostly limited to basket and portafilter swaps — no flow-control kits, no aftermarket shower screens to speak of.

## Flash heaters and software-defined groups

A further step away from traditional boiler architecture: the **Decent DE1Pro** uses flow-through flash heating with closed-loop software temperature control. Water is heated as it moves through the machine based on real-time temperature sensing; the pump, flow, pressure, and temperature are all computer-controlled simultaneously.

**Characteristics:**

- **Warmup under 5 minutes**.
- **Software-defined profiles** — temperature, flow rate, and pressure can follow arbitrary curves during a single shot.
- **No thermal mass means no "feel"** — the machine responds entirely to its sensors, not to the physics of hot metal.
- **Single-vendor ecosystem** — firmware updates, profile sharing, community-developed workflows are the mod path.

## Lever groups (out of scope for this wiki)

Worth naming for completeness: **manual lever groups** (La Pavoni, Olympia Cremina, ECM Classika Leva) use a human-powered piston to generate brew pressure, with pre-infusion controlled by how the operator moves the lever. Beautiful machines with a devoted following. Not represented on this wiki because they're a different skill category entirely and the user's "upgrade from Mr. Coffee" journey doesn't point there.

## How to choose

| You want | Group type |
|---|---|
| Stock mechanical pre-infusion, huge mod ecosystem, classic feel | E61 |
| Fastest warmup among boiler machines, compact, no cooling flush | Saturated |
| Sub-minute warmup at the cost of thermal stability | Thermoblock |
| Compact modern machine, don't care about modding | Proprietary/ring |
| Full software control over pressure/flow/temperature | Flash heater (Decent) |
| Manual pre-infusion by hand, ritual | Lever (not in this wiki) |

**For this user** (upgrading from Mr. Coffee, even milk/espresso split, $3,000 budget): E61 and saturated are both reasonable, with the choice coming down to warmup tolerance (saturated is faster) and modding appetite (E61 is deeper). The current top picks in the buyer's guide — Lelit Elizabeth V3 (saturated) and Lelit Bianca V3 (E61 with paddle flow control) — represent the two strong answers.
