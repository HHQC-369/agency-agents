---
name: henghua-commercial-ui
description: Master UI/UX and release-readiness skill for Henghua commercial Windows software. Combines design-taste direction, Impeccable-style critique/audit/polish, WPF/WinUI desktop rules, ERP/MES/printing/finance/DataGrid workflows, Windows 10 compatibility, Chinese UI/DPI reliability, and commercial release acceptance. Use for redesigning, repairing, auditing, hardening, or final-accepting production desktop software.
metadata:
  hhqc_revision: 2026.09
  platforms: [WPF, WinUI, Windows 10]
  domains: [ERP, MES, printing, finance, inventory, DataGrid]
  companion_skills: [design-taste-frontend, impeccable]
---

# Henghua Commercial UI

This is the top-level UI quality and commercial acceptance skill for Henghua desktop software.

It does not replace `design-taste-frontend` or `impeccable`; it orchestrates them and adds Windows desktop, ERP/MES/printing/finance, DataGrid, DPI, Chinese-language, release-gate, and commercial acceptance rules.

## 0. Core operating model

Use this chain unless the request clearly needs only one stage:

```
Taste direction
-> product/workflow truth
-> desktop architecture fit
-> shared design tokens/components
-> implementation
-> Impeccable critique
-> functional UI audit
-> domain-specific audit
-> Windows/DPI/DataGrid verification
-> hardening
-> commercial release gate
```

Never improve appearance by breaking business logic, permissions, printing, finance calculations, production state machines, keyboard workflow, or existing data contracts.

## 1. First classify the task

Classify the target as one or more of:

- ERP/admin
- MES/production
- printing/print-center
- finance/AR/AP/cashier
- inventory/purchasing
- customer/member/pricing
- DataGrid-heavy operations
- configuration/system settings
- dashboard/BI
- installer/licensing/update utility

Then classify the requested action:

- redesign
- refine
- unify
- critique
- audit
- repair
- harden
- performance
- DPI/layout
- DataGrid
- commercial acceptance

## 2. Taste layer

Use Taste rules to decide the visual direction before local styling.

For Henghua commercial software, default design intent is:

- professional, restrained, efficient;
- high information density without visual chaos;
- clear primary/secondary/destructive actions;
- low decorative motion;
- consistent spacing, typography, iconography, radius, border, and elevation;
- brand color used deliberately, not everywhere;
- semantic colors reserved for status and risk;
- modern Windows desktop feel without imitating web UI blindly.

Avoid:
- excessive cards;
- giant empty dashboards;
- glassmorphism;
- oversized marketing typography;
- decorative gradients;
- inconsistent button shapes;
- random shadows;
- pill controls everywhere;
- mobile-style navigation patterns forced into desktop ERP.

## 3. Desktop design system

Create or reuse shared resources before patching individual screens.

Centralize:
- color tokens;
- typography;
- spacing scale;
- control heights;
- corner radius;
- borders;
- focus visuals;
- icon size/stroke rules;
- button variants;
- input variants;
- ComboBox/DatePicker/Menu styles;
- DataGrid styles;
- status colors;
- validation states;
- disabled/read-only states;
- modal/dialog rules;
- loading/progress presentation.

Prefer global fixes through ResourceDictionary/Theme resources/components over one-off local XAML overrides.

## 4. WPF / WinUI rules

### WPF
Check:
- StaticResource vs DynamicResource intent;
- merged dictionary order;
- BasedOn inheritance;
- implicit style collisions;
- triggers and VisualState behavior;
- binding errors;
- command CanExecute state;
- focus scope;
- virtualization;
- dispatcher/UI-thread blocking;
- owner relationship for dialogs;
- text trimming and wrapping;
- DPI-aware sizing;
- touch targets only where genuinely needed.

### WinUI
Check:
- ThemeResource usage;
- VisualStateManager;
- NavigationView state;
- ContentDialog ownership/lifecycle;
- ItemsRepeater/ListView/GridView virtualization;
- XamlRoot correctness;
- theme switching;
- title bar behavior;
- Windows App SDK dependency assumptions.

