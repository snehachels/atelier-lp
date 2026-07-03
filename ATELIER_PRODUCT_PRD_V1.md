# Atelier Platform — V1 Product Requirements Document

**Owner:** Sneha Chelimilla
**Status:** Draft, pre-build
**Last updated:** 2026-07-03

This PRD covers the **actual Atelier product** (the booking, collaboration, and events platform), not the marketing/waitlist landing page (see `ATELIER_PRD.md` for that).

---

## 1. Summary

Atelier is a creative home for dancers: a platform where artists find rehearsal/performance space and collaborators, space owners fill idle studio hours, and organizers promote events to an engaged dance community. V1 is the minimum version of this three-sided platform that lets a real booking, a real collaboration, and a real event registration happen end to end, in one city, without manual workarounds.

## 2. Problem

Dancers currently coordinate space, collaborators, and events through fragmented channels: group chats, personal networks, generic space-rental sites not built for artists, and word of mouth for events. This costs time, loses opportunities, and gives studios no reliable way to fill off-peak hours. There is no single home built around the artist's workflow.

## 3. Users and Core Jobs

| Segment | Core job to be done |
|---|---|
| **Artist** | Find and book a rehearsal/performance space quickly. Find collaborators who fit their discipline and availability. |
| **Space Host** | List a space, set rates and availability, get booked by serious dancers, get paid without chasing invoices. |
| **Organizer** | Post an event, get it in front of the right artists, manage registrations in one place. |

## 4. Goals for V1

1. Enable a complete, unassisted booking: artist finds a space, books it, host gets paid.
2. Enable artist-to-artist discovery and contact (profile, search, direct message) so collaboration doesn't require an outside channel.
3. Enable a complete event flow: organizer posts an event, artists discover and register, organizer manages attendees.
4. Prove the commission model works end to end (money moves through Atelier, not around it).
5. Launch in a single city to validate liquidity (enough supply and demand to make the marketplace actually useful) before expanding.

### Non-goals for V1
- No recommendation/matching algorithm — search and browse only.
- No native mobile app — responsive web only.
- No in-app reviews/ratings system — defer to V1.1 once there's enough transaction volume to make ratings meaningful.
- No multi-city support — hardcode to one launch city.
- No insurance underwriting — hosts self-certify their own coverage, same as today.
- No built-in messaging beyond simple text (no video calls, no file sharing) at V1.

## 5. V1 Scope by Segment

### 5.1 Artists
- Create a profile: name, discipline(s), photo, bio, what they're looking for (space / collaborators / both).
- Browse and search spaces by location, date/time, price, space type.
- View a space listing: photos, rate (hourly/half-day/full-day), availability calendar, cancellation policy, host info.
- Book a space and pay through the platform.
- Browse and search other artists by discipline, location, and availability.
- Message another artist directly (basic text messaging).

### 5.2 Space Hosts
- Create a listing: space type, photos, description, location.
- Set pricing (hourly, half-day, full-day) and availability calendar.
- Set a cancellation policy from a small set of platform-defined options.
- Receive and confirm/decline booking requests (or accept auto-confirmed bookings, TBD in design).
- Get paid out to a bank account after a completed booking.
- View upcoming and past bookings in a simple dashboard.

### 5.3 Organizers
- Create an event listing: type (workshop, performance, showcase, competition, reading, etc.), date/time, location, description, capacity, price (free or paid).
- Event appears in a searchable events feed to artists.
- Artists register/purchase a ticket through the platform.
- Organizer dashboard: view registrant list, track attendance, message registrants.
- Handle cancellation/reschedule with automatic notification to registrants.

### 5.4 Platform-wide (all segments)
- Account creation and login (email-based to start).
- Payments: Atelier processes booking/ticket payments and takes a commission before payout to host/organizer.
- Payout to host/organizer bank account, target within 24-48 hours of a completed booking or event.
- Notifications: email confirmation for booking, registration, cancellation, and payout events.
- Founding member benefits honored: discounted commission rates and booking discounts for early waitlist members who converted from the landing page.

