# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Always Do First
- **Invoke the `frontend-design` skill** before writing any frontend code, every session, no exceptions.

## Project Overview

**DataScrive** is a data analytics consulting service for SMBs. The website's single goal is to convert visitors into **booked discovery calls** ("Book a Free Call").

**Two products:**
- **DataScrive Audit** — one-time project, the entry point
- **DataScrive Maintain** — monthly retainer, the logical continuation of the Audit

**Two ICPs (Ideal Customer Profiles):**
- Online stores / e-commerce
- Local / service businesses

**No social proof strategy:** DataScrive has no client base yet. Do not invent testimonials, case study numbers, or client metrics. Replace social proof with process transparency and objection handling.

## Brand Colors

These are the canonical DataScrive brand tokens — always use them, never Tailwind defaults:

| Token | Hex | Usage |
|-------|-----|-------|
| `--navy` | `#1C3054` | Primary brand, hero bg (dark CTA), headings |
| `--teal-deep` | `#2A8FA0` | Step numbers, featured card borders, accent text |
| `--teal` | `#4EC4C4` | Accent line, bullet icons, hover states |
| `--amber` | `#F0A830` | Final CTA button, warm accent |
| `--white` | `#F7F8FC` | Hero section background, off-white base |

## Homepage Wireframe Structure

The wireframe is at `branding_assets/datascrive_homepage_wireframe_en.html` — reference it for layout, section order, and copy hints.

| # | Section | Notes |
|---|---------|-------|
| 01 | **Hero** | 60/40 grid (copy left, visual right). Primary CTA: "Book a Free Call →". 3 micro-stats = process facts, not client metrics. |
| 02 | **The Problem** | 2-column layout, one card per ICP. Closing line unifies both. |
| 03 | **Solution + Positioning** | Teal background (`#EAF7F8`). 3 key differentiators. "We are not X, we are Y" framing. |
| 04 | **Services** | 2 cards: Audit (featured, teal border, "Step 1") + Maintain (secondary, "Step 2"). No artificial tiers. |
| 05 | **How It Works + What You Get** | 50/50 grid. Left: 4-step process. Right: 4 deliverable cards. Replaces social proof. |
| 06 | **Objection Handling** | Q&A format. 4 questions: timeline, technical knowledge needed, existing analytics, lock-in contracts. |
| 07 | **Final CTA** | Navy background. 50/50: left = headline + risk reversals (teal bullets); right = form (3 fields: Name, Email, Platform) + amber CTA button. |

**Removed sections** (do not add back): "The Bigger Picture" (confusing mid-page), "Results / Numbers" (no real data yet).

## Local Server
- **Always serve on localhost** — never screenshot a `file:///` URL.
- Start the dev server: `node serve.mjs` (serves the project root at `http://localhost:3000`)
- `serve.mjs` lives in the project root. Start it in the background before taking any screenshots.
- If the server is already running, do not start a second instance.

## Screenshot Workflow
- Puppeteer is installed at `C:/Users/nateh/AppData/Local/Temp/puppeteer-test/`. Chrome cache is at `C:/Users/nateh/.cache/puppeteer/`.
- **Always screenshot from localhost:** `node screenshot.mjs http://localhost:3000`
- Screenshots are saved automatically to `./temporary screenshots/screenshot-N.png` (auto-incremented, never overwritten).
- Optional label suffix: `node screenshot.mjs http://localhost:3000 label` → saves as `screenshot-N-label.png`
- `screenshot.mjs` lives in the project root. Use it as-is.
- After screenshotting, read the PNG from `temporary screenshots/` with the Read tool — Claude can see and analyze the image directly.
- When comparing, be specific: "heading is 32px but reference shows ~24px", "card gap is 16px but should be 24px"
- Check: spacing/padding, font size/weight/line-height, colors (exact hex), alignment, border-radius, shadows, image sizing

## Output Defaults
- Single `index.html` file, all styles inline, unless user says otherwise
- Tailwind CSS via CDN: `<script src="https://cdn.tailwindcss.com"></script>`
- Placeholder images: `https://placehold.co/WIDTHxHEIGHT`
- Mobile-first responsive

## Brand Assets
- Always check `branding_assets/` before designing — it contains the brand manual PDF and the homepage wireframe HTML.
- Use the brand color tokens above. Do not invent colors or use Tailwind palette colors.

## Reference Images
- If a reference image is provided: match layout, spacing, typography, and color exactly. Swap in placeholder content. Do not improve or add to the design.
- If no reference image: use the wireframe at `branding_assets/datascrive_homepage_wireframe_en.html` as the layout reference.
- Do at least 2 comparison rounds. Stop only when no visible differences remain or user says so.

## Anti-Generic Guardrails
- **Colors:** Use brand tokens above. Never use default Tailwind palette (indigo-500, blue-600, etc.).
- **Shadows:** Never use flat `shadow-md`. Use layered, color-tinted shadows with low opacity.
- **Typography:** Never use the same font for headings and body. Pair a display/serif with a clean sans. Apply tight tracking (`-0.03em`) on large headings, generous line-height (`1.7`) on body.
- **Gradients:** Layer multiple radial gradients. Add grain/texture via SVG noise filter for depth.
- **Animations:** Only animate `transform` and `opacity`. Never `transition-all`. Use spring-style easing.
- **Interactive states:** Every clickable element needs hover, focus-visible, and active states. No exceptions.
- **Images:** Add a gradient overlay (`bg-gradient-to-t from-black/60`) and a color treatment layer with `mix-blend-multiply`.
- **Spacing:** Use intentional, consistent spacing tokens — not random Tailwind steps.
- **Depth:** Surfaces should have a layering system (base → elevated → floating), not all sit at the same z-plane.

## Hard Rules
- Do not add sections, features, or content not in the reference
- Do not "improve" a reference design — match it
- Do not stop after one screenshot pass
- Do not use `transition-all`
- Do not use default Tailwind blue/indigo as primary color
- Do not invent client metrics, testimonials, or case study data