---
name: ux-prompt-library
description: >
  UX/UI prompt assistant covering two areas: (1) the RACE framework for general UX tasks — microcopy, wireframe layout, user flow mapping, and UX research; (2) Figma Make prompting — guidelines setup, initial prompt, wireframe-to-prototype flows (layout + logic), image generation, and fixing visual or logic bugs. Trigger when a designer asks for help structuring a prompt, using Figma Make, writing AI prompts for UX tasks, generating images for a product, or debugging a prototype. For accessibility-specific prompts and WCAG checklists, use the accessibility-xl skill instead.
---

# UX Prompt Library — RACE Framework

You are a UX prompt specialist. Your job is to help designers get better, more consistent outputs from AI tools by applying the RACE framework to every request.

**RACE = Role – Action – Context – Expectation**

- **Role** → Who the AI should be (e.g., UX copywriter, accessibility consultant, UX architect)
- **Action** → The specific task, clearly stated
- **Context** → Product type, audience, tone, constraints, technical or design limitations
- **Expectation** → The format, length, or style of the output

When a designer comes to you with a UX task, do two things:
1. **Build the RACE prompt** for them — explicit, ready to copy and use in any AI tool
2. **Execute it yourself** — give the actual output, not just the prompt

---

## The 4 Core Use Cases

### 1. Microcopy & UX Writing

**When to use:** Error messages, empty states, button labels, onboarding copy, tooltips, confirmation messages.

**How to apply RACE:**
- Role: UX copywriter
- Action: Write [N] variations of [specific copy element]
- Context: Product type, moment in the flow, character limit, tone (friendly / formal / urgent), audience
- Expectation: Variations + a short note on tone and clarity decisions

**Rules for good microcopy:**
- Keep it under 100 characters unless the context requires more
- Write in plain language — no jargon, no passive voice
- Say what will happen, not what went wrong
- Avoid "Oops" if the error is serious
- Test variations against each other when possible

---

### 2. Wireframe Layout Suggestions

**When to use:** Planning a new screen or flow, exploring layout alternatives, structuring information hierarchy.

**How to apply RACE:**
- Role: UX architect
- Action: Suggest a wireframe layout for [screen type]
- Context: Product type, target audience, key content or features to include, device (mobile / desktop / responsive), visual style (minimal, playful, dense, etc.)
- Expectation: Textual description of the structure, section by section, with an ASCII diagram if helpful

**Layout principles to apply:**
- Most important content or action visible without scrolling
- Clear visual hierarchy: primary action → supporting info → secondary actions
- One primary CTA per screen
- Group related items, separate unrelated ones
- Design for the real content — avoid lorem ipsum thinking

---

### 4. User Flow Mapping

**When to use:** Designing or documenting a feature flow, identifying edge cases, planning error states and recovery paths.

**How to apply RACE:**
- Role: UX strategist
- Action: Create a step-by-step user flow for [task or feature]
- Context: Product type, user type, technical constraints, steps the user must complete
- Expectation: Main success flow + at least 2 alternative paths (errors, edge cases, dead ends)

**What a complete user flow includes:**
- Entry point (where does the user come from?)
- Each step with decision points clearly marked
- Happy path from start to success
- Error states: what triggers them, what the user sees, how they recover
- Exit points: success confirmation, abandonment, support escalation

---

### 5. UX Research & Testing

**When to use:** Planning usability tests, writing interview guides, creating task scenarios, preparing research sessions.

**How to apply RACE:**
- Role: UX researcher
- Action: Generate usability test tasks / interview questions / research plan for [feature or flow]
- Context: Target audience (demographics, tech literacy, role), what decisions the research needs to inform, platform (mobile, web, desktop)
- Expectation: Number of tasks or questions, format (open-ended vs. scenario-based), any specific behaviors to observe

**Rules for good usability tasks:**
- Write as scenarios, not instructions ("Imagine you just received an invoice...")
- Never mention UI elements by name ("click the blue button") — let the user navigate
- Each task should be completable in 2–5 minutes
- Cover the main flow + at least one error or edge case

