---
name: accessibility-xl
description: >
  Xmartlabs accessibility analysis procedure based on WCAG 2.2 Level AA, Google Core Web Vitals, and UX/UI best practices. Use this skill whenever someone asks about accessibility checks, WCAG compliance, contrast ratios, alt text, keyboard navigation, screen reader support, cognitive accessibility, or wants to audit a design or product for accessibility issues. Also trigger when someone asks how Xmartlabs handles accessibility in its design process, what tools are used, or needs a checklist to review a feature before handoff.
---

# Accessibility Analysis Procedure — Xmartlabs

**Goal:** Improve the design of existing web platforms and apps to simplify navigation, interaction, and content comprehension — ensuring they can be used by as many people as possible. Enhancing accessibility also leads to better SEO positioning as a side result.

All work follows **WCAG 2.2 Level AA**, **Google Core Web Vitals**, and UX/UI best practices.

---

## Tools

| Tool | Purpose |
|------|---------|
| WCAG Color Contrast Figma plugin | Check contrast ratios directly in Figma |
| Color Blind Simulator Figma plugin | Preview designs under different color vision deficiencies |
| Low Vision Simulator Figma plugin | Simulate reduced visual acuity |
| Color advice for cartography | Accessible palettes for data visualization |
| Check Browsers display modes | Verify Light and Dark mode compliance |
| PageSpeed Insights | Core Web Vitals and performance |
| Browser Inspect mode | DOM structure, heading hierarchy, ARIA roles |
| VoiceOver (macOS / iOS) | Screen reader testing on Apple devices |
| Narrator or NVDA (Windows) | Screen reader testing on Windows |
| Manual visual check | Final human review |

---

## Guidelines

### 1. Color Contrast

- All text and images of text must have a contrast ratio of at least **4.5:1** (3:1 for large-scale text).
- UI components and graphical objects (borders for active inputs, radio buttons, checkboxes) require at least **3:1** contrast against adjacent colors — or use a divider line between them.
- **Exception:** Disabled inputs and buttons are exempt from minimum contrast requirements.
- Never use color as the **only** visual means of conveying information, indicating an action, or distinguishing a visual element. Use one or more of these approaches:
  - Icons to supplement colors
  - Explicit text labels (e.g., "Error")
  - A second differentiator for links — underline or bold — plus a minimum 3:1 contrast ratio against body text
  - Textures and tooltips for data visualization (charts, graphs)
  - Varying thicknesses and stroke patterns for line charts (solid, dashed, dotted, dash-dot)
- Error messages for inputs or text areas must include an **additional visual element** such as an icon.
- Verify contrast in all supported **display modes** (Light and Dark).

---

### 2. Text Alternatives

Use HTML text instead of images of text unless the specific visual style is essential to the brand or content.

Provide a text alternative for all non-text content following these rules:

| Image Type | Rule |
|-----------|------|
| **Decorative** (no essential info, no associated task) | `alt=""` — empty alt attribute. Otherwise screen readers read the file name. |
| **Functional** (button or link with icon) | Describe the action, not the visual: "Go to home" not "Instagram Logo". Use `alt=""` if the exact same text is written immediately next to the icon. |
| **Simple Informative** (can be described in under 150 characters) | Add a short caption. |
| **Complex Informative** (charts, mind maps, heatmaps) | Long description — state the essentials briefly at the beginning so the user can decide whether to keep listening. |

**Best practices for writing alt text:**
- Be concise and clear
- Don't start with "Image of…" — the screen reader already announces it as an image
- End with a period so the screen reader pauses after reading it
- Avoid keywords added only for SEO that lack meaning for the user
- Provide only information relevant to the user experience — create a listening experience, not a visual description
- Avoid naming colors unless they are contextually relevant
- Don't reuse the same alt text without considering context (an image can be decorative in one case and informative in another)
- Don't use abbreviations or technical vocabulary
- Add alt text in every language the page supports
- Check whether the content can be converted to HTML text to eliminate the need for the image altogether

---

### 3. UX Writing

- Use **plain language** — avoid figures of speech, idioms, jargon, or metaphors (cognitive accessibility).
- Avoid **sensory or spatial references** (shape, size, location like "the round button" or "on the right") — these are inaccessible to users with visual impairments and break when layouts shift on mobile.
- Use action verbs instead of sensory-based verbs:

| Instead of | Use |
|------------|-----|
| See / Look at / View | Refer to / Access / Explore |
| Watch | Play / Consume |
| Listen to | Review / Access |

- Use **consistent labels** for components with the same function across pages.
- Use **descriptive page titles and headings** that help users understand where they are (e.g., "Experienced & professional experts for you" not "Our team").
- Link text must describe what will happen: "Contact us" not "See more" or "Learn more".
- Provide **labels or instructions** when content requires user input.
- Button labels must explicitly state the result of an action — "Buy Now" should trigger a purchase, not open a contact form.
- Offer **specific suggestions** for fixing detected input errors.

---

### 4. Layout & Orientation

- Don't restrict content to only portrait or landscape unless a specific orientation is essential to the function.
- Text must be resizable up to **200%** without loss of content or functionality.
- Content must reflow at **400% zoom** without requiring scrolling in two dimensions on small screens.
- Use only **one `<h1>`** per page to clearly identify the main topic.
- Heading elements must follow a **logical, descending sequence** — an `<h4>` should never appear before the first `<h3>`.

---

### 5. Media Assets

**Mechanism controls:**
- Provide a way to pause, stop, or hide moving content that starts automatically and lasts more than 5 seconds.
- Provide a way to pause, stop, or control the volume of audio that plays automatically for more than 3 seconds.

