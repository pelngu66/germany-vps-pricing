# Cheap Germany VPS: What $3–$5 a Month Buys, Which Plans Are Actually in Stock, and the Renewal Price Nobody Quotes (Evoxt Plan Table Included)

The lowest verified entry point into a German data centre right now is $12 a year for a 1 GB KVM server in Frankfurt, and the trade-off is visible in what the offer leaves out: annual prepay, one IPv4, no backup mentioned anywhere on the page, no SLA number. If you want monthly billing and backups included in Germany, Evoxt's German location starts at $2.99/month for 512 MB and $4.99/month for 1 GB, with weekly offsite backups bundled rather than sold back to you as an add-on.

Below is the Evoxt plan table I could verify, then what "cheap" actually costs over two and four years at five other German providers, then the clause-level limits that decide whether a $3 box is usable for your workload.

> **Quick pick:** the 512 MB VM-0.5 at $2.99/month covers a WireGuard endpoint, a cron box, an uptime monitor or a small Git mirror. Move up to the 1 GB VM-0.75 at $4.99/month once a database or a JVM is involved. Both bill monthly, so a $3 decision doesn't require betting two years of budget.
> 👉 [See Evoxt's current plan prices and the German location](https://bit.ly/EvoXt)

## Evoxt's German plans, tier by tier

| Plan | vCPU / RAM / Storage | Monthly price | What it fits | Order |
| --- | --- | --- | --- | --- |
| VM-0.5 | 1 vCore / 512 MB / 5 GB | $2.99 | VPN endpoint, monitoring agent, cron, DNS | [Deploy VM-0.5](https://bit.ly/EvoXt) |
| VM-0.75 | 1 vCore / 1 GB / 10 GB | $4.99 | Small API, bot, Git mirror, one low-traffic site | [Deploy VM-0.75](https://bit.ly/EvoXt) |
| VM-1 | 1 vCore / 2 GB / 20 GB | $5.99 | Site with a database, Docker with a few containers | [Deploy VM-1](https://bit.ly/EvoXt) |
| VM-1.5 | 2 vCores / 2 GB / 20 GB | $6.95 | Build runners, parallel test jobs | [Deploy VM-1.5](https://bit.ly/EvoXt) |
| VM-2 | 2 vCores / 4 GB / 30 GB | $11.99 | Small game server, several services at once | [Deploy VM-2](https://bit.ly/EvoXt) |

Prices above are the standard-network monthly rates. Two things to check on the order page before paying. First, the same plan names appear on premium network tables with different transfer quotas, so the quota attached to your VM depends on which network you pick. Second, the lineup continues above VM-2, and those tiers are better read off the order page than from any cached listing.

The feature list matters as much as the specs at this price. Weekly offsite backups are included on every VM at no extra cost, IPv4 and IPv6 both come with the deployment, and there's a firewall you can configure from the control panel without SSH, browser-based VNC, a REST API, one-click app installs, and a one-click rescue mode. Billing runs from monthly up to multi-year prepayment, so annual is a discount option rather than a requirement.

## The sticker price is a first-term price

A cheap German VPS ad usually quotes the monthly figure of the longest commitment the provider can sell you. Compare what you actually pay:

| Provider | Entry plan | Price as advertised | What it really means |
| --- | --- | --- | --- |
| Servitro | EPYC $1: 1 vCPU, 1 GB, 10 GB NVMe, 1 TB, 1 Gbps | $12/year | $1/month effective, annual prepay, promo post dated September 2026 |
| Evoxt | VM-0.75: 1 vCPU, 1 GB, 10 GB | $4.99/month | Monthly billing, no prepay required |
| Senko Digital | DE-BUDGET-1: 1 vCPU, 1 GB DDR4, 10 GB NVMe, 4 TB | €2.29/month | Listed but out of stock when checked |
| Contabo | Cloud VPS 4: 4 vCPU, 8 GB, 100 GB SSD | €5.50/month | Rate explicitly labelled "for the first 24 months" |
| Hostinger | KVM 1: 1 vCPU, 4 GB, 50 GB NVMe, 4 TB | $6.49/month | $155.76 due today for 24 months, renews at $11.99/month |
| OVHcloud | VPS-1: 2 vCores, 4 GB, 40 GB NVMe | $4.54/month | "From" price, excluding GST |

Hostinger's KVM 1 is the clearest example of how the headline number works. You pay $155.76 upfront for two years, which is genuinely $6.49/month. The second term is billed at $11.99/month for the same 24 months, or $287.76. Run it to four years and the total is $443.52, an average of about $110.88 a year. The first-term number is real, and it's also the only term you'll ever get at that rate.

Contabo's €5.50 for Cloud VPS 4 carries a similar caveat in a subtler form. The page states "for the first 24 months" and doesn't publish the rate that follows, so €5.50 is not a number you can budget against for year three. OVHcloud's $4.54 is a "from" figure quoted before tax. Servitro's $12/year sits at the opposite end: no renewal cliff, but it comes from a promotional post published in September 2026, so check the current page before you plan around it.

The relevant question for a $3–$5 budget isn't which monthly figure is lowest. It's how much money leaves your account today, and what the same box costs in the second year. A monthly-billed plan at $4.99 costs more per month than a $12 annual plan and less than a locked-in $6.49 that renews at nearly double.

👉 [Start with Evoxt's $2.99 VM-0.5 on monthly billing and skip the prepay](https://bit.ly/EvoXt)

## Five limits that only show up in the terms

**Port 25 is closed, and on the budget line it stays closed.** Senko Digital shuts inbound and outbound SMTP on all plans by default. On the BUDGET line there's no path to reopening it; the company directs anyone who needs port 25 to a different product line and a compliance review. If your app sends password resets or alert emails, plan for an SMTP relay from day one.

**"Unlimited traffic" is a policy, not a pipe.** Contabo's unlimited traffic is subject to fair usage rules, and the port is capped at 200 Mbit/s on the entry plan. Senko's budget line takes the opposite approach with metered buckets of 4, 8, 12 and 16 TB and bandwidth locked between 125 and 500 Mbps.

**The unlimited-traffic asterisk doesn't apply to Germany.** OVHcloud's unlimited traffic excludes its Asia-Pacific data centres, where a monthly quota of 500 GB to 3 TB applies before speeds drop to 10 Mbps. A German VPS from the same provider isn't affected, which is exactly the kind of footnote that gets copied into comparisons of the wrong region.

**Stock is a variable, not a constant.** Every Senko BUDGET plan in Frankfurt and Helsinki showed out of stock at the time of checking. A listed price for an unavailable plan is not a price you can buy at.

**Backups are the quiet dividing line.** OVHcloud includes a daily backup covering the previous 24 hours, Hostinger includes weekly backups, and Evoxt includes weekly offsite backups on every VM. Servitro's and Senko's budget pages don't mention backups at all. On a $12/year box that's an acceptable trade; on anything holding data you can't rebuild, it isn't.

👉 [Check the plan specs, network tier and backup coverage before you pay](https://bit.ly/EvoXt)

## What a German location actually changes

Frankfurt sits in the middle of the European backbone, and that's the whole argument. Traffic between a Frankfurt server and users in Germany, the Netherlands, France, Switzerland, Austria or Poland travels a short physical distance, so the floor on your latency is set by distance rather than by routing detours. Serve the same audience from Singapore or Virginia and every request crosses an ocean twice.

The corollary gets skipped: a German VPS does nothing for visitors in Asia or South America. If your users are mostly outside Europe, the location is a liability with a nice network attached. OVHcloud lets you add up to 16 extra IPs and pick from 13 European locations, and Hostinger lets you switch data centre region from the dashboard, both of which are useful if your audience turns out to be somewhere else than you assumed.

One more scenario worth naming, because it's the reason a lot of people buy a cheap German box. If the goal is reaching mainland China, a June 2026 LowEndTalk post describes a delivered IP that was already blocked from China, with a refund denied under the provider's GFW-blocked-IP policy. One report isn't a pattern, and it says nothing about European routing, but it's the specific case where "cheap" and "refundable" can diverge.

## Who shouldn't buy the cheapest tier

The 512 MB tier is a bad fit in five situations, and recognising them early saves a migration later.

- **You need to send mail.** Port 25 restrictions and IP reputation make this a relay job regardless of provider.
- **Your data can't be rebuilt from a repo.** Pay for a tier with backups, or budget for object storage and your own snapshots.
- **You need SLA credits.** A 99.9% SLA with compensation exists at OVHcloud and Senko Digital. The cheapest tier generally doesn't come with a financial remedy worth pursuing.
- **You'll push more than a few TB.** Metered plans and fair-use clauses both start to matter around that point; check the quota attached to the specific network tier.
- **You need Windows or a control panel.** Both add licence cost and RAM that a 512 MB box doesn't have.

## FAQ

**Does a German VPS make my site faster?**
For visitors in Germany and neighbouring countries, yes, because the distance between server and browser shrinks. For visitors in Asia or the Americas, no. Location is a targeting decision, not a speed upgrade.

**Is annual billing always cheaper?**
Per month, usually. In total commitment, not always. $12/year beats $4.99/month on cash outlay, but it also means a year of sunk cost if the box turns out to be wrong for the job. Monthly billing at $2.99 buys the option to walk away.

**What can 512 MB actually run?**
WireGuard, a monitoring agent, a cron runner, a DNS resolver, a static site, a small bot. Not a MySQL-backed application, not a JVM with default heap settings, not Docker with three containers.

**Will the price go up at renewal?**
At Evoxt, the listed monthly rate is the rate, and you can stay monthly. At Hostinger, KVM 1 renews at $11.99/month after the $6.49 first term. At Contabo, the published €5.50 covers the first 24 months only, and the following rate isn't shown on the page.

**What if the plan I want is out of stock or the promo expired?**
Senko's budget line shows the failure mode: listed, priced, unbuyable. Promotional posts age too, and a September 2026 offer is two months old by now. Confirm the price and stock on the order page before you commit, not on the review you read.

## Picking a tier in one line each

A VPN endpoint, a cron box or a monitor: VM-0.5 at $2.99/month. A small API, a bot or a Git mirror: VM-0.75 at $4.99/month. A site with a real database, or Docker with a handful of containers: VM-1 at $5.99/month. Several services or a game server for a few friends: VM-2 at $11.99/month.

Two things to confirm before you pay anywhere: the billing term and the renewal rate attached to it, and whether IPv4 and backups are included or billed separately. On Evoxt both are in the base price, the term is your choice, and the German location is one of several you can deploy into.

👉 [Deploy a German VM on monthly billing and confirm the current price at checkout](https://bit.ly/EvoXt)
