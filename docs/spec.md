# Pickleball booking app: market research and technical spec

Nov 5, 2026

## Summary

There is room for a club booking platform whose player app beats PlayByPoint on the things Picklr members complain about: calendar integration, self-service, reliability and a cleaner UI.

- **The incumbent is beatable.** The Picklr runs on PlayByPoint, chosen for its branded app. In 2026 its app removed self-service features, still lacks working calendar integration for members, and draws complaints about speed.
- **No rival wins both sides.** CourtReserve, PlayByPoint and PodPlay sell to operators; Pickleheads is loved by players (4.9 stars) but doesn't book courts. Branded apps cost $499–$599 per month.
- **The market is the indoor, paid segment.** About 18,300 US venues, indoor courts filling 2–3x better than outdoor, and franchises growing from 2% to a projected 10–14% of venues by 2028.
- **Recommendation:** sell club software with a branded player app on every tier, start with independent indoor clubs, and make calendar sync, Wallet passes and full self-service the headline features from version one.

## The Picklr and PlayByPoint today

The Picklr won PlayByPoint on branding and scale, not on player experience, and its own reviewers say the app has gone backwards in 2026.

**The customer.** [The Picklr](https://www.franchisepayback.com/franchise/the-picklr) is the largest indoor pickleball franchise in North America, founded in Utah in 2021 and franchising since March 2023. It had 59 operating units in 2026 and has sold over 500 franchise locations across the US, Canada and Japan. Its booking, membership billing and reservations run on PlayByPoint ([apis.io](https://apis.io/providers/the-picklr/)).

**Why they chose it.** Picklr's co-founders said the first draw was having their own branded app in the App Store, plus one system for communication, point of sale and court management ([PlayByPoint blog](https://blog.playbypoint.com/?p=336)). PlayByPoint sells exactly that: a white-label app, full data export and pickleball formats like open play, leagues and ladders ([PlayByPoint](https://www.playbypoint.com/tools/comparison/solutions/pickleball)).

**What the app offers players.** Booking runs date, court type, time slot, waiver, add players, checkout. Players can pay their share or for the whole group, and get an email or on-screen confirmation ([PlayByPoint help](https://intercom.help/playbycourt/en/articles/10859758-how-players-book-a-court)). PlayByPoint's help center lists an add-to-calendar option at confirmation, yet Picklr users still ask for calendar integration, so it is missing, hidden or broken in the Picklr build.

**What Picklr players complain about** ([App Store, 4.4 stars, 552 ratings](https://apps.apple.com/us/app/the-picklr/id1663342732)):

| Complaint | Detail from reviews |
| --- | --- |
| Removed self-service | Members can no longer remove players from a booking or turn off auto-renew in the app; both now need a call to the club, with a $1,400 renewal at stake |
| No web account | Account and membership can only be managed in the phone app |
| No calendar integration | A reviewer asks for add-to-calendar "like PodPlay" so bookings come with reminders |
| Speed and reliability | Slow on iPhone 17 / iOS 26; fails to load on some home Wi-Fi after iOS 26 |
| Locked account links | Unlinking DUPR needs tech support |
| Capacity | Popular skill-level sessions sell out a week ahead; no waitlist or demand signal to add sessions |
| Hard for daily users | One reviewer tells the developers to copy CourtReserve |

Your own pain points add three more: the floating tab bar covers the last booking card's Cancel and Details buttons, every card repeats the same badge, time and title, and recurring sessions are not grouped. The Picklr app ships near-weekly releases noted only as "improvements/bug fixes", and declares no accessibility features in its App Store listing.

Across all PlayByPoint apps, an independent review analysis flags crashes while finalizing a booking and broken sign-up flows as the main complaints ([Marlvel](https://marlvel.ai/apps/playbypoint/reviews)).

## What PlayByPoint earns from The Picklr (estimate)

PlayByPoint most likely takes in about **$0.4M–$1.0M a year** from The Picklr, or roughly **$7k–$14k per club**. That's revenue, not profit, estimated from public prices and Picklr's franchise filings.

- **Two income streams:** a share of Picklr's $1,120/month per-club Technology Fee, plus a margin on 2.7% + $0.15 card processing. At a chain this size, the processing margin earns about as much as the subscription.
- **What clubs pay:** roughly $37k–$42k a year each for software and card fees, which leaves room for a cheaper all-in offer.
- **Risk:** Picklr's franchisor filed for Chapter 11 in October 2026; its franchisees are not part of the filing ([Franchise Times](https://www.franchisetimes.com/franchise_news/picklr-files-for-bankruptcy-after-pickleball-franchisor-signs-too-many-lease-guarantees/article_5a6b9ee5-fd02-4606-9f38-6991cbea03da.html)).

Full breakdown, assumptions and sources: [cost-estimates.md](cost-estimates.md).

## Competitor comparison

Every club platform sells to operators and treats the player app as a thin front end; the one product players love (Pickleheads) doesn't do court booking itself.

| App | Sells to | Price | Player-side strengths | Player-side weaknesses |
| --- | --- | --- | --- | --- |
| [PlayByPoint](https://www2.playbypoint.com/pricing/) | Clubs, franchises (The Picklr) | $199 / $399 / $599 per month; white-label app and webhooks only on the $599 tier | Branded app, group payment split, live chat support | Crashes at checkout, removed self-service, weak calendar support, no web account at Picklr |
| [CourtReserve](https://courtreserve.com/?p=7507) | Clubs, parks and rec; 1,900+ clubs and 5M players ([G2](https://www.g2.com/products/courtreserve/reviews)) | $99 / $199 / $499 / $549 per month; branded app only on top two tiers | Subscribable calendar feed for Google, Apple, Outlook ([help](https://intercom.help/courtreserve/en/articles/5930740-calendar-feed-for-players)); leagues, ladders, DUPR | Reviews call the iOS app glitchy, with booking options missing versus web ([App Store](https://apps.apple.com/ca/app/courtreserve/id1392556575)) |
| [PodPlay](https://docs.podplay.app/support-and-troubleshooting/general-faqs) | Tech-forward clubs (Pickleball Kingdom, CityPickle) | $100 venue + $30 per court (Basic) up to $500 + $350 per court (Autonomous); about $2,500 per court hardware | Add-to-calendar, video replays, scoreboards, door access, bill splitting | Hardware cost; Pickleball Kingdom's Android app sits at 3.6 stars ([Google Play](https://play.google.com/store/apps/developer?id=PodPlay)) |
| [Playtomic](https://apps.apple.com/app/1242321076) | Clubs, but players use one shared app | Free for players; a reviewer cites a 5% booking fee | 2M+ players, 16,000+ courts, matchmaking, one app across clubs | Strongest in padel; reviews cite fees, confusing cancellation rules, too much social clutter |
| [Pickleheads](https://www.pickleheads.com/groups) | Players and organizers; integrates with CourtReserve | Free; Plus $2.99/mo, Pro $24.99/mo ([App Store](https://apps.apple.com/app/id6448714446)) | 4.9 stars on 9.9k reviews; round robins, court push notifications, waitlists, USA Pickleball's court finder | No court booking or payments for clubs; depends on the club's booking system |

The pattern: operators buy on branding, payments and programs, while players judge on speed, self-service and how well the app fits their week. Nobody wins both, and branded apps are gated behind the most expensive tiers.

## Market size and growth

The buyer pool is the fast-growing indoor, paid-court segment, not public courts: public court building has nearly stalled while dedicated facilities and franchises keep expanding.

| Measure | Figure | Source |
| --- | --- | --- |
| US pickleball and padel venues | 18,342 venues, 76,589 courts (Mar 2026) | [CourtSource](https://www.courtsource.us/2026-state-of-the-courts-report.html) |
| Indoor share of supply | 36.9%, with 2–3x the utilization of outdoor courts | [CourtSource](https://www.courtsource.us/2026-state-of-the-courts-report.html) |
| Franchise share of venues | 2.2% today, projected 10–14% by 2028 | [CourtSource](https://www.courtsource.us/2026-state-of-the-courts-report.html) |
| Dedicated facilities growth | +55% year over year (SFIA) | [Bounce](https://www.bounce.game/blog/pickleball-statistics) |
| Public courts in top 100 cities | +4% in 2026, down from 13% in 2025 and 14% in 2024 (Trust for Public Land) | [Axios](https://www.axios.com/local/san-antonio/2026/06/08/san-antonio-still-trails-in-pickleball-courts-as-sport-slows) |
| Participation | +223% from 2020 to 2024 (USA Pickleball) | [Community Impact](https://communityimpact.com/houston/heights-river-oaks-montrose/health-care/2026/01/14/health-wellness-edition-pickleballs-rapid-rise-reshapes-houstons-recreation-scene) |

Franchises are the concentrated prize: The Picklr alone has sold 500+ locations, and Pickleball Kingdom signed nearly 400 franchises onto PodPlay ([InBusiness](https://inbusinessphx.com/?p=184290)). One franchise decision moves hundreds of clubs at once.

Target region: the whole US for now, so these national figures are the working market size.

## Gaps and opportunity

Recommendation: build club software that operators pay for, and win the sale with a player app that is clearly better than PlayByPoint's, starting with independent clubs priced out of white-label tiers.

**Gaps no incumbent closes well:**

1. **Bookings don't fit into players' lives.** CourtReserve has a subscribable feed, PodPlay and PlayByPoint a one-off add-to-calendar, and Picklr users can't find it at all. No one offers two-way sync, Wallet passes, or bookings that update everywhere when changed.
2. **Self-service is shrinking.** Picklr members now call the desk to drop a guest or stop a $1,400 auto-renew. Every account action should work in the app and on the web.
3. **Demand goes unseen.** Sold-out sessions turn players away with no waitlist signal, and clubs can't see which extra time slots would fill.
4. **Reliability.** Checkout crashes and slow loads top the review complaints for PlayByPoint and CourtReserve alike.
5. **Branding is a premium tax.** White-label apps start at $499–$599 per month, which small clubs can't justify.
6. **Repetitive, cramped UI.** Duplicated badges, ungrouped recurring sessions and controls hidden behind the tab bar.

**Who chooses the app.** The club does. Players install whatever their club uses, so a player-only app can't book courts without club integrations; PlayByPoint offers webhooks only on its top tier. A player-side app stays a later option once there's a club base to connect to.

**Beachhead.** Independent indoor clubs with 4–12 courts: they pay for software, feel the branding tax most, and can switch in weeks. Franchises like The Picklr are the second wave once the product is proven, since one deal moves dozens to hundreds of sites.

## Technical specification

The product is a multi-tenant club platform with a branded player app on every tier, whose bookings live in the player's calendar, wallet and messages, not just inside the app.

### Product goals and targets

| Goal | Target to beat PlayByPoint |
| --- | --- |
| Book a court fast | Home screen to confirmed booking in 3 taps for a repeat player |
| Reliable checkout | 99.5%+ of started checkouts succeed; 99.8%+ crash-free sessions |
| Bookings everywhere | Every booking reaches the player's calendar automatically and stays in sync on change or cancel |
| Full self-service | Every account, booking and membership action available in app and web, no desk call |
| Speed | App cold start under 2 s; availability loads under 300 ms at p95 |
| Accessible | WCAG 2.2 AA, Dynamic Type, VoiceOver and TalkBack support |

### Users

- **Player:** books courts and open play, invites friends, pays, manages membership.
- **Front desk:** checks players in, handles walk-ins, refunds and no-shows.
- **Club owner or manager:** sets courts, pricing, memberships, programs and rules; reads reports.
- **Coach or organizer:** runs clinics, round robins, leagues and ladders.
- **Franchise admin:** manages many locations, shared memberships and brand.

### Player app features

| Area | Requirement | Priority |
| --- | --- | --- |
| Booking | Availability grid by court and time, filters for court type and skill level; slot held 5 minutes during checkout | P0 |
| Calendar | Auto-add on booking; personal subscribe feed; two-way Google and Microsoft sync (details below) | P0 |
| Group play | Invite by contact, link or club roster; each invitee accepts and pays their share; organizer can remove a player | P0 |
| Self-service | Cancel, reschedule, swap players, change or pause membership, toggle auto-renew, unlink DUPR | P0 |
| Waitlist | Join any full session; auto-offer the spot with a timed claim; "notify me" for times with no session | P0 |
| Recurring | Book a weekly series; series shown as one grouped card with next date and count | P0 |
| Wallet | Apple Wallet and Google Wallet pass per booking with check-in QR code, updated on change | P1 |
| Sharing | Share a booking as a link with preview, or as an .ics file | P1 |
| Open play and programs | Skill-level sessions, clinics, leagues, ladders, round robins with live court assignments | P1 |
| Social | Find players by DUPR range and availability; optional, off by default | P2 |
| Multi-club | One account across every club on the platform, each with its own membership | P1 |
| Web parity | Every player action also works in a mobile browser | P0 |
| Offline | Upcoming bookings, passes and check-in QR available offline | P1 |

### Calendar and sharing

This is the headline feature, so it gets its own spec.

1. **One-tap and automatic add.** On confirmation, write the event to the device calendar (EventKit on iOS, CalendarContract on Android), with title, court, address, players and a deep link back to the booking. Default on, with a setting to choose the calendar.
2. **Subscribe feed.** Each player gets a private, revocable `webcal://` iCalendar feed (RFC 5545) of all bookings, programs and waitlist offers. Each event keeps a stable `UID`; changes bump `SEQUENCE`; cancellations publish `STATUS:CANCELLED` so the event disappears instead of going stale.
3. **Two-way sync.** Optional Google Calendar and Microsoft Graph connection. The app writes bookings to the chosen calendar and reads free/busy, so it can flag conflicts and suggest open times.
4. **Reminders.** Configurable reminders (default 24 h and 2 h) via push, plus `VALARM` in calendar events; cancellation-deadline reminders so players drop slots before fees apply.
5. **Email and text.** Every confirmation includes an .ics attachment and Add to Google / Outlook / Apple links.
6. **Wallet passes.** Pass per booking; pushed updates when time or court changes; shows on the lock screen near the club.

### UI principles

- **Nothing hidden by chrome.** All scrollable content respects safe-area and tab-bar insets; the last card's actions are never covered.
- **Cards show what differs.** Booking cards lead with date, time and court; shared labels go in a section header, not on every card.
- **Group what repeats.** Recurring bookings and programs collapse into one series card.
- **One primary action per screen.** Book, Pay, Check in.
- **Plain cancellation rules.** One clear deadline and fee shown before payment, not conflicting lines.
- **Design system** with light and dark themes and per-club brand tokens (color, logo, font), so white-label is configuration, not a custom build.

### Operator console (web)

| Area | Requirement | Priority |
| --- | --- | --- |
| Courts and schedule | Courts, hours, blackouts, court types; drag-and-drop day view | P0 |
| Pricing | Per court, per spot or split-bill; peak and off-peak; member pricing | P0 |
| Memberships | Plans, trials, pauses, freezes, multi-location access, proration | P0 |
| Payments | Cards, Apple Pay, Google Pay, stored credits, refunds, payouts | P0 |
| Rules | Booking windows by membership, max bookings, cancellation and no-show fees | P0 |
| Programs | Clinics, leagues, ladders, round robins, coach booking | P1 |
| Demand insight | Waitlist depth, fill rate and turned-away demand by time and skill level, with suggested sessions to add | P1 |
| Front desk | Check-in, walk-ins, POS for pro shop and guest fees | P1 |
| Communication | Push, email, SMS campaigns by segment | P1 |
| Reports and export | Utilization, revenue, retention; full data export anytime | P0 |
| Multi-location | Franchise view, shared members, brand control | P2 |

### Architecture

- **Apps:** React Native (Expo) for iOS and Android from one codebase; per-club white-label builds generated from brand tokens through EAS build pipelines. Next.js for the player web app and operator console.
- **Backend:** TypeScript service on Node with a REST API and generated client SDK; background jobs on a queue (BullMQ on Redis) for reminders, sync and payouts.
- **Database:** PostgreSQL. Double booking is impossible at the database level: a `tstzrange` exclusion constraint on (court, time). Row-level security keyed on club ID isolates tenants.
- **Holds:** Redis-backed slot holds with a 5-minute expiry during checkout.
- **Payments:** Stripe Connect, each club a connected account; split payments per player; platform fee taken at charge time.
- **Notifications:** APNs and FCM for push, an email provider such as Postmark, and Twilio for SMS.
- **Calendar service:** generates feeds, writes to Google and Microsoft calendars, and fans out updates when a booking changes.
- **Integrations:** DUPR ratings; door access (Kisi, Brivo); video (PlaySight); public API and webhooks on every plan; CSV import from PlayByPoint and CourtReserve for switching clubs.
- **Hosting:** managed cloud (for example AWS or GCP) with infrastructure as code, staging and production environments, and feature flags.

### Core data model

| Entity | Key fields |
| --- | --- |
| Club | id, brand tokens, time zone, address, rules, Stripe account |
| Court | club, name, type (indoor, outdoor), surface, bookable hours |
| Player | account, profile, DUPR id, calendar connections, notification settings |
| Membership | player, club, plan, status, renewal date, auto-renew flag |
| Booking | court, time range, organizer, status, price, series id, cancellation deadline |
| Participant | booking, player or guest, share owed, payment status |
| Series | recurrence rule, booking ids |
| Session | open play, clinic or league slot; skill range; capacity |
| Waitlist entry | session or slot, player, position, offer expiry |
| Payment | amount, method, split, refund, Stripe ids |
| Calendar link | player, provider, external event ids, sync token |

All times are stored in UTC alongside the venue's time zone, and displayed in the venue's local time.

### Non-functional requirements

- **Availability:** 99.9% monthly uptime for booking and checkout.
- **Performance:** API p95 under 300 ms for availability; booking writes under 500 ms.
- **Concurrency:** no double bookings under load; tested with simultaneous checkouts for the same slot.
- **Security:** card data only through Stripe (PCI SAQ-A); MFA for staff; audit log of all staff actions; SOC 2 path by year two.
- **Privacy:** CCPA and GDPR ready; players can export or delete their data; the club owns its data and can export it anytime.
- **Observability:** crash reporting, tracing on checkout, alerts on checkout failure rate.

## Roadmap

Ship calendar sync and self-service in the very first version, because they are what Picklr players ask for and what PlayByPoint lacks.

**Phase 0 · Validate.** Interview a court manager and 5–10 open-play players. Build a click-through prototype of booking, calendar and self-service.
*Gate: 3 clubs agree to pilot.*

**Phase 1 · MVP for one pilot club.** Booking, payments, memberships, self-service, waitlist, web parity. Calendar auto-add, subscribe feed, reminders, .ics in emails.
*Gate: the pilot club runs all bookings on it for 30 days.*

**Phase 2 · v1 for paying clubs.** Two-way calendar sync, Wallet passes, programs and round robins. Demand insight, branded builds, CSV import from PlayByPoint.
*Gate: 10 paying clubs, 99.5% checkout success.*

**Phase 3 · v2 for franchises.** Multi-location admin, shared memberships, franchise brand control. Door access, video and DUPR integrations, public API and webhooks.

Each phase starts only when its gate is met; the gate targets are proposals to adjust after the pilot.

**Success metrics to track from the pilot on:**

- Checkout success rate and crash-free sessions
- Share of bookings that reach a player's calendar
- Desk calls or messages per 100 bookings (self-service should cut these)
- Waitlist fills and no-show rate
- Court utilization in off-peak hours
- Club retention and net revenue per club

## Sources

Cost-estimate sources are listed in [cost-estimates.md](cost-estimates.md).


- [The Picklr on the App Store](https://apps.apple.com/us/app/the-picklr/id1663342732)
- [The Picklr franchise data, Franchise Payback](https://www.franchisepayback.com/franchise/the-picklr)
- [The Picklr provider profile, apis.io](https://apis.io/providers/the-picklr/)
- [Picklr co-founders on PlayByPoint, PlayByPoint blog](https://blog.playbypoint.com/?p=336)
- [PlayByPoint for pickleball clubs](https://www.playbypoint.com/tools/comparison/solutions/pickleball)
- [PlayByPoint pricing](https://www2.playbypoint.com/pricing/)
- [How players book a court, PlayByPoint help](https://intercom.help/playbycourt/en/articles/10859758-how-players-book-a-court)
- [PlayByPoint review analysis, Marlvel](https://marlvel.ai/apps/playbypoint/reviews)
- [CourtReserve pricing update](https://courtreserve.com/?p=7507)
- [CourtReserve calendar feed for players](https://intercom.help/courtreserve/en/articles/5930740-calendar-feed-for-players)
- [CourtReserve on G2](https://www.g2.com/products/courtreserve/reviews)
- [CourtReserve on the App Store](https://apps.apple.com/ca/app/courtreserve/id1392556575)
- [PodPlay general FAQs and pricing](https://docs.podplay.app/support-and-troubleshooting/general-faqs)
- [PodPlay apps on Google Play](https://play.google.com/store/apps/developer?id=PodPlay)
- [Pickleball Kingdom and PodPlay agreement, InBusiness](https://inbusinessphx.com/?p=184290)
- [Playtomic on the App Store](https://apps.apple.com/app/1242321076)
- [Pickleheads groups](https://www.pickleheads.com/groups)
- [Pickleheads on the App Store](https://apps.apple.com/app/id6448714446)
- [2026 State of the Courts, CourtSource](https://www.courtsource.us/2026-state-of-the-courts-report.html)
- [Pickleball statistics 2026, Bounce](https://www.bounce.game/blog/pickleball-statistics)
- [Public court growth slows, Axios](https://www.axios.com/local/san-antonio/2026/06/08/san-antonio-still-trails-in-pickleball-courts-as-sport-slows)
- [Houston pickleball growth, Community Impact](https://communityimpact.com/houston/heights-river-oaks-montrose/health-care/2026/01/14/health-wellness-edition-pickleballs-rapid-rise-reshapes-houstons-recreation-scene)
