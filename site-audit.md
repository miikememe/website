# memefpv.net — Site Audit

Audit started 2026-05-06. Source: live screenshots of the current Squarespace site.

## Site map for the **new** site

The site is being rebranded from a **"FPV pilot service for hire"** business pitch to a **personal portfolio of projects** with a contact page. This changes content, voice, and structure (but not the visual design — dark/cinematic stays).

**New nav (7 items):**
1. **Home** — hero showcase + quick intro to who I am
2. **About** — personal, more prominent in the rebrand
3. **What I Do** — reframed Services (personal context, not sales pitch)
4. **Drone Work** — was Portfolio (FPV/aerial video projects)
5. **3D Prints** — was 3D Printing (gallery of things I've built — no more "submit an idea for pricing" CTA)
6. **Other Projects** — new — room to grow into other things later (code, art, builds, whatever)
7. **Contact**

*(Store dropped.)*

> **Note:** 7 nav items is on the high side. If it feels crowded once we're building, the easiest squeeze is folding "What I Do" content into the Home page — but we can decide that when we get there.

---

## Brand & visual identity

**Logo.** Wordmark "MEMEFPV" in a heavy, slightly italic sans, with a stylized bird/wing silhouette tucked into the right side of the V. Two color treatments in use:
- **Black logo** on dark background in the header (looks intentional — embossed/dimensional feel because it's so close to the bg).
- **White logo** in the footer.

**🎯 Animated propeller (must keep in new site).** The logo's bird element actually has a **spinning propeller**, and it appears in both the header and footer of every page. This is a signature brand detail — Mike has confirmed it must carry over to the new site. Implementation is straightforward in the rebuild:
- Export the logo as **SVG with the propeller as a separate `<g>` group**.
- Apply a CSS animation: `animation: spin 1.2s linear infinite` with `transform-origin` set to the propeller hub.
- Use the same SVG in the header and footer; the spin is purely CSS, no JS required.
- Pause animation when `prefers-reduced-motion: reduce` for accessibility.

**Color palette (from homepage).**
- Background: very dark grey, near-black — roughly `#1a1a1a` / `#222`.
- Primary text / body copy: warm off-white, slightly cream — roughly `#f3ece1` or `#ebe2d2`.
- Accent / highlight color: not really visible on the homepage — the design relies on imagery for color.
- CTA button: black pill with off-white text.

**Typography.**
- **Wordmark uses Archivo** — confirmed from `logo high res.svg` (italic, weight 700, letter-spacing -59.64 / very tight tracking, 284px @ original res). Archivo is a free Google Font, so we can match the current brand exactly without licensing.
- Body & headings: same Archivo family is a safe pick for the rest of the site too. Heavy weight for headings, regular for body.
- Hero: "Telling stories from the air" — title-cased, ~88–104px desktop.
- Section titles: e.g. "We make it happen." — same family, slightly different weight.
- Service names: `Live Events`, `Cinema-grade storytelling`, `Commercial Applications` — appear to be expandable accordions (note the `+` icons on the right).

**Logo files in project folder.**
- `logo high res.svg` — wordmark only (just the "MEMEFPV" text in Archivo).
- `logo propellor .svg` — drone silhouette with 4 vector paths.
  - The **small circular dot in the middle is the propeller hub** (confirmed by Mike). That's the rotation center — `transform-origin` for the spin animation will be set there.
  - The two large swept shapes flanking the hub are most likely the propeller blades (or the silhouette around them); the tall vertical path is the body. Will confirm during build by isolating each path and inspecting visually.

**Imagery.**
- Heavy use of video as hero content (autoplay-style player, 02:17 length on the homepage clip — looks like marina/boat-show coverage).
- Behind the "We make it happen" section: a large blurred FPV drone shot (looks like a quad on dirt — maybe a freestyle/racing frame).
- Overall vibe: cinematic, action, motion-blur, drone POV.

---

## Page: Home

**Header**
- Black background.
- Logo top-left (MemeFPV wordmark + bird).
- Nav top-right: Home, Services, Portfolio, 3D Printing, About, Contact, Store, Cart (0).
- Active page indicator: small underline beneath the active nav item ("Home" is underlined).

**Hero section**
- Two-column layout (text left / video right).
- Headline: **"Telling stories from the air"**.
- CTA button: **"Contact for more information!"** — small rounded black pill button.
- Video on the right with custom Squarespace player chrome (volume / settings / fullscreen icons bottom-right).

**"We make it happen" section**
- Full-width section with a blurred FPV drone background image (warm/orange tones).
- Heading: **"We make it happen."** — left-aligned.
- Right-aligned list of services with `+` accordion toggles:
  - Live Events
  - Cinema-grade storytelling
  - Commercial Applications

**Footer**
- White MemeFPV logo bottom-left.
- "MemeFPV Social" label and an Instagram icon link.
- That's it — no phone, no address, no email, no second nav.

---

## Page: Services

**Hero**
- Heading: **"Precise *and* Accurate"** — note the italicized "and". This italic-accent treatment looks like a deliberate brand pattern; we should keep it.
- No CTA button at the top (just the heading on dark background).

**Three-column service cards**
- Each card uses a **soft squircle / rounded-square mask** on the image — distinctive look. Worth replicating in CSS (`border-radius` ~30% or an SVG clip-path).
- Card 1 — **Live Events**
  - Image: aerial of a motocross track with riders.
  - Copy: "Experience top-quality drone live streaming and cinema production services. Capture events from new angles, creating captivating content for your viewers."
- Card 2 — **Cinema-Grade Storytelling**
  - Image: motorcycle POV ripping through a parking deck.
  - Copy: "Whether the need is a full studio production, or just a pilot with a drone. Our team specializes in capturing moments that wow, providing exceptional value to your project."
- Card 3 — **Commercial**
  - Image: office interior with cubicles.
  - Copy: "Bring your business to life with fresh new looks and new ways to draw people in. Our team delivers unmatched creativity and expertise to ensure your visuals stand out from the crowd."

**Footer CTA section**
- Slightly lighter dark grey strip across full width.
- Heading: **"Book a complimentary consultation"**
- Button: **"Book consultation"** — black pill, off-white text. Likely links to a Squarespace scheduling block or to the Contact page.

## Page: Portfolio

**Hero**
- Heading: **"Let us help get your ideas off the ground"** — three-line stacked, large.

**Grid of work**
- 2-column grid, mixed video sources (some embedded YouTube, some native Squarespace video uploads).
- Each item has a video player + a caption underneath.

**Visible items so far:**
1. **Lazy River MX Yamaha Invitational** — embedded YouTube, "Yamaha Invitational at Lazy River MX October 2023".
2. **In collaboration with Divinify Productions** — embedded YouTube, "Lake Lanier Boat Show Fall 2023".
3. **In collaboration with Braxton's Antique Mall & Bravo Film House** — native Squarespace video (01:02 long).
4. **Desert Car chase, 2022 - 1 month into flying FPV** — embedded YouTube, "Vegas Desert Car Chase".
5. Native Squarespace video of a runner / track session (01:16 long) — caption cut off in screenshot.

*(Possibly more below the fold — let me know if there are.)*

**Migration notes for this page**
- YouTube embeds will copy over trivially — just `<iframe>` tags.
- Native Squarespace videos will need to be **downloaded from Squarespace** (or we re-host them on YouTube, which is what I'd actually recommend — free CDN, less bandwidth on your host, automatic compression).

## Page: 3D Printing

**This page is the design outlier.** Everything else on the site is dark + cinematic; 3D Printing is colorful and playful. Worth deciding during the redesign whether to bring it back into the brand system or keep it as an intentional contrast.

**Visuals**
- Full-bleed **animated gradient background** — soft fluid blob effect with green, red, magenta, and blue mixing. There's a small pause control bottom-right (⏸), confirming the animation runs by default.
- The whole page floats on top of the gradient. No images, no cards.

**Hero**
- Large heading top-left: **"Bring ideas to life"**
- Centered subtitle: "Print for fun and for function."
- Two pill outline buttons (transparent fill, thin border):
  - **"Submit an idea for pricing"**
  - **"Browse past creations"**
- Helper text below: "Tap or click on one to find out more!"

**Lower hero**
- Bottom-left, oversized: **"One layer at a time"**

**Migration notes**
- Animated gradient: doable in plain CSS with keyframe-animated `radial-gradient` or `conic-gradient`, or with an SVG filter. ~30 lines of CSS, no JS required for a similar effect.
- The pause button is overkill for a static rebuild — I'd drop it unless you want it for accessibility (reducing motion). Better: respect `prefers-reduced-motion` automatically and skip the manual control.
- Outline pill buttons here are different from the filled black pills elsewhere — pick one style for the new site and apply consistently.
- The two CTAs go somewhere — need to know where. Likely "Submit an idea for pricing" → contact form, "Browse past creations" → either a sub-page or scrolls to a gallery on the same page. Let me know what's below the fold.

## Page: About

Returns to the dark + cinematic theme. Personal/individual feel — clearly built around you, not a generic agency.

**Heading**
- **"About me"** — stacked across two lines (large heading).

**Section 1 — "technology enthusiast"** *(lowercase subheading — note the brand voice choice)*
- Para 1: "Based in Atlanta, Georgia, I have been fascinated by technology since my early years. I now specialize in aerial live streaming, cinema-quality production, and capturing events from new angles to captivate viewers."
- Para 2: "With my expertise and passion for technology, I can bring a unique perspective to your projects. Whether it's live-streaming a special event, adding new and never before seen angles to your production, or showcasing your business from above, I have the skills and equipment to deliver outstanding results."
- Photo right: outdoor headshot, smiling, near a tree. **Photo is tilted ~7° clockwise** — distinctive design element worth replicating.

**Section 2 — "certified drone operator"**
- Para 1: "As a certified and insured operation, we bring safety at the top of our priorities. We take every precaution possible to ensure the wellbeing of talent and property while operating."
- Para 2: "My goal is to provide you with visually compelling content that stands out from the rest. I understand the power of storytelling and strive to create captivating narratives through my drone footage. By combining technical expertise with artistic vision, I can help you showcase your brand, capture unforgettable moments, and engage your audience in a whole new way."
- Photo right: studio shot in magenta/pink lighting, wearing a MemeFPV-branded hoodie, holding controller. Also tilted.

**Design notes**
- **Tilted photo treatment** is a strong design pattern on this page — both photos are rotated by the same angle. Easy to do in CSS with `transform: rotate(7deg)`.
- **Lowercase subheadings** ("technology enthusiast", "certified drone operator") are a deliberate type choice that contrasts with the title-case page heading. Worth keeping.
- The two photos sit on the right while text flows on the left — straightforward two-column layout.

**Copy notes (worth tightening during the rebuild)**
- The voice slips between "I" and "we" within the same paragraph. Pick one — since this is clearly a one-person shop, I'd lean **all "I"** unless you actually have collaborators. It reads more honest and personal.
- A few of the second-section sentences ("strive to create captivating narratives," "engage your audience in a whole new way") read like AI/marketing filler. We can replace with one or two specifics — actual gear, actual certifications, actual locations flown — when we rebuild.

## Page: Contact

Two-column layout — info left, form right. Same dark theme.

**Heading**
- **"Contact us!"**

**Left column — info**
- Intro: "Do you have an idea for a project, or just have a question? Fill out the form below and we'll reach out as soon as possible."
- Email shown today: ~~**info@memetech.solutions**~~ → **changing to `info@memefpv.net`** in the new site (Mike's decision, 2026-05-06).
- Phone: **+1 404-465-2446** *(italic-styled)*
- Location: "Based in Kennesaw GA"
- Instagram link: "Follow us on Instagram!" + IG icon

**Right column — contact form**
- Name (First Name required, Last Name required — side-by-side)
- Email (required)
- Message (required, multi-line textarea)
- **Send** button (filled black pill)

**🚩 Things worth flagging**

1. ~~**Two different brand emails on the site.**~~ ✅ **Resolved.** New canonical email is **`info@memefpv.net`** — replace `info@memetech.solutions` everywhere on the new site. Mike will need to make sure that mailbox / forward exists in his Microsoft email setup before launch.
2. **Location is North Georgia *(was Kennesaw, GA on the live site — Mike updated to "North Georgia" 2026-05-06)*** — not "Atlanta" proper (though Kennesaw is in the Atlanta metro). The homepage and search snippets describe it as Atlanta-based, which is reasonable shorthand but worth being consistent about.
3. **Public phone number** is on the live site. Up to you whether to keep it on the new site or move to form-only.

**Migration plan for the form (decided 2026-05-06)**
- Hosting is **GitHub Pages** — does not process forms server-side.
- Contact form will be a **Microsoft Form**, **linked** (not embedded) from the Contact page.
- The new Contact page replaces the inline form with a clean "Get in touch" button → opens the MS Form in a new tab.
- Microsoft fits Mike's existing email setup; embedded forms would clash with the dark theme.

## Page: Store

**Decision (2026-05-06): Dropping the Store from the new site.** Mike confirmed.

For reference: the existing store had a single product — "Dummy13 Action Figure Build Kit" from $20.00. Dark theme, single product card, otherwise empty.

**Implications**
- New site nav shrinks from 8 items to 6: Home, Services, Portfolio, 3D Printing, About, Contact. Cleaner.
- No `Cart (0)` indicator needed.
- No e-commerce platform / Snipcart / Stripe integration to worry about — big simplification.
- If Mike ever wants to sell again later, the simplest add later would be Stripe Payment Links pointing at one-off products from the 3D Printing page, no full shop required.

---

## Summary — what carries over to the new site

**Brand pillars (must keep)**
- Dark, cinematic theme (near-black background, warm off-white text).
- **Archivo italic 700** as the brand wordmark font.
- Logo with **spinning propeller** in both header and footer.
- Italicized connector words in headings used **selectively** — works on the Services hero ("Precise *and* Accurate") but doesn't fit every heading. Don't apply by default; pick spots where it adds emphasis.
- Lowercase subheadings on the About page ("technology enthusiast").
- Tilted photo treatment on About.
- Squircle/rounded-square image masks on Services.
- Black pill CTA buttons.

**Pages (final list — 6 total)**
Home → Services → Portfolio → 3D Printing → About → Contact

**Resolved questions**
- ✅ Tech stack: plain HTML/CSS/JS, no framework.
- ✅ Hosting: TBD — leaning Cloudflare Pages.
- ✅ Email on the new site: `info@memefpv.net` (replacing `info@memetech.solutions`).
- ✅ Store: dropped.
- ✅ Spinning propeller: required, hub is the dot in the middle.

**Open questions to resolve before build**
1. ~~3D Printing CTAs~~ ✅ Page is now a **gallery of things Mike has built** — no "submit idea" / "pricing" pitch. Just a portfolio.
2. ~~Phone number on Contact page~~ ✅ **Removed** in the new site.
3. ~~Native videos on Portfolio~~ ✅ **Upload to YouTube and embed.** Same approach for the homepage hero video.
4. **Voice on About** — clean up "I" vs "we" inconsistency. Personal-portfolio rebrand makes "I" the obvious choice everywhere.
5. **"What I Do" page content** — needs to be rewritten in personal/portfolio voice rather than agency sales pitch. We'll draft together.
6. **"Other Projects" page** — what goes here at launch? Could be empty placeholder, could have something. Open to your input.
7. **Confirm the propeller animation behavior** — full SVG path inspection happens at build time.

---

## Initial migration notes (from homepage alone)

- Design is **dark + cinematic + video-forward**. Easy to replicate in plain HTML/CSS — the heavy lifting is the video assets, not the code.
- Hero video and section background image will need to be **downloaded from Squarespace** before cutover.
- The accordion-style services list (`+` toggles) is straightforward in vanilla JS — ~20 lines of code.
- Logo files (black + white versions) need to be exported as SVG or high-res PNG.
- **Store is the wrinkle.** Plain HTML/CSS/JS can't run a real shop. Options when we get there:
  1. Drop the store entirely if it's not making money.
  2. Replace with a "Buy on [Etsy / Big Cartel / Shopify Lite / Stripe Payment Links]" approach.
  3. Use a static-friendly cart like Snipcart or Stripe Payment Links embedded into a static page.
- Instagram is the only social link — keep that.
- The site is **single-language, US**, no blog, no booking system in evidence so far. That keeps the rebuild small.
