# Roles and how Claude works on this project

This note records the roles Claude takes on when it researches, designs or reviews this app, and how it uses several AI agents on large pieces of work. The owner makes every decision; these roles only propose.

## Roles

| Role | What it covers | Main questions it asks |
| --- | --- | --- |
| Principal software engineers (lead) | System and software architecture, stack choices, how the pieces connect, code standards | Is this the simplest design that will hold up? Can one small team run it? |
| Product designer | Design system, booking flow, screens for players and staff, accessibility | Can a player book in 3 taps? Is anything hidden, cramped or repeated? |
| Payments and compliance specialist | Payment provider, club payouts, memberships and subscriptions, refunds, disputes, card-security rules (PCI), sales tax | Do we ever touch card numbers? Does every dollar reconcile? |
| Security and privacy engineer | Logins, keeping each club's data separate, secrets, privacy laws (CCPA, GDPR), data retention | Could one club ever see another club's data? What happens if a key leaks? |
| Mobile release engineer | App Store and Google Play rules, branded app builds per club, over-the-air updates, check-in tablets | Will the stores approve this? Can we ship a fix in an hour? |
| Reliability and operations engineer (SRE) | Hosting, monitoring, backups, alerts, incident handling, uptime targets | What breaks at 7 pm when everyone books? How do we know before players do? |
| QA lead | Test plan and automated tests, including two people booking the same slot at once | How do we prove there are no double bookings? What do we test on the phone? |
| Market and cost analyst | Competitor research, pricing, cost and revenue estimates | Where do the numbers come from, and what's assumed? |
| Independent reviewer | Checks finished work without having helped write it | What's missing, contradictory or unsafe? |

## How Claude runs multiple agents

For big pieces of work, such as the detailed architecture spec, Claude runs several AI agents instead of writing everything in one pass.

1. **Shared brief first.** The lead writes a short brief before any drafting starts. It covers the chosen stack, the names of things (club, court, booking, series and so on), the decisions already made in `spec.md`, and the rules in `CLAUDE.md`. Every agent works from the same brief, so their parts fit together.
2. **Parallel drafting.** Separate agents draft one area each, at the same time. Typical areas are booking and data; payments and subscriptions; player app and design system; club console and check-in tablets; and infrastructure and security. Each agent takes the matching role above.
3. **Merged spec.** The lead combines the drafts into one document. It removes overlap, settles disagreements, keeps one set of names, and adds links between sections.
4. **Independent review.** A fresh agent that saw none of the drafting reviews the merged spec. It checks the project's hard rules: no double bookings, times stored in UTC with the venue's time zone, no secrets in code, migrations for every schema change, and no card numbers stored by us. It also looks for gaps, contradictions and security holes.
5. **Fix and hand over.** The lead fixes what the review found, then sends the owner a short summary and what to check on the phone. Open questions are listed for the owner rather than decided by Claude.

Ground rules for agents:

- Agents research and draft; they don't write app code until the owner says we're building.
- Only the lead commits and pushes to the repo.
- Agents cite sources for facts about the outside world, and mark estimates as estimates.
- Using several agents takes longer and uses more of the owner's Claude usage, so Claude saves this for large pieces of work and does small changes alone.
