# Atelier Platform — MVP Product Requirements Document

**Owner:** Sneha Chelimilla
**Status:** Draft, pre-build
**Last updated:** 2026-07-03

This PRD defines the **true MVP**: the smallest version of the Atelier product that proves the core hypothesis with real money moving through the platform. It is a deliberate narrowing of `ATELIER_PRODUCT_PRD_V1.md`, which scoped a three-sided platform (booking, collaboration, events). Building all three at once is the biggest risk called out in that doc. This MVP cuts to one flow so we can ship faster and learn faster.

---

## 1. Summary

Atelier MVP is a space booking marketplace for dancers in a single city. An artist searches for a rehearsal or performance space, books it, and pays through the platform. A host lists their space, gets booked, and gets paid. That is the entire product.

Collaborator discovery and event/organizer tools are validated demand (from the waitlist) but are **not** part of MVP. They come after we prove the booking loop works.

## 2. Why This Scope

The riskiest, most valuable thing to learn first is: **will artists actually book space through Atelier, and will hosts actually get filled and paid reliably?** That's the transaction at the center of the business model (commission on bookings). Collaboration and events are real needs, but they don't require payments infrastructure to validate, and they dilute engineering focus if built simultaneously. Cutting them from MVP is a sequencing decision, not a decision to ignore that demand.

## 3. Problem

Dancers waste time coordinating rehearsal and performance space through generic rental sites, personal networks, or DMs, none of which are built for how dancers actually search (by discipline, by hour, by neighborhood) or pay (per session, not per lease). Studios have idle hours they can't easily fill with serious, vetted renters.

## 4. Goal

Prove, in one city, that: 
1. Artists will search, book, and pay for space through Atelier instead of their current workaround.
2. Hosts will list space, accept bookings, and get paid reliably enough to keep listing.
3. There's enough supply and demand to reach basic liquidity (a booking can actually get filled).

## 5. Users

| Segment | Role in MVP |
|---|---|
| **Artist** | Books space. |
| **Space Host** | Lists space, gets booked, gets paid. |

**Organizers are not a user in MVP.** Event posting and ticketing are deferred (see Section 8).

## 6. Scope

### 6.1 Artist
- Sign up / log in (email-based).
- Minimal profile: name, discipline, location.
- Search and filter spaces by location, date/time, price.
- View a listing: photos, rate, availability, cancellation policy.
- Book a specific time slot and pay through the platform.
- View upcoming and past bookings.

### 6.2 Space Host
- Sign up / log in (email-based).
- Create one listing: space type, photos, description, location.
- Set hourly rate and availability calendar.
- Set a cancellation policy from a small set of platform-defined options.
- Confirm or decline incoming booking requests.
- Get paid out to a bank account after a completed booking.
- View upcoming and past bookings.

### 6.3 Platform-wide
- Payments: Atelier processes the booking payment and takes a commission before payout.
- Payout to host bank account after booking completion.
- Email notifications: booking confirmation, booking decline, cancellation, payout sent.
- Founding member discount honored for waitlist members who converted (per landing page commitments) on both commission rate and booking price.

## 7. Core Flow

**Booking:**
Artist searches by location/date → views listing → requests to book a time slot → pays → host confirms or declines → if confirmed, booking is locked and artist is charged → host is paid out after the session.

**Listing:**
Host creates a listing → sets rate, availability, cancellation policy → publishes → receives booking requests → confirms → gets paid.

*(Design decision needed: host-confirmed bookings, as written above, vs. instant-book. Host-confirmed is simpler to build and safer for MVP trust, at the cost of a slower artist experience. Recommend starting host-confirmed and revisiting instant-book post-MVP.)*

## 8. Explicitly Out of Scope for MVP

- Collaborator discovery / artist-to-artist search and messaging
- Event posting, ticketing, and organizer tools
- Reviews and ratings
- Instant-book (auto-confirmed bookings)
- Recurring bookings
- Group/team accounts
- In-app messaging beyond what's needed to confirm a booking
- Native mobile app
- Multi-city support
- Dispute resolution tooling beyond manual support handling
- Insurance verification (hosts self-certify, same as today)

## 9. Requirements

### Functional
- A booking cannot be paid for twice, double-booked into the same slot, or confirmed after the slot is taken.
- Cancellations must follow the host's stated policy and trigger a notification to the other party.
- A host must not be able to receive payout for a booking that hasn't completed.

### Non-functional
- Single launch city, hardcoded.
- Payments handled through a processor with built-in marketplace/split-payment support (e.g., Stripe Connect) rather than custom-built payment logic.
- Responsive web only, no native app.

## 10. Success Metrics

| Metric | Why it matters |
|---|---|
| Completed bookings | Direct proof the core loop works |
| Number of active listings in launch city | Minimum supply needed for liquidity |
| Search-to-booking conversion rate | Signals whether listings/search meet real demand |
| Repeat bookings per artist | Signals real ongoing use, not one-time trial |
| Host payout turnaround time | Trust driver for the supply side; slow payouts kill retention |
| Host listing retention (host still active after first booking) | Signals hosts see MVP as worth staying on |

*(Set numeric targets once launch city and waitlist size are confirmed.)*

## 11. Assumptions and Risks

- **Assumption:** Space booking alone, without collaboration or events, is enough to keep artists coming back. Risk: if artists only book space rarely, the product may feel thin without the community layer. Mitigation: track repeat booking rate closely; if it's weak, that's a signal to accelerate collaboration features.
- **Assumption:** The waitlist has enough host supply concentrated in one city to reach liquidity. Risk: if hosts are spread thin across cities, booking may fail due to no availability. Mitigation: check waitlist city distribution before locking launch city.
- **Risk:** Payments/payouts remain the highest-liability component even at MVP scope. Using a processor with native marketplace support is a hard requirement, not a nice-to-have.

## 12. Open Questions

- What is the launch city, based on where the waitlist is most concentrated on both the artist and host side?
- Host-confirmed or instant-book at MVP?
- What commission rate applies at MVP launch, and does it match what founding hosts were already promised on the landing page?
- What is the minimum number of active listings we want live before opening broad artist access, so the marketplace doesn't feel empty on day one?

## 13. What Comes After MVP

Once the booking loop is proven (completed bookings, repeat usage, reliable host payouts), the next additions, in order:
1. **Collaborator discovery** (artist profiles, search, direct messaging) — this was the second most-validated need from the waitlist and doesn't require new payments infrastructure.
2. **Events and organizer tools** (event posting, registration, ticketing) — highest complexity of the three because it introduces a second payment/commission structure and a new dashboard.
3. **Reviews, instant-book, and other trust/convenience features** once there's enough transaction volume for them to be meaningful.

This is the same three-sided platform scoped in `ATELIER_PRODUCT_PRD_V1.md`; MVP is step one toward it, not a replacement for it.
