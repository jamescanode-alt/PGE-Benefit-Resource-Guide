# CHANGE_LOG

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
