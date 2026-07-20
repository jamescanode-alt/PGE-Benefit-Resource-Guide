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
