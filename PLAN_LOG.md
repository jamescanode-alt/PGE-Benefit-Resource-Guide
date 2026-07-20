# PLAN_LOG

## 2026-07-20 — Build PG&E advisor field guide (Union + Management)

**Task.** Create a PG&E benefits resource site for new wealth advisors, modeled on the
AT&T Benefit Resource Guide (jamescanode-alt.github.io/ATT-Benefit-Resource-Guide/): same
single-page-per-population structure, sidebar nav, callouts, worked examples, interactive
calculator, glossary, contacts. Two populations: Union-represented (IBEW/ESC/SEIU 383) and
Management, Administrative & Technical (non-union). No references to any advisory firm — this
is a firm-neutral training reference.

**Sources.** `PGE_Union_Benefits_Advisor_Guide.docx` (existing Union-focused advisor summary —
used for structure/scope only; verified against source SPDs since several figures in it were
inaccurate), `All SPDs PGE Union.pdf` (511pp, 2014 SPD "Benefits Effective January 1, 2014" for
union-represented employees, retirement section pp.337-431 read in full), `All SPDs PGE
Management.pdf` (530pp, same-vintage SPD for Management/A&T employees, retirement section
pp.351-441), plus current IRS/SSA/Medicare figures verified via web search (2026: 402(g)
$24,500, catch-up $8,000/$11,250, 415(c) $72,000, IRMAA $109k/$218k, SS wage base $184,500, RMD
age 73→75 in 2033).

**Key corrections made vs. the source docx** (verified against SPD, not taken on faith):
- Union pension is officially the **"Final Pay Pension"**, not "Final Average Pay (FAP)" — that
  name belongs to the *Management* plan's formula instead.
- Cash Balance pay-credit table was understated by 1 point at every tier in the docx (SPD: <40
  pts=5%, 40-49=6%, 50-59=7%, 60-69=8%, 70-79=9%, 80+=10%; docx had 4/5/6/7/8/9/10 with an extra
  fabricated 80-89 tier).
  Interest credit is the **30-year Treasury average**, not a "GATT rate" (docx's term doesn't
  appear in the SPD).
- RMSA is far more than "interest accrual from 46" — it's a **$5,000/yr direct credit from age
  45**, plus $1,000/yr for service beyond 15 years, plus up to a $7,500 lump sum at retirement,
  4.5% compounding from 46, AND a **separate parallel account for the spouse/domestic partner**.
  Eligibility also requires 10+ years of Credited Service (for post-2004 terminations), which the
  docx omitted.
- Added the "Pop-Up" Special Joint Pension option and the 25/50/75/100% joint-pension tiers,
  which the docx didn't mention at all.
- 401(k) match for Final Pay participants (60% up to 3%/6% of pay by tenure) wasn't specified in
  the docx; sourced from SPD p.391.
- 2025-2026 forward-looking items in the docx (Roth 401(k) added to RSP, automatic in-plan Roth
  conversion) can't be verified against the 2014 SPD — flagged as unverified/to-confirm rather
  than stated as fact, with a note on why it's plausible (SECURE 2.0 Roth catch-up mandate).

**Risks.** The base SPD is a 2014 document; PG&E has certainly issued SMMs since then that this
project doesn't have. All dollar figures tied to statute (IRS limits, IRMAA, wage base) use
current 2026 figures instead of the stale 2014 SPD numbers; plan-design mechanics (formulas,
vesting, match %, RMSA structure) are presented as documented in the 2014 SPD with an explicit
"verify with the PG&E Pension Center" caveat, consistent with the AT&T guide's pattern.

**Next steps.** Build `index.html` (Union) → `management.html` (Management/A&T, once the
Management SPD extraction finishes) → preview both → push → CHANGE_LOG.

## 2026-07-20 (2) — management.html built from direct SPD verification (background agent failed)

**Task.** The background agent tasked with extracting Management SPD retirement details hit its
session limit before finishing. Rather than wait, personally read the Management SPD's Final
Average Pay Pension (pp.359-378), Cash Balance Pension (pp.381-395), Retirement Savings Plan
(pp.403-418), and Retiree Medical/RMSA/Postretirement Life Insurance (pp.433-441) sections
directly and built `management.html` from that primary-source reading.

**Key differences from the Union guide, confirmed against the SPD (not assumed by analogy):**
- Formula name and shape differ: "Final Average Pay Pension" (flat 1.7% × years × 36-month
  average salary), not "Final Pay Pension" (1.5%/1.6% split formula on near-retirement pay).
- Early-retirement reduction table has a **35-year full-exemption threshold** and an extra
  "30-34 years" band, vs. the union table's 30-year threshold and 4 bands. Verified the two
  tables share identical percentages in their overlapping columns (<15/15-24/25-29), only the
  top band differs — confirmed by cross-checking the SPD's own worked example, which uses
  identical numbers ($1,000 at 20 YOS) in both SPD books.
- 401(k) contribution range is 1%-50% of pay (Management) vs. 1%-20% (Union) — verified directly
  against both SPDs' "Enrolling in the Plan" sections after noticing the source docx's "1-20%"
  claim needed independent confirmation.
- 401(k) match structure is genuinely different in kind, not just rate: Management match is a
  flat $0.75/$1 for both formulas (6% cap for Final Average Pay, 8% for Cash Balance); Union
  match is 60 cents/$1 (Final Pay, 3%/6% cap by tenure) vs. $0.75/$1 (Cash Balance, 8% cap).
- Cash Balance mechanics (points table, interest methodology, vesting) and RMSA mechanics
  ($5,000/yr from 45, $1,000/yr past 15 YOS, $7,500 lump sum, 4.5% interest, spousal account)
  are identical across both populations — confirmed by finding the *same* "Sam" cash-balance
  example and "Joe & Jane" RMSA example, with matching dollar figures, in both SPD books.
- Postretirement Life Insurance is materially richer for tenured Management retirees (salary-
  linked, up to $50,000) vs. Union's flat $8,000 — added as its own callout in the RMSA section
  rather than a full new numbered section, to keep scope from ballooning.

**Files.** `management.html` (new, ~1050 lines), same design system as `index.html`. Wrapped all
10 tables in `.table-wrap` from the start (learned from the mobile-overflow bug found and fixed
in `index.html`) rather than discovering it again.

**Tests.** Local preview: retirement estimator calculator tested for the default case, the
30-34-year band (verifies Management's extra band produces a non-zero reduction where Union's
would already show 0%), and the 35-year exemption. Mobile viewport (375px): confirmed the page
itself has no real horizontal overflow (the table-wrap divs correctly scroll internally at
520px content width inside a 327px container). Dropdown cross-navigation to/from index.html
confirmed correct in both directions. Grepped the full repo for "farther" and "focus team"
(case-insensitive): zero matches.

**Risks.** Same 2014-SPD-vintage caveat as the Union guide. See TODO.md for the RMSA-specific
staleness risk (flagged as highest of any figure in either guide, since it has no public index
to cross-check against, unlike IRS/IRMAA figures).

**Next steps.** Push `management.html` → update CHANGE_LOG → done unless the user wants a
case-studies page or further population coverage.
