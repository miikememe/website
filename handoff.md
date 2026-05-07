# memefpv.net Migration — Handoff

Quick context dump so a fresh chat can pick up where we left off.

## The project
Mike (beginner web dev) is migrating **memefpv.net** off Squarespace to a self-coded **plain HTML/CSS/JS** site, hosted on **GitHub Pages**, with the design rebranded from "FPV pilot service for hire" to a **personal portfolio of projects + contact me** site.

## Current state (2026-05-07)
- v0.1 of the homepage is live at `https://miikememe.github.io/website/`
- It has a header (logo + nav), hero section, footer (logo + Instagram). All other nav links 404 — only `index.html` exists so far.
- We're iterating on the **logo** — placement, sizing, and propeller blade design. Last attempt made it bigger but Mike says the propeller "is a bit worse." Open question.

## Folder layout
- **Cloned repo (the actual site):** `~/Documents/miikememe/website/`
  - `.git/`, `.gitignore`, `README.md`, `index.html`, `style.css`, `assets/bird.svg`
  - This is what gets pushed to GitHub and deployed.
- **Planning workspace:** `/Users/mikememe/Documents/Claude/Projects/Personal Website/Personal Website Update/`
  - `site-audit.md` — comprehensive audit of the current Squarespace site
  - `migration-checklist.md` — phased checklist
  - `logo high res.svg`, `logo propellor .svg` — original brand assets
  - Working copies of `index.html`, `style.css`, `assets/bird.svg` (same as the cloned repo for reference/diffs)

## Workflow rules
- Mike uses **GitHub Desktop** for all git operations (commit, push). He has it installed.
- Claude writes/edits files only — **never run git in the bash sandbox** (creates lock files we can't delete and blocks GitHub Desktop).
- When Claude needs a diff, use bash `diff` between the cloned repo and the planning workspace, not `git diff`.

## Decisions locked in
- **Tech stack:** plain HTML/CSS/JS, no framework, no build step
- **Host:** GitHub Pages, repo `miikememe/website`
- **Domain:** keep memefpv.net, point DNS at GitHub Pages (not done yet)
- **Email on site:** `info@memefpv.net` (replaces `info@memetech.solutions`); Mike uses Microsoft for email
- **Contact form:** Microsoft Forms, **linked** (not embedded) from Contact page
- **Site map (7 pages):** Home, About, What I Do, Drone Work, 3D Prints, Other Projects, Contact
- **Brand:**
  - Dark cinematic theme (bg `#181818`, text `#ebe2d2`)
  - **Archivo italic 700** for the wordmark (free Google Font)
  - Logo's **propeller must spin** in both header and footer (CSS animation)
  - Hub of propeller is the small dot in the middle of the original `logo propellor .svg`
  - Italic connector words used **selectively**, not on every heading
  - Tilted About photos, squircle Services image masks (for later pages)
- **Removed:** Store, phone number, agency-pitch voice (rebrand to first-person portfolio)
- **Location language:** "North Georgia" (not Kennesaw, GA)
- **Portfolio videos:** re-upload native Squarespace videos to YouTube and embed

## Open questions / next steps
1. **Logo propeller redesign.** Current design is two crossing ellipses (a `+` that spins). Mike feels it's "a bit worse" at the larger size. Options: (a) fewer/different blade shape (simple 2-blade), (b) actual drone-style 3-blade swept blades, (c) keep but tune size/speed.
2. **Logo placement at the V.** Currently overlapping with negative margin; Mike said "closer but not at the top of the logo" before the size bump.
3. **Hero text overflow on mobile** — added `overflow-wrap` and reduced clamp; verify it looks right on phone.
4. **Build remaining 6 pages.** About, What I Do, Drone Work, 3D Prints, Other Projects, Contact.
5. **DNS cutover** when site is ready: unlock domain at Squarespace, point at GitHub Pages, add `CNAME` file in repo, wait for SSL.
6. **`info@memefpv.net` mailbox** — confirm exists in Mike's Microsoft setup before launch.

## Tasks (completed / open)
Done: site audit, GitHub repo created, Pages enabled, scaffolding pushed, git workflow set up.
In progress: building site (homepage iteration).
Pending: Microsoft Form for contact, DNS cutover, remaining 6 pages.

## Memory files (persistent across chats)
- `user_mike.md` — Mike's profile (beginner, North Georgia, owns memefpv.net)
- `project_memefpv_migration.md` — all project decisions
- `feedback_logo_propeller.md` — propeller spin requirement
- `feedback_no_git_in_sandbox.md` — workflow rule about not running git in sandbox
