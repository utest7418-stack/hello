# Nexovra Creative Media — Website

Premium, black-and-gold marketing site for **Nexovra Creative Media** ("We Create. You Grow.").
Static production build: plain HTML/CSS/JS, GSAP + ScrollTrigger for animation, Lenis for smooth
scroll — no build step required. Open `index.html` directly, or serve the folder with any static
host (Vercel, Netlify, GitHub Pages, Nginx).

## Structure

```
nexovra/
├── index.html        # All sections/markup
├── css/style.css      # Design tokens + all component styles
├── js/main.js          # Loader, cursor, Lenis, GSAP reveals, all interactions
└── assets/             # Drop real photos/videos here (see Placeholders below)
```

## Sections included

Navbar (glass, sticky) · Hero (animated headline, device mockup, particles) · Marquee strip ·
Services (11 cards) · Portfolio (filterable masonry) · Video Editing Showcase (tool pills +
timeline UI) · Why Choose Us · Animated stats counters · Process timeline (7 steps) ·
Testimonials carousel · Industries served · Pricing (monthly/one-time toggle) · FAQ accordion ·
Newsletter · Contact form · Footer · Floating WhatsApp/Call/Back-to-top · Booking popup ·
Live notification toast · Chat assistant widget · Cookie consent · Dark/light theme toggle ·
Language switch (EN/HI, cosmetic).

## Placeholders — replace before launch

Everything marked `[ SCREENSHOT PLACEHOLDER ]` or `[ VIDEO PLACEHOLDER ]` in `index.html` is a
stand-in for real media (portfolio pieces, the video showreel, Google Maps embed). No real client
work, logos, or footage was available, so nothing was invented — swap these `.port-placeholder`
/ `.edit-placeholder` blocks for actual images or `<video>` elements, and replace the map
placeholder with a real Google Maps `<iframe>` embed and the phone/email/address details with the
agency's real contact information.

## Notes on scope vs. the original brief

The brief specified a React / Next.js / TypeScript / Tailwind stack. This build is static
HTML/CSS/JS instead, because generating that stack requires an `npm install` with internet access,
which this environment doesn't have. Everything visual and interactive from the brief (GSAP,
Framer-style motion via GSAP, Lenis smooth scroll, parallax, magnetic buttons, custom cursor,
counters, accordion, filterable portfolio, pricing toggle, chat widget, booking popup, etc.) is
implemented natively in vanilla JS, so it runs anywhere without a build pipeline. If you want the
React/Next.js version for a team workflow, this markup and CSS translate directly into components —
happy to scaffold that structure on request.

## Performance / accessibility baked in

- `prefers-reduced-motion` respected (disables non-essential animation).
- Visible keyboard focus states on all interactive elements.
- Semantic landmarks (`header`, `main`, `footer`, `nav`), labeled form fields, `aria-live` region
  on the contact form's confirmation message.
- Fonts loaded via `<link>` with `preconnect`; GSAP/Lenis loaded from cdnjs.
- No layout-shifting fixed-position elements until content is ready (loader gates first paint).

## Future improvements

- Wire the contact form to a real backend/email service (currently simulates success client-side).
- Replace placeholder reels/screenshots with real, optimised (WebP/MP4) assets and add `loading="lazy"`.
- Add real Google Maps embed and social links.
- Consider migrating to Next.js + Tailwind if the team wants component reuse and CMS-driven content.
