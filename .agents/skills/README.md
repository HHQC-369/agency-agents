# Curated Design Skills

This folder contains two self-contained design skills curated for this repository.

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

## Recommended combined flow

For a major visual redesign:

```
design-taste-frontend
  -> impeccable critique
  -> implementation
  -> impeccable audit
  -> impeccable polish / harden
```

For an existing ERP/admin screen with inconsistent controls:

```
impeccable audit
  -> extract shared tokens/components
  -> layout + typeset
  -> harden
  -> final polish
```

## Notes

These are curated, standalone operational adaptations. They do not vendor the upstream projects' runtime scripts, binaries, or complete reference trees. Consult each upstream repository when you need its full installer, runtime, command bundle, or latest behavior.
