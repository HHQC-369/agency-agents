---
name: impeccable
description: Use to design, redesign, critique, audit, polish, harden, adapt, typeset, optimize, clarify, or extract a UI system. Covers web and desktop product interfaces, including dashboards, ERP/admin screens, forms, settings, onboarding, data-heavy workflows, responsive behavior, accessibility, error states, localization, performance, tokens, and final release quality.
metadata:
  upstream_family: pbakaus/impeccable
  upstream_reference_version: 4.3.1
  upstream_license: Apache-2.0
  hhqc_revision: 2026.09
---

# Impeccable UI Quality Skill

A self-contained execution and quality-control skill. It turns an existing or newly designed interface into a coherent, production-ready surface through bounded inspection and repair.

This repository does not vendor the upstream Impeccable runtime, scripts, binaries, or reference bundle. This skill is intentionally standalone.

## Core rule

Complete the requested scope, inspect it in a bounded pass, fix the defects found as one batch, verify once more, then stop. Do not enter an endless polish loop.

The user's brief and product truth outrank aesthetic preference.

## 1. Select the surface mode

Choose the mode from the surface being worked on:

- **Persuade**: landing, pricing, campaigns. Optimize attention, comprehension, and action.
- **Operate**: ERP, dashboards, editors, admin, settings, tools. Optimize scanability, speed, error prevention, consistency, and confidence.
- **Read**: docs, articles, help, reports. Optimize comprehension and navigation.
- **Experience**: portfolio, gallery, showcase. Let the artifact lead while UI recedes.

A product can contain different modes on different surfaces.

## 2. Establish context

Before changing UI:
- inspect current code/components/tokens;
- inspect screenshots or visual regression fixtures when available;
- identify existing product/design documentation;
- identify supported devices, themes, localization, permissions, and accessibility constraints;
- preserve facts, behavior, routes, labels, legal text, and workflow semantics unless the request changes them.

For redesigns, distinguish between:
- **refinement**: preserve visual identity and improve execution;
- **replacement**: preserve product truth but establish a new visual world.

## 3. Quality workflow

Use this sequence:
1. **Shape** - define the user task, hierarchy, states, and interaction model.
2. **Build/Repair** - implement through shared tokens and components where possible.
3. **Inspect** - review representative screens and states together.
4. **Batch Fix** - repair all discovered issues coherently.
5. **Confirm** - one final verification pass.

## 4. Critique

Evaluate:
- task clarity;
- information hierarchy;
- cognitive load;
- navigation and orientation;
- consistency;
- affordances;
- error prevention and recovery;
- content clarity;
- accessibility;
- visual hierarchy and craft.

Report defects by severity and user impact, not by personal taste.

## 5. Audit

Check technical UI quality:
- keyboard access and focus visibility;
- contrast and non-color-only meaning;
- labels, names, roles, and error association;
- responsive or resizable-window behavior;
- overflow, clipping, truncation, DPI scaling;
- performance hotspots and unnecessary redraw/re-render work;
- loading, empty, error, offline, permission, and partial-data states;
- localization expansion;
- theme consistency;
- disabled/read-only distinction;
- destructive-action safeguards.

## 6. Layout

Repair:
- inconsistent spacing;
- misaligned baselines;
- arbitrary widths/heights;
- over-nesting of containers;
- weak grouping;
- poor density;
- inconsistent toolbar/filter/action placement;
- unstable tables and columns.

For task-heavy interfaces, consistency beats novelty. Keep frequently used actions in stable locations.

## 7. Typeset

Repair:
- weak heading hierarchy;
- inconsistent font sizes/weights;
- excessive line lengths;
- clipped glyphs;
- inconsistent casing;
- unreadable secondary text;
- poor numeric alignment in finance/data tables;
- mixed font families without a rule.

For data-heavy UI, use tabular numerals where the chosen font supports them.

## 8. Colorize

Use color for:
- brand emphasis;
- status semantics;
- focus and selection;
- hierarchy where typography alone is insufficient.

Do not use brand color as a substitute for success/warning/error semantics. Ensure states remain understandable without relying only on hue.

## 9. Harden

Before release, cover:
- empty datasets;
- partial failures;
- slow operations;
- retry/cancel behavior;
- very long names and values;
- zero/negative/large numbers;
- permission denial;
- concurrent edits;
- stale data;
- duplicate submissions;
- localization;
- offline/intermittent connectivity when relevant;
- destructive confirmations;
- recoverability after failure.

## 10. Adapt

### Web
Check:
- narrow mobile;
- tablet;
- common desktop;
- wide desktop;
- zoom and text enlargement.

### Windows desktop / WPF / WinUI
Check:
- 100%, 125%, 150%, 175%, 200% DPI;
- 1366x768 minimum practical workspace where the product requires it;
- resizable windows and minimum sizes;
- Windows 10 behavior when supported;
- keyboard navigation and access keys;
- high-contrast/theme compatibility where applicable;
- DataGrid column sizing, frozen columns, selection, editing, sorting, and virtualization;
- ComboBox/DatePicker/Menu/Flyout placement near screen edges;
- modal ownership and focus return;
- multi-monitor DPI transitions;
- text rendering with Chinese and Latin mixed content.

Do not blindly apply web-only patterns to desktop software.

## 11. ERP/admin density rules

For ERP, MES, finance, inventory, printing, and back-office software:
- optimize for repeat operators, not first-impression spectacle;
- keep dense information readable without turning every datum into a card;
- distinguish primary action, secondary action, dangerous action, and row-level action;
- preserve table scan lines and column alignment;
- make filters discoverable and resettable;
- show applied-filter state clearly;
- keep totals and key financial numbers visually stable;
- avoid animated layout shifts;
- make batch operations explicit;
- show progress and cancellation for long-running print/import/export tasks;
- separate system status, business status, and permission status.

## 12. Clarify

Improve labels and messages so the user knows:
- what happened;
- why it happened;
- what can be done next.

Error copy should identify the failed object/action when safe, avoid blame, and offer recovery.

## 13. Optimize

Investigate:
- unnecessary component redraws/re-renders;
- oversized assets;
- blocking work on the UI thread;
- unvirtualized long lists/tables;
- repeated expensive layout measurement;
- excessive shadows/blur/effects in scrolling regions;
- unbounded event listeners or timers;
- animation that competes with input responsiveness.

Performance is part of perceived design quality.

## 14. Extract

When repeated UI patterns exist, consolidate:
- color tokens;
- typography tokens;
- spacing scale;
- radii;
- shadows/elevation;
- icon rules;
- control heights;
- table density;
- validation states;
- status colors;
- reusable components.

Fix the system first, then exceptions.

## 15. Polish gate

A release-quality pass should verify:
- all controls align and use the same sizing rules;
- spacing follows a defined scale;
- hover/focus/pressed/disabled/read-only states are distinct;
- destructive actions are clearly differentiated;
- typography and numeric formatting are consistent;
- tables remain usable with real-world data lengths;
- tooltips are not required for essential information;
- no clipped Chinese text at supported DPI;
- no fake data or claims were introduced;
- no regression was created outside the requested scope.

## 16. Pairing with Design Taste

Use `design-taste-frontend` first when the problem is "this looks generic; establish a stronger visual direction."

Use `impeccable` first when the problem is "this interface is inconsistent, incomplete, fragile, inaccessible, or not release-ready."

For major redesigns:
`design-taste-frontend -> impeccable critique -> implementation -> impeccable audit -> impeccable polish/harden`.
