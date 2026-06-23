# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

**Atelier** is a creative community platform for dancers. This directory contains the **marketing landing page** — a single-file HTML application designed to capture emails, explain the value proposition, and drive awareness pre-launch.

**Purpose:** Marketing site for a marketplace connecting dancers with studio spaces and collaborators  
**Tech:** Static HTML + inline CSS + vanilla JS (no build system)  
**Deployment:** Vercel (auto-deploys from GitHub)  
**Current state:** Landing page built and ready to deploy; old "DanceHub" HTML (LP.html) can be deleted

---

## Key Files & What They Are

- **index.html** — Current, production-ready landing page with warm palette applied (Rust, Sage, Warm Dark, Gray, Cream). Ready to deploy to Vercel.
- **ATELIER_Brand_Design_System.md** — **Complete visual identity guide.** Read before making any design changes. Contains color palette with hex codes, typography hierarchy, logo strategy, spacing rules, imagery guidelines, section-by-section landing page guide.
- **ATELIER_Brand_Guidelines.md** — Brand positioning, voice, messaging, storytelling. Reference for copy and messaging direction.
- **ATELIER_7_Day_Quick_Start.md** — Launch strategy (domain setup, deployment, social, interviews). Reference for business/marketing tasks.
- **ATELIER_Landing_Page.md** — Old HTML template (reference only, replaced by index.html)
- **LP.html** — Outdated DanceHub version. Can be deleted.

---

## Common Tasks

### Editing Landing Page Copy

The HTML in **ATELIER_Landing_Page.md** is fully self-contained (inline CSS + scripts). To edit:

1. Copy the HTML from ATELIER_Landing_Page.md
2. Save as `index.html` 
3. Edit text directly (search for sections: hero, features, why-atelier, faq, etc.)
4. Push to GitHub; Vercel auto-deploys
5. **Always check brand guidelines** before changing copy — ensure messaging aligns with "creative home" positioning (not "marketplace," not generic startup speak)

### Updating Colors or Typography

Colors and fonts are defined in the `<style>` block. Current palette:
- **Charcoal:** #2C2C2C (primary dark)
- **Rose Gold:** #D4A5A5 (accent/creative)
- **Cream:** #F5F3F0 (background)

Fonts: **Montserrat** (headlines) + **Crimson Text** (body). Loaded from Google Fonts.

Do NOT change without consulting ATELIER_Brand_Guidelines.md.

### Email Signup Integration

Currently, the form uses a simple `alert()` on submit. For production, replace with:
- **Mailchimp:** Get embed code from mailchimp.com, replace the form HTML
- **Zapier:** Route submissions to Google Sheets for manual tracking

See ATELIER_7_Day_Quick_Start.md (Day 2, Task 4) for setup details.

### Adding Real Images

The "Why Atelier" section has a placeholder: `[A space for your creative vision]`. Replace with real dancer photos. Per guidelines, use:
- Real dancers, not stock photos
- Candid/rehearsal shots (not posed)
- Studio lighting
- Diverse bodies and dance styles

---

## Deployment

**Vercel (automated):**
1. Save HTML as `index.html` in a GitHub repo
2. Push to GitHub
3. Link repo to Vercel project at vercel.com
4. Vercel auto-deploys on every push
5. Add custom domain (atelierdance.com) in Vercel dashboard

**Testing locally:**
Open `index.html` in any browser (no build step needed).

---

## Brand & Messaging

Before editing anything, understand Atelier's positioning:

- **NOT** a transactional marketplace
- **YES** a creative *home* for the dance community
- **Tone:** Respectful, professional, insider language (speak like a dancer, not a startup)
- **Tagline:** "Where dancers create together"

Reference: ATELIER_Brand_Guidelines.md for full voice, tone, visual style, and messaging pillars. Copy should validate the problem ("We talked to dancers...") and emphasize community over features.

---

## Responsive Design

The page includes mobile breakpoints at 768px. Test on:
- Desktop (1200px+)
- Tablet (768-1024px)
- Mobile (under 768px)

All sections collapse to single-column layouts on mobile. Navigation hides (display: none).

---

## Analytics & Tracking

Add Google Analytics (`google.com/analytics`) to the `<head>` for visitor tracking. Instructions in ATELIER_7_Day_Quick_Start.md (Day 3, Task 1).

---

## Next Steps (If Deploying)

1. Save ATELIER_Landing_Page.md HTML as `index.html`
2. Create GitHub repo (`git init`, add index.html, push)
3. Deploy to Vercel (connect GitHub repo, auto-deploys)
4. Point atelierdance.com domain to Vercel
5. Test email signup (integrate Mailchimp or Zapier)
6. Monitor analytics + email signups

See ATELIER_7_Day_Quick_Start.md for detailed 7-day launch plan.