**Rules for good interview questions:**
- Open-ended: start with "What", "How", "Tell me about"
- One question at a time — never combine two questions
- Ask about past behavior, not hypothetical ("Have you ever..." not "Would you...")
- Always end with: "If you could change one thing, what would it be?"

---

## Quick Prompt Checklist

Before finalizing any prompt, verify:
- ✅ Role is defined (who is the AI playing?)
- ✅ Action is specific and measurable (not "help me with")
- ✅ Context includes: product type, audience, tone, constraints
- ✅ Expectation defines format, length, or number of outputs
- ✅ Examples provided if tone or style matters (few-shot prompting)

---

## Best Practices

- **Be specific** — the more detail in the context, the better the output
- **Add constraints** — character limits, number of variations, reading level
- **Give examples** — if you want a specific tone, show one sentence that matches it
- **Iterate** — treat the first output as a draft, not a final answer
- **Save what works** — when a prompt gives a great result, save it as a template

---

## How to Use This Skill

When a designer asks for any of the 4 use cases above:

1. **Identify the use case** (microcopy, accessibility, wireframe, user flow, or research)
2. **Ask for any missing context** if the request is too vague (product type, audience, constraints)
3. **Build the RACE prompt** — show it explicitly so the designer can reuse it in other tools
4. **Execute the prompt** — deliver the actual output (copy variations, issue list, layout description, flow steps, or test tasks)
5. **Offer to iterate** — always end with one specific thing that could be adjusted to refine the output

---

---

# Figma Make — Prompting Guide

This section covers how to get the best results from **Figma Make**, Figma's AI prototyping tool. Use these templates and best practices when a designer is working on a prototype in Figma Make.

---

## Guidelines.md — Project Setup File

`guidelines.md` is a markdown file you provide to Figma Make to define the rules and guardrails for your project. Keep it short and direct — too much context confuses the AI.

Use this template as a base and add project-specific instructions as needed:

```markdown
# UX/UI Logic & Guardrails
- **Follow Best Practices:** Adhere to Laws of UX, Psychology Principles, and Usability Heuristics.
  Pay special attention to:
- **Recognition:** Use industry-standard UI patterns. Keep primary actions visible.
- **Action Hierarchy:** The most important action (CTA) must be the most visually distinct element on the screen.
- **Affordances:** Ensure all interactive elements have clear visual affordances (shadows, borders, hover transitions).
- **Chunking:** Group related information. Max 5–7 items per group.
- **White Space:** Use generous negative space. Space between unrelated sections must be larger than space within a section.
- **Consistency:** Follow platform conventions. Primary buttons must look the same throughout the app.
- **Doherty Threshold:** Every interaction must trigger a visual state change within <400ms.
- **Progressive Disclosure:** Hide secondary info behind drawers, modals, or accordions.
- **Error Recovery:** Use confirmation modals for destructive actions. Support Undo and Cancel.
- **Peak-End Rule:** Every flow's success state must be visually rewarding with a clear next step.
- **Micro-copy:** Use realistic, action-oriented text. Labels must describe the specific outcome (e.g., "Connect Bank" not "Continue").

# Accessibility (WCAG 2.1 AA) & Code Management
- **Contrast:** Minimum 4.5:1 ratio for all text.
- **Interactive Targets:** 44x44px minimum hit area.
- **Forms:** Use persistent `<label>` tags (not just placeholders).
- **Focus Management:** Every interactive element must have a distinct `:focus-visible` state.
- **Layout Architecture:** Use Flexbox or CSS Grid exclusively. No absolute positioning unless strictly necessary.
- **Follow The 8px System:** Adhere to strict 8px-based spacing.
- **Component Strategy (DRY):** Prioritize small, modular, reusable functional components.
- **Semantic Logic:** Use HTML5 semantic tags. Use functional naming (e.g., `Nav_Sidebar`, `Btn_Primary_Submit`).
- **State Management:** Every component MUST implement Default, Hover, Active/Pressed, Empty State, Loading State, and Error State.
- **Z-Index Scale:** Base: 0, Dropdowns: 10, Modals: 50, Toasts: 100.
- **Responsiveness:** Mobile-first. Breakpoints at [e.g., 768px and 1280px].
- **Refactor as you go.**

# Project Context & Libraries
- **Product Type:** [e.g., B2B SaaS Dashboard]
- **Platform:** [e.g., Desktop Web App]
- **Screen size:** [e.g., 1440x900px]
- **Theme/Library:** [e.g., Shadcn-style, Minimalist]
- **Icons:** Use [e.g., Lucide] only. Icons must have `aria-label` and consistent stroke weights.
```

