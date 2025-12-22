# Core Styles

This project defines reusable design tokens and helper classes in `src/styles/global.css`.
Use the tokens directly in Tailwind utilities or the `cs-` helpers for consistent typography.

## Design Tokens

Colors (from `@theme`):
- `--color-primary`, `--color-primary-light`
- `--color-secondary`, `--color-secondary-light`
- `--color-header`, `--color-body`, `--color-body-white`

Tailwind examples:
- `text-primary`, `bg-primary`, `text-secondary`
- `text-header`, `text-body`, `bg-body-white`

Typography tokens:
- `--text-topper`
- `--text-topper--line-height`
- `--text-topper--letter-spacing`
- `--text-topper--font-weight`
- `--text-display`
- `--text-display--line-height`
- `--text-display--font-weight`

Spacing tokens:
- `--spacing-section-y`
- `--spacing-section-x`

Token usage examples:
- `class="text-topper leading-[var(--text-topper--line-height)] tracking-[var(--text-topper--letter-spacing)] font-[var(--text-topper--font-weight)]"`
- `class="text-display leading-[var(--text-display--line-height)] font-[var(--text-display--font-weight)]"`
- `class="py-[var(--spacing-section-y)] px-[var(--spacing-section-x)]"`

## Helper Classes

Defined in `@layer components`:
- `.cs-topper`: uppercase topper text for section intros.
- `.cs-title`: display-sized section heading.
- `.cs-text`: standard body copy block.

These helpers are meant to be composed with layout utilities (widths, margins, flex, grid).

## New Component Example

```astro
<section class="py-[var(--spacing-section-y)] px-[var(--spacing-section-x)]">
  <div class="mx-auto max-w-[80rem]">
    <span class="cs-topper">Section Label</span>
    <h2 class="cs-title">A bold, readable headline</h2>
    <p class="cs-text">Support text that stays within the body color scale.</p>
  </div>
</section>
```

Guidelines:
- Prefer `cs-` helpers for consistent typography.
- Use the `text-header` and `text-body` tokens for headings and body copy.
- Use spacing tokens for section padding instead of hard-coded values.
- Keep max widths aligned with existing components (`max-w-[80rem]` for containers).
