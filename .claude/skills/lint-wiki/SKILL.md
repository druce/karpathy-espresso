---
name: lint-wiki
description: Use when auditing the espresso wiki for drift — after adding or editing machines, before publishing, or on periodic review. Catches orphaned pages, broken image paths, README/CLAUDE.md/machine-page inconsistencies, boiler-type mismatches, template compliance gaps, and stale prices.
---

# lint-wiki

Audit the espresso-machine research wiki for the drift Karpathy's LLM-wiki methodology warns about: orphan pages, contradictions across pages, missing cross-references, stale claims, and schema inconsistencies. Project-specific to this repo's structure (`machines/`, `concepts/`, `images/`, `README.md`, `CLAUDE.md`, `buyer-guide.md`).

## When to use

- After adding a new machine page (highest value — most drift happens here)
- After editing `CLAUDE.md`, `README.md`, or `_template.md` (schema changes ripple)
- Periodic review (monthly) to catch stale prices and dead links
- Before sharing the repo publicly

Do NOT use for editorial judgment (tone, tier recommendations, whether a machine belongs). Lint is mechanical checks only.

## Workflow

Run the checks in order. Report findings grouped by severity: **blocker** (file missing, broken reference), **drift** (two sources disagree), **advisory** (stale, missing optional link). Only edit files if the user confirms — lint reports, it does not auto-fix.

### 1. File ↔ listing consistency (blockers)

The canonical machine list lives in `CLAUDE.md` under "## Machine list". It must stay synchronized with files and with `README.md`.

- Every `machines/*.md` except `_template.md` appears in `CLAUDE.md`'s Machine list
- Every machine in `CLAUDE.md`'s list has a `machines/<slug>.md` file
- Every machine page is linked from `README.md`'s comparison table
- Every `README.md` table row points to a file that exists
- Every machine page has `images/<slug>.{jpg,png}` (same slug as the .md file)
- Every image in `images/` is referenced by a machine page (orphans)

Use `Glob` for file lists, `Grep` on `CLAUDE.md` and `README.md` for the canonical lists.

### 2. Template compliance (drift)

Source of truth is `machines/_template.md`. Every machine page must contain these 12 H2 headers verbatim:

`Key features`, `Quick facts`, `Steam and milk workflow`, `Brew workflow and temperature stability`, `Grinder pairing`, `Complexity and learning curve`, `Modification and upgrade potential`, `Pros and cons`, `Where to buy`, `Key reviews, videos and references`, `Notable forum threads`, `Who it's for`

Check: `Grep '^## (Key features|Quick facts|...)' machines/ --count` should return 12 per file. Also verify each page:
- Starts with H1 title linking to manufacturer
- Has a `> ` blockquote positioning sentence on line 2-ish
- Has `![...](../images/<slug>.<ext>)` image reference near the top (relative path, not URL)
- Quick facts table contains rows: Type, MSRP, Street price, Dimensions, Weight, Warmup, PID, Flow/pressure control, Steam Wand, Group, Portafilter, Reservoir, Plumbable, Fits under 16" cabinet, Boiler(s), Pump, Build

### 3. Cross-page consistency (drift — highest value)

- **Boiler type match**: the `**Type**` row in each machine page must match the "Type" column in the `README.md` comparison table. Compare semantically, not by exact string: "HX (E61)" in README can match "Heat exchanger, E61" on the page.
- **Boiler-type gotchas** from `CLAUDE.md` (verify explicitly — these are easy to get wrong):
  - Profitec Pro 400 → HX (not DB)
  - Rocket Mozzafiato Evoluzione R → HX with rotary pump (not DB)
  - ECM Classika PID → single-boiler E61 (commonly grouped with HX by convention)
  - Lelit Elizabeth, Profitec Pro 300, Profitec Move → saturated group (not E61)
  - Quick Mill Alexia Evo → E61 single boiler
  - Quick Mill Andreja Premium Evo → HX, 16" height (exceeds under-cabinet)
  - Quick Mill QM67 Evo → DB E61, 16.25" height (exceeds)