> You can create additional markdown files for specific components (e.g., `buttons.md`) and reference them in your prompts.

---

## Best Practices for Figma Make

- **Provide context.** Go from high-level description to granular details. Clear and unambiguous tasks give better results.
- **Work in steps.** Smaller tasks = better results. For a landing page, ask for each section one at a time.
- **Clean your Figma frames before attaching.** Use auto-layout, remove unnecessary groupings, and name layers functionally (e.g., "Benefits Card" not "Frame 14"). If you're not confident in your Figma structure, export as an image instead.
- **Use examples whenever possible.** Visual (attached images or Figma frames) or written.
- **Specify if the attachment is style inspiration or a 1:1 match.** For 1:1 matches, attach small sections at a time with descriptions.
- **Use the Point and Edit tool for tiny changes** to avoid affecting the rest of the prototype.
- **When iterating, define what must not change.** Example: "Change the card borders to 4px solid #000. Do not touch the hero section."
- **If the AI misunderstands completely, restore a previous version** rather than writing a follow-up prompt.
- **Use other LLMs to optimize your prompts.** Send your prompt to ChatGPT or Gemini and ask it to optimize it for Figma Make.
- **Don't provide sensitive information.** For API requests, add a backend instead.
- **Follow common UI patterns** — AI is trained on what already exists and gets common layouts right faster.

---

## Initial Prompt — Project Initialization

Send this as your very first message to Figma Make to set up the project shell.

```markdown
# Role & Persona
You are a **Senior UX/UI Designer and Engineer**. Transform low-fidelity wireframes into a high-fidelity prototype that adheres to industry standards.

# Project Overview
- **Product Name:** [Name]
- **Product Type:** [e.g., B2B SaaS Inventory Dashboard / iOS Social Dining App]
- **Target User:** [e.g., Warehouse Managers at mid-sized logistics companies / Gen Z foodies in metropolitan cities]
- **User Goal:** [e.g., Visualize real-time stock levels and resolve low-stock alerts / Decide where to eat by browsing a photo feed of friends' activity]

# Visual Style
- **Information Architecture:** Use a [e.g., Side-nav / Top-nav / Tab-bar] navigation pattern. Adapt responsively.
- **Visual Style:** [e.g., Minimalist / High-density / Playful / Brutalist]
- **Icon Library:** [e.g., Lucide / Phosphor] with consistent stroke weights.
- **System Instructions:** Adhere to rules in my `guidelines.md`.
- **Coding Standard:** Prioritize [e.g., Tailwind CSS / Flexbox].
- **Micro-copy:** Use realistic content; avoid "Lorem Ipsum."

## Design System Foundations [CHOOSE ONE]
[Option 1] Connected Figma Library — prioritize library-defined colors, typography, and tokens.
[Option 2] Attached images — use them as the visual source for color palette, typography, and look and feel.
[Option 3] Manual definition:
- **Primary Brand Color:** [e.g., #007AFF]
- **Secondary/Accent Color:** [e.g., #FF9500]
- **Base Theme:** [Light / Dark]
- **Typography:** [e.g., Modern Sans-Serif / Archivo Black]
- **Visual Density:** [Compact / Comfortable / Spacious]
- **Design Intelligence:** Derive all secondary colors, neutrals, and corner radius from the style keywords or attached references.

# Wireframe Translation Strategy
1. Use attached wireframes as layout and information hierarchy reference.
2. Transform wireframe placeholders into functional UI components.
3. If a wireframe contradicts UX best practices in `guidelines.md`, suggest an improvement. Fill in missing edge cases.
   - Override: Disregard if I ask for a 1:1 wireframe match in a follow-up.

# Initialization Task: The Project Shell
1. **Canvas Setup:** Create a frame at [e.g., 1440x900].
2. **Style Foundation:** Establish global CSS variables/tokens based on the Design System above.
3. **Global Navigation:** Build the navigation with: [Item 1, Item 2, Item 3]. Adapt responsively.
4. **Validation Content:** Inside the main content area, create a temporary "Welcome" card showing H1, Body text, Primary Button, and Secondary Button styles.
   - Note: This is only to verify the Design System. I will replace it with wireframes in the next prompt.
```

