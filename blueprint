---
name: premium-site-blueprint
description: >
  Generate a complete, Awwwards-level multi-page website blueprint AND master implementation prompt
  for any brand, industry, or product. Use this skill whenever the user wants to build a premium,
  highly interactive, multi-page website and asks for a blueprint, plan, design doc, or site spec.
  Trigger on phrases like: "build me a website for X", "create a blueprint for a startup site",
  "design a premium landing page", "plan a multi-page site", "I want a website like NEXUS/AETHERIS",
  "Awwwards-style site", "new industry website", or any request combining a brand/product name with
  website creation. Always use this skill — do not fall back to basic landing page advice or generic HTML.
---

# Premium Multi-Page Site Blueprint

Generate a complete **blueprint + master implementation prompt** for a premium, eccentric,
highly interactive multi-page website. Output must be production-ready and agent-executable.

**ABSOLUTE HARD LIMIT:** The master implementation prompt (Section 6) must never exceed **40,960 characters**. Be dense, high-signal, zero filler.

Two non-negotiable layers every time:
- **Structural DNA** — interaction architecture (always same premium level)
- **Visual Skin** — design kit (always unique to the industry)

---

## Step 1: Extract Brand Context

Extract or infer from context:

| Field | What to capture |
|---|---|
| **Brand name** | Site/product name |
| **Industry** | SaaS, Web3, Fashion, Fintech, Healthcare, etc. |
| **Core product/service** | 1-sentence description |
| **Target audience** | Who is this for? |
| **Tone** | Institutional, Editorial, Playful, Technical, Luxury |

Only ask if critically missing. Make expert decisions autonomously — do not pepper the user with questions. The only exception: ask ONE clarifying question if the industry requires a highly specific physical interaction (e.g., 3D product configurator, AR try-on).

---

## Step 2: Select or Invent the Design Kit (Visual Skin)

Pick the closest kit. If the industry does not fit any of the 5, **invent a completely new, highly specific kit** tailored to that exact niche — define its palette, fonts, texture, and motion style from scratch.

| Kit | Industries | Palette | Fonts | Texture | Motion |
|---|---|---|---|---|---|
| **Institutional Tech** | Web3, AI, SaaS, Fintech | Void black, holographic silver, neon cyan/violet | Clash Display / JetBrains Mono | Isometric grid (0.03) | Sharp geometric, snap-to-section |
| **Editorial Luxury** | Fashion, Real Estate, Jewelry | High-contrast B&W, gold or dusty rose | Cormorant / Playfair / Satoshi | Film grain (0.04) | Slow cinematic parallax, long easing |
| **Organic Trust** | Healthcare, Wellness, Sustainability | Soft off-whites, forest green or clinical blue | Inter / Satoshi / DM Sans | Organic blob SVG, soft gradient | Liquid/smooth, no hard snaps |
| **Brutalist Craft** | Architecture, Agencies, Coffee | Concrete gray, stark black, one bold accent | Space Mono / Bebas Neue / Inter | Blueprint grid or raw concrete | Hard snap-scroll, zero easing |
| **Kinetic Energy** | Fitness, Automotive, Gaming, Events | Near-black, volt green or racing red | Impact / Barlow Condensed / Rajdhani | Diagonal slashes, speed-blur lines | Aggressive fast transitions |