- **Height flags**: any machine with H ≥ 15.5" must be marked "Tight" or "Exceeds" in `README.md`'s W×D×H column. Cross-check against the machine page's Dimensions row.
- **Phase-out notes**: Profitec Pro 300 and Pro 600 should carry phase-out notes in `README.md` (succeeded by Move and Ride respectively).
- **Schema drift between `CLAUDE.md` and `_template.md`**: `CLAUDE.md`'s "Per-machine page template" required-sections list must match the actual H2 headers in `_template.md`. (Currently drifts: `CLAUDE.md` lists 16 sections with a separate "Specs" block; `_template.md` folds specs into the Quick facts table, giving 12 sections. Flag this.)

### 4. Buyer-guide synchronization (drift)

- Every machine mentioned in `buyer-guide.md` must exist in `machines/`
- New machines added to `CLAUDE.md` since the last buyer-guide update should be considered for tier inclusion — flag as advisory, do not auto-edit

### 5. Price and date freshness (advisory)

- `README.md` declares "Prices are April 2026 street". Check the current date (from environment) — flag if > 90 days stale.
- Each machine page's "Street price" should include a year stamp (e.g., "as of 2026"). Flag pages missing it.
- When README and the machine page disagree on street price, report both — do not pick a winner.

### 6. Link hygiene (advisory)

- Each machine page should have: ≥1 manufacturer URL in the H1, ≥1 retailer under "Where to buy", ≥2 reviewer links under "Key reviews", ≥1 forum thread.
- Do NOT fetch URLs to check for 200s unless the user asks — it's slow and most lint passes don't need it. Offer it as a follow-up.

### 7. Concept cross-references (Karpathy orphan check)

- Every concept page in `concepts/` is linked from at least one machine page or from `README.md`.
- Terms like "E61", "PID", "HX" / "heat exchanger", "pre-infusion", "flow control" appearing in machine pages should link to the relevant `concepts/*.md` at least on first use per page — flag missing links as advisory (low priority, lots of noise).

## Reporting format

Output a single markdown report with four sections. Keep it scannable — one line per finding, file paths with line numbers where applicable.

```
## Blockers (N)
- `machines/foo.md:12` — missing H2 "Key features"
- `images/bar.jpg` — orphan, no machine page references it

## Drift (N)
- `README.md:74` vs `machines/profitec-pro-400.md:17` — type mismatch: "HX (E61)" vs "Heat exchanger, E61" [semantic match, OK]
- `CLAUDE.md:104` vs `machines/_template.md` — schema drift: CLAUDE.md lists 16 sections, template has 12

## Advisory (N)
- `README.md:62` — "Prices are April 2026 street" is 73 days old
- `buyer-guide.md` — has not been re-evaluated since Quick Mill Pop Up was added

## Clean (summary)
- 23/23 machine pages have all 12 required sections
- 23/23 machine pages have valid image references
- 23/23 boiler types match between README and machine pages
```

Stop after reporting. Ask the user which findings to fix before touching files.

## Known-clean baseline (as of 2026-04-21)

When this skill was written, the repo passed checks 1, 2, and 3 (file consistency, template compliance, boiler types all match). The only real drift was the `CLAUDE.md` ↔ `_template.md` section-count mismatch. Use this as a sanity check: if your pass reports lots of blockers in areas previously clean, suspect your check logic before suspecting the repo.

## Common mistakes

- **Auto-fixing without asking.** Lint reports. Edits require a separate confirmation.
- **Treating semantic type matches as drift.** "HX (E61)" in README and "Heat exchanger, E61" on the page are the same thing — normalize before comparing.
- **Flagging every unlinked "PID" mention.** Cross-reference noise buries real findings. Only flag first use per page, and only if the page has zero links to the relevant concept page.
- **Fetching every URL.** Slow and flaky. Do it only when the user asks for a link-rot pass specifically.
- **Using ripgrep or grep from Bash.** Use the Grep tool — it's the one configured for this session.