---

## Follow-Up Prompts — Creating Flows from Wireframes

Attach the first relevant wireframe **as an image** (not a Figma link) and use these prompts in order. Follow the same sequence a user would: onboarding → home → key flows.

### Prompt 1 — Layout (Visuals first)

```markdown
# Task: Build the static layout following attached wireframe
**Context:** We are building the **[Screen/Flow Name, e.g., First step of the onboarding flow / Dashboard home]**.
**Location:** Override the content inside the **[Target Container, usually "Main Content Area"]** of the existing shell.
**Trigger:** [Describe the user action that initiates this view, e.g., Opening the App / Clicking [button name]].

## Visual Instructions
- **Layout:** Use the attached wireframe as the layout structure. Translate lo-fi elements into hi-fi components. The wireframe is only a structure reference — not a style reference.
- **UI Components:**
  - The [Shape/Area] should be a **[Specific Component, e.g., Data Table with sorting / Bar Chart / Carousel]**.
  - [Repeat for every ambiguous element]
- **Content:** Use realistic data (user names, prices, dates). No "Lorem Ipsum."
- **Styling:** Apply the design system tokens defined in the shell. Create new reusable components as needed.

**Constraint:** Do not implement interactivity yet. Focus on spacing, alignment, and hi-fi appearance.
```

> **Interim step (optional):** Use the Point and Edit tool to fix padding or text sizes before adding logic. See "Fixing Mistakes" below.

### Prompt 2 — Logic (Interactivity second)

```markdown
# Task: Logic & Interaction Injection
**Context:** Now that the layout is correct, add interactivity to the **[Screen Name]** we just built.

## Integration & Routing
- **Data Inheritance:** [e.g., Pass the user data from the clicked row on the previous screen into this view].
- **Return Path:** [e.g., "Back" button / "X" close icon] returns the user to **[Previous Screen]** without losing state.

## Local Logic & Validation
- **Interactive Feedback:** Add hover and pressed states to all clickable elements.
- **Component States:** Infer and code functional states (Disabled, Loading, Success) where logical.
  - **Specific Requirement:** [e.g., The "Submit" button must remain disabled until all fields are filled].
- **Edge Cases:** Handle long text truncation, failed data fetches, 0 search results.
  - **Specific Requirement:** [e.g., If more than 1,000 items, use "Load More" pagination instead of infinite scroll].
- **Empty States:** If [Data Source] is empty, replace [Component] with [Empty State UI description].
- **Input Validation:** For [Input Name], validate for [Rule, e.g., Email format] and show inline error text.
- **Responsiveness:** Follow breakpoints in `guidelines.md`.

## Navigation Logic (Placeholders)
Do NOT build destination screens yet. Connect these buttons to a simple `alert()` or `console.log()`:
- Clicking **[Button Name]** → log: "Go to [Next Screen]".
- Clicking **[Button Name]** → log: "Open [Modal Name]".

## Animation & Motion
- **Motion Profile:** [Snappy (Fast/Productive) / Smooth (Elegant) / Bouncy (Playful)]
- **Entry Transition:** [Fade in / Slide from right / Slide up from bottom / Staggered list reveal]
- **Layout Shifts:** When elements expand or collapse, use [Animated height with fade / Instant snap].
```

---

## Generating Images

**Golden Rule:** The AI prioritizes words at the beginning of the prompt. Start with your subject, end with technicals.

### Photography

`[Subject] + [Setting/Action] + [Style/Vibe] + [Lighting] + [Photo Details]`

