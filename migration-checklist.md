# memefpv.net Migration Checklist

Goal: Move memefpv.net off Squarespace to a self-coded static site (plain HTML/CSS/JS) on a simple host. Keep the design similar to today but a bit fresher.

The list is intentionally broken into small concrete steps. We'll work through it together — when we get to a step, I'll explain what to do.

---

## Phase 1 — Audit & decisions

- [x] Walk through every page on the current memefpv.net and list them
- [x] Identify any forms, embeds, or special features
- [x] Decide what to drop (Store) and what to keep (everything else)
- [x] Confirm new contact email is `info@memefpv.net`
- [ ] Pick a hosting platform — leaning Cloudflare Pages, decision pending
- [ ] Confirm 3D Printing page targets ("Submit idea" / "Browse creations")
- [ ] Decide on phone-on-contact-page question
- [ ] Email migration plan (Microsoft email — already handled per Mike, just need `info@memefpv.net` mailbox/forward set up before launch)
- See full audit: `site-audit.md`

## Phase 2 — Account & tool setup

- [ ] Install a code editor (VS Code is free and beginner-friendly)
- [ ] Create a free GitHub account (for storing your code and auto-deploys)
- [ ] Create an account on the chosen host (e.g. Cloudflare)
- [ ] Set up a project folder on your computer for the site

## Phase 3 — Pull content out of Squarespace

- [ ] Save all page text into plain text/markdown files
- [ ] Download every image and other asset (logos, photos, videos)
- [ ] Note all the current page URLs (so we can match them or set up redirects)
- [ ] Export any contact list / mailing list if you have one
- [ ] Note any custom fonts or colors used today

## Phase 4 — Design refresh

- [ ] Decide on a small color palette (2–4 colors)
- [ ] Choose 1–2 web fonts (Google Fonts is free and easy)
- [ ] Sketch the new homepage layout (rough — hand drawing or in a doc)
- [ ] Decide page structure: which pages, what's in the nav menu
- [ ] Pick a logo treatment (keep current logo or refresh)

## Phase 5 — Build the site

- [x] Create the folder structure (`index.html`, `style.css`, `assets/`, etc.)
- [x] Build a base HTML template (header, footer, nav)
- [x] Build the homepage
- [x] Build each additional page
  - [x] About (`about.html`)
  - [x] What I Do (`what-i-do.html`)
  - [x] Drone Work (`drone-work.html`)
  - [x] 3D Prints (`3d-prints.html`)
  - [x] Other Projects (`other-projects.html`)
  - [x] Contact (`contact.html`)
- [x] Style everything with one shared CSS file (`style.css`)
- [ ] Make sure it looks good on mobile (responsive layout) — homepage tuned, verify the 6 new pages on a phone
- [x] Add favicon, page titles, and SEO meta tags (bird favicon + title + description on every page)
- [ ] Add a contact method — Contact page is built with `mailto:info@memefpv.net`; still need to drop the published Microsoft Forms URL into the "Open the contact form" button (currently `#`)

## Phase 6 — Test locally

- [ ] Open the site in a browser and click every link
- [ ] Check on your phone (resize the browser or use a phone)
- [ ] Verify every image loads
- [ ] Run the site through a free accessibility/perf check (Lighthouse in Chrome)

## Phase 7 — Deploy to the web

- [ ] Push the project to GitHub
- [ ] Connect the host to your GitHub repo
- [ ] Verify the site works at the host's preview URL (e.g. `your-site.pages.dev`)
- [ ] Fix anything that broke between local and production

## Phase 8 — Domain & email cutover

- [ ] Make sure the new site looks right at the preview URL
- [ ] Move DNS for memefpv.net to the new host (or to Cloudflare DNS)
- [ ] Point memefpv.net at the new site
- [ ] Confirm HTTPS / SSL certificate is working
- [ ] Set up MX / forwarding so **mike@memefpv.net** keeps working
- [ ] Send a test email to and from your domain address
- [ ] Set up redirects from old Squarespace URLs (if URL structure changed)

## Phase 9 — Post-launch

- [ ] Monitor the live site for a week (any broken links, missing images)
- [ ] Cancel the Squarespace subscription (only after everything's confirmed working)
- [ ] Set up basic analytics (Cloudflare Web Analytics is free, no cookie banner needed)
- [ ] Save a backup copy of the project locally and to GitHub
- [ ] Write a short note for yourself: "How to update my site" (so future-you knows)

---

## Things we'll figure out together as we go

- Which exact host (I'll recommend after you tell me about email and any forms you need)
- Whether to keep the current logo or refresh it
- What the contact form should do (mailto vs. real form vs. just an email link)
- Any special features (mailing list, blog, store?) that need extra setup
