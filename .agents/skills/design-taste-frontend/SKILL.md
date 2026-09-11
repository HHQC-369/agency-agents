---
name: design-taste-frontend
description: Use for frontend visual direction, redesigns, landing pages, portfolios, brand-led web surfaces, and any interface that looks generic or templated. Reads the brief first, chooses an intentional design language, sets variance/motion/density, then enforces typography, color, layout, imagery, motion, states, responsiveness, and a final anti-slop review. For dense enterprise product UI, pair with impeccable.
metadata:
  source_family: Leonxlnx/taste-skill
  upstream_license: MIT
  hhqc_revision: 2026.09
---

# Design Taste Frontend

A self-contained design-direction skill for agents that need to make interfaces feel intentional rather than statistically average.

## When to use

Use this skill for:
- landing pages, campaign pages, portfolios, brand sites, and marketing surfaces;
- redesigns where the current UI feels generic, repetitive, or obviously AI-generated;
- new frontend work where aesthetic direction is underspecified;
- brand-led product shells where visual character matters.

Do not use it as the only skill for dense ERP tables, admin workflows, financial forms, MES screens, or other task-heavy product UI. In those cases, use this skill to establish the visual language, then use `impeccable` to audit and harden execution.

## 1. Read the brief before designing

Before writing UI code, infer:
- surface type;
- audience;
- brand and business context;
- desired mood;
- references supplied by the user;
- existing assets and constraints;
- accessibility, regulatory, or trust requirements.

Write one short internal design read:
`<surface> for <audience>, using a <visual language>, optimized for <primary outcome>.`

Do not force a favorite aesthetic onto a clear brief.

## 2. Set three design dials

Choose explicit values from 1-10:

- `DESIGN_VARIANCE`: symmetry and conventionality -> expressive asymmetry.
- `MOTION_INTENSITY`: static -> cinematic.
- `VISUAL_DENSITY`: airy -> information-dense.

Typical starting points:
- enterprise/product: 4 / 3 / 7
- mainstream SaaS marketing: 7 / 5 / 4
- premium consumer: 7 / 5 / 3
- creative/agency: 9 / 8 / 3
- public-sector/trust-first: 3 / 2 / 5

Adjust from the brief, not habit.

## 3. Choose a design foundation deliberately

Prefer one coherent system rather than mixing multiple component languages.

Examples:
- Microsoft/enterprise: Fluent UI
- IBM/data-heavy: Carbon
- Google/Material product: Material 3
- GitHub-like dev tools: Primer
- accessible headless/react foundation: Radix or an existing project system
- custom brand marketing: native CSS/Tailwind plus a coherent token system

If the project already has a mature design system, preserve it unless the user explicitly requests a redesign.

## 4. Anti-template rules

Avoid automatic LLM defaults unless the brief actually calls for them:
- centered hero + three equal cards;
- purple/blue glow gradients used without brand rationale;
- glassmorphism everywhere;
- excessive card nesting;
- identical split-layout sections repeated down the page;
- random pills, badges, dots, micro-labels, and fake metrics;
- decorative motion with no purpose;
- generic placeholder copy presented as product truth.

Prefer composition that reflects the actual information hierarchy.

## 5. Typography

- Choose type for the brand and content, not because it is fashionable.
- Maintain a clear scale: display, heading, body, supporting text, labels.
- Keep line length readable and prevent display copy from wrapping into awkward walls of text.
- Use one primary family and, at most, one deliberate secondary family.
- Maintain consistent weights, tracking, line-height, and casing rules.
- Verify clipping, truncation, localization growth, and Windows font fallback when relevant.

## 6. Color

- Establish semantic tokens before scattering literal colors.
- Keep one dominant accent unless the product semantics require additional state colors.
- Separate brand color from semantic success/warning/error/info colors.
- Check contrast for text, controls, focus rings, disabled states, and overlays.
- Keep neutral temperature consistent across the surface.
- Do not switch visual theme by section unless the brief intentionally calls for it.

## 7. Layout and rhythm

- Use a small spacing scale and repeat it.
- Align to meaningful columns and baselines.
- Prefer whitespace and separators over unnecessary containers.
- Vary section composition intentionally on expressive pages.
- On product surfaces, prioritize scanability, predictable placement, and stable geometry over novelty.
- Prevent accidental horizontal scroll and unstable viewport-height behavior.

## 8. Imagery and iconography

- Use real product/brand imagery when available.
- Do not fake product screenshots or fabricate brand assets.
- Use one icon family per surface.
- Keep icon stroke/fill language consistent.
- Decorative imagery must support hierarchy or storytelling, not fill empty space.

## 9. Motion

Every animation must serve one of:
- hierarchy;
- state transition;
- feedback;
- spatial continuity;
- storytelling.

Respect reduced-motion preferences. Keep high-frequency product interactions faster and quieter than marketing storytelling.

## 10. Complete interaction states

Do not ship only the happy path. Cover:
- loading;
- empty;
- error;
- disabled;
- focus;
- hover;
- pressed/active;
- success/confirmation;
- long text/localization;
- permission-restricted states where applicable.

## 11. Redesign protocol

For an existing project:
1. inspect the current visual system and screenshots;
2. separate product truth from visual habit;
3. identify what must be preserved;
4. list repeated design defects;
5. set the new/preserved visual language;
6. apply changes globally through tokens/components before local patches;
7. verify representative screens after implementation.

Do not "redesign" by changing only colors and border radii.

## 12. Pre-flight gate

Before delivery, verify:
- brief and audience are reflected in the result;
- one coherent visual language is used;
- typography hierarchy is consistent;
- accent and semantic colors are consistent;
- spacing and radius rules are coherent;
- no repeated AI-template patterns dominate the page;
- buttons and forms have sufficient contrast;
- loading/empty/error/focus states exist;
- motion has a reason and reduced-motion fallback;
- desktop and mobile layouts were both checked for web work;
- no fabricated factual copy, logos, metrics, testimonials, or product claims were introduced.

If the surface is task-heavy product UI, continue with the `impeccable` skill for audit and production hardening.
