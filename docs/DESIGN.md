---
name: Snor
description: Private AI landing page, local-first AI chat for Android
colors:
  bg: "#0e1618"
  surface: "#142023"
  surface-2: "#1b2c30"
  border: "#223031"
  text: "#f5f6f6"
  muted: "#a1a8aa"
  accent: "#2c6a75"
  accent-soft: "rgba(44,106,117,0.12)"
typography:
  display:
    fontFamily: "Georgia, 'Times New Roman', serif"
    fontSize: "clamp(40px, 7vw, 72px)"
    fontWeight: 400
    lineHeight: 1.12
    letterSpacing: "-0.02em"
  lede:
    fontFamily: "system-ui, -apple-system, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif"
    fontSize: "19px"
    fontWeight: 400
    lineHeight: 1.65
  body:
    fontFamily: "system-ui, -apple-system, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif"
    fontSize: "1rem"
    fontWeight: 400
    lineHeight: 1.6
  mono:
    fontFamily: "ui-monospace, 'SF Mono', Menlo, Consolas, monospace"
    fontSize: "13px"
    fontWeight: 400
    lineHeight: 1.55
rounded:
  sm: "6px"
  md: "8px"
  lg: "10px"
spacing:
  container: "24px"
  gap: "16px"
  gap-lg: "28px"
  section: "96px"
components:
  site-header:
    backgroundColor: "rgba(14,22,24,0.85)"
    typography: "{typography.body}"
    rounded: "{rounded.lg}"
    padding: "16px 24px"
    height: "72px"
  nav-link:
    textColor: "{colors.muted}"
    typography: "{typography.body}"
    padding: "6px 12px"
    height: "36px"
  nav-link-hover:
    textColor: "{colors.text}"
    typography: "{typography.body}"
    padding: "6px 12px"
    height: "36px"
  button-primary:
    backgroundColor: "{colors.accent}"
    textColor: "{colors.text}"
    typography: "{typography.body}"
    rounded: "{rounded.lg}"
    padding: "14px 32px"
    height: "52px"
  button-primary-hover:
    backgroundColor: "{colors.accent}"
    textColor: "{colors.text}"
    typography: "{typography.body}"
    rounded: "{rounded.lg}"
    padding: "14px 32px"
    height: "52px"
  feature-card:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.text}"
    typography: "{typography.body}"
    rounded: "{rounded.lg}"
    padding: "24px"
  privacy-card:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.text}"
    typography: "{typography.body}"
    rounded: "{rounded.md}"
    padding: "20px"
  footer:
    textColor: "{colors.muted}"
    typography: "{typography.body}"
    padding: "24px"
---

## Overview

Snor is a private AI chat app for Android that runs a model fully on your phone. Every choice in this design serves that story.

The visual voice is **quiet depth**. The page reads as a calm, dark surface — like a dive console seen through a mask — rather than a marketing screen shouting for attention. Nothing flares. Highlights stay restrained and precise: one deep-teal accent against a near-black ink base, serif display type for moments of declaration, and soft light that only appears on hover.

The North Star is **The Submersible Console**: a dark, measurement-conscious control surface that feels engineered, self-contained, and trustworthy — the physical opposite of the noisy "keep your data in the cloud" sites it competes against. The user should feel the page itself is proof that the product keeps things close and quiet.

Three product truths anchor the copy and layout: **local-first privacy** (on-device GGUF inference, no account), **cloud on your terms** (explicit opt-in), and **a real, shippable build** (v1.0.3, Android 8.0+, ARM64, ~101 MB — a download link, not a wishlist).

**Key Characteristics:**
- Quiet depth: a composed, dark console surface, not a shouting marketing screen.
- Low-chroma palette: Abyssal Ink base, two lifted surfaces, one Deep Water Teal accent.
- Serif declares, sans explains, mono measures.
- Flat by default; depth appears only on hover.
- Local-first by design: keeps everything close and quiet — the page is the proof.

## Colors

Colors are dark-first and surface-lead. The base is Abyssal Ink `#0e1618`, a blue-green near-black that reads darker than pure black but carries the teal identity forward. Surfaces step up through two slightly lifted layers, `surface #142023` and `surface-2 #1b2c30`, so cards sit apart from the page without needing shadows.

Accent is Deep Water Teal `#2c6a75`. It is used sparingly — the headline emphasis word, the primary button, hover glows — and only where a single point of focus belongs. Its soft wash `accent-soft rgba(44,106,117,0.12)` feathers radial gradients behind the hero and gif cards, giving depth without a hard edge.

Text is near-white `#f5f6f6`; secondary text is muted slate `#a1a8aa`. Borders are `#223031`, a barely-lighter version of the ink base, so structure lines whisper rather than shout. These are normative: accent never fights the base, muted never approaches text brightness.

**The Rare Accent Rule.** Accent teal appears only at the point of focus — the emphasized headline word, the primary button, the hover glow.

| Token | Value | Use |
| --- | --- | --- |
| `bg` | `#0e1618` | Page base |
| `surface` | `#142023` | Cards and panels |
| `surface-2` | `#1b2c30` | Lifted states / code chips |
| `border` | `#223031` | Hairline structure |
| `text` | `#f5f6f6` | Primary copy |
| `muted` | `#a1a8aa` | Secondary copy, meta |
| `accent` | `#2c6a75` | Focus, primary action |
| `accent-soft` | `rgba(44,106,117,0.12)` | Depth washes, gif-card field |

## Typography

Type does the emotional work while color stays flat. Two voices:

