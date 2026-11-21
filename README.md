# CN2 VPS plans: which AkkoCloud tier fits your traffic, what the 30–200 Mbps unmetered caps really allow, and what to confirm before checkout

AkkoCloud sells one CN2 line: San Jose, with CN2 GIA on the return path for all three Chinese carriers and CN2 GIA outbound for China Telecom. The choice is between 15 cart entries that differ in RAM, disk, monthly traffic and port speed. Metered plans run a 1000 Mbps port with a monthly allowance from 800 GB to 12 TB. Unmetered plans drop the monthly cap and cap the port instead, at 30, 50, 100 or 200 Mbps.

If you're putting a site, an API or a small app on it and your traffic is spiky, a metered plan is the better buy: you get the full gigabit when you need it and pay for a monthly ceiling rather than a permanent speed limit. If your transfer is flat and modest, the unmetered tier removes the counting, but run the port math below before you pay for "unlimited."

> **Shortlist:** the **A2 mini** annual plan (1 GB RAM, 15 GB SSD, 800 GB bidirectional) for one small site; **C1** (2 GB RAM, 30 GB SSD, 4 TB at 1000 Mbps) for anything with real traffic; **U2 or U3** if you want a flat port instead of a monthly counter.
> 👉 [Check current prices and stock for each San Jose CN2 plan](https://bit.ly/akkocloud)

## All 15 AkkoCloud CN2 plans in the cart

AkkoCloud sets the price per plan in the cart rather than on the plan list, and promotions move. What stays fixed is the spec sheet, so that's what the table below covers. Click through on the plan you're considering and read the figure on that page.

| Plan | vCPU / RAM | SSD | Monthly traffic and port | Billing | Order |
| --- | --- | --- | --- | --- | --- |
| KVM-CN2-A2 mini | 1 / 1024 MB | 15 GB | 800 GB bidirectional, 1000 Mbps | Annual promo | [ Order](https://bit.ly/akkocloud) |
| KVM-CN2-B1 mini | 1 / 1024 MB | 20 GB | 1200 GB bidirectional, 1000 Mbps | Annual promo | [ Order](https://bit.ly/akkocloud) |
| KVM-CN2-B1 | 1 / 1536 MB | 20 GB | 1500 GB bidirectional, 1000 Mbps | Standard | [ Order](https://bit.ly/akkocloud) |
| KVM-CN2-B2 | 1 / 2048 MB | 30 GB | 3000 GB bidirectional, 1000 Mbps | Standard | [ Order](https://bit.ly/akkocloud) |
| KVM-CN2-C1 | 1 / 2048 MB | 30 GB | 4000 GB bidirectional, 1000 Mbps | Standard | [ Order](https://bit.ly/akkocloud) |
| KVM-CN2-D1 | 2 / 2048 MB | 20 GB | 6000 GB bidirectional, 1000 Mbps | Standard | [ Order](https://bit.ly/akkocloud) |
| KVM-CN2-E1 | 4 / 8192 MB | 60 GB | 9000 GB bidirectional, 1000 Mbps | Standard | [ Order](https://bit.ly/akkocloud) |
| KVM-CN2-F1 | 4 / 8192 MB | 60 GB | 12000 GB bidirectional, 1000 Mbps | Standard | [ Order](https://bit.ly/akkocloud) |
| KVM-CN2-U1 | 2 / 2048 MB | 20 GB | Unmetered, 30 Mbps | Standard | [ Order](https://bit.ly/akkocloud) |
| KVM-CN2-U2 | 4 / 8192 MB | 50 GB | Unmetered, 50 Mbps | Standard | [ Order](https://bit.ly/akkocloud) |
| KVM-CN2-U3 | 4 / 8192 MB | 80 GB | Unmetered, 100 Mbps | Standard | [ Order](https://bit.ly/akkocloud) |
| KVM-CN2-U4 | 8 / 16384 MB | 100 GB | Unmetered, 200 Mbps | Standard | [ Order](https://bit.ly/akkocloud) |
| KVM-CN2-C1 old | 1 / 2048 MB | 30 GB | 4000 GB bidirectional, 1000 Mbps | Standard | [ Order](https://bit.ly/akkocloud) |
| KVM-CN2-U1 old | 2 / 2048 MB | 20 GB | Unmetered, 30 Mbps | Standard | [ Order](https://bit.ly/akkocloud) |
| KVM-CN2-E1 old | 4 / 8192 MB | 60 GB | 9000 GB bidirectional, 1000 Mbps | Standard | [ Order](https://bit.ly/akkocloud) |

Every entry ships **one IPv4 address**. None of them lists IPv6, additional IPs or a Windows licence, so budget for those separately if you need them.

The three "old" rows are worth a second look before you check out. C1 old has the same 1 vCPU, 2 GB, 30 GB, 4 TB spec as C1. U1 old matches U1. E1 old matches E1. They're legacy SKUs kept in the cart, not a cheaper or better variant, and picking one by accident is easy when the names differ by three characters.

## "Unlimited" at 30 Mbps is not the same as unlimited at 1 Gbps

Run the numbers on the port cap. Sustained 30 Mbps moves about 3.75 MB/s, which is roughly 324 GB a day, or around **9.7 TB over a 30-day month** if the pipe never idles. U1's theoretical ceiling is therefore higher than the 800 GB on the A2 mini. The catch is the "never idles" part. A backup job, a cron-driven sync or a site with a few hundred daily visitors will not saturate 30 Mbps around the clock, and you don't get a burst above it during a traffic spike.

Compare U1 with C1: C1 gives you 4 TB counted monthly but a 1000 Mbps port, so a 50 GB restore or a plugin update pushing a large file finishes in minutes instead of half an hour. U1 gives you no monthly counter and a 30 Mbps wall. Which one is "bigger" depends entirely on whether your traffic is bursty or flat.

The metered allowances count **both directions**. AkkoCloud labels them "bidirectional," so 800 GB means upload plus download combined, not 800 GB of downloads with uploads on the house. If you run off-site backups, push logs or accept large uploads, that halves the usable figure fast. Double your estimate before you pick a tier, and check whether the plan you're on has the headroom when the counter resets.

👉 [Compare the metered and unmetered entries side by side in the cart](https://bit.ly/akkocloud)

## What "three-network CN2 GIA" covers, and what it doesn't

AkkoCloud describes the San Jose route as three-network return CN2 GIA with CN2 GIA outbound for China Telecom. Read that carefully. The premium routing is stated for the **return** path across Telecom, Unicom and Mobile, while outbound premium is specified only for Telecom. If your workload is mostly Chinese visitors downloading from you, you get the full benefit. If it's mostly uploads from Chinese users into your server, or you care about Unicom and Mobile users on the outbound leg, the page doesn't promise the same treatment.

The page also publishes a looking glass and a test IP, then warns that the test IP doesn't represent the address range you'll be assigned and that the server isn't guaranteed to be on a native IP. Refund requests made on native-IP grounds are refused under the terms of service. Test from your own network before you buy, and treat "native IP" as something to verify on the deployed machine, not something to argue about after the fact.

A London looking glass exists too (Poplar, AS41378), so AkkoCloud has a European footprint. The CN2 GIA plans in the cart are the San Jose ones. Don't assume a London plan carries the same China routing until the product page says so.

## Five things to confirm before you pay

1. **Which SKU you clicked.** C1, C1 old, U1 and U1 old sit next to each other with near-identical names.
2. **The current price on that plan page.** Prices are set per plan in the cart and change with promotions, so a figure quoted in a review from a few months back is not a quote.
3. **Traffic direction.** Metered plans count both directions; unmetered plans count none but cap the port.
4. **Port speed against your workload.** 30 Mbps is fine for a monitoring node and painful for a media server.
5. **The terms on IP and refunds.** Native-IP complaints aren't a refund route here, and the plan list doesn't advertise a trial.

👉 [Read the plan terms and current stock before you order](https://bit.ly/akkocloud)

## How the alternatives price out

Two other CN2 lines come up constantly in this search, and they solve different problems.

| Provider / line | Entry plan | Spec | Price | Notes |
| --- | --- | --- | --- | --- |
| HostDare CSSD (LA, CN2 GIA) | CSSD0 | 1 core / 768 MB / 10 GB / 250 GB / 30 Mbps | $40.99/yr | 3-day refund, may be refused at 20%+ monthly bandwidth use; Windows needs your own licence |
| HostDare CSSD (LA, CN2 GIA) | CSSD2 | 2 cores / 2 GB / 50 GB / 1000 GB / 60 Mbps | $115.99/yr | Same line; CSSD3 and up recommended for Windows |
| HostDare CAMD (LA, CN2 GIA) | CAMD0 | 1 core / 768 MB / 10 GB / 250 GB / 30 Mbps | $45.99/yr | Same specs as CSSD0 at a higher price; listed as a separate AMD line |
| Tudcloud HK CN2 Unmetered | HK.KVM.1C1G | 1 vCPU / 1 GB / 10 GB / unlimited at 3 Mbps | $5.00/mo | Order page showed 0 available when checked |
| Tudcloud HK CN2 Premium | HK-400GB | 1 vCPU / 1.5 GB / 15 GB / 400 GB at 20 Mbps | $6.99/mo | Order page showed 0 available when checked |

The pattern: HostDare wins on annual entry price and offers a refund window with strings attached. Tudcloud's Hong Kong CN2 is cheap per month but slow per port, and its stock was empty on every Hong Kong CN2 plan at the time of checking. AkkoCloud's San Jose lineup competes on port speed and traffic volume, with 1000 Mbps on every metered plan and unmetered options up to 200 Mbps, which is a different bracket from a 3 Mbps Hong Kong box.

## Which plan to pick

- **One small site or a dev box, lowest entry cost:** A2 mini. 1 GB RAM and 15 GB SSD is enough for a static site, a small WordPress install or a build server.
- **Two or three sites, roughly 1 TB of real traffic:** B1 mini or B1. The extra 512 MB on B1 matters more than the 300 GB of traffic.
- **An app with 3–4 TB and bursty load:** C1. Two gigabytes of RAM and a 1000 Mbps port handle concurrent users better than any 1 GB plan.
- **Heavy transfer, 9–12 TB:** E1 or F1. They share the same 4 vCPU / 8 GB spec, so you're buying the traffic allowance, not more CPU.
- **Flat, predictable transfer with no spikes:** U1 or U2. Skip U4 unless you actually have eight cores' worth of work; 16 GB of RAM with a 200 Mbps ceiling is a narrow combination.
- **Windows or multiple IPs:** none of these plans lists either, so price those in before comparing totals.

One last check on the checkout page: confirm the billing cycle on the plan you picked. The two mini entries are marked as annual promos, and everything else is listed without a stated cycle, so the term you see in the cart is the term you're agreeing to.

👉 [Open the AkkoCloud cart and confirm the plan, price and billing cycle](https://bit.ly/akkocloud)
