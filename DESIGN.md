# Design System Document

## 1. Overview & Creative North Star: "The Celestial Observer"
The Creative North Star for this design system is **"The Celestial Observer."** This is an editorial-first, immersive digital experience that eschews traditional, "boxy" web layouts in favor of depth, light, and infinite scale. 

To move beyond a generic "dark mode" template, the system utilizes **intentional asymmetry**—placing content off-center to mimic the vastness of the cosmos—and **tonal layering**. Elements should appear as if they are floating in a three-dimensional nebula rather than pinned to a flat grid. We use high-contrast typography scales (Space Grotesk) to command authority, paired with "glowing" interactive elements that act as navigational beacons in the dark.

---

### 2. Colors & Surface Logic
The palette is rooted in the deep void of space, accented by high-energy gases (Cyan and Violet).

#### The "No-Line" Rule
**Explicit Instruction:** Do not use 1px solid borders to define sections. Boundaries must be established through shifts in background tone or soft gradients. 
*   **Good:** A `surface-container-low` section transitioning into a `surface` background.
*   **Avoid:** Using `outline` at 100% opacity to "box in" a feature.

#### Surface Hierarchy & Nesting
Treat the UI as a series of stacked, semi-transparent layers. Use the following tiers to define depth without shadows:
*   **Base Layer:** `surface` (#0c0e18) – The infinite void.
*   **Secondary Content:** `surface-container-low` (#10131f).
*   **Primary Interactive Cards:** `surface-container` (#161927).
*   **Floating/Elevated Elements:** `surface-container-highest` (#212538).

#### The "Glass & Gradient" Rule
To achieve a premium "Nebula" feel, use **Glassmorphism**. Floating panels should use a semi-transparent `surface-variant` with a `backdrop-blur` of 20px–40px. 
*   **Signature Texture:** For primary CTAs, use a linear gradient from `primary` (#81ecff) to `primary_dim` (#00d4ec) at a 45-degree angle. This provides a "radiating" energy that flat colors lack.

---

### 3. Typography
The system uses a pairing of **Space Grotesk** (Display/Headline) for a technical, modern edge and **Inter** (Body/Label) for peak legibility.

*   **Display (Space Grotesk):** Use `display-lg` (3.5rem) with -0.04em letter spacing for hero sections. The extreme scale creates an editorial, high-end feel.
*   **Headlines (Space Grotesk):** `headline-lg` (2rem) should be used for section titles. Ensure high contrast using `on_surface` (#e1e4fe).
*   **Body (Inter):** Use `body-lg` (1rem) for general reading. The generous x-height of Inter ensures clarity against the dark background.
*   **Labels (Inter):** `label-md` (0.75rem) should always be in `on_surface_variant` (#a7aac2) to maintain hierarchy and prevent visual noise.

---

### 4. Elevation & Depth
In this system, light is the primary indicator of importance.

*   **The Layering Principle:** Avoid "Drop Shadows" in the traditional sense. Instead, use "Tonal Lift." Place a `surface-container-highest` card on a `surface` background to create a natural, soft separation.
*   **Ambient Shadows:** If a floating effect is required (e.g., a modal), use an ultra-diffused shadow: `box-shadow: 0 20px 50px rgba(129, 236, 255, 0.08);`. Note the use of the `primary` tint in the shadow to mimic light reflecting off a nearby star.
*   **The Ghost Border Fallback:** If a border is required for accessibility, use `outline_variant` (#43475c) at **15% opacity**. It should be felt, not seen.
*   **Glow States:** Interactive elements (buttons, active chips) should utilize a `0 0 15px` outer glow using the `primary` or `secondary` token to signify they are "active" energy sources.

---

### 5. Components

#### Buttons
*   **Primary:** Gradient fill (`primary` to `primary_dim`), `xl` rounded corners (1.5rem), white text. On hover, increase the outer glow spread.
*   **Secondary:** Ghost style. No fill, `outline_variant` at 20% opacity. On hover, fill with `surface_bright` at 10% opacity.
*   **Tertiary:** Text only, using `primary` color with an underline that appears only on hover.

#### Cards & Lists
*   **The Divider Ban:** Strictly forbid `hr` tags or 1px dividers. Separate list items using `spacing.4` (1.4rem) of vertical white space or by alternating background tones between `surface-container-low` and `surface-container-lowest`.
*   **Interactive Cards:** Use `surface-container` with an `xl` corner radius. On hover, transition the background to `surface-container-high`.

#### Input Fields
*   **Style:** Minimalist. No bottom line. Use `surface_container_highest` with a 5% `primary` tint. 
*   **Active State:** The border should glow with the `primary` (#81ecff) color at 40% opacity.

#### Cosmic Chips
*   Used for categorizing celestial bodies (e.g., "Nebula," "Exoplanet").
*   **Style:** `full` roundedness (pill shape). Use `secondary_container` (#3e0061) with `secondary` (#e4b5ff) text.

---

### 6. Do's and Don'ts

#### Do
*   **Do** use asymmetrical margins (e.g., `spacing.20` on the left, `spacing.10` on the right) to create a dynamic, editorial flow.
*   **Do** use the `24` spacing token (8.5rem) for section breaks to let the "starfield" background breathe.
*   **Do** apply `backdrop-filter: blur(12px)` to all navigation bars to allow the cosmic background to peak through.

#### Don't
*   **Don't** use pure black (#000000) for large surfaces; it kills the "depth" of the deep space blues. Use `surface` (#0c0e18).
*   **Don't** use standard "Drop Shadows" (Black/Grey). They look muddy on dark blues. Always tint shadows with `primary` or `secondary` tones.
*   **Don't** use sharp 90-degree corners. The universe is organic; always use the `DEFAULT` (0.5rem) or `xl` (1.5rem) roundedness scale.

---

### 7. Layout & Spacing
*   **The "Deep Space" Buffer:** Use the `20` and `24` spacing tokens to create massive gaps between high-level sections. This mimics the isolation of objects in space.
*   **Micro-Interactions:** Elements should "drift" into place. Use `cubic-bezier(0.2, 0, 0, 1)` for all transitions to give a feeling of weightlessness and high-end precision.