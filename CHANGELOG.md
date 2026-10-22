# Changelog — Clever Koi Gilbert sales & labor tracker

## 2026-10-22 — v1.2

- Posted vs actual by department rewritten for readability: posted, worked and the department difference first, then "worked longer than posted" and "worked shorter than posted" as people counts with hours and dollars. Removed the separate net/gross columns.

## 2026-10-22 — v1.1

- New people with no payroll history can be given their real hourly rate. It's used until their first payroll week, then their own rate takes over.
- "No longer with us" button on the missing-regulars list stops a departed person being flagged. Can be undone in Settings.
- A department posted at less than 25% of its usual hours is treated as not posted yet. Its comparison and the total labor % are withheld instead of reading as a cut.

## 2026-10-22 — v1

First build, based on the Central tracker but rebuilt for one sales bucket and two departments.

- One Sales-by-day export, no time filter. Orders and guests are discarded on import.
- Toast payroll, one week per file. The week comes from the filename. Multi-week ranges, non-Monday starts and other locations are refused.
- 7shifts weekly schedule, week from the Monday date in the filename. Overlapping shifts on the same day are flagged and not double-counted.
- No closed days are assumed. Dates inside an export's range with no row must be confirmed once.
- House/terminal accounts are excluded by name and title before any per-person logic.
- Salaried list, house accounts, job map and name links live in the workbook, not in this page.
- Name matching: exact, then manual link, then two or more shared name tokens, unique in both directions. Unmatched names are reconciled, never reported as unposted labor.
- Posted vs actual by department (over, under, net, gross); anyone within ±1 hr is listed by name in a collapsed line.
- Overtime: premium = OT pay ÷ 3, repeat count over the trailing 8 weeks, diagnosis (scheduled above 40 / ran over / not on schedule / not reconciled). Overtime threshold is strictly above 40.
- Next week: posted over 40, drift forecast (needs at least 3 weeks per person), department vs trailing norm in hours and dollars (suppressed when salaried coverage moves 8+ hrs), labor % vs projection last. Time-off caveat always shown.
- Forward pricing uses regular pay ÷ regular hours. Actuals use weighted average total pay ÷ hours.
- Projection: last year's same week × trailing YoY ratio, falling back to a trailing average. Commit locks; later changes are logged as revisions.
- Workbook stamped with location; a workbook from another tracker is refused. Separate browser storage key from the Central tracker.
- "Today" uses the browser's local date (Central's version jumped a week early on Sunday evenings).
- Removed from the Central version: three sales buckets, ATP departments, the "who had room" overtime suggestion, covers and average check.
- Fiscal anchor is P8 WK1 = 2026-07-06 and is still unverified.
