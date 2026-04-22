```markdown
# Design System Document: The Authoritative Technical Archive

## 1. Overview & Creative North Star: "The Intellectual Engine"
This design system moves away from the "generic ed-tech" aesthetic, which often feels juvenile or overly simplistic. Instead, we are building **"The Intellectual Engine."** This system is designed to feel like a high-end technical journal—authoritative, precise, and sophisticated. 

We achieve this through a "Digital Editorial" lens. By leveraging extreme typographic contrast (oversized headlines paired with dense technical body copy) and an "Asymmetric Grid," we create a rhythm that guides the eye through complex formulas and certification paths. This is not just a platform; it is a professional tool that commands respect through breathing room, tonal depth, and the absence of visual "noise" like borders and heavy shadows.

---

## 2. Colors & Surface Philosophy
The palette is grounded in the stability of `primary` (#00236f) and the aspirational energy of `secondary` (#006a61). 

### The "No-Line" Rule
To achieve a premium, custom feel, **1px solid borders are strictly prohibited for sectioning.** Boundaries must be defined solely through:
1.  **Background Color Shifts:** A `surface_container_low` section sitting against a `surface` background.
2.  **Tonal Transitions:** Using the hierarchy of surfaces to imply containment.

### Surface Hierarchy & Nesting
Treat the UI as a series of stacked, physical layers—like sheets of architectural vellum. 
- **Base Layer:** `surface` (#f7f9fb)
- **Content Sections:** `surface_container_low` or `surface_container`
- **Active Interactive Elements (Cards/Modals):** `surface_container_lowest` (#ffffff) to provide a "lifted" appearance without traditional elevation.

### The "Glass & Gradient" Rule
To avoid a "flat" or "template" appearance, utilize **Glassmorphism** for floating sidebars or persistent formula calculators. 
- Use a semi-transparent `surface_container_lowest` with a `backdrop-blur` of 20px. 
- **Signature Texture:** Apply a subtle linear gradient (from `primary` to `primary_container`) on high-impact CTAs to provide "visual soul"—a slight 15-degree tilt that mimics the refraction of light on a professional instrument.

---

## 3. Typography: The Editorial Scale
We utilize two distinct families to balance technical precision with modern authority: **Manrope** for Display/Headlines (structural and bold) and **Inter** for UI/Body (legibility for complex formulas).

- **Display-LG (Manrope, 3.5rem):** Reserved for hero certification titles. It should feel massive and immovable.
- **Headline-SM (Manrope, 1.5rem):** Used for technical module headings. Use tight letter-spacing (-0.02em) for a custom look.
- **Title-MD (Inter, 1.125rem):** The workhorse for dashboard cards and technical labels.
- **Body-MD (Inter, 0.875rem):** Optimized for high-density technical reading. Ensure a line-height of at least 1.6 to prevent "eye-strain" during long study sessions.

**Typographic Hierarchy:** Always pair a `headline-lg` in `on_surface` with a `label-md` in `on_tertiary_fixed_variant`. This high-contrast pairing (large/serif-adjacent vs small/utilitarian) creates the signature editorial look.

---

## 4. Elevation & Depth: Tonal Layering
Traditional shadows look "web-generic." We use **Tonal Layering** to define space.

- **The Layering Principle:** Place a `surface_container_lowest` card on a `surface_container_low` section. The slight delta in hex value creates a soft, natural lift.
- **Ambient Shadows:** If an element must float (e.g., a technical tooltip), use a "tinted" shadow. Instead of black, use `on_surface` at 6% opacity with a 40px blur. This mimics natural light reflecting off technical equipment.
- **The "Ghost Border" Fallback:** If accessibility requires a stroke (e.g., in high-contrast modes), use `outline_variant` at **20% opacity**. Never use a 100% opaque border.
- **Glassmorphism:** For dashboard navigation overlays, use `surface_tint` at 5% opacity over a blurred background to maintain the "Technical Archive" depth.

---

## 5. Components

### Buttons: The "Precision" Tool
- **Primary:** `primary_container` background with `on_primary_container` text. Use `rounded-md` (0.75rem) for a modern, architectural feel.
- **Secondary:** Use the `secondary_fixed` token. This teal provides the "Growth" signal against the deep blue.
- **Interaction:** On hover, do not change color—instead, increase the `surface_tint` overlay by 8% to create a "glow" effect.

### Input Fields: "Technical Entry"
- **Style:** Forgo the 4-sided box. Use a subtle background fill of `surface_container_highest` with a thicker 2px bottom-bar in `primary`. This mimics an engineering blueprint or data entry terminal.
- **Error State:** Use `error` text with a `error_container` subtle background glow.

### Cards & Lists: "The Seamless Feed"
- **Rules:** **Forbid divider lines.** 
- **Separation:** Use vertical white space (32px or 48px) to separate list items. 
- **Active State:** Instead of a border, an active list item or card should shift its background to `secondary_fixed_dim`.

### Specialized Components: "The Formula Bar"
- **Formula Containers:** Technical formulas must be housed in a `tertiary_container` with `on_tertiary_container` (a sophisticated navy-grey) to isolate them from standard text.
- **Progress Trackers:** Use `secondary` (#006a61) for completion bars. It should be a thin 4px line to maintain the professional, minimalist aesthetic.

---

## 6. Do’s and Don’ts

### Do:
- **Do** use asymmetric margins. For example, a dashboard container might have a 64px left margin and a 120px right margin to create an editorial "white space" column.
- **Do** use `on_surface_variant` for metadata. It provides enough contrast for technical readability without competing with primary headings.
- **Do** layer your surfaces. A white card on a light grey background is the hallmark of this system.

### Don't:
- **Don't** use 1px borders. If you feel you need one, try a background color shift first.
- **Don't** use standard drop shadows. If it looks like a "box shadow," it’s too heavy. It should look like a "glow" or "soft lift."
- **Don't** use high-saturation reds for everything. Use the `error` tokens sparingly; the platform should remain calm and professional even when a user gets an answer wrong.
- **Don't** crowd the interface. If the technical formulas are complex, double the surrounding white space. High contrast requires room to breathe.

---

### Closing Director's Note
The goal of this design system is to make the user feel smarter the moment they log in. By stripping away the "crutches" of modern UI—like heavy borders and generic shadows—and relying on intentional typography and tonal layers, we create a tool that feels as precise as the certifications it provides. Use the tokens precisely; they are the "measurements" of our engineering.```