Do not copy a web CSS mental model into XAML.

## 5. Windows 10 compatibility

When Windows 10 is in scope, verify:

- target framework and Windows target minimums are compatible;
- no Windows 11-only API is used without fallback;
- title bar, mica/acrylic, rounded-window, backdrop, and system effect assumptions degrade safely;
- fonts exist or have safe fallback;
- high-DPI behavior works;
- shell/file-picker/print-dialog behavior is compatible;
- installer prerequisites are explicit;
- offline startup does not depend on unavailable web resources.

Windows 10 support is a release requirement, not a visual preference.

## 6. DPI and window-size gate

Verify representative scaling at:
- 100%
- 125%
- 150%
- 175%
- 200%

Check:
- no clipped Chinese text;
- no truncated buttons;
- no cropped ComboBox popup;
- no off-screen dialogs;
- no overlapping labels;
- no fixed-pixel layout that collapses at scale;
- no blurry bitmap assets when vector equivalents exist;
- resizable windows preserve task usability;
- minimum supported window size is explicit.

For multi-monitor use, check moving the window between monitors with different scaling.

## 7. ERP rules

ERP UI must optimize repeated operations.

Require:
- stable toolbar locations;
- predictable filters;
- visible applied-filter state;
- clear reset;
- batch actions separated from row actions;
- status visible without opening detail pages;
- permission-restricted actions disabled/hidden consistently;
- destructive operations require explicit confirmation;
- totals and balances remain visually anchored;
- form save/cancel semantics are consistent;
- unsaved-change handling exists where needed.

Do not hide core operational actions behind decorative overflow menus without strong reason.

## 8. MES rules

MES screens must make production truth unmistakable.

Separate:
- planned
- queued
- in production
- paused
- blocked
- completed
- failed
- rework
- cancelled

Require:
- current work-center/machine/operator context;
- job/order linkage;
- timestamps;
- quantity planned/completed/rejected;
- exception reason;
- restart/retry rules;
- permission boundary;
- clear distinction between system state and business state.

Do not use color alone to communicate production state.

## 9. Printing software rules

Printing workflows are safety-critical to cost and time.

Verify:
- printer availability and real device identity;
- paper/media size;
- orientation;
- simplex/duplex;
- color/mono;
- copies;
- page range;
- scaling/fit/actual size;
- tray/media-type mapping when supported;
- queue state;
- cancellation;
- failure reason;
- retry behavior;
- duplicate-print protection where appropriate.

Long-running print preparation must show progress and allow cancellation when technically possible.

Never show "success" merely because a print command was queued; distinguish submitted, spooling, printing, completed, cancelled, and failed when data is available.

## 10. Finance rules

Finance UI must prioritize correctness and auditability over visual flair.

Require:
- consistent currency formatting;
- decimal precision rules;
- negative values distinguishable;
- debit/credit direction unambiguous;
- receivable/payable status clear;
- payment method shown;
- partial payment handled;
- refund/reversal distinguished from deletion;
- write-off/adjustment requires permission and reason;
- timestamps and operator identity visible in audit-sensitive actions;
- totals reconcile visually with line items;
- read-only posted/closed states cannot look editable.

Never let AI-generated UI invent financial numbers, labels, or accounting semantics.

## 11. DataGrid rules

For every major DataGrid, inspect:

### Structure
- column order reflects operator workflow;
- frozen columns only for genuinely persistent identifiers/actions;
- widths have sensible min/max rules;
- text vs numeric alignment is consistent;
- financial and quantity columns align numerically;
- row height supports scanning without wasting space.

### Interaction
- sorting state visible;
- filtering state visible;
- selection state clear;
- edit mode distinct from navigation mode;
- keyboard navigation works;
- Enter/Tab/Escape behavior is predictable;
- multi-select and batch actions are explicit;
- row double-click behavior is consistent.

