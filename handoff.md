# memefpv.net Migration — Handoff

Quick context dump so a fresh chat can pick up where we left off.

## The project
Mike (beginner web dev) is migrating **memefpv.net** off Squarespace to a self-coded
**plain HTML/CSS/JS** site, hosted on **GitHub Pages**.

## Direction change (2026-08-30)

Mike is **moving on from flying drones as his main hobby**. Not selling the drones, but he doesn't fly much. The site was rebuilt around this:

- Drone work becomes **the archive** — past projects still shown, still available for the right shoot, but no longer the headline.
- The through-line is now **building electronics**: FPV was the entry point, and the same skills carry into RC cars, 3D printing and the homelab.
- Still **a business, wider scope**. Three things for hire: **3D printing & prototyping**, **homelab & self-hosting setup**, and **FPV/aerial video**.
- Nav: Home · About · What I Do ▾ (Drone Work · 3D Printing · RC & Builds · Homelab & Code) · Contact
- `other-projects.html` was replaced by `rc-builds.html` and `homelab.html`.
- **Logo corrected:** the wordmark is the full **MEMEFPV** (MEME off-white, FPV red) with the propeller sitting *over* the V — it does not replace the V. An earlier build dropped the V; that was wrong.
- Part 107 / insured credentials stay, combined into a single item in the creds strip so it
  doesn't read as a drone-pilot badge on every page.

**Two logo lockups (2026-09-09).** Mike asked for the MemeFPV mark to belong to Drone Work
and a more universal mark everywhere else:
- **MEME WORKS** (`MEME` off-white + `WORKS` red, Archivo italic 700, no propeller) — the site
  mark, on all pages except Drone Work. `og:site_name` is "Meme Works" and page titles read
  "… — Meme Works".
- **MEMEFPV + spinning propeller** — `drone-work.html` header and footer only. That page's
  `<body class="page-fpv">` is the CSS hook, its title stays "Drone Work — MemeFPV", and it
  gets its own social card `assets/og-drone.jpg`.
- The **favicon stays the propeller** on every page (Mike's call — it's the domain's icon and
  the only thing legible at 16px).
- `.site-header` has a fixed `min-height` so the nav doesn't shift when moving between marks.
- The domain is unchanged: memefpv.net.

**⚠️ Copy rule (2026-08-30, explicit):** **Never write anywhere that Mike flies less, has
stepped back, or that drone work is in the past.** No "these days", "I fly less than I used
to", "still available for the right shoot", "the archive". Everything drone-related stays in
confident present tense; the de-emphasis is done entirely by **placement and proportion** —
drones are one of four areas on the homepage, aerial is the last of the three services, and
Drone Work is the only page where they lead. FPV as the *origin of the skills* is welcome
framing; retreat language is not.

**Also removed:** the "Available for travel" claim — Mike never confirmed it. Add it back only
if he says so.

## Build state
All eight pages plus a 404 are built, styled and consistent. The site is content-ready —
what's left is Mike's own photos, video embeds, and the DNS cutover.

**Done:**
- **Animated logo shipped.** `assets/prop.svg` is the three-blade propeller extracted from
  `MemeFPV Logo.svg`, re-centred on its hub so it spins true, with the CSS animation and the
  `prefers-reduced-motion` guard inside the SVG file. The header/footer logo is HTML text —
  full **MEMEFPV** in Archivo italic 700, `MEME` off-white and `FPV` in the brand red — with
  the propeller overlapping the **V**. Header padding carries extra top space so the top blade
  isn't clipped. Same lockup in header and footer on every page.
- **Copy written** in the professional first-person voice: actively taking paid work,
  "priced for quality", North Georgia. Rewritten 2026-08-30 around building rather than
  flying — see the direction change above.
- **Mobile nav** is now a hamburger drawer (`site.js`) instead of a stacked column.
- **Accent colour introduced** — the brand red `#e8442a` from the logo file, used sparingly
  (eyebrow labels, propeller-adjacent brand type, hover states, credential dots).
- **Launch files added:** `CNAME`, `404.html`, `robots.txt`, `sitemap.xml`, Open Graph +
  Twitter card meta on every page, `assets/favicon.svg`, `assets/apple-touch-icon.png`,
  `assets/og-default.jpg` (a rendered social share card).
- **Media fixed.** `assets/homepage.gif` was **52 MB** — it would have made the page unusable
  on mobile data. Re-encoded to `assets/hero.mp4` (**1.1 MB**) with `assets/hero-poster.jpg`.
  The old GIF is still in the repo and can be deleted.
- **Portrait wired in.** The 1.5 MB studio photo is now `assets/portrait.jpg` (73 KB, cropped
  4:5) on the About page with the tilt treatment.
- Accessibility: skip link, visible focus rings, real `aria-current`, labelled menu button.

## Folder layout
- **Cloned repo (the actual site):** `~/Documents/miikememe/website/`
- **Planning workspace:** `~/Documents/Claude/Projects/Personal Website/Personal Website Update/`
  (older copies — the repo is the source of truth)

## Workflow rules
- Mike uses **GitHub Desktop** for all git operations.
- Claude writes/edits files only — **never run git in the sandbox** (creates lock files that
  can't be removed and blocks GitHub Desktop).
- The repo files live in iCloud Drive and are often stored as **cloud-only placeholders**.
  Reading them through the device shell fails with "Resource deadlock avoided" until they're
  hydrated — stage them once (`device_stage_files`) and they read fine afterwards.

## Decisions locked in
- Plain HTML/CSS/JS, no framework, no build step
- GitHub Pages, repo `miikememe/website`, domain memefpv.net
- Email on site: `info@memefpv.net`
- Contact form: Microsoft Forms, **linked** not embedded
- Nav (4 top-level): Home, About, What I Do ▾ (Drone Work, 3D Prints, Other Projects), Contact
- Brand: dark theme `#181818` / `#ebe2d2`, accent red `#e8442a`, Archivo italic 700 wordmark,
  spinning propeller as the V, italic connector words used selectively, tilted About photos,
  squircle masks on service cards
- Location language: "North Georgia"
- Portfolio videos: re-upload to YouTube and embed

## Open questions / next steps
1. **Mike to review the copy** — written to the build-first direction, every word up for edit.
2. **Photos.** Every dashed box names the image it wants and the size. Fifteen slots now —
   the new RC and homelab pages need photos that don't exist yet.
3. **YouTube embeds** on Drone Work (four), plus re-uploading the Braxton's Antique Mall
   video that only exists natively on Squarespace.
4. **Microsoft Form** — publish it and paste the URL into `contact.html` (search `href="#"`).
5. **Second About photo** — the outdoor headshot from the old Squarespace site.
6. **DNS cutover** — unlock the domain at Squarespace, point at GitHub Pages, wait for SSL.
   `CNAME` is already in the repo.
7. **`info@memefpv.net` mailbox** — confirm it exists in Microsoft before launch.
8. Delete the old 52 MB `assets/homepage.gif` — nothing references it, and once committed it
   bloats the git repo permanently. `other-projects.html` is also now unused.

## Memory files (persistent across chats)
- `user_mike.md`, `project_memefpv_migration.md`,
  `feedback_logo_propeller.md`, `feedback_no_git_in_sandbox.md`