**Display — serif.** Georgia at `clamp(40px, 7vw, 72px)`, regular weight, tight line-height and a slight negative tracking. Declarations set in serif feel considered and calm — the h1 reads like a carved instrument face. The emphasized word in the h1 ("your") is dropped in accent teal, plain. Never italicize, never bold the serif.

**Body — system sans.** One stack throughout UI copy, meta, nav, and buttons: `system-ui, -apple-system, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif`. Body runs at 1rem/1.6; the lead paragraph is 19px/1.65. It stays invisible and legible, letting the serif headline carry the personality.

**Mono — only where measurement belongs.** The version meta line (`v1.0.3 · Android 8.0+ · ARM64 · ~101 MB`) and technical footnotes render in `ui-monospace, 'SF Mono', Menlo, Consolas`. This is the "console" in the North Star: a machine-readable fact, not marketing.

**The Three-Voices Rule.** Serif declares, sans explains, mono measures — each stays in its lane.

## Layout

The page is a single quiet column: centered, constrained, generous.

Content sits in a container of `min(1080px, calc(100% - 48px))` — a 24px gutter on each side that holds even on narrow phones. Sections breathe on a 96px rhythm (`section`), with the hero given more air: 120px top, 96px bottom. One breakpoint at 640px collapses grids; there is no density to lose — cards simply drop to a single column.

The hero is stacked and centered: eyebrow, serif headline covering two strong lines, a one-sentence lead, the single action (a solid teal button to the APK), then the version meta in mono beneath. One action, not a menu.

The features grid uses `auto-fit minmax(280px, 1fr)` with a 16px gap; each card pairs a small heading with body copy. The privacy section narrows to 820px and tightens the gap to 28px — its text is shorter and slower, and it should feel like a statement, not a catalog. The footer is a single line of muted copy, terminal-quiet.

## Elevation & Depth

Flat is the default. Cards do not cast day-to-day shadows; separation comes from the surface ladder (bg → surface → surface-2) and 1px `border` hairlines. Depth is reserved for hover and is never gratuitous.

**The Flat-By-Default Rule.** Surfaces are flat at rest; shadows appear only as a response to hover.

- **Hover glow:** primary elements lift with `0 6px 24px rgba(44,106,117,0.35)` — a soft teal bloom, not a drop shadow. It signals "this one answers" only when the pointer arrives.
- **Card hover:** border warms to `rgba(44,106,117,0.45)` with the same teal glow. The card body stays put; only the edge and aura respond.
- **Header:** sticky, `rgba(14,22,24,0.85)` fill with `backdrop-filter: blur(10px)` and a 1px bottom hairline. It is a frosted panel floating over scrolling content — the one place the console surfaces above the page.
- **Depth wash:** radial `accent-soft` gradients breathe behind the hero and gif cards to create atmosphere (a lit console in a dark room) without elevation.

## Shapes

Radius language is small and consistent: 10px for cards and the primary button (`lg`), 8px for compact panels (`md`), 6px for chips and the smallest chrome (`sm`). Nothing is pill-shaped and nothing is brutally square — the middle ground reads as engineered rather than playful.

Cards seat their media with the radius clipped: `.gif` fields tuck a trailing edge of `accent-soft` behind, and header/body edges use `rounded-t` so imagery never bleeds past the corner. Structure (borders, dividers) is always square-cornered and 1px; only filled shapes earn a radius.

## Components

Components are tokens-first: the frontmatter is normative, prose describes behavior.

- **Site header** — frosted bar, avatar + wordmark left, three nav links (Features, Privacy, Download) right. Nav links rest at `muted`, warming to `text` on hover. Sticky with blur; content scrolls beneath it.
- **Primary button** — solid accent fill, near-white text, 10px radius, 14px/32px padding (52px tall). Content-first: a "Download the APK" label with an inline SVG badge, no arrow clutter. Hover lifts with the teal glow (frontmatter variant `button-primary-hover`); active state pressed but flat, glow cleared. Tap target comfortably exceeds 48px.
- **Feature cards** — `surface` panels, 16px gaps. Each pairs a small sans heading over body copy (e.g. "Local inference", "Cloud fallback"). The gif cards frame their animation in an `accent-soft` field with clipped trailing corners, captioning the live behavior rather than illustrating it.
- **Privacy cards** — via the same surface family at the narrower 820px band, `md` radius, 20px padding. Rhetorical question + honest answer pattern ("Is anything uploaded?" → "No on-device reasoning is ever uploaded. Cloud is off unless you flip it on."). No lock icons; restraint is the trust signal.
- **Footer** — a single muted mono/sans line, terminal-quiet. No newsletter, no social row, no noise.

## Do's and Don'ts

**Do**
- Let dark-to-dark contrast do the layering — prefer the surface ladder and 1px `border` over shadows.
- Save accent teal for moments of focus: the emphasized h1 word, the primary button, hover glow.
- Use serif for declarations, sans for explanation, mono for facts. Keep each in its lane.
- Communicate privacy with honest, plain claims and a calm tone — the design is the trust signal.
- Keep buttons and tap targets comfortably above 48px; the page must thumb-navigate on a phone.

**Don't**
- Don't add gradients to type, glassmorphism candy, or animated headline entrances — quiet depth means the content surfaces, not the motion layer.
- Don't lighten the accent block; never swap near-white button text for ink or tinted text.
- Don't write mock testimonials, fake benchmarks, or "join the waitlist" — this is a shipped build with a real APK link.
- Don't over-punctuate the muted scale or push `muted` toward `text` (or `text` toward pure white).
- Don't break the radius ladder with pills or circles, and don't let card media spill past clipped corners.