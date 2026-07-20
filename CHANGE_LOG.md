# CHANGE_LOG

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
