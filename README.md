# DataScrive — Website

Marketing site for **DataScrive**, a data analytics consulting service for SMBs. The site has a single conversion goal: turn visitors into booked discovery calls.

> **Live booking:** [calendly.com/contact-datascrive/30min](https://calendly.com/contact-datascrive/30min)

---

## What's in here

A single-page static site, hand-built with no framework or build step.

```
.
├── index.html                # The whole site — markup, styles, scripts
├── favicon.svg               # D-mark cropped from the brand PNG
├── branding_assets/
│   ├── DataScrive_ Logo.png             # Primary horizontal lockup
│   ├── DataScrive_ Logo.jpeg            # JPEG fallback
│   ├── DataScrive_Brand_Manual_v2.pdf   # Brand guidelines
│   └── datascrive_homepage_wireframe_en.html   # Source wireframe
├── CLAUDE.md                 # Working rules for Claude Code sessions
└── README.md
```

## Stack

- **HTML / CSS / vanilla JS** — single `index.html`, all styles inline
- **Type:** [Fraunces](https://fonts.google.com/specimen/Fraunces) (display) · [Geist](https://fonts.google.com/specimen/Geist) (body) · [Geist Mono](https://fonts.google.com/specimen/Geist+Mono) (labels)
- **Hosted via** GitHub (static)

No build, no bundler, no dependencies. Open `index.html` and it runs.

## Brand colors

| Token        | Hex       | Use                                          |
|--------------|-----------|----------------------------------------------|
| `--navy`     | `#1C3054` | Primary brand, headings, dark sections       |
| `--teal-deep`| `#2A8FA0` | Step numbers, featured borders, accents      |
| `--teal`     | `#4EC4C4` | Accent line, bullet icons, hover states      |
| `--amber`    | `#F0A830` | Final CTA button                             |
| `--cream`    | `#F7F8FC` | Off-white base, hero background              |

## Page structure

The homepage follows the wireframe in [`branding_assets/datascrive_homepage_wireframe_en.html`](branding_assets/datascrive_homepage_wireframe_en.html):

1. **Hero** — headline, primary CTA, 3 process micro-stats, animated chart panel
2. **The Problem** — two ICP cards (online stores · local/service businesses)
3. **Solution + Positioning** — 3 differentiators, "we are not X, we are Y" framing
4. **Services** — DataScrive Audit (one-time, featured) + DataScrive Maintain (monthly)
5. **How It Works + What You Get** — 4-step process and 4 deliverables
6. **Objection Handling** — 4 Q&A cards (timeline, technical, existing analytics, contracts)
7. **Final CTA** — navy section with inline form + Calendly link

## Run locally

The site is a single static file, so any static server works. From the project root:

```bash
# Python
python -m http.server 3000

# Node (if you prefer)
npx serve .
```

Then open `http://localhost:3000`.

## Deploy

Any static host works (GitHub Pages, Netlify, Vercel, Cloudflare Pages). The repo is structured for zero-config deployment — point at the project root and serve `index.html`.

## Products

- **DataScrive Audit** — one-time project. Two-week deep dive into the analytics stack, returning a documented diagnosis, fixed tracking, a custom KPI dashboard, and a 30-day support window.
- **DataScrive Maintain** — monthly retainer. Ongoing health checks, anomaly alerting, and tracking updates as the stack evolves. Month-to-month, no lock-in.

## License

All rights reserved. Brand assets in `branding_assets/` are property of DataScrive.
