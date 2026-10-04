# IPRoyal Pricing: What You Actually Pay per GB, and When Per-IP Billing Costs Less

People searching for IPRoyal pricing usually want one number. What they get instead is four products, two billing models, and a headline rate that almost nobody pays.

The homepage says residential proxies "from $1.75/GB". The checkout says $7.35/GB if you're buying your first gigabyte on pay-as-you-go [12]. That 4.2x gap is the single most important thing to understand before you put a card down, and it's the reason so many people end up comparing a per-gigabyte bill against a flat per-IP plan a week later.

Below is what IPRoyal actually charges, product by product, plus the alternative pricing model worth knowing about if your workload doesn't fit per-GB billing at all.

## IPRoyal's product lines and how each one is billed

Four products, two very different billing philosophies. Residential and rotating mobile charge for traffic. ISP (static residential), datacenter and dedicated mobile charge per IP for a set number of days.

| Product | Billing model | Advertised "from" | What a first-time buyer actually pays |
| --- | --- | --- | --- |
| Residential (rotating) | Per GB of traffic | $1.75/GB | $7.00/GB subscription, $7.35/GB pay-as-you-go |
| ISP / static residential | Per IP, by duration | $1.80/IP | $1.80/IP is the 24-hour tier; 30 days is $2.70/IP, 90 days $2.40/IP |
| Datacenter | Per IP, by duration | $1.39/IP | $1.39/IP at 90 days; $1.57/IP on the monthly plan |
| Mobile (rotating) | Per GB | $6.80/GB | $6.80/GB, dropping to about $5.20/GB at volume |
| Mobile (dedicated) | Per proxy, per day | $10.11/day | $10.11/day, or roughly $130/month |
| Web Unblocker | Per requests | $1.00 / 1,000 requests | $1.00 / 1,000 requests |

Datacenter and mobile are the honest ones. A 1.1x gap between the advertised floor and the entry rate is not something anyone would call misleading. Residential is where the pricing gets interesting, and not in a fun way.

### The residential ladder, and why the $1.75 rate is mostly theoretical

IPRoyal sells residential traffic two ways, and the difference is 5% plus a flexibility question that matters far more than the 5%.

**Subscription:** $7.00/GB at the 1 GB tier instead of $7.35. Cheaper per gigabyte, but it renews on a schedule whether you used the traffic or not.

**Pay-as-you-go:** 5% more per gigabyte, and the traffic does not expire. It sits in your account until you consume it [2][7].

The advertised $1.75/GB isn't a lie. It's attached to a bulk custom plan in the region of 10 TB that requires talking to the sales team rather than clicking a checkout button [12]. The pay-as-you-go equivalent at that volume is slightly higher, around $1.84/GB. If you are buying a gigabyte to see whether the network works on your targets, you will pay $7.35 and the advertised figure has nothing to do with you.

The volume curve also does most of its work immediately. A second gigabyte knocks roughly 15% off the rate. After that it flattens hard, and at 50 GB you are still paying multiples of the advertised floor. Worth knowing: third-party breakdowns of the mid-tier numbers don't agree with each other, so treat anything between 2 GB and 20 GB as "check the cart" rather than budgeting from a blog table.

### ISP, datacenter and mobile are priced by commitment, not quantity

There's a quirk here that catches people comparing vendors. IPRoyal advertises ISP proxies "from $1.80/IP" with no duration attached, and every other provider in this market quotes ISP proxies monthly, so it reads as a monthly price. Open the ISP product page and $1.80 is the **24-hour** tier. A plain 30-day month is $2.70/IP [12]. The cheap rates live behind 60- and 90-day commitments instead of higher unit counts, which suits steady workloads and penalises seasonal ones.

Datacenter follows the same logic: $1.57/IP monthly, $1.39/IP if you commit to 90 days, unlimited traffic either way under fair use.

### The fine print that costs real money

- **No free trial for individuals.** The residential page has a "start free trial" button. IPRoyal's own documentation says trials go to verified companies, and individuals are told to buy the minimum traffic [3][4].
- **The residential refund window closes at 100 MB consumed.** That is a small fraction of a gigabyte [2][3].
- **ISP, datacenter and mobile orders can be refunded within 24 hours** if the service isn't working as expected [11].
- **Crypto payments are non-refundable**, and one-day plans aren't refundable either [2][11].
- **Pool figures differ between pages** on the same site, quoted anywhere from 64M to 68M residential IPs [2][8]. Pool size is self-reported marketing across the whole industry; don't weight it heavily.

