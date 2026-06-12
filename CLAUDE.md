# Drive More Media — Website Project Brief

## Who
- **Client / Owner:** Karl Brussolo
- **Company:** Drive More Media — Toronto-based digital marketing agency
- **Email:** hello@drivemoremedia.com | karl@drivemoremedia.com
- **Phone:** +1 647-370-9148
- **Website:** https://drivemoremedia.com
- **Related:** https://mysunnyai.com (sister company) | https://app.drivemoremedia.com (client portal)

## Tech Stack
- Pure HTML / CSS / JS — no framework, no build step, no package manager
- Tailwind CSS via CDN
- DM Sans font via Google Fonts
- Hosted on **Cloudflare Pages / Workers**
- Repo: `mysunnyai/dmm-website` on GitHub
- Deploy branch: `main`
- Feature branches must be prefixed `claude/`

## Files
```
index.html       — main site (~2,430 lines)
booking.html     — Book a Strategy Call page (~192 lines)
logo.png         — DMM logo
Flower Of life.webp
robots.txt
sitemap.xml
Clients/1.png … Clients/18.png  — client logos for carousel
```

## Homepage Sections (in order)
1. **Nav** — sticky, slides in once hero scrolls out of view. Has DMM App Login (hidden on mobile) + Book a Call CTA
2. **Hero** — black bg, WebGL shader canvas, whiteboard graphic, floating pills (hidden on mobile), glow "Book a Strategy Call" CTA button, channels strip
3. **Value Prop** — "We increase customer acquisition..." with interactive agency pill (3-state: idle → loading → saved)
4. **2 Ways To Drive Growth** — two `[data-glow]` service cards (Our Marketing Services + Customer Acquisition Infrastructure)
5. **Sunny AI** — Meet Sunny AI section with sparkle/beam effect
6. **Animated Gradient / Timer** — bold callout with countdown-style animation, red/orange/blue gradient
7. **Trusted By** — auto-scrolling infinite carousel, 18 client logos (JS-driven, 3× duplicates for seamless loop)
8. **Lamp / Stats** — attention stats section with lamp cone effect (cones hidden on mobile)
9. **Dear Business Owner** — Karl's letter in a `[data-glow]` dark card with meteor shower effect
10. **Footer** — 3-column grid (collapses to 1 on mobile), links to Privacy Policy + Terms

## Integrations
- **Google Analytics GA4:** `G-327876801`
- **SEO:** meta tags, Open Graph, Twitter Card, JSON-LD structured data (MarketingAgency schema)
- `sitemap.xml` + `robots.txt` in root
- **Cloudflare Workers** config via `wrangler.jsonc`

## Styling Notes
- Brand background: `#f1e9dd` (warm cream)
- Brand green: `#3d7f5b`
- Dark sections: `#000000`
- Font: DM Sans
- Glow cards use `[data-glow]` attribute + spotlight CSS + JS mouse tracking
- Mobile breakpoint: `max-width: 768px` and `max-width: 480px`
- Floating pills hidden on mobile (`display:none !important`)
- DMM App Login hidden on mobile

## Known Fixes Applied (as of Mar 2026)
- `touch-action: pan-y` added to `[data-glow]` on mobile — was blocking vertical scroll on service cards and about card
- `#hero { overflow: visible }` on mobile — was clipping the glow button blur effect
- Clients carousel `setWidth` now recalculated from actual rendered item width via `requestAnimationFrame` — CSS overrides item size from 180px to 100px on mobile which broke the loop and hid some logos
- SEO meta tags, GA4, sitemap, robots.txt added
- Social share OG image added (`Social share.png`)

## Karl's Preferences
- No unnecessary comments in code
- Keep it clean and minimal — don't over-engineer
- Mobile experience is important — Karl tests on his phone regularly
- Commits should be descriptive and clear
