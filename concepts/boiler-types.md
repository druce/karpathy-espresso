# Boiler types: single boiler, heat exchanger, dual boiler

The boiler architecture is the single most consequential design choice in an espresso machine — it determines workflow, temperature stability, size, warmup time, price, and energy draw. Everything else is downstream.

## Single boiler (SB)

One boiler. It heats water to brew temperature (~93 °C) or steam temperature (~130 °C), but not both at the same time.

**Workflow:** Pull shot → flip to steam mode → wait 30-60 seconds for boiler to rise → steam milk → (if pulling another shot) flush cold water through the group to drop back to brew temp → wait.

**Tradeoffs:**

- **+** Cheapest tier. Most machines under $1000 are SB.
- **+** Small footprint, low weight, fast warmup (5-10 min).
- **+** With a PID (factory or modded), brew-temp stability is genuinely good.
- **-** Serial workflow. Making two cappuccinos back-to-back is tedious.
- **-** Steam power is modest. Milk for one cup is fine; two in a row, less so.
- **-** Cycling between brew and steam modes adds mental overhead.

**Who it's for:** Solo drinker, one or two drinks per session, doesn't mind a deliberate workflow, wants to learn espresso without overspending.

**Machines in this wiki:** Gaggia Classic Pro, Rancilio Silvia, Lelit Anna, Profitec Go, Breville Bambino Plus.

The Bambino Plus is the odd one out — it uses a thermoblock instead of a small boiler, giving near-instant steam and brew transitions at the cost of absolute stability.

## Heat exchanger (HX)

One boiler holds water at steam temperature continuously. A copper tube passes through the boiler carrying cold water from the reservoir directly to the group; as it transits the hot boiler, it heats up to brew temperature on the way. So steam is always ready, and brew water is generated on demand.

**Workflow:** Pull shot and steam simultaneously (one lever, one knob, both work). For the first shot after an idle period, pull a "cooling flush" — a few ounces of water through the group — to stabilize brew temperature before locking in the portafilter.

**Tradeoffs:**

- **+** Simultaneous brew and steam. This alone is a huge quality-of-life upgrade.
- **+** Powerful continuous steam.
- **+** Always-ready steam; no mode switching.
- **+** Thermosiphon plumbing with an E61 group is a mature, serviceable architecture. Many HX machines last decades.
- **-** Brew temperature is indirect. It depends on boiler temp, flow rate, and idle time. A cooling flush is usually required after idle periods.
- **-** Brew temperature is "set" implicitly by boiler pressure, not set directly. Fine-tuning means adjusting the pressurestat. Less convenient than a dual boiler's PID.
- **-** Larger and heavier than single boilers. Warmup 15-25 min.

**Who it's for:** Two-person household, both drinking espresso or milk drinks, wants commercial-style steaming without dual-boiler pricing, comfortable with a light flushing ritual.

**Machines in this wiki:** Rocket Appartamento, Lelit Mara X, ECM Classika.

The Lelit Mara X sits at an interesting spot: it has an HX but also a PID that actively manages the thermosiphon to reduce the need for cooling flushes. It's the most "dual-boiler-like" HX on the list.

## Dual boiler (DB)

Two separate boilers. One runs at brew temperature; the other at steam temperature. A PID controls each independently.

**Workflow:** Turn on, wait ~15-25 min, pull shot and steam milk in either order, never flush.

**Tradeoffs:**

- **+** Best brew temperature stability at any price. No flushing, no compromise.
- **+** Simultaneous brew and steam; steam is always at temperature.
- **+** Brew temperature is explicitly set by PID to 0.5 °C precision — easy to experiment with.
- **+** Commercial-grade performance in a domestic package.
- **-** Most expensive tier. Entry DB starts around $1400 (Breville), real prosumer DBs start around $1600-$2000.
- **-** Biggest, heaviest. Several in this range are tight under a standard 16" cabinet.
- **-** Higher energy draw at idle (two boilers to maintain).
- **-** More internal complexity → more potential failure points over 10+ years.

**Who it's for:** Daily driver for a household that wants the workflow to be instantaneous and the temp stability to be unconditional. Light-roast drinkers. People who'll keep the same machine for 10+ years.

**Machines in this wiki:** Breville BES920XL, Profitec Pro 300, Profitec Pro 400, Lelit Elizabeth, Profitec Pro 600, Rocket Mozzafiato R, ECM Synchronika, Lelit Bianca, Decent DE1Pro.

The Decent DE1Pro doesn't use traditional boilers — it uses thermoblock-style flash heaters with software temperature control. Functionally it behaves like a high-stability DB with full pressure/flow/temperature profiling, and is grouped here because it competes at the same price point for the same buyer.

## How to choose

| You want | Go here |
|---|---|
| Lowest-cost way to learn real espresso | Single boiler (Gaggia Classic Pro, Silvia) |
| One milk drink per morning, compact | Single boiler with good PID (Lelit Anna) or Bambino Plus |
| Two milk drinks back to back, no waiting | HX minimum, DB is better |
| Light-roast espresso, precise temp control | Dual boiler |
| Pressure or flow profiling | Lelit Bianca, Decent, or mod a Pro 600/Synchronika |
| Commercial workflow at home, pro steam | HX or DB with E61 group |
| Plumbed in | Only some DB machines (check individual pages) |

Given this user's even-split use case (milk drinks and espresso in equal measure), HX is the minimum sensible tier and DB is the default recommendation.
