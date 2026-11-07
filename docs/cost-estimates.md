# Cost estimates

Cost and revenue estimates for the pickleball booking app. The summary lives in [spec.md](spec.md); the detail lives here.

## What PlayByPoint earns from The Picklr

PlayByPoint most likely takes in about **$0.4M–$1.0M a year** from The Picklr, or roughly **$7k–$14k per club**. The contract is private, so this is an estimate built from public prices and Picklr's franchise disclosure document (FDD). It is revenue, not profit. PlayByPoint's costs for hosting, support, app store accounts and staff are not public, so its true net can't be known.

### How the money flows

Each Picklr club pays two kinds of charges that reach PlayByPoint:

| Charge | What's public | Who pays |
| --- | --- | --- |
| Software subscription | Picklr's FDD charges each franchisee a **$1,120/month Technology Fee**, starting 90 days after opening. It bundles "POS (currently PlaybyPoint), Bridge LMS, Picklr email, Podium" and other tools, so PlayByPoint gets only part of it. PlayByPoint's list price for the white-label tier is **$599/month** per club. | The franchisee, through the tech fee |
| Card processing | **2.7% + $0.15** per transaction on PlayByPoint's Advanced and Premium plans. Clubs connect their own Stripe account. PlayByPoint keeps the gap between this rate and its own Stripe cost. | The club, out of every booking and membership charge |
| Player fees | None found. PlayByPoint lists no booking or convenience fee for players. | Nobody |
| Setup and hardware | Picklr's FDD lists about $5,000 for POS equipment and software at opening. No PlayByPoint setup fee is public. | The franchisee, once |

### Inputs

- **Clubs:** 59 open per the 2026 FDD (56 franchised, 3 company-owned); more than 75 worldwide per Franchise Times in Oct 2026.
- **Sales per club:** $962,734 average annual gross sales across 12 franchised clubs open at least a year (2026 FDD).

### Estimate per club, per year

| | Low | Mid | High |
| --- | --- | --- | --- |
| Clubs | 59 | 67 | 75 |
| PlayByPoint's share of the tech fee | $300/mo | $450/mo | $599/mo (list) |
| Sales paid by card through PlayByPoint | 85% | 90% | 95% |
| Average transaction | $60 | $50 | $40 |
| PlayByPoint's margin over Stripe cost | 0.30% + $0.05 | 0.45% + $0.05 | 0.60% + $0.05 |
| **Subscription per club** | $3,600 | $5,400 | $7,188 |
| **Processing margin per club** | $3,137 | $4,766 | $6,631 |
| **Total per club** | **$6,737** | **$10,166** | **$13,819** |
| **Total across Picklr** | **~$0.40M** | **~$0.68M** | **~$1.04M** |

### What clubs actually pay

Card processing at 2.7% + $0.15 costs each club about $24k–$28k a year, or $1.4M–$2.1M across the chain. Most of that goes to Stripe and the card networks, not PlayByPoint. Picklr's full Technology Fee comes to about $0.8M–$1.0M a year across all clubs. In total, each club spends roughly $37k–$42k a year on software and card processing.

### What's assumed and what's unknown

- PlayByPoint's share of the $1,120 tech fee is not disclosed. The low case assumes a franchise discount, and the high case assumes list price.
- Stripe's cost to PlayByPoint is not public. The margin range assumes a large platform on negotiated rates.
- Some clubs may pay for add-ons such as beacons, TV displays or data sharing. These aren't counted.
- The figure for sales per club comes from only the 12 clubs open a full year, and newer clubs likely earn less.

### Why it matters for us

- **The real prize is payments.** At a chain like Picklr, processing margin earns about as much as the subscription. Our pricing should plan for both.
- **Clubs feel the cost.** A club spends roughly $37k–$42k a year on software and card fees, which is room for a cheaper all-in offer with a branded app included.
- **The franchisor is unstable.** Picklr's franchisor filed for Chapter 11 in October 2026 over lease guarantees, though its franchisees and subsidiaries are not part of the filing. A reorganization can reopen vendor contracts, but it also makes Picklr a riskier customer to rely on.

## Sources

- [The Picklr 2025 FDD (Technology Fee, Item 6)](https://static1.squarespace.com/static/681229e5d5049f03a4754bba/t/688b6f139c24b63e6eb95c43/1753968403829/Picklr+-++2025+FINAL+FDD+(4.18.25).pdf)
- [The Picklr fees summary (2025 FDD), FDD Exchange](https://fddexchange.com/fdd/the-picklr-2025/)
- [The Picklr franchise report (2026 FDD), Zee Report](https://zeereport.com/reports/picklr)
- [Picklr files for bankruptcy, Franchise Times](https://www.franchisetimes.com/franchise_news/picklr-files-for-bankruptcy-after-pickleball-franchisor-signs-too-many-lease-guarantees/article_5a6b9ee5-fd02-4606-9f38-6991cbea03da.html)
- [PlayByPoint pricing](https://www2.playbypoint.com/pricing/)
- [How to connect your Stripe account, PlayByPoint help](https://help.playbypoint.com/en/articles/11647355-how-to-connect-your-stripe-account)
- [Best pickleball court reservation software, Pickleheads](https://www.pickleheads.com/pickleball-gear/best-pickleball-court-reservation-software)
