# CHANGE_LOG

## 2026-07-21 — Refresh both guides against PG&E's current online plan summaries

**Summary.** The user supplied PG&E's current benefit PDFs (401(k), Pension, Pension Quick Start,
Your Pension Guide) plus the mypgebenefits.com resource URLs. Parsed them (Firecrawl `parse`,
since PDF image rendering was unavailable) and updated both guides to match current plan terms.
The headline change: the RSP now offers a **Roth contribution source effective January 1, 2026** —
both guides previously said Roth was "unconfirmed / not offered," now corrected to a confirmed,
prominent Roth callout.

**Key content changes (both guides unless noted):**
- **Roth 401(k):** replaced the "unconfirmed" warn callout with a confirmed "New for 2026" good
  callout (three sources: pre-tax / Roth / regular after-tax) plus an advisor's-lens callout on
  the career-stage Roth decision. Added Roth to the section intro line and a glossary entry.
- **Union contribution cap 20% → 50%** (effective Jan 1, 2026), and removed the now-false
  "wider than the union's 20% cap" phrasing from the management guide (both are 50% now).
- **Mandatory cash-out confirmed at $5,000** (PG&E did NOT adopt the $7,000 SECURE 2.0 option);
  removed the old "confirm which" hedge.
- **New: Excess Plan callout** — PG&E-paid, non-qualified, unsecured, not-PBGC-insured top-up for
  pensions exceeding IRS §415/§401(a)(17) limits. Framed for high-overtime union clients;
  emphasized for the (higher-earning) management population, with the $360,000 2026 pay limit.
- **New: PG&E's published 8-form sample payment table** ($4,236.26 single-life spread across all
  joint/pop-up percentages) added to the payment-options section of both guides — real current
  illustrative data replacing reliance on the synthetic SPD factor alone.
- **Investing:** Core Funds corrected to **7** (was 11/10); BrokerageLink expansion to ETFs/ETNs/
  closed-end funds (Aug 1, 2024); 20% PG&E-stock cap; added an **Edelman Financial Engines** /
  Income+ advisory callout.
- **Auto-enrollment** timing corrected to ~30 days after hire (union table), with match-eligibility
  distinction spelled out.
- **HCE threshold $160,000 (2026)** added to the management 401(k) section.
- **Portal/administrator updates:** pension is now **PG&E PensionConnect (mypensionconnect.com),
  administered by Willis Towers Watson (WTW)** — replaced all "Xerox" / "pgepensioncenter.com"
  references (hero label, formula-check link, contacts, footer). Added QDRO team email
  (WTWQDRO@willistowerswatson.com) and an "Online benefit resources" block linking the four
  mypgebenefits.com pages the user provided.

**Files.** `index.html`, `management.html`, `TODO.md` (resolved the Roth and cash-out items),
`CHANGE_LOG.md`, `PLAN_LOG.md`.

**Tests.** Local preview on both pages: confirmed Roth callout, 50% cap, sample table ($4,236.26),
Excess Plan, PensionConnect, Edelman, 7 Core Funds, HCE $160k all render. Tag balance intact
(index 186/186 div, 11/11 table, 15/15 section; management 189/189, 11/11, 15/15). No page-level
horizontal overflow at 375px (tables scroll inside their wrappers). Grep confirmed zero remaining
"Xerox / pgepensioncenter / unconfirmed / farther / focus team" references.

**Sources.** PG&E current online summaries via mypgebenefits.com (retrieved July 2026):
401(k) RSP, Pension, Pension Quick Start Guide, Your Pension Guide. The Roth detail is stated on
the 401(k) page ("Starting January 1, 2026, PG&E will offer a Roth contribution option…").

## 2026-07-20 (3) — Named client examples added throughout both guides

**Summary.** Added a "Client example" callout to every substantive section of both guides (up
from a handful of SPD-sourced "worked examples") using two running personas per guide, so a
trainee can follow one consistent client's numbers through the whole document instead of seeing
disconnected figures per section.

- **index.html (Union):** Maria Delgado (hired 2008, Final Pay Pension) carries eligibility,
  formula ID, FAP mechanics, early retirement, the calculator, payment options, 401(k) match,
  RMSA, IRMAA, and a capstone strategy recap. Devon Park (hired 2016, Cash Balance) covers the
  cash-balance-specific sections and a QDRO example.