Residential traffic not expiring is genuinely a good policy and one of the better ones in the market. It's also the main reason IPRoyal's per-GB rate sits above providers who reset your allowance every month [12].

## Where per-GB pricing stops making sense

The pricing model you should pick depends on which resource your work actually burns.

**Bandwidth-heavy scraping.** If you're rendering JavaScript pages that weigh 2–5 MB each, cost scales with page weight you don't control. A pipeline pulling 100,000 pages a month is buying hundreds of gigabytes. At IPRoyal's entry rate of $7.35/GB pay-as-you-go, 100 GB bills about $735 before the volume discount kicks in — and the discount only reaches the advertised floor at 10 TB [12]. Providers that charge a flat price per IP with unlimited data invert that math: scrape 100 pages or 10,000 through the same IP and the bill doesn't move [5].

**Work that needs many stable identities at once.** Anti-detect browser profiles, multi-account setups, regional QA across dozens of cities. That's a per-IP problem, and it's where IPRoyal's ISP product lands at $2.40–$2.70 per IP, which is mid-market, not cheap [3].

**Small, occasional tests.** Here IPRoyal is fine. Buy the minimum gigabyte, keep it, use it over months. This is the scenario its model is genuinely good at.

## The flat per-IP alternative: how 9Proxy prices the same work

9Proxy takes the opposite approach to the bandwidth problem. Its core product is per-IP with unlimited data: you buy a package of residential IPs, and bandwidth isn't metered. There's also a per-GB line for rotation-heavy work, plus bundles that mix both.

Two things to know before the numbers. First, the IP-based packages and bundles went through the company's first price increase on 1 June 2026, while the GB-based packages stayed unchanged [1]. Second, IP-based proxies come from real residential connections, so an individual IP stays live for a few hours up to about 24 hours, then goes offline — the model assumes you rotate and replace rather than sit on one address for a month [6]. GB-based plans run from the dashboard with username/password or IP whitelisting; the IP-based product needs the Windows desktop app for local port forwarding [6].

### IP-based packages — unlimited bandwidth per IP

| Package | Price per IP | Total | Notes |
| --- | --- | --- | --- |
| 100 IPs | $0.24 | $24 | Smallest entry point |
| 500 IPs | $0.144 | $72 | Unlimited data per active IP |
| 1,000 IPs (+500 bonus) | $0.084 | $126 | Most popular tier |
| Large volume tiers | down to $0.018 | up to $8,625 at 500,000 IPs | 100,000 IPs listed at $2,300 |