**Requirements by media type:**

| Type | Captions | Subtitles | Audio Description | Transcript | Sign Language |
|------|----------|-----------|------------------|------------|---------------|
| Audio-only (podcasts, voice notes) | N/A | N/A | N/A | ✅ Required | Optional |
| Video-only (silent) | N/A | N/A | ✅ Required | ✅ Required | Optional |
| Synchronized media (video + audio) | ✅ Required | Required only if dialog is in a different language than the page | ✅ Required | Required for AAA | Required for AAA |

- Apply these rules to **user-uploaded content** as well.

---

### 6. Visual Stability & Performance

- Use **predefined placeholders** with `height` and `width` set to reserve space for images and dynamic embeds — prevents Cumulative Layout Shift (CLS).
- Upload images in **.webp or AVIF** format for the highest web-optimized compression.
- **Compress images before uploading** — don't rely on browser-side processing.
- Use **SVG** for icons and simple graphics to minimize file weight and increase rendering speed.

---

### 7. Interactions & Keyboard

- Elements receiving keyboard focus must remain **fully visible** — the page must scroll automatically to keep the focused item in the viewable area (not hidden by sticky headers, footers, or banners).
- Allow users to **review, confirm, and correct** information before completing a legal or financial transaction.
- Any functionality requiring a complex pointer gesture (dragging, swiping) must also work with a **single click or tap** — carousels must have next/back buttons; sliders must accept a tap at a specific point on the track.
- Provide a way to operate **motion-triggered features** (e.g., shaking to open the flashlight) via standard UI components like buttons.

---

### 8. Design System Requirements

**Target size and focus:**
- Minimum target size for pointer inputs: **24×24 CSS pixels** (aim for 44×44 when possible).
- Design a **custom focus state** (border, outline, or glow) for every interactive component — or verify the default browser focus state is visible.
- Clearly define **all component states**: default, hover, focus, disabled, checked.
  - Don't just change the color to gray for disabled — the "Disabled" state must be a functional part of the component's logic in the design system.

**Input fields:**
- Use **standard labels** for common user data (name, email, address) so the browser can offer correct autofill.
- Provide clear **instructions and format examples** for fields requiring specific input (e.g., DD/MM/YYYY).
- Identify required fields with the word "required" or a universally understood symbol (asterisk *).
- **Auto-populate** previously entered information in later steps — don't make users re-type data.

---

### 9. User Customization

- Allow users to turn off or extend any **session timeouts** by at least 10× the default limit.
- Provide a way to turn off or reconfigure **single-character keyboard shortcuts** to prevent accidental activation by voice-input users or users with motor disabilities.
- Provide a mechanism to **pause and resume auto-updating content** so users have enough time to read and interact.
- Allow users to **disable motion actuation** entirely to prevent accidental triggers.

---

### 10. Cognitive Accessibility

- Use **left-aligned text** for LTR languages and right-aligned for RTL languages.
- Place **help and support features** in the same relative location across all pages.
- Login processes must not rely on **cognitive tests** (puzzles, maths) — allow password managers, copy-paste, and biometrics.
- Ensure **"Back" and "Undo"** are always available to help users recover from mistakes without anxiety.
- **Limit navigation choices** in a single view to prevent distraction.
- Avoid presenting too much content at once — use steppers or progress bars for complex flows.

---

## Glossary

| Term | Definition |
|------|-----------|
| **Alt Text** | A brief text description added to the website code assigned to an image or non-text element that explains its meaning or purpose to screen reader users |
| **Audio Description** | A secondary narration track that describes important visual details (actions, facial expressions, scene changes) during natural pauses in the dialogue, for users who are blind or low-vision |
| **Captions** | On-screen text synchronized with a video providing an equivalent for all audible information: dialogue + meaningful sound effects (e.g., [phone rings]). Must be in the same language as the audio. |
| **CLS (Cumulative Layout Shift)** | A Google metric that measures how much content on a page "jumps" or shifts unexpectedly during loading, which can cause users to lose their place or click the wrong element |
| **Interactive Transcript** | A transcript that highlights words as they are spoken in the audio |
| **Sign Language** | A visual-gestural language used to provide an accessible version of spoken audio for users whose primary language is sign |
| **Subtitles** | On-screen text synchronized with a video that translates spoken dialogue into another language. Required only when the dialog is in a different language than the page. |
| **Transcript** | A text-based version of audio or video content, allowing users to consume the information at their own pace without needing to listen or watch |
| **WCAG** | Web Content Accessibility Guidelines — the international standard for digital accessibility, maintained by the W3C. Xmartlabs targets Level AA compliance. |

---

## How to Use This Skill

When reviewing any Xmartlabs design or product for accessibility:

1. **Start with color** — run the WCAG Color Contrast plugin before anything else. Catch ratio failures early.
2. **Check all states** — verify every interactive component has default, hover, focus, disabled, and checked states defined.
3. **Review alt text** — go through every image and icon and classify it (decorative / functional / informative). Write or validate the alt text accordingly.
4. **Test with a screen reader** — use VoiceOver on macOS/iOS or NVDA on Windows. Navigate by headings, links, and form elements.
5. **Test at 200% zoom** — resize the browser and verify no content is lost or overlapping.
6. **Verify in both Light and Dark mode** — contrast issues often hide in one mode only.
7. **Check UX copy** — look for sensory references, vague link text, and missing field labels.
8. **Use the checklist** — go through the 10 categories above systematically. Mark each item as Pass, Needs Fix, or Not Applicable.
