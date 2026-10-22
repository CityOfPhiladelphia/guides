# Accessibility

> **Status:** 🟢 Adopted
> **Last reviewed:** 2026-10-22

These standards cover what engineering builds. Writing alt text, captions, and transcripts is a content responsibility; engineering ensures components support them.

Engineering work **must** meet [WCAG 2.1 Level AA](https://www.w3.org/TR/WCAG21/). Automated checks catch only part of what WCAG covers; the standards below cover the rest. Every item is a **must** unless it says otherwise.

The sections below follow WCAG's four principles of accessibility, known as [POUR](https://www.w3.org/WAI/WCAG21/Understanding/intro#understanding-the-four-principles-of-accessibility): content is **Perceivable**, **Operable**, **Understandable**, and **Robust**.

## Perceivable
- Images rendered in code have meaningful alt text, or `alt=""` if decorative. Components that display author-supplied images output the author's alt text and support marking an image as decorative.
- Text is real text, not an image of text, except in logos.
- Headings use heading elements in order, landmarks use elements such as `header`, `nav`, `main`, and `footer`, and data tables mark header cells with `th` and `scope`.
- The reading order in the code matches the visual reading order.
- Instructions never rely only on shape, size, position, or sound, such as "the round button" or "the link on the right."
- Text contrast is at least 4.5:1, or 3:1 for large text. Interface components and focus indicators are at least 3:1.
- Text resizes to 200% without loss of content, and content reflows at 320 CSS pixels wide without horizontal scrolling.
- Content works in both portrait and landscape; orientation is never locked unless it's essential.
- Content stays readable with line height at 1.5 times the font size, paragraph spacing at 2 times, letter spacing at 0.12 times, and word spacing at 0.16 times. Fixed-height text containers **should** be avoided.
- Information is never conveyed by color alone.
- Fields that collect personal information use the matching `autocomplete` attribute, such as `autocomplete="email"`.
- Content that appears on hover or focus can be dismissed, stays visible while hovered, and doesn't disappear on its own. (By using Escape key is preferred)
- Media players support captions, audio description, and transcripts, with keyboard-accessible controls to turn them on. Players used for live video support live captions.
- Audio that plays automatically for more than three seconds can be paused or stopped, or its volume controlled separately from the system volume.

## Operable
- All functionality works by keyboard, with no keyboard traps.
- Single-character keyboard shortcuts can be turned off or remapped, or only work when the related component has focus.
- Every interactive element has a visible focus indicator. Never remove the default outline without replacing it.
- Focus order follows the visual order. When a modal opens, focus moves into it, stays within it until it closes, and Escape closes it; focus then returns to the control that opened it. When a view changes, focus moves to the new view's heading or main content.
- A skip link leads to the main content.
- Each page has a unique, descriptive title, and link and button text describes its purpose.
- Headings and labels describe their topic or purpose.
- Pages can be reached more than one way, such as navigation plus search or a sitemap, except for steps in a process.
- A control's accessible name includes its visible label text.
- Anything that moves, scrolls, or auto-updates for more than five seconds can be paused, stopped, or hidden.
- Nothing flashes more than three times per second.
- Any time limit, including session timeouts, warns the user before expiring and lets them extend it.
- Anything done by dragging, swiping, or multi-finger gestures also works with a single tap or click.
- Actions fire when the pointer is released, not when it's pressed, so users can slide off a control to cancel.
- Anything triggered by shaking or tilting the device also has an on-screen control, and the motion trigger can be turned off.

## Understandable
- Every input has a visible `label` element tied to it, and related inputs such as radio buttons are grouped with `fieldset` and `legend`.
- Invalid fields are marked with `aria-invalid="true"`, and the error message is tied to the field with `aria-describedby`. Errors identify the field and explain how to fix it.
- Submissions with legal or financial consequences, or that change or delete user data, can be reviewed, corrected, or reversed before they're final.
- Focusing on or changing a control never navigates, submits, or opens new content on its own without warning.
- The page language is set with the `lang` attribute on the `html` element, and content in another language carries its own `lang` attribute.
- Navigation and component names stay consistent across pages.

## Robust
- Native HTML elements are used before ARIA, and ARIA is used only where native semantics fall short.
- Custom components expose their name through a visible label, `aria-labelledby`, or `aria-label`; their role through the matching ARIA role; and their state through attributes such as `aria-expanded`, `aria-checked`, or `aria-selected`, updated whenever the state changes.
- Status messages are announced through live regions: `role="status"` for routine updates and `role="alert"` for errors and urgent messages. The live region **must** already exist in the page before its content changes, or screen readers may not announce it.

## Automated checks
> **TODO:** Add the Pa11y workflow that runs automated accessibility checks on PRs.

## Testing
- Automated accessibility checks run in CI on every PR.
- Any change to interactive behavior gets a keyboard-only pass before merge.
- New or changed components get a screen reader check with NVDA or VoiceOver.
- Automated results supplement manual review; they never replace it.

> **TODO:** Once these standards are adopted, add a matching accessibility checklist to the pull request template so reviewers apply them on every PR. See [PR Standards](pr-standards.md#pr-template).

## Accessibility specialist
The accessibility specialist:
- Maintains these standards and the pull request checklist.
- Reviews new or changed shared components and Cloud Template Library templates before release.
- Performs manual and screen reader testing on templates and key user flows before launch, and verifies fixes.
- Advises engineering and content on applying these standards.

## References
- @michaelmahrt-philagov
- [WCAG 2.1](https://www.w3.org/TR/WCAG21/)
- [Pa11y](https://pa11y.org/)