### Reliability
- virtualization enabled for large datasets;
- no expensive converters/layout work per cell when avoidable;
- async loading does not freeze UI;
- stale row data has a refresh strategy;
- empty/loading/error states exist;
- very long Chinese names and file paths do not destroy layout.

### Safety
- row-level delete/destructive actions are not easy to trigger accidentally;
- finance/production critical edits expose validation and confirmation rules.

## 12. Chinese UI quality

Audit:
- Simplified Chinese terminology consistency;
- no mixed half-translated labels;
- punctuation consistency;
- no clipped Chinese glyphs;
- no awkward forced line breaks;
- no garbled encoding;
- no overuse of English abbreviations where operators need Chinese;
- technical identifiers remain unambiguous;
- date/time/number formats are consistent with product requirements.

Chinese and Latin mixed strings must remain visually balanced.

## 13. Permissions and business truth

UI must reflect backend permission truth.

Check:
- hidden vs disabled policy is consistent;
- unauthorized deep-link entry is blocked;
- readonly states cannot mutate;
- command availability matches server authorization;
- role changes refresh UI appropriately;
- stale permissions do not leave clickable actions;
- admin-only diagnostics are not exposed to normal operators.

Never treat front-end hiding as security.

## 14. State completeness

Every important screen should account for:
- loading;
- empty;
- normal;
- partial data;
- validation failure;
- permission denied;
- network/service failure;
- backend timeout;
- conflict/concurrent edit;
- success;
- cancellation;
- retry;
- offline/degraded mode where relevant.

The UI must explain what happened and what the operator can do next.

## 15. Performance

Check:
- UI-thread blocking;
- synchronous file/DB/network calls;
- oversized images;
- unvirtualized lists;
- repeated layout invalidation;
- large shadow/blur effects in scrolling regions;
- excessive bindings/converters;
- repeated polling;
- memory leaks from events/timers;
- slow startup caused by eager initialization;
- DataGrid redraw storms.

Fast operational feedback is part of commercial UX quality.

## 16. Accessibility and keyboard workflow

At minimum verify:
- logical tab order;
- visible focus;
- keyboard activation;
- screen-reader names where applicable;
- non-color-only status;
- sufficient contrast;
- accessible error association;
- Escape/Enter behavior in dialogs;
- access keys/shortcuts do not conflict.

For repeat desktop operators, keyboard efficiency is a first-class feature.

## 17. Commercial UI acceptance sequence

Before calling a UI commercially ready:

1. Taste review
2. Global token/style consistency
3. WPF/WinUI architecture check
4. ERP/MES/printing/finance domain review
5. DataGrid review
6. permissions/state review
7. DPI 100-200% review
8. Windows 10 review
9. keyboard/accessibility review
10. performance review
11. exception/empty/error hardening
12. representative screenshot review
13. regression check outside modified scope
14. final release gate

Do not declare success if only static XAML inspection was possible. State what was and was not runtime-verified.

## 18. Severity model

Classify defects:

- **P0 Blocker**: data loss, financial error, wrong production/print state, crash, permission bypass, unusable primary workflow.
- **P1 Critical**: major task blocked, severe DPI/layout break, incorrect status, inaccessible core control.
- **P2 Major**: inconsistent interaction, important validation/state missing, serious visual fragmentation.
- **P3 Minor**: polish, spacing, minor typography/icon inconsistencies.

Fix P0/P1 before aesthetic polish.

## 19. Definition of done

A task is not complete until:
- scope is implemented;
- shared styles are used where appropriate;
- no new duplicate styling pattern was introduced;
- critical workflows still function;
- error/empty/loading states are covered;
- DPI and Windows 10 constraints were considered;
- DataGrid behavior remains usable;
- permissions are respected;
- commercial release gate is either passed or clearly reports remaining blockers.

For a full release review, also read:
- `CHECKLIST.md`
- `WINDOWS-DESKTOP.md`
- `RELEASE-GATE.md`
