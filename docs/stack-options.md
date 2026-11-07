# Stack and payment options

Options for how to build the app, for the owner to choose from. Nothing here is decided until the owner picks it; the choice then goes into `CLAUDE.md` under a Stack section.

## Should we use microservices?

**Not yet.** Microservices split an app into many small services that each run and deploy on their own. They help large companies with many teams, but for one owner working with Claude they add cost and moving parts: more hosting, more things to monitor, and network calls that can fail between services.

The better fit is a **modular monolith**: one backend app, split inside into clear modules (booking, payments, memberships, calendar, notifications, programs). Each module owns its own tables and talks to others through a defined interface. Background jobs run in a separate worker process from the same code.

A module gets pulled out into its own service only for a concrete reason, such as a part that needs to scale on its own, a separate team owning it, or tighter security for payments. The clean module boundaries make that split easy later.

## Stack options

All three work from a phone. Code lives in GitHub, Claude writes and tests it in the cloud, preview links let you open each change in your phone's browser, and test builds of the app install straight onto your phone.

### Option A: Custom TypeScript backend

React Native (Expo) apps, a Next.js website and club console, a Node.js API (TypeScript), Postgres, Redis and Stripe. This is the stack in the current spec.

- **Cost for the pilot:** about $50–150/month for hosting the API, database, Redis and website.
- **Speed to build:** slower. We build login, permissions, file storage and the admin tools ourselves.
- **Android and iOS:** full reach from one codebase, plus the web.
- **Without a computer:** works well; everything runs and deploys in the cloud.
- **Strengths:** full control, no lock-in, every part is standard and portable.
- **Weaknesses:** more to build and run before the pilot; more for the owner to look after.

### Option B: Supabase-based (recommended to start)

The same Expo apps and Next.js site, but the backend is Supabase: a hosted Postgres database with login, row-level security, live updates, file storage, scheduled jobs and small server functions built in. Stripe for payments. Business logic that outgrows server functions moves into a small Node.js API later, which turns this into Option A.

- **Cost for the pilot:** Supabase Pro is $25/month ([selfhost.dev](https://selfhost.dev/blog/supabase-pricing-explained/)), plus website hosting; roughly $25–75/month in total.
- **Speed to build:** fastest. Login, data security rules and live court availability come built in.
- **Android and iOS:** same as Option A.
- **Without a computer:** works well; Supabase also has preview databases for testing changes.
- **Strengths:** it's still plain Postgres, so the no-double-booking database rule and per-club data separation work exactly as in the spec. Redis isn't needed at first: checkout holds can be short-lived rows in the same table, protected by the same rule.
- **Weaknesses:** some reliance on Supabase's login system; complex logic spread across database rules and functions can get messy if we're not disciplined.

### Option C: Flutter + Firebase

Google's Flutter for the apps and Firebase (Firestore database, login, functions).

- **Cost for the pilot:** low at first, but billing is per read and write, so costs climb with a busy availability screen.
- **Speed to build:** fast for simple apps.
- **Android and iOS:** full reach from one codebase; the web version is weaker.
- **Without a computer:** works.
- **Weaknesses:** Firestore isn't a relational database. It has no built-in rule that makes double bookings impossible, so we'd rely on careful app code. Reports, revenue figures and data exports for clubs are harder. **Not recommended** for a booking and payments product.

### Recommendation

Start with **Option B**, structured so it grows into **Option A**: keep business logic in a shared TypeScript module, not scattered through the database, so it can move into a Node.js API once there are paying clubs. Both share the same apps, website, database design and payments.

## Payment providers

The platform needs "marketplace" payments: players pay the club, the club gets paid out, and we can take a platform fee. It also needs recurring billing for memberships, and card readers or tap-to-pay at the front desk.

| Provider | How it works for us | Pricing | Best for | Drawbacks |
| --- | --- | --- | --- | --- |
| **Stripe Connect** | Each club has a connected account; we set our fee on each charge; Stripe Billing for memberships; Stripe Terminal for card readers | Published: US cards 2.9% + $0.30; when we set prices, $2 per active club account per month plus 0.25% + $0.25 per payout; Billing 0.7% ([Swipesum, Q2 2026](https://www.swipesum.com/insights/stripe-alternatives-for-saas-companies)) | Startups and small platforms; self-serve, best documentation | Highest list cost at large volume |
| **Square** | Clubs use their own Square accounts and connect through Square sign-in; we add an app fee to each payment ([Square docs](https://developer.squareup.com/docs/payments-api/take-payments-and-collect-fees)) | Club pays Square's rates; our fee is added on top | Clubs already on Square hardware | Less control over the checkout; each club must have Square; fees on memberships through the API aren't clearly documented |
| **Adyen for Platforms** | Enterprise marketplace payments | Negotiated interchange-plus; deals often take 60+ days ([FintechSpecs](https://fintechspecs.com/blog/payfac-as-a-service-providers/)) | Large, global platforms | Built for enterprise volume; not a fit for a pilot |
| **Finix** | We become a payment facilitator with their help | Negotiated buy rate plus platform fee; targets $500K+ processed per month ([FintechSpecs](https://fintechspecs.com/blog/payfac-as-a-service-providers/)) | Vertical software with real volume that wants payment margin | Too early for us |
| **Worldpay for Platforms (formerly Payrix)** | Payment-facilitator platform with hardware support | Negotiated; aimed at platforms processing eight figures or more; 6–12 weeks to set up ([Swipesum](https://www.swipesum.com/insights/stripe-alternatives-for-saas-companies)) | Franchise software and hardware-heavy platforms | Slow to set up; too early for us |

**Recommendation: Stripe Connect now.** It's the best fit at our size: fastest to launch, published prices, memberships and card readers in one place, and room to take a processing margin, which the cost estimates show is a big part of PlayByPoint's income. Even a vendor selling alternatives advises staying on Stripe below about $10M a year processed. We'd revisit Finix or Worldpay above that. To keep the switch possible, all payment calls go through one payments module in our code, not straight to Stripe from everywhere.

## Subscriptions

There are two kinds, and they're kept separate:

1. **Our subscription to clubs** (our software plan): billed with Stripe Billing on our own Stripe account.
2. **Club memberships for players**: billed with Stripe Billing on each club's connected account, with our platform fee set on each charge. Players can pause, cancel or turn off auto-renew themselves.

Apple and Google allow non-store payments for real-world services like court time and club memberships, so players pay by card, Apple Pay or Google Pay, with no app-store cut.

## Check-in tablets (moved earlier)

Check-in tablets are now part of the pilot (Phase 1). The plan:

- A **front-desk mode** of the same Expo app, run on an iPad (locked with Guided Access) or an Android tablet (locked in kiosk mode).
- The tablet's camera **scans the player's booking QR code**; the desk sees who's checked in, who's late and open courts.
- **Walk-ins** can be booked and paid at the tablet; card readers or tap-to-pay come through Stripe Terminal.
- If the internet drops, the tablet keeps today's bookings so check-in still works.
