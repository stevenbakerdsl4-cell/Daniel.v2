# Handoff: Daniel Schwager — Homepage

## Overview

A single-page marketing homepage for **Daniel Schwager**, an established Manual Therapist and Acupuncturist practising in Marylebone / Harley Street, Central London. The homepage's job is to position Daniel as a highly experienced London practitioner (not a massage therapist, not a wellness template) and drive prospective patients to book an appointment or get in touch.

Key positioning to reinforce throughout implementation:

- **Manual Therapist & Acupuncturist**, not a massage therapist
- **30+ years of experience** (Manual Therapy since 1994, Acupuncture since 2007)
- Integrated, hands-on, whole-body approach — combining manual soft tissue therapy, acupuncture and dry needling
- Background and knowledge in **anatomy, movement, sport, yoga and Pilates**
- Highly individual, person-centred, **not a standard treatment protocol**
- **His hands are one of his greatest assets — sensitive, experienced and precise** (this is the design's conceptual through-line)
- Located on Wimpole Street, Marylebone — **Harley Street area** SEO is important
- Target audience: back pain, neck/shoulder pain, muscular tension, sports injuries, persistent pain and movement problems
- **Testimonials are distributed throughout** — not confined to a testimonials page

## About the Design Files

The files in this bundle are **design references, created in HTML** — they represent the intended look, layout, behaviour and copy of the homepage. They are **not production code to ship as-is**.

The task is to **recreate this design in the target codebase's existing environment** (React / Next.js / Vue / Astro / SvelteKit / plain HTML+CSS+JS, whichever the developer/agency has established) using its established patterns, component library, routing and CMS. If no environment exists yet, the recommended stack is **Next.js (App Router) + Tailwind CSS + a headless CMS (Sanity or Contentful) for testimonials, conditions and copy blocks**, deployed on Vercel — this suits the SEO/local search priority.

All copy, colours, spacing, typography and interaction states shown in the HTML are final for the initial launch and should be reproduced faithfully.

## Fidelity

**High-fidelity (hifi).** The prototype is a pixel-considered mockup with final colours, typography, spacing, motion and copywriting. The developer should reproduce the UI faithfully. Where the target codebase has an existing typography or spacing scale, prefer that scale — but the visual result must match the mockup.

## Screens / Views

This is a single-page design. Below is a section-by-section breakdown. All sections live in `Daniel Schwager Homepage v2.html`.

### 1. Global — Navigation (fixed)

- **Purpose:** persistent access to sections; always-visible booking CTA; live availability signal.
- **Layout:** fixed top, 3-column grid (`brand` / `nav-links` (centered) / `nav-cta` (right)). Padding `22px var(--pad-x)`; on scroll past 32px adds `.compact` (padding drops to `14px`, background solidifies, hairline bottom border appears). Backdrop blur `saturate(140%) blur(10px)` and `background: color-mix(in oklab, var(--paper) 82%, transparent)`.
- **Brand:** "Daniel Schwager" set in **Fraunces** at 21px / weight 400 / optical size 30, followed by a 1px vertical divider (`--rule`) and an italic serif tag "est. MCMXCIV" in oxblood.
- **Nav links:** Practice, Approach, Conditions, Treatments, Daniel, Visit. 14px Instrument Sans. Hover produces a hairline underline that scales in from the left over 350ms.
- **Availability pill:** rounded pill, hairline border, green pulse dot (`#4a8a5f`) with a keyframe pulse animation. Text: "Consulting Tues & Thurs".
- **CTA button:** "Book" in a black pill button with arrow — inverts on hover (transparent bg, black text, black border).

### 2. Progress ribbon (fixed, bottom-right)

- Tiny `Spread NN / 09` counter + 44px hairline track with an oxblood fill that grows with scroll progress. Uses `mix-blend-mode: multiply` on light sections; on the two dark sections (`data-dark="1"`) it switches to `on-dark` styling. Hidden below 640px.

### 3. Hero — full viewport typographic statement

- **Purpose:** immediately communicate who Daniel is, what he does, who he helps, how experienced he is, and how to book.
- **Layout:** min-height `100vh`, padded `132px` top / `88px` bottom. Contents: side rail (top), typographic block (center), lower row with copy + CTA (bottom, above a hairline rule).
- **Eyebrow:** `Manual Therapist & Acupuncturist · Marylebone · Since 1994` — Instrument Sans 11.5px, letter-spacing `.22em`, uppercase, preceded by a 28px hairline.
- **Headline (three lines):** 
  1. "Thirty-two years"
  2. "of *listening*" — italic *listening* in oxblood, with a **portrait embedded as an inline block** between "of" and "listening" (see below).
  3. "through the fingertips."
  - Type: Fraunces, weight 300, `font-size: clamp(56px, 9.2vw, 148px)`, line-height 0.92, letter-spacing `-0.035em`, variation `"opsz" 144, "SOFT" 40`.
  - Italic word variation: `"opsz" 144, "SOFT" 100, "WONK" 1`.
- **Inline portrait:** a `clamp(120px, 12vw, 200px)` square (border-radius 2px) sitting on the baseline, translated up 20%, containing `assets/portrait-hero.jpg` centered at `center 22%/cover` with `filter: saturate(0.85) contrast(1.02)`. On hover: image scales to 1.06. On mousemove within the hero, applies a subtle `translate(x * -6px, y * -6px)` parallax.
- **Word-by-word reveal:** on hero load, each word rises from `translateY(105%)` to `0` with 60ms staggered delays over 1s.
- **Lower row (grid `1fr auto 1fr`):**
  - **Left:** paragraph — "An established Central London practitioner — **not a massage therapist**. Daniel combines manual soft tissue therapy, acupuncture and dry needling in an individual, whole-body approach — for people dealing with back, neck and shoulder pain, muscular tension, sports injuries, persistent pain and movement problems." (The "not a massage therapist" clause is `font-weight: 500` in `--ink`.)
  - **Middle:** primary oxblood button "Book an Appointment →" and underline link "Read the approach".
  - **Right:** figure caption — italic "Fig. 01 —" in oxblood + one line "Portrait of the practitioner at 25 Wimpole Street."
- **Side rail (top):** `W1G · Marylebone · Wimpole St.` (left) / `Vol. II · MMXXVI` (right).

### 4. Focus band

- Directly below the hero. Reinforces "who Daniel helps" as a fast-read line.
- Padding `32px 0`, hairline top border.
- Layout: horizontal flex, wrap allowed.
- Kicker: `DANIEL WORKS WITH` in `--ink-mute`, hairline right border acting as a separator.
- Items (Fraunces, 15–17px): **Back pain · Neck & shoulder pain · Muscular tension · Sports injuries · Persistent pain · Movement problems**. Middot separators between items are `content: "·"` pseudo-elements.

### 5. Ticker (marquee)

- Full-width horizontal marquee, 60s linear infinite scroll (`translateX(0) → translateX(-50%)`), duplicate track for seamless loop.
- Content: `Manual Therapy · Since 1994 · Acupuncture · Since 2007 · Marylebone · Wimpole St. · CNHC Registered · Persistent Pain · Musculoskeletal Health · Sports Injuries · Post-Surgical Recovery · Movement & Function` — with 4px oxblood dot separators.
- 12px Instrument Sans, letter-spacing `.28em`, uppercase, colour `--ink-mute`.

### 6. Practice Index (Section § 01)

- **Purpose:** communicate 30+ years of accumulated expertise as a career index, not a stats block.
- **Head:** `§ 01` italic marker + h2 "A practice built quietly, one *decade* at a time." + right-aligned kicker paragraph. Hairline bottom border.
- **List** (grid: 100px `1fr` `1fr` auto):
  - Six rows, each with year / title / description / tag (years-count).
  - Rows are separated by hairline bottom borders on each cell.
  - Years: Fraunces 22px, dark ink.
  - Titles: Fraunces `clamp(22px, 1.9vw, 28px)`, weight 350.
  - Descriptions: Instrument Sans 14.5px, `--ink-2`, max-width 42ch.
  - Tags: Instrument Sans 11px, letter-spacing `.16em`, uppercase, `--ink-mute`, right-aligned.
- **Content:** 
  - `1994 · Manual & Soft Tissue Therapy · 32 Years`
  - `2001 · Movement & Rehabilitation · 25 Years`
  - `2007 · Acupuncture · 19 Years`
  - `2011 · Dry Needling & Trigger Point · 15 Years`
  - `2014 · Harley Street Physiotherapy · 12 Years`
  - `Today · CNHC Registered Practitioner · Ongoing`
- **Foot** (grid `1fr 1fr`, gap 80px):
  - Left: "Roughly *thirty-two thousand* hours of hands-on clinical work — and counting." (Fraunces, clamp 28–40px).
  - Right: paragraph naming *anatomy, movement, sport, yoga and Pilates* as the wider knowledge base.

### 7. Philosophy (Section § 02)

- **Layout:** three columns (`1fr 1.4fr 1fr`) with 64px gap.
- **Left:** hands-detail image (aspect 4/5, `assets/hands-detail.jpg`), covered, `contrast: 1.05, brightness: 1.02`. Filled with a `clip-reveal` (a `--paper`-coloured overlay wipes from right to left over 1.2s while the underlying image scales from 1.12 to 1).
- **Center:** lede paragraph + two body paragraphs. Copy in file.
- **Right:** sticky "Working Principles" note (position: sticky, top: 120px), listing three principles:
  1. *The technique matters less than the reasoning behind it.*
  2. *The body compensates long before it complains.*
  3. *Treatment is a conversation, refined session by session.*
  - Header: Instrument Sans 11px `.22em` uppercase.
  - Roman numeral: Fraunces italic 13px, oxblood.
  - Principle text: Fraunces 18px, weight 350, `--ink`.
- Background: `--paper-2` (`#ece5d6`).

### 8. Featured testimonial (Section § between)

- **Layout:** `auto 1fr auto` grid, 60px gap.
- **Left:** giant oxblood italic Fraunces quote-mark, `clamp(80px, 10vw, 160px)`, variation `"opsz" 144, "SOFT" 100, "WONK" 1`.
- **Center:** blockquote — `clamp(28px, 3.6vw, 54px)`, line-height 1.1, weight 350. Content: "After eighteen months and five practitioners, Daniel was the first to actually *explain* what was happening — and why. The treatment worked because the thinking behind it was different." (with the word "explain" italicised in oxblood).
- **Right:** attribution — italic name "M.H." + meta "Patient — 2 years / Chronic lower back".

### 9. Hand anchor (Section § — dark)

- **Purpose:** the conceptual centerpiece — reinforces the "his hands are one of his greatest assets" positioning as a memorable visual moment.
- Full-bleed, min-height 82vh, background `#0a0908`.
- Background: `assets/hands-detail.jpg` cover-centered, `filter: contrast(1.05) brightness(0.75)`, initial `scale(1.08)` transitioning to `scale(1)` over 1.4s on intersection.
- Gradient overlay: `linear-gradient(180deg, rgba(0,0,0,.15) 0%, rgba(0,0,0,.55) 100%)`.
- **Content** (centered, max-width 1100px, 120px vertical padding):
  - Eyebrow "On the practice of touch" (light on dark)
  - Statement: "A treatment begins the moment the hands make contact. Everything before that is *preparation*." — Fraunces, clamp(36, 5.4vw, 82px), weight 300, variation `"opsz" 144, "SOFT" 40`; italic *preparation* in `--oxblood-2` (`#d47a68`).
  - Footnote: "Fig. 02 — Detail" — 12.5px `.16em` uppercase.

### 10. Conditions (Section § 03)

- **Purpose:** the "who Daniel helps" section, with distributed testimonials.
- **Head:** `§ 03` + h2 "The problems worth taking *seriously.*" + right-aligned instruction "Hover a condition to read a note from someone Daniel has treated for it."
- **List** — six rows (grid: 60px 1.2fr 1.6fr 1fr auto, 40px gap, 28px vertical padding, hairline borders):
  1. **Persistent & Chronic Pain** — Manual Therapy · Acupuncture · Dry Needling
  2. **Neck, Shoulder & Back Pain** — Manual Therapy · Dry Needling
  3. **Sports Injuries & Overuse** — Manual Therapy · Dry Needling · Movement
  4. **Muscular Imbalances & Postural Pain** — Manual Therapy · Movement
  5. **Post-Surgical Recovery** — Manual Therapy · Acupuncture · Movement
  6. **Stress-Related & Somatic Tension** — Acupuncture · Manual Therapy
  - Each row: italic oxblood number (01–06), Fraunces title clamp(26,2.2vw,34px), a set of pill-shaped tags (`cond-tag` — 10.5px `.12em` uppercase, hairline border, rounded-full), a plain-text description column, and a small circular arrow icon.
  - **Row hover:** background fills to `paper-2/60%`, padding increases by 20px horizontally over 400ms, arrow rotates -45deg to become an outbound arrow with black fill; a hidden testimonial (`cond-testimonial`) expands from max-height 0 to 180px, opacity 0→1, showing a short italic quote + attribution.
  - Testimonial content per row is in the HTML — real-sounding, first-person, patient-tenure oriented.

### 11. Treatments (Section § 04 — dark)

- **Purpose:** communicate the three disciplines as a considered practice.
- Full-bleed dark section (`--ink` background, `--paper` text). Same visual language as the hand anchor but content-focused.
- **Head:** `§ 04` + "Treatments" eyebrow (light on dark).
- **Intro (grid 1fr 1fr):** h2 "Three disciplines, one *considered* practice." + body paragraph about tools chosen to suit the person.
- **Three-column magazine essay layout** (`repeat(3, 1fr)`, 56px gap):
  - **i. Manual Therapy** — foundation of the practice; three decades; deep tissue and myofascial work, remedial soft tissue, joint mobilisation, postural assessment.
  - **ii. Acupuncture** — Western medical tradition; used as part of a broader approach.
  - **iii. Dry Needling** — precise Western-medical tool for trigger points/referred pain.
  - Each column has an italic roman numeral kicker in `--oxblood-2`, an h3 title, and 2 body paragraphs.
- **"How a session unfolds"** — a 4-step sequence in a 4-column grid: i. Conversation, ii. Assessment, iii. Treatment, iv. Follow-through. Each step has the italic roman kicker, a Fraunces 22px title, and a one-sentence description.

### 12. About Daniel (Section § — light)

- **Layout:** `1fr 1.2fr` two-column grid, 48–96px gap, aligned center.
- **Left:** portrait image `assets/portrait-about.jpg`, aspect 4/5, `filter: saturate(.85) contrast(1.02)`; a "Fig. 03 — At the practice" italic stamp in the bottom-left with blurred-glass background (`background: rgba(26,23,20,.35); backdrop-filter: blur(6px)`).
- **Right:**
  - Eyebrow "About Daniel"
  - h2 "Experience matters. *So does* listening." (italic clause in oxblood)
  - Two body paragraphs of biography, one naming the *anatomy, movement, sport, yoga and Pilates* knowledge base explicitly, one reinforcing that his hands are his most valuable instrument — *sensitive, experienced and precise*.
  - **Credentials block** (2-column grid, 32px gap, hairline top border):
    - Left: "Training & Registration" — CNHC registered, Manual & Soft Tissue Therapy, Western Medical Acupuncture, ongoing CPD.
    - Right: "Practice" — Harley Street Physiotherapy, 25 Wimpole Street, W1G, Consulting Tuesday & Thursday.
  - **Signature line:** Fraunces italic "Daniel Schwager" (34px, variation `"opsz" 60, "SOFT" 100, "WONK" 1`) + role kicker.

### 13. Testimonials strip (Section § 05)

- **Purpose:** proof volume + caliber of clientele.
- **Head:** `§ 05` + h2 "The reputation is *quietly* built." + right-aligned kicker.
- **Slider:** four testimonials, one visible at a time; autorotate every 9s; hover pauses autorotate.
- **Slide layout** (`1fr 1fr` grid, 96px gap):
  - Left: Fraunces quote, `clamp(26, 2.6vw, 38px)`, weight 350. Sample content ("I've seen Daniel on and off for over a decade..." / "Twelve years of chronic pain..." / "His hands find things I didn't know were there..." / "What sets Daniel apart is that he treats the *person*, not the complaint...").
  - Right: attribution (italic name + role + tenure) + a separate "Daniel is trusted by / Referred by / Working with / Longevity" list that varies per slide — this communicates high-profile clientele (consultants, barristers, dancers, cyclists, musicians) without naming names.
- **Nav row:** italic oxblood "01" (current) + arrow buttons (44px circles, hairline black border, invert on hover) + right-aligned "of 04" total.

### 14. Location (Section § — full-bleed hero + details)

- **Location hero:** 78vh min-height, `assets/marylebone-dusk.jpg` cover, `scale(1.06)` → `scale(1)` on intersection, dark gradient overlay bottom-heavy.
- **Overlay content (bottom-left):** eyebrow "The Practice" + h2 "A quiet street in the *middle* of things." (light on dark).
- **Details block** (`1.2fr 1fr 1fr 1.2fr` grid, 64px gap, 120px vertical padding, `--paper` background):
  - **Address:** clinic label + address block + "Find the practice →" link.
  - **Consulting:** hairline-separated rows (Tuesday, Thursday, Reception, Text Daniel).
  - **Fees:** hairline-separated rows — Fraunces values (30 min £80, 1 hour £140, 90 min £200) + a note "Initial consultation includes a full assessment."
  - **On Arrival:** numbered list (i–iv) of arrival instructions, hairline dividers between rows. i. Enter via main door · ii. Lift to 3rd floor · iii. Reception expecting you · iv. Bond Street & Oxford Circus — five minutes.

### 15. Final CTA

- **Layout:** `1fr auto` two-column grid.
- **Left:** eyebrow "Take the first step" + huge h2 "Meet *Daniel.*" (clamp 64–168px, italic *Daniel* in oxblood) + body copy about the first appointment being a conversation.
- **Right:** two stacked buttons — primary oxblood "Book an Appointment →" (linking to the real Cliniko URL) and ghost "Call the practice →" (`tel:+442072244588`), plus a small italic footnote "Or text Daniel directly on 07932 671 463".

### 16. Footer (dark)

- 4-column grid on the top row: Brand (with name + role + CNHC registration blurb) / Practice links / Visit (address, phone, book) / Consulting (hours + text-Daniel link).
- Bottom row: copyright, italic "Wimpole Street · Marylebone · London W1G" mark, Privacy · Terms.
- Background `--ink`, foreground `--paper`, hairline dividers in `color-mix(in oklab, var(--paper) 15%, transparent)`.

## Interactions & Behavior

- **Nav compaction:** on `scroll > 32px`, add `.compact` class → padding shrinks, background solidifies, hairline bottom appears. 350ms `cubic-bezier(.2,.6,.2,1)`.
- **Progress ribbon:** track fill width = `window.scrollY / (scrollHeight - clientHeight)`. Determines "current spread" by iterating `[data-spread]` elements, comparing their `offsetTop` to `scrollY + innerHeight * 0.4`. When the current spread has `data-dark="1"`, the ribbon switches to `on-dark` styling and drops `mix-blend-mode: multiply`.
- **Word-by-word hero reveal:** each headline line is walked; text nodes are split into words wrapped in `.word-wrap > .word` spans; each word's `transitionDelay` is staggered (`0.06 + i * 0.04`s). Reveal triggers ~120ms after DOM ready.
- **Reveal-on-scroll:** IntersectionObserver (threshold 0.12, `rootMargin: '0px 0px -8% 0px'`) adds `.in` class → `opacity: 0 → 1` and `translateY(24px → 0)` over 900ms. Delay classes `.d1`, `.d2`, `.d3`, `.d4`, `.d5` add 80/160/240/320/400ms.
- **Clip-reveal (images):** on `.in`, an overlay `::after` filled with `--paper` scaleXs from 1 to 0 (origin right) over 1.2s while the underlying image scales from 1.12 to 1 over 1.6s.
- **Hero portrait parallax:** on mousemove within `.hero` on hover-capable devices, sets `transform: translate(x * -6px, y * -6px) scale(1.06)` on the inline portrait's `.img`. Resets on mouseleave.
- **Conditions rows:** hover → `padding-left/right: 20px` (400ms), background fills to `paper-2/60%`, arrow rotates -45deg and inverts, hidden testimonial expands (`max-height 0 → 180px`, `opacity 0 → 1`).
- **Testimonials slider:** manual arrows + autorotate every 9000ms. `mouseenter` on `.test-strip` calls `clearInterval` to pause autorotate. `setSlide(n)` uses modulo for wraparound.
- **Ticker:** CSS-only, `translateX(0 → -50%)` over 60s linear infinite. Duplicate content in the track for a seamless loop.
- **Location hero image:** IntersectionObserver (threshold 0.25) adds `.in`, which scales the image from 1.06 → 1 over 1.4s.
- **Smooth scroll:** all `a[href^="#"]` intercept click, compute `target.getBoundingClientRect().top + scrollY - 72` (nav offset), `window.scrollTo({top, behavior: 'smooth'})`.
- **Availability pulse:** the green dot in the nav pill runs a 2.4s `pulse` keyframe scaling the box-shadow ring from `0 0 0 0 rgba(74,138,95,.55)` to `0 0 0 8px rgba(74,138,95,0)`.

## State Management

Trivial. The prototype is stateless apart from:

- Testimonials slider index (`let idx = 0`, wrapping via modulo).
- Autorotate interval, cleared on `mouseenter`.
- Scroll-driven derivations (nav compact flag, progress fill, current spread) — all computed inside a single `onScroll` handler.

In a React/Next port, express these as:
- `useState` for the testimonials index.
- `useEffect` for the autorotate `setInterval`.
- A `useScroll`-style hook (or manual `scroll` listener + `useRef`) for nav/progress state.
- Prefer IntersectionObserver for reveals over scroll-position math (already used in the prototype).

## SEO / Local Search

Local SEO is a priority. The homepage already includes:

- `<title>`: "Daniel Schwager — Manual Therapist & Acupuncturist · Marylebone, Harley Street, London"
- `<meta name="description">` targeting Marylebone / Harley Street / manual therapy / acupuncture / persistent pain
- `<meta name="keywords">` covering primary local queries
- Open Graph tags (`og:title`, `og:description`, `og:type`, `og:locale=en_GB`)
- `<link rel="canonical">`
- **JSON-LD structured data**: `MedicalBusiness` + `LocalBusiness` schema with full address, phone, opening hours, geo coordinates (51.5199, -0.1467), `areaServed` (Marylebone, Harley Street, Central London, West End, Mayfair) and `medicalSpecialty`.

At build time, developers should:

- Ensure the same JSON-LD ships in the compiled `<head>` (Next.js: add via `metadata` or a `<Script type="application/ld+json">` inside a Layout `<head>`).
- Register with Google Business Profile at 25 Wimpole Street; wire the profile URL to `sameAs`.
- Create a `sitemap.xml` and `robots.txt` at build.
- Add per-page metadata for any future service or condition landing pages (e.g. "Back Pain Treatment Marylebone", "Acupuncture Harley Street").
- Configure server headers for `Cache-Control` and ensure image responses include `Content-Type: image/jpeg` with reasonable `Cache-Control: public, max-age=31536000, immutable` for the hashed asset filenames.

## Design Tokens

### Colours

```
--paper:      #f2ede3   /* warm off-white — page background */
--paper-2:    #ece5d6   /* panels / philosophy / testimonials strip */
--paper-3:    #e4dbc8   /* deeper cream (rare use) */
--ink:        #1a1714   /* primary foreground / dark sections */
--ink-2:      #2c2622   /* body text */
--ink-mute:   #6e655a   /* secondary / metadata / eyebrows */
--rule:       #cfc4ae   /* hairline dividers */
--rule-soft:  #ded1b6   /* softer hairlines */
--oxblood:    #6b2a1e   /* accent — used sparingly */
--oxblood-2:  #d47a68   /* oxblood tint used on dark backgrounds */
```

Availability pulse: `#4a8a5f` with `rgba(74,138,95,.55) → 0` box-shadow ring.

### Typography

- **Serif (display):** Fraunces (Google Fonts, variable). Axes used: `opsz` (9–144), `wght` (300–800), `SOFT` (30–100), `WONK` (0–1). Default weight 350.
- **Sans (UI/body):** Instrument Sans (Google Fonts, variable). Weights 400–700.
- **Fallback serif stack:** `"Instrument Serif", ui-serif, Georgia, serif`.
- **Fallback sans stack:** `ui-sans-serif, system-ui, -apple-system, "Helvetica Neue", Arial, sans-serif`.
- Font-feature-settings on body: `"ss01", "ss02", "kern"`.

### Type scale

```
display:  clamp(56px,  9.2vw, 148px)  / lh 0.92  / tracking -0.035em / opsz 144
h-xl:     clamp(40px,  5.4vw,  82px)  / lh 1.0   / tracking -0.022em
h-lg:     clamp(30px,  3.4vw,  48px)  / lh 1.08  / tracking -0.018em
h-md:     clamp(22px,  2vw,    28px)  / lh 1.2
lede:     clamp(17px,  1.25vw, 21px)  / lh 1.5
body:     16px                        / lh 1.65
meta:     12px  / .16em uppercase / --ink-mute
eyebrow:  11.5px / .22em uppercase / --ink-mute / with 28px hairline prefix
```

Italic display words use variation `"opsz" 144, "SOFT" 100, "WONK" 1` — noticeably softer/wonkier than roman glyphs. This is deliberate; it's the design's most distinctive typographic move.

### Spacing

Layout gutter: `--pad-x: clamp(24px, 6vw, 96px)`.
Max content width: `--max: 1440px`.
Section vertical padding: `140–160px` desktop, `88px` mobile (≤640px).
Grid gaps at desktop: `48–96px`.

### Easing

```
--ease:      cubic-bezier(.2, .6, .2, 1)      /* general */
--ease-out:  cubic-bezier(.16, 1, .3, 1)      /* reveals */
```

Standard durations: 250ms (hover states), 350ms (nav/button), 900ms (reveal), 1200ms (clip-reveal wipe), 1400–1600ms (image scale reveal), 2400ms (pulse), 60s (ticker).

### Radii

- Buttons and pills: `999px` (fully rounded).
- Images / cards: 2px (subtle softening only).
- Hairline dividers: 1px `var(--rule)`.

### Shadows

Deliberately not used. This is a flat, paper-and-ink design. The only shadow-like effects are:
- Pulse ring: `box-shadow: 0 0 0 [0-8]px rgba(74,138,95,[0-.55])` — animated only.
- Grain overlay: fixed SVG turbulence noise at 0.05 opacity with `mix-blend-mode: multiply`.

### Grain overlay

```html
<!-- body::before -->
opacity: 0.05
mix-blend-mode: multiply
background-image: SVG feTurbulence baseFrequency=0.9 numOctaves=2
```

This is what gives the design its "printed" feel — do not skip it.

## Assets

All images live in the `assets/` folder of the source project:

| File | Usage | Notes |
|---|---|---|
| `assets/portrait-hero.jpg` | Hero — inline portrait between headline lines | ~1568px, `filter: saturate(0.85) contrast(1.02)` at usage |
| `assets/portrait-about.jpg` | About section — 4:5 portrait | ~1568px, `filter: saturate(0.85) contrast(1.02)` |
| `assets/marylebone-dusk.jpg` | Location hero — full-bleed dusk architecture | ~1280×1920, dark gradient overlay on top |
| `assets/marylebone-day.jpg` | Not used in v2 but available | Backup daytime shot |
| `assets/hands-detail.jpg` | Philosophy image (4:5) AND full-bleed Hand Anchor background | Same file, two treatments. `contrast: 1.05, brightness: 1.02` in philosophy; `contrast: 1.05, brightness: 0.75` under dark overlay in Hand Anchor |

**Production note:** these are licensed stock placeholders used purely for the mockup. For launch, commission a dedicated **editorial photography session** with Daniel — portrait, hands-in-treatment detail, and treatment-room / Marylebone environment. The design will not achieve its intended feeling with mismatched or lower-quality photography. Aim for natural-light, film-toned, considered images similar in mood to the placeholders.

Font files are served from Google Fonts via CDN in the prototype. In production, self-host both **Fraunces** and **Instrument Sans** (variable formats, `woff2`) for performance and privacy.

## Content / Copy

Copy is final and should be reproduced exactly. Key strings the developer must preserve:

- Hero eyebrow: `Manual Therapist & Acupuncturist · Marylebone · Since 1994`
- Hero headline: `Thirty-two years / of listening / through the fingertips.`
- Hero lead paragraph — must retain the bolded phrase *"not a massage therapist"*.
- Focus band items — six conditions listed in this exact order: Back pain, Neck & shoulder pain, Muscular tension, Sports injuries, Persistent pain, Movement problems.
- Working Principles — three lines, wording verbatim.
- Hand Anchor statement: `A treatment begins the moment the hands make contact. Everything before that is preparation.`
- Practice Index years and titles — verbatim.
- CNHC registration language — verbatim in About and Footer.
- Fees — verbatim (£80 / £140 / £200 for 30 min / 1 hour / 90 min).
- Address: `Harley Street Physiotherapy, 3rd Floor, 25 Wimpole Street, Marylebone, London W1G 8GL`.
- Booking URL: `https://harley-street-physiotherapy.cliniko.com/bookings?business_id=74152&practitioner_id=1457296841786787559#service`.
- Reception phone: `+44 20 7224 4588` → `tel:+442072244588`.
- Direct text number: `+44 7932 671 463` → `tel:+447932671463`.

**Testimonials in the prototype are placeholder text in Daniel's voice/tone but not literal quotes.** Before launch, replace with actual patient testimonials — Daniel has a substantial collection. Keep the pattern of `Initial. + role/profession + years-of-tenure` metadata, and vary the "trusted by / referred by" side blocks. Do NOT invent named quotes.

## Files

Files included in this handoff (see this folder):

- `README.md` — this document
- `Daniel Schwager Homepage v2.html` — the primary prototype (the v2 direction)
- `Daniel Schwager Homepage.html` — v1 for reference; illustrates the earlier direction before the strategic revision
- `assets/` — image bundle used by both HTML files

Notes for the developer:

- Both HTML files inline all CSS in a `<style>` block in `<head>`, and all JS in one `<script>` at the end of `<body>`. In production, split into components/CSS modules per the target framework's conventions.
- No third-party JS libraries are used — every animation is native (IntersectionObserver, CSS transitions, `requestAnimationFrame`). Preserve this.
- The design is desktop-first (1440px target) with a `1080px` mid-breakpoint and a `640px` mobile breakpoint. Test carefully on 1024px iPads and 375–414px phones; several grid layouts collapse deliberately (the hero portrait shrinks; the practice index tags reflow beneath the description; the ticker keeps scrolling; the progress ribbon hides below 640px).
- Accessibility: all interactive elements are semantic (`<a>`, `<button>`). The testimonials arrows have `aria-label`s. Reveal animations don't gate content — ensure prefers-reduced-motion disables them (add a media query around `.reveal` transitions in production).