Define exactly:
- 5 hex codes with semantic roles
- 3 font tiers (Display, Body, Mono)
- 1 global texture + opacity
- 4 motion rules (from Structural DNA below, tuned to this kit's personality)

---

## Step 3: Apply the Structural DNA (Never Changes)

Every blueprint must include **all** of these:

### Mandatory Interactions
1. **Lenis Smooth Scroll** — `@studio-freight/lenis`; disable on touch devices: `if (!('ontouchstart' in window)) { lenis.start() }`; fallback to native OS scroll
2. **Masked Text Reveals** — clip-path or overflow:hidden slide-up; never simple opacity fade
3. **Sticky Scrollytelling** — ≥1 page: left sticky text, right scrolling animated diagram/mockup
4. **LayoutGroup Morphing Grid** — ≥1 page: filterable grid with Framer Motion `<LayoutGroup>` smooth reorder
5. **Interactive Calculator/Slider** — ≥1 page: slider dynamically updates large numbers (ROI, APY, savings)
6. **Magnetic or Holographic Hover** — magnetic button cursor pull OR rotating conic-gradient card border
7. **CustomCursor** — fixed 16px circle, Framer Motion spring follow, `mix-blend-mode: difference` (visible on both light/dark); scales 3× on hover over links/buttons with text label inside ("VIEW", "DRAG", "CLICK"); disabled on touch devices

### Mobile Performance Rules (mandatory in every master prompt)
- Disable Lenis on touch devices — native scroll only
- Disable heavy `useScroll` parallax on mobile — fallback to simple `opacity` fade at 60fps
- All sliders and morphing grids must have touch/swipe support
- No animation should drop below 60fps on a mid-range mobile

### Mandatory Global Components
| Component | Implementation note |
|---|---|
| `SmoothScrollWrapper` | Lenis init with touch detection guard |
| `TextReveal` | Takes string, splits to words, animates each with clip-path mask |
| `MagneticButton` or `HolographicCard` | Pick based on kit; magnetic uses `useMotionValue` + spring transform |
| `AnimatedCounter` | `useInView` triggers count-up with easing |
| `CustomCursor` | Spring-follow circle, mix-blend-mode: difference, scale+label on hover |

---

## Step 4: Autonomous Motion Choreography

Do not say "add an animation." Write the **exact Framer Motion variant code** for core animations in the master prompt. Minimum required reps:

```ts
// Text reveal mask
const maskVariants = {
  hidden: { clipPath: 'inset(100% 0 0 0)' },
  visible: { clipPath: 'inset(0% 0 0 0)', transition: { duration: 0.8, ease: [0.22, 1, 0.36, 1] } }
}

// Staggered container
const containerVariants = {
  hidden: {},
  visible: { transition: { staggerChildren: 0.08, delayChildren: 0.1 } }
}

// Magnetic button (useMotionValue x,y + spring)
const springConfig = { stiffness: 150, damping: 15, mass: 0.1 }

// Scroll-linked opacity (mobile fallback)
// Desktop: useTransform(scrollYProgress, [0, 0.5], [0, 1])
// Mobile: simple whileInView={{ opacity: 1 }} initial={{ opacity: 0 }}
```

Add kit-specific variants on top (e.g., Editorial Luxury gets longer duration + high ease-out; Kinetic Energy gets duration 0.3 + spring overshoot).

---

## Step 5: Generate the Blueprint

Output ALL sections. Do not skip any.

### 5.1 Executive Creative Direction
- Primary direction (1 phrase)
- Visual language (1 sentence)
- Experience goal (3–4 adjectives)
- 3 design principles

### 5.2 Site Map (5–6 pages)
Table: Route · Page Name · Purpose · **Signature Interactive Hook** (no two pages share the same hook)

Cover these archetypes:
| Archetype | Hook |
|---|---|
| Home | Cinematic hero + marquee + manifesto |
| Product/Tech | Sticky scrollytelling + animated diagrams |
| Use Cases/Ecosystem | LayoutGroup filterable morphing grid |
| Human/Company | Cursor-tracking or full-bleed manifesto |
| Data/Pricing | Slider/calculator + accordion tiers |
| Developer/Contact | Split-screen IDE typewriter or animated form |

### 5.3 Design System
- 5 hex codes + semantic role each
- 3 font tiers (specific names)
- Texture (name + opacity + CSS note)
- 4 motion rules tuned to this kit

### 5.4 Page-by-Page Deep Dive
For each page:
- Layout paradigm
- Content sections in order
- The hook (exact interactive description)
- Copy direction: 1–2 real, brand-specific headlines

### Copywriting Protocol (enforced on all copy)
- **NEVER use:** elevate, seamless, unlock, unleash, synergy, next-generation, cutting-edge, revolutionize, empower
- **Write like:** Apple, Linear, Aesop — short, punchy, declarative
- **Focus on:** mechanism + outcome, not hype
- ✅ "Edit the same file. Zero latency. Zero conflicts."
- ❌ "Unlock seamless next-generation collaboration."

### 5.5 Tech Stack + Project Structure

Base stack (always):
```
Next.js 14 (App Router) · TypeScript · Tailwind CSS
Framer Motion · Lenis (@studio-freight/lenis) · Lucide React
React Hook Form + Zod
```

Per industry additions:
- `Recharts` / `Visx` → data-heavy (fintech, Web3)
- `Three.js` / `@react-three/fiber` → 3D/immersive (gaming, automotive)
- `canvas-confetti` → form success states
- `Mapbox GL` → location/contact maps

**Mandatory project structure (include exact file tree in master prompt):**
```
app/
  layout.tsx          # SmoothScrollWrapper + CustomCursor + NoiseOverlay
  page.tsx            # Home
  [route]/page.tsx    # One per page
components/
  ui/
    SmoothScrollWrapper.tsx
    TextReveal.tsx
    MagneticButton.tsx OR HolographicCard.tsx
    AnimatedCounter.tsx
    CustomCursor.tsx
    NoiseOverlay.tsx
  sections/
    [PageName]/       # Section components per page
lib/
  motion.ts           # All shared Framer Motion variants
  fonts.ts            # Font config
public/
  fonts/              # Self-hosted display font if needed
```

---

## Step 6: Write the Master Implementation Prompt

Output as a single fenced code block. Must contain in order:

1. **Role + anti-template opening**
2. `CRITICAL RULE 1: STRUCTURAL DNA` — all 7 mandatory interactions + mobile rules
3. `CRITICAL RULE 2: VISUAL SKIN` — full design system (hex codes, fonts, texture, motion rules)
4. `PROJECT STRUCTURE` — exact file tree
5. `MOTION CHOREOGRAPHY` — actual TypeScript/Framer Motion variant code (minimum 4 reps)
6. `MULTI-PAGE ARCHITECTURE` — imperative instructions per route with hooks
7. `GLOBAL COMPONENTS` — all 5, with brief implementation note
8. `IMPLEMENTATION RULES`:
   - `app/` directory, `page.tsx` per route
   - No lorem ipsum — bold, declarative, brand-specific copy
   - No external image URLs — CSS/SVG code-first art only
   - Respect `prefers-reduced-motion`
   - Disable Lenis + heavy parallax on touch devices
   - All reusable logic in `components/ui/` and `lib/motion.ts`
   - Apply Copywriting Protocol (banned words list)
   - Start: folder structure → global CSS → SmoothScrollWrapper → pages one by one

**Hard limit: master prompt ≤ 40,960 characters. Dense, no filler, every word actionable.**

---

## Step 7: Quality Checklist

Before outputting, verify:

- [ ] Design kit is industry-specific (or newly invented for the niche)
- [ ] No two pages share the same interactive hook
- [ ] Lenis touch-device disable included
- [ ] Mobile parallax fallback specified
- [ ] CustomCursor component included with mix-blend-mode: difference
- [ ] Sticky scrollytelling on ≥1 page
- [ ] LayoutGroup grid on ≥1 page
- [ ] Interactive slider/calculator on ≥1 page
- [ ] All 5 global components named and described
- [ ] Master prompt has CRITICAL RULE 1 + CRITICAL RULE 2 headers
- [ ] Master prompt includes actual Framer Motion variant code (≥4 reps)
- [ ] Master prompt includes exact project folder tree
- [ ] Copywriting protocol enforced (banned words absent from all copy)
- [ ] Master prompt ≤ 40,960 characters