👉 [Start with the 100-IP tier to test against your own targets](https://bit.ly/9-Proxy)

Unused IPs don't expire, and IPs can be targeted by country, state, city, ZIP and ISP [6]. Compare that to IPRoyal's ISP proxies: 500 static IPs for 90 days runs $1,200. Whether the difference is worth it depends entirely on whether you need a truly static address or just a clean residential one that lasts a working session.

### GB-based packages — 180-day validity

| Package | Price per GB | Total | Validity |
| --- | --- | --- | --- |
| 5 GB | $3.00 | $15 | 180 days |
| 50 GB (+5 GB bonus) | $2.10 | $105 | 180 days |
| 100 GB | $1.50 | $150 | 180 days |
| 200 GB | $1.00 | $200 | 180 days |
| 1,000 GB | $0.80 | $800 | 180 days |
| 2,000 GB | $0.75 | $1,500 | 180 days |

👉 [See the per-GB ladder and current bonus traffic](https://bit.ly/9-Proxy)

The GB model generates unlimited endpoints and supports sticky or rotating sessions, so it covers the use case IPRoyal's residential product covers — at $3.00/GB at the bottom of the ladder rather than $7.35 [5][7]. Bandwidth expires after 180 days unless you're on an enterprise plan.

### Enterprise bandwidth — unlimited validity

| Package | Price per GB | Total | Validity |
| --- | --- | --- | --- |
| 3,000 GB | $0.72 | $2,160 | Unlimited |
| 6,000 GB | $0.70 | $4,200 | Unlimited |
| 10,000 GB | $0.68 | $6,800 | Unlimited |

Enterprise includes unlimited data validity, a team of one owner plus up to five members, per-member traffic controls, activity logs and shared bandwidth that doesn't expire inside the team [6].

### Bundle packages — IPs plus bandwidth

| Bundle | Contents | Price |
| --- | --- | --- |
| Starter | 100 IPs + 5 GB | $30 |
| Popular | 1,500 IPs + 50 GB | $180 |
| Pro | 5,000 IPs + 500 GB | $720 |

👉 [Compare the bundle options side by side](https://bit.ly/9-Proxy)

Bundles make sense when part of your work needs a stable session and part just needs cheap rotation. If every job you run looks the same, one of the two pure models will be cheaper.

> The bundle prices above reflect the 1 June 2026 adjustment. Before that date, the same packages sold for $25, $150 and $600 — if you find an older comparison table quoting those figures, it predates the change [1][5].

## A quick note on what third-party reviews actually say

Feedback on 9Proxy is split, and it's worth reading the split rather than the average.

Geekflare's review treats the pricing structure as the main strength and walks through the same IP-based and GB-based tiers listed above [5]. Product Hunt commenters and at least one directory review describe stable connections that work with anti-detect browsers [9][10]. Payment coverage is broad — cards, crypto including USDT and BTC, Alipay, Apple Pay and Google Pay — and support runs 24/7 through Telegram, email and tickets [5].

On the other side, reseller-run catalog pages have reported service disruptions during 2026, and review aggregators carry complaints about proxies disappearing shortly after purchase. A security-scan page lists 9proxy.com as "unverified" with an elevated-risk flag while noting the domain's long history and a valid certificate [13]. Those reports come from sources with their own agendas — one of them sells competing inventory — and I can't independently confirm the outage claims.

The practical response is the same either way: start with the smallest package, test it against the exact sites you care about, and don't prepay for a year of inventory on the strength of anyone's review, including this one.

## How to compare these two price tags without getting fooled

Four questions, in order:

1. **Is the advertised number a rate you can buy today?** IPRoyal's $1.75/GB needs a 10 TB conversation with sales. 9Proxy's $0.015/IP is the 500,000-IP tier. Both are real, neither is the price a first purchase costs.
2. **Is the price per gigabyte or per day?** IPRoyal's $1.80 ISP figure is a 24-hour rate sitting next to competitors' monthly rates. Duration is the discount lever there, not quantity.
3. **Does the balance expire?** IPRoyal's pay-as-you-go residential traffic doesn't. 9Proxy's GB packages run 180 days, and IP-based packages don't expire at all.
4. **What does a failed test cost?** IPRoyal refunds within 100 MB consumed on residential, or 24 hours on ISP and datacenter. Keep crypto out of any purchase you might want to reverse.

## Which one fits your workload

If you need **static IP addresses you keep for a month or longer** for regional QA or long-lived accounts, IPRoyal's ISP product at $2.40–$2.70/IP is a legitimate mid-market answer, with unlimited bandwidth and country-level targeting.

If you need **a lot of clean residential IPs for short sessions**, or your scraping burns bandwidth faster than your budget likes, per-IP pricing is the cheaper shape: 9Proxy's 500-IP package costs $72 with no data meter running, against $1,200 for 500 static ISP IPs over 90 days at IPRoyal.

If your work is **pure rotation with light requests** — ad verification, geo-checks, API polling — per-GB is the right model, and the entry rates ($3.00/GB at the small end, down to $0.68/GB on enterprise volume) are worth benchmarking against whatever you pay now.

And if you're just **curious what IPRoyal costs** before committing: buy one gigabyte pay-as-you-go, keep the non-expiring balance, and test it on your actual targets. Ten minutes of that answers more than any pricing table.

## FAQ

**Is IPRoyal's $1.75/GB rate real?**
Yes, and practically nobody pays it. It's tied to a bulk custom plan around 10 TB that requires contacting sales, and it applies to the subscription option. The pay-as-you-go rate at that volume is about $1.84/GB [12].

**Does IPRoyal offer a free trial?**
Not to individuals. The company says trials go to businesses after verification of registration and ownership; everyone else is directed to buy the minimum traffic [3][4].

**Does IPRoyal residential traffic expire?**
No, on pay-as-you-go. The balance stays in your account until you use it [2][12].

**Is 9Proxy cheaper than IPRoyal?**
For rotating residential bandwidth and for bulk IP counts, yes by a wide margin — $3.00/GB at the smallest 9Proxy tier versus $7.35/GB at IPRoyal's entry tier, and $72 for 500 IPs versus $1,200 for 500 static ISP IPs over 90 days. For genuinely static IPs held for months, IPRoyal's ISP product is the closer fit to that requirement, and it's priced accordingly.

**Can I switch without wasting the balance I already bought?**
With IPRoyal, usually yes for residential — the traffic doesn't expire. With 9Proxy, GB packages carry 180-day validity and IP-based packages don't expire. Buy the minimum at both while you test, and run your real targets through each before you move the rest of your budget.