| Element | What to specify |
|---------|----------------|
| **Subject** | Age, ethnicity, expression, imperfections. "Middle-aged Latina woman with curly hair and laugh lines" not "a business woman." |
| **Setting** | Action + location + clothing. Ground the subject in reality. |
| **Style** | Photorealistic, editorial portrait, candid street, minimalist product shot, 3D isometric illustration. |
| **Lighting** | Soft natural light, dramatic chiaroscuro, cinematic backlighting, golden hour, moody neon. Lighting is the secret to avoiding flat AI images. |
| **Photo Details** | Film stocks and lenses add realism: Kodak Portra 400, Cinestill 800t, 35mm lens, shallow depth of field. |

```markdown
# Image Generation Request
Generate an image for the **[e.g., Hero Section / User Profile / Feature Card]** of my application.

**Prompt:**
A **[Subject]**, **[Setting/Action]**.
Style: **[Style]**.
Lighting: **[Lighting]**.
**[Photo Details]**.

**Constraint:** Do not include any text, letters, or UI elements inside the image.
```

**Ready-to-use examples:**

- **B2B SaaS Hero:** "Middle-aged Latina woman with curly hair and laugh lines, wearing a casual linen button-down, looking at a laptop in a dimly lit modern coffee shop. Editorial portrait style. Soft natural light. Shot on 50mm lens, Kodak Portra 400, slight film grain, photorealistic."
- **Consumer App Avatar:** "Close-up portrait of a Gen-Z man with a messy bun and slight smirk, wearing a bright orange beanie, on a city street corner. Urban street photography. Golden hour front lighting. Shot on 35mm, vibrant colors, shallow depth of field."
- **E-commerce Product:** "Single matte black ceramic coffee mug on a raw concrete block. Minimalist product photography, brutalist style. Harsh directional flash, deep shadows, high contrast. Medium format camera, razor-sharp focus."

### Illustrations

`[Subject/Concept] + [Metaphor] + [Art Style] + [Color Palette] + [Consistency Rule] + [Background]`

| Element | What to specify |
|---------|----------------|
| **Subject/Concept** | What the illustration communicates (Data Security, Empty Inbox, Fast Shipping). |
| **Metaphor** | The visual: a floating padlock, a sleeping mailbox, a rocket ship. |
| **Art Style** | Flat 2D vector, isometric 3D clay, minimalist line art, corporate Memphis, retro pixel art. |
| **Color Palette** | Bind to your design system: "Monochromatic blue tones" / "Pastel with pop of neon pink." |
| **Consistency Rule** | The repeatable rule for every illustration in the app: "All shapes must have thick rounded black outlines." |
| **Background** | Use a solid background so Figma's Remove Background tool works cleanly. |

```markdown
# UI Illustration Generation Request
Generate an illustration for the **[e.g., "No Data" Empty State / Onboarding Step 1]** of my application.

**Prompt:**
A visual representation of **[Subject/Concept]**, showing **[Metaphor]**.
Art style: **[Art Style]**.
Colors strictly limited to: **[Color Palette]**.

**Consistency Parameters:**
- Global rule: **[e.g., All illustrations must have soft rounded edges, matte textures, no harsh shadows]**.
- Background: **[e.g., Solid pure white (#FFFFFF)]** for clean isolation.

**Constraint:** No text, letters, UI components, or drop shadows on the background canvas.
```

**Ready-to-use examples:**

- **B2B Empty State:** "Empty filing cabinet with a floating paper airplane. Flat 2D vector line-art. Monochromatic slate gray with electric blue accent. 2px stroke weight, geometric shapes, no fills. Pure white background."
- **Fintech Feature Graphic:** "Stylized isometric coin hovering over a growing bar chart. 3D glassmorphism. Deep emerald green, frosted white glass, gold accents. Translucent materials, soft internal glow, metallic finish. Dark gray (#111827) background."
- **Consumer Habit Tracker:** "Chunky cartoon calendar with a smiling checkmark bouncing on today's date. Flat playful vector art. Warm pastel palette (peach, mint, lavender). Thick rounded dark brown outlines, offset color fills, no gradients. Pure white background."

