# TODO

- [ ] Re-verify all figures against current PG&E SPD/SMMs as newer versions are published
      (guides now reflect PG&E's current online plan summaries retrieved July 2026, layered on
      the 2014 base SPD).
- [x] ~~Confirm Roth 401(k) availability.~~ RESOLVED 2026-07-21: PG&E's current 401(k) page
      confirms a **Roth contribution option effective January 1, 2026**. Both guides updated from
      "unconfirmed" to a confirmed Roth callout (three sources: pre-tax / Roth / regular after-tax).
- [x] ~~Confirm mandatory-cashout threshold ($5,000 vs $7,000).~~ RESOLVED 2026-07-21: PG&E's
      current pension page keeps it at **$5,000** (did NOT adopt the $7,000 SECURE 2.0 option).
      Both guides updated to state $5,000 as current.
- [ ] Union final-pay 401(k) match is shown as "60% / $0.60 per $1"; the 2026 401(k) page phrases
      it as "$0.60 per $1." Equivalent, but if a future update changes the rate, re-check both the
      match cards and the Maria client example.
- [x] ~~Add an interactive advisor tool.~~ DONE 2026-07-21: added `triggers.html` (Financial
      Trigger Finder), wired into both guides' nav. Computes retiree gate, pension reduction %,
      Rule of 55, and a dated trigger timeline + separation checklist.
- [ ] The Trigger Finder's early-retirement reduction % uses the birthday-age band (reduction as
      of the last birthday); PG&E computes it by exact month. Fine for an educational estimate,
      but note it if a client is mid-band and the exact figure matters, direct them to PensionConnect.
- [ ] Add a case-studies/quiz page (parallel to the AT&T guide's case-studies.html) if wanted —
      out of scope for this build.
- [ ] Annual maintenance: update the 2026 IRS/IRMAA/SSA figures each fall when new COLA figures
      are released (see AT&T guide's ANNUAL-TAX-FIGURES.md for the pattern to replicate here).
- [ ] Confirm the RMSA reimbursement percentage (55% pre-Medicare / 30% Medicare) is still current
      — the 2014 SPD only explicitly schedules this through 2018 and asserts (as a forward-looking
      claim, not a guarantee) that it holds afterward. No public index exists to cross-check this
      figure the way IRS limits can be, so it carries the highest staleness risk of any number in
      either guide.
- [ ] Same staleness caveat applies to the RMSA dollar formula itself ($5,000/yr, $1,000/yr past
      15 YOS, $7,500 lump sum, 4.5% interest) — these are PG&E plan-design choices set by
      amendment, not statute, so they could have changed since 2014 with no external signal.