- **management.html:** Karen Whitfield (hired 2005, Final Average Pay) plays the same role,
  including a dedicated example contrasting her 9%-reduced 32-year/age-58 benefit against what a
  union employee with identical years would get (fully exempt at 30 years vs. Management's 35).
  Priya Nair (hired 2017, Cash Balance) covers the cash-balance section, and a new unnamed
  transfer example illustrates the union-to-Management blended-benefit rule in Section 13.

**Files.** `index.html`, `management.html` (content only, no structural changes).

**Tests.** Re-verified after edits: div/table/section tag counts balanced in both files (182/182,
185/185 divs; 10/10 tables; 15/15 sections). Calculator re-tested with values matching the new
examples (age 58/22yrs union &rarr; 14%; age 58/32yrs management &rarr; 9%) and produced results
matching the prose exactly. No mobile overflow regression. Re-ran the farther/focus-team grep
across both files: still zero matches.

**Issues.** One internal-consistency fix made during review: the first draft of Karen's strategy-
playbook recap implied a single continuous timeline (58 with more years than 65), which is
impossible — retiring earlier means fewer accumulated years, not more. Reworded to frame the two
early-retirement/normal-retirement figures as separate illustrative scenarios rather than
sequential points in one client's life, consistent with how the SPD's own examples work.

**Not yet done.** The user also asked whether the guide should be split into separate pages by
hire date (pre/post-2013) with an intro selector page. Recommended against a full page split
(would duplicate the ~90%-identical Cash Balance/RMSA content across twice as many pages) in favor
of a lighter hero quick-start selector, pending user direction before building either.

## 2026-07-20 (2) — Management/A&T employee guide (management.html)

**Summary.** Published `management.html`, the parallel guide for Management and Administrative
&amp; Technical employees. Same design system and section structure as `index.html`, with
content built from direct SPD verification: Final Average Pay Pension (flat 1.7% formula, 36-
month salary average, 35-year full-exemption threshold with an extra reduction band vs. the
union guide's 30-year threshold), Cash Balance Pension (identical mechanics to the union plan),
a 1%-50% 401(k) contribution range with a flat $0.75/$1 match structure, RMSA (identical
mechanics to the union plan), and a salary-linked Postretirement Life Insurance benefit unique
to this population.

**Files.** `management.html` (new). `PLAN_LOG.md` and `TODO.md` updated with the verification
notes and a new RMSA staleness-risk item.

**Tests.** Same local-preview verification approach as `index.html`: retirement estimator tested
across the 30-34-year band (Management-specific) and the 35-year exemption, both producing
correct output distinct from the union calculator's 30-year threshold. All 10 tables wrapped in
`.table-wrap` from the start; confirmed no real page-level horizontal overflow at 375px (table
content correctly scrolls inside its container instead). Confirmed the "Viewing plan" dropdown
correctly cross-links to and from `index.html`. Repo-wide case-insensitive grep for "farther" and
"focus team": zero matches across both HTML files and all markdown docs.

**Status.** Pushed to `main`. Both guides now live at
https://jamescanode-alt.github.io/PGE-Benefit-Resource-Guide/ (Union) and
https://jamescanode-alt.github.io/PGE-Benefit-Resource-Guide/management.html (Management/A&T).

**Issues.** The background agent assigned to extract Management SPD details failed partway
through (hit its session usage limit) — worked around by reading the relevant SPD pages directly
instead of waiting on it; no impact on the delivered content, but noting it since the task list
briefly showed it as failed before being manually verified complete.

## 2026-07-20 — Initial push: Union employee guide (index.html)

**Summary.** Published `index.html`, a single-page advisor field guide covering PG&E's
Retirement Plan (Final Pay Pension and Cash Balance Pension formulas), the early-retirement
reduction table, an interactive retirement estimator, pension payment options (including the
"Pop-Up" Special Joint Pension), the 401(k)/Retirement Savings Plan, the Retiree Medical Savings
Account (RMSA), IRMAA/income-sequencing guidance, a strategy playbook, protections & rules,
glossary, and contacts. Repo scaffolding (`README.md`, `PLAN_LOG.md`, `TODO.md`, `.nojekyll`,
`.claude/launch.json`) added alongside it.

**Files.** `index.html` (new), `README.md`, `PLAN_LOG.md`, `TODO.md`, `.nojekyll`,
`.claude/launch.json`.

**Tests.** Verified in a local static-server preview: page renders correctly, all nav
scroll-spy links work, the retirement estimator calculator was tested across all logic branches
(Final Pay under-55, Final Pay reduced, Final Pay 30-year exemption, Final Pay at/after 65, Cash
Balance) via direct JS invocation and produced correct output matching the source SPD's
reduction table. Fixed a mobile-viewport bug found during testing: the 5-column reduction table
forced horizontal page scroll at 375px width; wrapped all tables in a `.table-wrap` scroll
container to fix it (verified 375px scrollWidth == clientWidth after the fix, at both mobile and
desktop breakpoints).

**Status.** Pushed to `main` and GitHub Pages enabled
(https://jamescanode-alt.github.io/PGE-Benefit-Resource-Guide/). The sidebar "Viewing plan"
dropdown links to `management.html`, which does not exist yet, next push.

**Issues.** None blocking. See TODO.md for follow-ups (SMM currency, Roth 401(k) confirmation,
mandatory cash-out threshold confirmation).