## 6. Out of Scope for V1 (explicitly deferred)

- Reviews and ratings
- In-app video/voice
- Recurring/subscription bookings (e.g., "every Tuesday at 6pm")
- Group/team accounts (e.g., a dance company managing multiple members under one account)
- Dispute resolution tooling beyond manual support handling
- Advanced discovery (recommendations, saved searches, alerts)
- Native mobile apps
- Multi-city/multi-region support

## 7. Key Flows

**Artist books a space:**
Search → filter by date/location/price → view listing → select time slot → pay → receive confirmation → host receives booking notification.

**Artist finds a collaborator:**
Search/browse artists by discipline and location → view profile → send direct message.

**Host lists a space:**
Create listing → set rates and availability → publish → receive booking request → confirm → get paid after booking completes.

**Organizer runs an event:**
Create event → publish to feed → artists discover and register/pay → organizer manages attendee list → event happens → organizer can message attendees before/after.

## 8. Monetization

- Commission taken on space bookings (rate TBD by finance/leadership; founding hosts get a locked-in discount per landing page commitments already made).
- Commission taken on paid event registrations/tickets (same principle as above; founding organizers get a temporary discounted rate).
- Listing spaces and posting events remain free, consistent with what the landing pages already promise.

## 9. Success Metrics for V1

| Metric | Why it matters |
|---|---|
| Completed bookings (space) | Core proof the transaction loop works |
| Completed event registrations | Core proof the events loop works |
| Artist-to-artist messages sent | Proof collaboration discovery is being used |
| Supply liquidity: number of active space listings in launch city | Marketplace needs enough supply to be useful |
| Demand liquidity: repeat bookings per artist | Signals real, ongoing usage vs. one-time trial |
| GMV (gross booking + ticket value processed) | Overall marketplace health |
| Host payout turnaround time | Trust and retention driver for supply side |

*(Specific numeric targets should be set once the founding-member waitlist size and launch city are confirmed.)*

## 10. Assumptions and Risks

- **Assumption:** The founding-member waitlist from the marketing site converts into real launch-day supply and demand. Risk: interest expressed via email doesn't always convert to actual usage; plan to interview waitlist members before launch to pressure-test this.
- **Assumption:** One city has enough supply and demand to reach liquidity. Risk: if either side is too thin, the marketplace feels empty and both sides churn. Mitigation: consider manually recruiting a critical mass of hosts before opening broad artist access.
- **Risk:** Payments and payouts are the highest-complexity, highest-liability part of V1. This likely means integrating a payments processor with built-in marketplace/split-payment support rather than building payment logic in-house.
- **Risk:** Combining three distinct flows (booking, collaboration, events) in one V1 is a lot of surface area. Worth revisiting whether to sequence (e.g., space booking first, events second) rather than launching all three simultaneously.

## 11. Open Questions

- Do we launch all three flows (space booking, collaborator discovery, events) simultaneously, or sequence them to reduce V1 build risk?
- What is the launch city?
- Are bookings host-confirmed or auto-confirmed by default?
- What payments processor are we using, and does it support split payments/marketplace payouts natively (e.g., Stripe Connect)?
- What exact commission rates apply at launch, and what are the locked-in founding member rates already implicitly promised on the landing pages?
- What is the support model for disputes (bad booking, no-show, event cancellation) at V1, given there's no formal dispute tooling yet?

## 12. Next Steps

1. Resolve open questions above with leadership/finance, especially payments processor and commission rates.
2. Decide on sequencing: all three flows at once vs. phased rollout.
3. Confirm launch city based on founding-member waitlist concentration.
4. Scope technical design for payments/payouts, since this is the highest-risk component.
5. Define concrete numeric success targets once city and waitlist size are known.
