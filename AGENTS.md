# LANDING PAGE GENERATOR

## Mission

Create a demo landing page for a real small business.

The goal is not to create a beautiful website.

The goal is to create a website that the business owner immediately recognizes as their business and wants to buy.

The briefing file already contains the research.

Do not repeat the research process.

Do not create additional planning documents.

Go directly from briefing to website.

---

# Source of Truth

The briefing file is the primary source of truth.

Use as much information from the briefing as possible.

Before writing any code:

- Read the entire briefing.
- Extract all important information.
- Use real business details.
- Use real services.
- Use real location.
- Use real contact information.
- Use real differentiators.

Never ignore information from the briefing.

---

# Website Requirements

Create:

- index.html

Everything must be inside a single file:

- HTML
- CSS
- JavaScript

No build tools.

No frameworks.

Ready for Netlify Drop.

---

# Design Philosophy

The website must never look AI-generated.

Forbidden:

- Generic SaaS layouts
- Hero centered on white background
- Blue-purple gradients
- Inter as primary font
- Bootstrap look
- Tailwind look
- Generic cards everywhere
- Empty decorative sections
- Placeholder content

Required:

- Strong visual identity
- Business-specific atmosphere
- Premium typography
- Custom layout decisions
- Real visual hierarchy
- Modern but believable design

---

# Design Direction

Choose one visual direction that fits the business.

Examples:

- dark motorsport
- editorial luxury
- industrial performance
- clean premium
- brutalist raw
- organic soft
- bold playful

Commit to one direction.

Do not mix multiple styles.

---

# Content Rules

Use briefing content first.

Do not replace real information with generic marketing copy.

Avoid:

- High quality services
- Professional team
- Industry leader
- Trusted partner
- Customer satisfaction is our priority
- Rule-of-three templated phrases (e.g. "bez pośpiechu, bez kompromisów, z dbałością") — a classic AI tell
- Empty intensifiers — prefer concrete, verifiable facts

Do not name specific individuals (owner / staff) in headings or body copy, even if the briefing mentions them by name. It is a privacy risk and ages badly. Real names belong only inside genuine quoted reviews. Refer to the business as a studio / team.

Write naturally.

Write as a human. Short, plain sentences beat a polished marketing cadence.

The copy should feel written specifically for this business.

---

# Layout Rules

Adapt the structure to the business.

Typical sections:

- Navigation
- Hero
- Services
- Why Choose Us
- Portfolio
- Reviews
- Contact
- Footer

Do not force sections that do not fit.

---

# Responsive & QA

Design mobile first, then verify a full matrix BEFORE declaring done — test widths and short heights, not just one phone and one desktop:

- 320 (ultra-small), 375 / 390 (phones), 430 (large phone)
- 768 / 820 (tablet portrait)
- 1280 / 1440 (desktop) — and at a short viewport height (~800px); laptop screens expose hero overflow

On every size confirm:

- No horizontal scrolling (scrollWidth === innerWidth)
- No overlaps — especially the fixed nav over hero content
- Readable text, even/symmetric spacing, full-width touch buttons

Collapse the nav to a burger at ~960px, not at the phone breakpoint — the 768–960 tablet range squishes a desktop nav, and a lone CTA gets stranded in the middle by `space-between` once the links hide (hide that CTA too; the burger menu carries it).

After ANY global change (line-height, breakpoints, hero height), re-run the whole matrix. Global edits routinely break sizes you already verified.

---

# Images

Use:

1. Images from briefing
2. Images from social media
3. Relevant placeholders only if absolutely necessary

Prefer real content whenever available.

---

# CSS & Layout Standards

Hard rules learned from real fix cycles — apply them up front instead of patching later:

- Hero: use `min-height` (e.g. `min-height:88vh`), never a fixed `height` / `height:vh`. Fixed heights clip content that grows (longer copy, bigger line-height) and shove it up under the nav.
- Diacritic-heavy languages (Polish etc.): tight display fonts (Anton, Bebas) collide on accents (Ó, Ż) and ogoneks (Ę, Ą). Use line-height ≥1.2 for large hero headings, ≥1.12 for section headings.
- Logo needs real presence: ~60px+ in the nav, larger in the footer. Add `white-space:nowrap` to brand text so it never wraps.
- Stat / badge rows: give each value the SAME fixed-height top line so labels share one baseline (mixing star glyphs with numeric type misaligns them). On mobile use an explicit grid (`1fr 1fr`), not `flex-wrap` + `min-width` hacks.
- Galleries / masonry: set `grid-auto-rows` to cap tile heights, or wide/tall spans balloon and force endless scrolling.
- Off-canvas / mobile menu: the closed state needs `visibility:hidden` (alongside the transform) or its bottom edge peeks at the top on short screens; add `overflow-y:auto` for tall menus.
- NEVER use the `padding` / `margin` shorthand in a media-query override when you mean one axis — it resets all sides (this silently killed the hero's bottom spacing). Use `padding-left/right` or `padding-top/bottom`.
- Reuse spacing tokens so vertical rhythm stays even between sections.

---

# Final Self Review

Before finishing ask:

- Does this look custom-made for this business?
- Does it look expensive?
- Does it feel trustworthy?
- Would the owner recognize their brand?
- Does it avoid common AI website patterns?

If not, improve before finalizing.