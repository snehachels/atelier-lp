# Atelier Landing Page — Product Requirements Document

**Owner:** Sneha Chelimilla
**Status:** Live (pre-launch phase)
**Last updated:** 2026-07-03

---

## 1. Summary

Atelier is a creative community platform connecting dancers with rehearsal/performance spaces, collaborators, and event organizers. Before the full platform launches, we need a marketing site that validates demand, builds a waitlist, and starts positioning Atelier as "a creative home for dancers," not a transactional booking marketplace.

This PRD covers the **pre-launch marketing site** (the current repo), not the eventual marketplace product itself.

## 2. Problem

Dancers currently rely on fragmented, informal channels (group chats, personal networks, generic space-rental sites) to find rehearsal space, collaborators, and events. Studio owners struggle to fill off-peak hours. There is no single, artist-first home for this community. We need to prove there is real demand before building the full product, and start capturing early adopters across all three sides of the market: artists, space hosts, and event organizers.

## 3. Goals

1. Validate demand for Atelier across three audiences: artists, space hosts, event organizers.
2. Build a founding-member waitlist (email capture) ahead of platform launch.
3. Establish brand tone and visual identity ("creative home," not "marketplace") ahead of any paid marketing.
4. Give each audience a tailored landing experience so messaging resonates with their specific need.

### Success Metrics

| Metric | Target |
|---|---|
| Email signups (total, all segments) | Track weekly; set baseline in first 2 weeks live |
| Signup conversion rate (visitors → email) | 5%+ |
| Segment split (artist vs. host vs. organizer) | Directional read on where demand is strongest |
| Bounce rate | Under 60% |

*(Exact targets should be revisited once we have 2-3 weeks of real traffic data.)*

## 4. Target Users

- **Artists/Dancers** — looking for rehearsal space, collaborators, and a creative community.
- **Hosts (Studios/Spaces)** — have underutilized space and want to fill it with serious dancers.
- **Organizers** — run events, showcases, or classes and want to promote them to the dance community.

Each segment gets its own landing page (`/artists`, `/spaces` or `/studios`, `/organizers`) plus a unified entry point (`/`) that routes visitors to the right one.

## 5. Scope

### In scope
- Single-page marketing site per audience segment (static HTML, no backend/app logic).
- Email capture forms per segment, feeding into Google Forms for lead collection.
- FAQ sections addressing common objections per audience.
- Founding-member incentive messaging (e.g., lifetime commission discount for hosts, early product input for artists).
- Responsive layout (desktop, tablet, mobile).
- Brand-consistent visual design per the Atelier Brand Design System.

### Out of scope (for this phase)
- Actual booking, payment, or messaging functionality — this is a lead-gen site only.
- User accounts / login.
- CMS or backend — content changes are made directly in HTML.
- Paid acquisition / ad campaigns (separate workstream, see 7-Day Quick Start doc).

## 6. Key Features (current state)

1. **Segmented landing pages** — `index.html` (unified), `artists.html`, `spaces.html`, `studios.html`, `organizers.html`, each with tailored hero copy and CTA.
2. **Email signup forms** — per-segment forms wired to Google Forms, with a success/confirmation state on submit.
3. **FAQ accordions** — answer top questions per segment (cost, commission, product input, etc.).
4. **Founding member incentives** — messaging that early signups get benefits (e.g., discounted commission for hosts, product input for artists) to drive urgency.
5. **Brand system** — Charcoal, Rose Gold, Cream palette; Montserrat + Crimson Text typography, per the Brand Design System doc.

## 7. Requirements

### Functional
- Every page must have a working, validated email capture form.
- Form submission must show clear confirmation (no dead-end or silent failure).
- Navigation between segment pages must be discoverable from the homepage.
- All copy must reflect approved brand voice (see Brand Guidelines: no "marketplace," no generic startup language).

### Non-functional
- Page load should be fast (single static HTML file, no heavy JS frameworks).
- Fully responsive down to mobile (375px width).
- No build step required; deployable as static HTML via Vercel.

## 8. Open Questions

- What is the actual target number of founding members before we consider the waitlist phase "validated" enough to build the full product?
- Are we running any paid traffic to this site, or is growth organic/referral only for now?
- Do we need basic analytics (e.g., Google Analytics) instrumented before or after initial launch traffic?
- Should host/organizer segments get a lightweight qualification question (e.g., studio size, event type) to improve lead quality?

## 9. Risks

- **Messaging drift:** Easy to slip into generic "marketplace" language under deadline pressure; undermines brand differentiation. Mitigation: always check Brand Guidelines before copy changes.
- **Low signal from waitlist alone:** Email signups don't guarantee willingness to pay or actually use the platform. Consider a lightweight follow-up (interview, survey) with early signups.
- **Fragmented pages drift out of sync:** With five separate HTML files, a design or copy update to one section (e.g., FAQ style) can be missed on others. Worth a periodic consistency check.

## 10. Next Steps

1. Confirm success metrics/targets with the team.
2. Instrument analytics if not already live.
3. Run the current site past 2-3 weeks of traffic, then review segment performance.
4. Decide go/no-go on building full platform based on waitlist size and quality of interest.
