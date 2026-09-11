# Commercial Release Gate

A release can be called commercially ready only when the following evidence exists or the missing evidence is explicitly reported.

## Gate A - Build and startup
- Clean build succeeds
- Application starts on supported Windows 10 environment
- Required runtimes/prerequisites documented
- No startup crash from missing assets/resources

## Gate B - Primary workflows
Representative ERP/MES/printing/finance workflows complete without UI blockage.

## Gate C - Data truth
- UI values map to real backend data
- Status labels match state machine truth
- Finance totals reconcile
- Print success is not falsely reported
- Permission truth matches backend enforcement

## Gate D - DataGrid
Large datasets remain responsive, sortable/filterable as intended, and do not lose usability under DPI scaling.

## Gate E - DPI and localization
100-200% DPI and Chinese text are usable on representative screens.

## Gate F - Failure behavior
Timeouts, validation failures, offline/service errors, permission denial, cancellation, and partial failure produce recoverable UI.

## Gate G - Accessibility and keyboard
Core workflows are operable without relying exclusively on mouse or color.

## Gate H - Regression
Modified global styles/resources do not silently break unrelated screens.

## Gate I - Severity
- P0 blockers: zero
- P1 critical defects: zero
- P2 defects: fixed or explicitly accepted
- P3 polish: may remain only if documented

## Evidence statement
Final acceptance should state:
- build verified: yes/no
- runtime verified: yes/no
- Windows 10 verified: yes/no
- DPI matrix verified: yes/no
- representative workflows verified: yes/no
- remaining P0/P1/P2 counts
- known limitations
