# UI / UX Reference (Template)

> **This document defines the reusable design system, interaction rules, and accessibility guardrails for any BMAD project.** Swap placeholder tokens with project-specific details, but keep the structure so designers and developers share the same vocabulary.

---

## 1. Design Principles
- **Clarity:** Keep layouts minimal and copy action-oriented.
- **Continuity:** Cross-platform components should behave consistently.
- **Assistive Feedback:** Every state change provides visual + audible confirmation when relevant.
- **Inclusivity:** Meet or exceed WCAG 2.1 AA standards by default.

List the 3–5 principles your team will actually enforce. Tie them to personas in the PRD.

---

## 2. Design Tokens

### 2.1 Color Palette

| Token | HEX | Usage Notes |
|-------|-----|-------------|
| `color.background.default` | `#FFFFFF` | Primary surface |
| `color.background.alt` | `#0F1115` | Dark theme surface |
| `color.text.primary` | `#101828` | Body text |
| `color.text.inverse` | `#FFFFFF` | On dark surfaces |
| `color.intent.success` | `#12B76A` | Confirmation states |
| `color.intent.warning` | `#F79009` | Needs attention |
| `color.intent.error` | `#F04438` | Critical failure |

> Store tokens inside `src/theme/tokens.ts` (or equivalent). Never hard-code hex values elsewhere.

### 2.2 Typography

| Token | Font Family | Weight | Size / Line Height | Usage |
|-------|-------------|--------|--------------------|-------|
| `type.display.lg` | `<Primary font>` | 600 | 32 / 40 | Hero headlines |
| `type.heading.md` | | 600 | 24 / 32 | Screen titles |
| `type.body.md` | | 400 | 16 / 24 | Paragraphs |
| `type.body.sm` | | 400 | 14 / 20 | Captions |
| `type.mono` | `<Mono font>` | 500 | 13 / 20 | Code snippets |

Specify fallbacks for each OS/platform.

### 2.3 Spacing & Layout
- Base grid: `4px`.
- Component padding increments: `8px, 12px, 16px, 24px`.
- Container max widths: `600px mobile`, `1200px desktop`.
- Breakpoints: `sm 0–599`, `md 600–1023`, `lg 1024+`.

Include diagrams if helpful; link to Figma or Miro resources.

---

## 3. Component Library

For each component, include structure, states, and usage guidance. Example:

### 3.1 Button
- **Variants:** `primary`, `secondary`, `ghost`, `destructive`.
- **States:** default / hover / pressed / loading / disabled.
- **Anatomy:** Label, optional icon (left/right), hit area min 44×44.
- **Behavioral Notes:** Loading state locks width, shows spinner, and disables repeated taps.
- **Do / Don’t:** Provide quick bullet examples to avoid misuse.

Repeat this format for Cards, Inputs, Modal Sheets, Alerts, Empty State, Lists, etc. Reference component file paths (e.g., `src/components/Button/Button.tsx`) so devs know where to look.

---

## 4. Interaction Patterns

| Pattern | Description | Triggers | Guidelines |
|---------|-------------|----------|------------|
| **Task Creation Flow** | Stepper that validates required fields before scheduling alarms. | FAB tap, voice command. | Save automatically, surface conflict warnings inline. |
| **Notification Center** | Aggregated feed of past alerts. | Alarm completion. | Group by date, show CTA to “mark done” or “snooze”. |

Document navigation conventions (tab vs stack), gestures, and micro-interactions (e.g., vibration duration for critical alerts). Link to prototypes where possible.

---

## 5. Accessibility Requirements
- Minimum contrast ratio `4.5:1` for body text, `3:1` for large headings.
- All interactive elements must support voice control labels and keyboard focus.
- Provide haptic/audio cues for critical alarms; offer opt-out controls.
- Ensure animations respect “Reduce Motion” OS settings.
- Add localization guidelines (date formats, RTL support) if relevant.

---

## 6. Content & Tone
- **Voice:** e.g., “Calm, direct, supportive.”
- **Microcopy Guidelines:** Use verbs first (“Save changes”), avoid jargon.
- **Error Messages:** Format: `{What happened}. {Impact}. {What to do next}.`
- **System Messages:** Reference severity tokens (info, warning, error).

Include table of reusable strings or component-specific copy blocks if this doc doubles as a content source.

---

## 7. Assets & References
- Link to design files (`Figma project URL`).
- Document icon library, illustration sets, and licensing info.
- Explain how to export assets and where to place them in the repo (`/assets/icons`).

---

## 8. Review & Handoff
- Designers add changelog entries when updating tokens or components.
- Developers confirm implementation matches spec inside `.acontext/tasks` logs (link to sections of this doc).
- Accessibility audits recorded in `Bug_tracking.md` or `.acontext/decisions`.

---

### Usage Checklist
- [ ] Each UI change references a section of this doc in its task log.
- [ ] New components cannot merge until their spec exists here (or in linked design file).
- [ ] Accessibility rules enforced via linting/testing where possible.
- [ ] This doc stays tech-agnostic—no React-specific instructions beyond file references.

Maintain this reference so every contributor—designer, engineer, or agent—shares the same mental model for how the product should look, feel, and behave.
