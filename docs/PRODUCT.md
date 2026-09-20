# Product

<!-- impeccable:product-schema 1 -->

## Platform

android

## Users

Privacy-minded Android users who distrust cloud AI. Primary job: run a capable AI assistant without their conversations leaving the device. Unknowns recorded as open decisions in Capabilities and Constraints.

## Product Purpose

Snor is a local-first AI assistant for Android. Success means the user gets genuinely useful on-device inference they trust, with cloud used only when they explicitly choose it.

## Positioning

True on-device GGUF inference over the Vulkan GPU — the mechanism a cloud-only competitor could not truthfully copy. Cloud is an optional, explicit opt-in, not the default path.

## Operating Context

The user installs Snor on Android, downloads a model, and runs inference locally on-device (Vulkan GPU). Cloud is available as a fallback only when the user turns it on.

## Capabilities and Constraints

- Confirmed: on-device GGUF inference accelerated by the Vulkan GPU.
- Confirmed: optional cloud fallback, chosen explicitly by the user.
- Open decisions (not invented here): model sourcing/size, GPU device coverage, cloud provider details, pricing, distribution channel.
- This repository is the marketing landing page for the app, not the app itself.

## Brand Commitments

- Name: Snor.
- Framing: "Local-first privacy, cloud on terms."

## Evidence on Hand

- The landing page itself (`index.html`, `styles.css`, `assets/img/*.gif`) demonstrates the current communication and visual system.
- The six GIF assets in `assets/img` are transparent and render on the card surface.
- No testimonials, customers, benchmarks, or deployment claims exist; none should be fabricated.

## Product Principles

- Local first: on-device processing is the default and the identity.
- Cloud on terms: any cloud use is explicit, user-driven, and never silent.
- User control: the user decides what leaves the device.
- Trust through transparency: communicate where data goes, plainly.

## Accessibility & Inclusion

No product-specific accessibility requirement was established during init.