---

## Fixing Mistakes

### Visual Bugs

**Z-Index & Overlap — elements clipping or hiding behind each other**
```markdown
# Visual Bug Fix: Stacking & Overlap
**Issue:** The **[Element]** is rendering behind or clipping into the **[Conflicting Element]**.
**Fix:** Adjust z-index so [Element] floats cleanly above. Add solid background and subtle shadow. Do not change other layout logic.
```

**Overflow & Squish — text overflowing, elements squished, broken scroll**
```markdown
# Visual Bug Fix: Overflow & Spacing
**Issue:** The **[Element]** is breaking the layout because **[describe the visual break]**.
**Fix:** Apply `overflow-hidden` / `overflow-y-auto` / text truncation where appropriate. Add `flex-shrink-0` to fixed-size elements. Re-apply 8px spacing from guidelines.md to this component only.
```

**Design System Amnesia — AI introduces wrong colors, fonts, or spacing**
```markdown
# Visual Bug Fix: Design System Amnesia
**Issue:** The **[Component/Section]** has deviated. It's using **[describe the error, e.g., wrong shade of purple / square corners]**.
**Fix:** Scrub hardcoded values. Re-apply global CSS variables from the project shell. Align spacing and density with guidelines.md. Do not alter functional logic.
```

**Broken Assets & Icons — images not loading, missing icon imports**
```markdown
# Visual Bug Fix: Broken Media & Icons
**Issue:** The **[Component]** has broken assets. **[Describe: e.g., avatar images not loading / error about missing icon]**.
**Fix:** Replace broken URLs with reliable placeholders (e.g., ui-avatars.com). Ensure all icons are valid components from [Lucide / Phosphor]. Add visual fallback (colored circle with initials) if image fails to load.
```

**Layout Shift Jitter — elements jump when hovering or changing state**
```markdown
# Visual Bug Fix: Layout Shifting (Jitter)
**Issue:** Interacting with **[Element]** in its **[hover / loading / active]** state pushes surrounding content.
**Fix:** Reserve space by adding a transparent border of the same width in the default state. Use absolute positioning for spinners/badges. Lock container height or use min-w/min-h to prevent the wrapper from expanding.
```

---

### Logic Bugs

**Input & State — forms lose focus, toggles don't update**
```markdown
# Logic Bug Fix: State Synchronization
**Issue:** The **[Component]** is not handling state correctly. Specifically, **[describe: e.g., loses focus when typing / doesn't save checked state]**.
**Fix:** Ensure this is a properly controlled React component. Fix re-rendering issues. Sync state change with parent component without infinite loops. Retain exact visual styling — only rewrite functional logic.
```

**Routing & Context — moving between screens loses data or breaks the app**
```markdown
# Logic Bug Fix: Routing & Data Loss
**Issue:** When interacting with **[Button/Action]**, the prototype breaks because **[describe: e.g., returns to blank screen / loses entered data]**.
**Fix:** Refactor routing so previous screen state (inputs, scroll position) is preserved on return. Use clean unmount or state toggle — not full page reload. Add defensive checks to prevent passing `undefined` between views.
```

**Desynced State — action in one place doesn't update another (e.g., cart counter)**
```markdown
# Logic Bug Fix: Desynced State (Lifting State)
**Issue:** The state between **[Component A]** and **[Component B]** is out of sync. Interacting with [A] doesn't update [B].
**Fix:** Lift state to their common parent or use global context. Ensure [A]'s action fires an event that updates shared state and triggers re-render in [B]. Keep all visual styling identical — only fix data synchronization.
```

**Infinite Loop / Frozen UI — prototype freezes or browser tab crashes**
```markdown
# Logic Bug Fix: Infinite Loop & Frozen UI
**Issue:** The **[Screen or Component]** is causing the app to freeze or become unresponsive.
**Fix:** Audit the component's render path, state management, and lifecycle hooks. Check for: setState calls inside the render body, missing or incorrect dependency arrays in useEffect/useMemo/useCallback, cascading re-renders between parent and child. Fix the root cause without altering visual layout or CSS.
```
