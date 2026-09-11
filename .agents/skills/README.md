# Curated Design Skills

This folder contains three self-contained design and UI quality skills curated for this repository.

## Skills

### design-taste-frontend
Path: `.agents/skills/design-taste-frontend/SKILL.md`

Use when the main problem is visual direction:
- generic/templated output;
- landing pages and portfolios;
- brand-led web design;
- redesign direction;
- typography/color/layout/motion taste.

Upstream family: https://github.com/Leonxlnx/taste-skill  
Upstream license: MIT.

### impeccable
Path: `.agents/skills/impeccable/SKILL.md`

Use when the main problem is execution quality:
- UI/UX critique;
- accessibility and technical audit;
- layout and typography consistency;
- responsive/DPI adaptation;
- error/empty/loading states;
- production hardening;
- ERP/admin/data-heavy desktop UI;
- final polish.

Upstream family: https://github.com/pbakaus/impeccable  
Referenced upstream version at curation time: 4.3.1.  
Upstream license: Apache-2.0.

### henghua-commercial-ui
Path: `.agents/skills/henghua-commercial-ui/SKILL.md`

Top-level commercial Windows software UI controller for:
- Taste + Impeccable orchestration;
- WPF / WinUI;
- ERP / MES;
- printing workflows;
- finance / AR / AP;
- DataGrid-heavy operations;
- Chinese UI;
- Windows 10;
- 100%-200% DPI;
- permissions and state truth;
- performance and keyboard workflow;
- commercial release acceptance.

Supporting references:
- `CHECKLIST.md`
- `WINDOWS-DESKTOP.md`
- `RELEASE-GATE.md`
- `UPSTREAM.md`

## Recommended combined flow

For Henghua commercial desktop software:

```
henghua-commercial-ui
  -> design-taste-frontend when visual direction is weak
  -> impeccable critique
  -> shared XAML tokens/components
  -> implementation
  -> impeccable audit
  -> Windows/DPI/DataGrid/domain checks
  -> harden
  -> commercial release gate
```

For an existing ERP/admin screen with inconsistent controls:

```
henghua-commercial-ui
  -> impeccable audit
  -> extract shared tokens/components
  -> layout + typeset
  -> DataGrid / permission / DPI verification
  -> harden
  -> final commercial acceptance
```

## Notes

These curated skills do not vendor the upstream projects' full runtime scripts, binaries, or complete reference trees. Consult the upstream repositories when the full installers, runtimes, command bundles, or latest behavior are required.
