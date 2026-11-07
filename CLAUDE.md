# Pickleball Booking App — Instructions for Claude

## About the app
A pickleball court booking app to build and sell to the pickleball community, starting US-wide. The benchmark is PlayByPoint's app for The Picklr: this app must beat it with a better UI and more robust features (for example, adding a booking to your calendar). The owner has no computer and works entirely from a phone, so anything built must run in the cloud and be testable on a phone.

## Current stage
- Early: idea and market research. No tech stack chosen yet.
- When it's time to choose, propose 2–3 stack options with plain-language trade-offs (cost, speed to build, Android + iOS reach, how well it works without a computer) and let the owner decide. Once chosen, add a Stack section here.
- Don't start writing app code until the owner says we're moving from research to building.
- `docs/spec.md` is the single source of truth for research and the spec; cost and revenue estimates live in `docs/cost-estimates.md`, summarized and linked from the spec. Keep the two in sync.
- Stack and payment options are in `docs/stack-options.md` (not yet decided). Roles Claude takes on, and how it runs multiple agents, are in `docs/roles-note.md`.

## How we work
- One feature at a time. After each one, give something testable on a phone before moving on.
- Before multi-file changes, give a short plan in plain language and wait for OK.
- Make minimal, focused changes. Don't refactor or restyle unrelated code.
- Follow existing patterns, file structure and naming once the repo exists.
- Ask before adding any new dependency or paid service.
- Never claim something works until it type-checks, builds and passes tests. Say exactly what to test on the phone.
- If unsure an API, library or plugin method exists, say so and check instead of guessing.
- Explain things simply; assume review on a phone screen.

## Product principles
- Booking a court should take as few taps as possible; speed and clarity beat feature count.
- Every competitor feature we match should be noticeably easier to use than PlayByPoint's version.
- Features the owner asked for go in as stated; ideas Claude suggests are proposals until approved.

## Multi-user and data
- This app has real customers: accounts, bookings and (likely) payments. Treat data correctness and security as top priority.
- No double bookings: booking logic must be safe when two people book the same slot at the same time.
- Store all times in UTC with the venue's time zone; display in the venue's local time. The US spans several time zones.
- Never put secrets, API keys or credentials in code or in the app; use environment config on the server.
- Use a proven payment provider; never store card numbers ourselves.
- Collect only the personal data the app needs, and keep a clear privacy policy in mind.
- Any database schema change needs a migration; never drop or reset real data.

## Mobile UI
- Phone first: touch targets at least 48dp, main actions reachable one-handed.
- Respect safe areas (status bar, notches, gesture nav) and support dark mode.
- Handle the Android back button sensibly on every screen.
- Handle poor or no connection gracefully: clear loading and error states, no lost input.
- Accessibility: readable text sizes, sufficient contrast, screen-reader labels.

## Native features
- Calendar export, notifications and location should use native plugins/APIs, not browser workarounds.
- Request permissions at runtime with a clear reason, and keep the app usable if a permission is denied.
- Don't change app IDs, signing configs or keystores without asking.
