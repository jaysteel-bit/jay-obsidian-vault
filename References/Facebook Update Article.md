## What Is Andromeda?

### The short version: Meta rebuilt the brain of its ad system

Before December 2024, when a user opened Facebook or Instagram, Meta’s ad system used a relatively simple process to decide which ads to show. It relied on rule-based logic, audience targeting settings you defined, and historical performance data to match ads with people.

That system no longer exists.

Meta replaced it with Andromeda - a completely new retrieval engine powered by deep neural networks that use computer vision and semantic analysis to read the actual content of your creatives and match them to individual users in real time.

![meta andromeda overview](https://cdn.confect.io/uploads/media/meta_andromeda_overview.jpg)

This is not a settings change or a minor algorithm tweak. It’s a full architectural rebuild of the first and most critical stage of ad delivery: retrieval.

### What “retrieval” means and why it matters

Meta’s ad delivery works in two stages. Most advertisers only think about the second one, the auction - where your bid, budget, and predicted performance determine whether your ad wins the impression.

But before the auction even happens, there’s a gatekeeper stage: retrieval. This is where Meta’s system scans tens of millions of active ads and narrows them down to roughly 1,000 candidates that get a ticket to compete in the auction.

If your ad doesn’t make it through retrieval, nothing else matters. Your targeting, your bid, your budget - none of it gets a chance to work.

Andromeda is that gatekeeper. And it works fundamentally differently from the old one.

The old retrieval system used rule-based heuristics and isolated model stages. It leaned heavily on the audience parameters you set; your interest targeting, your lookalike audiences, your custom audiences, to filter which ads reached which people.

Andromeda replaces all of that with end-to-end deep neural networks. Instead of asking “does this user match the advertiser’s targeting settings?”, it asks “does this creative match this individual user’s interests and behavior?”

![meta gem](https://cdn.confect.io/uploads/media/meta_andromeda_meta_gem.jpg)

The primary targeting mechanism has shifted from advertiser-defined audiences to AI-driven creative matching.

In other words: your creative now does most of the targeting work.

### 10,000x more complex - and what that actually means for your ads

Meta’s engineering team described Andromeda as enabling a “10,000x increase in model complexity” at the retrieval stage. That sounds impressive but abstract. Here’s what it means in practice for eCommerce advertisers:

**Andromeda reads your creatives.** The system uses computer vision and semantic analysis to understand what’s actually in your ad: the product, the style, the text, the colors, the mood. It doesn’t just look at your targeting settings or your pixel data. It looks at the ad itself.

**It clusters similar ads into one “entity.”** This is one of the most important changes. If you’re running ten variations of the same product shot with minor tweaks - different headline colors, slightly cropped images, small text changes - Andromeda treats them as a single creative entity. Ten ads, one retrieval ticket.

That means the old playbook of creating dozens of small variations and letting the algorithm pick a winner is now actively working against you. The system doesn’t see 50 ads. It sees 5, or 3, or sometimes just 1.

**It matches creatives to users, not audiences to ads.** Andromeda builds its own understanding of who would find your creative interesting, based on real-time signals. Your interest targeting still exists, but it’s now more of a soft suggestion than a hard filter. The system will override your targeting if the creative signals suggest a better match elsewhere.

**It rewards diversity and penalizes repetition.** Because each genuinely distinct creative gets its own entity ID, its own ticket to the auction, advertisers with more diverse creative libraries get more chances to be matched with different user segments. Advertisers running the same concept in 20 slightly different versions get one chance.

### Andromeda is not working alone

Andromeda handles retrieval, “the gatekeeper stage”. But Meta also introduced two other AI systems that work alongside it:

**Meta Lattice** handles the ranking stage (the auction itself). It delivered 10% metric gains and 6% conversion improvements according to Meta’s engineering team. Where Andromeda decides which ads get a chance, Lattice decides which ad wins.

![meta lattice](https://cdn.confect.io/uploads/media/meta_lattice_meta_andromeda.jpg)

**GEM (Generative Engagement Model)** is a generative foundation model that Meta says is 4x more efficient at driving performance. It’s the system behind Meta’s AI-powered creative tools like background generation and text variations.

Together, these three systems represent a complete overhaul. The retrieval is new. The ranking is new. The creative generation tools are new. The entire pipeline from “which ads exist” to “which ad wins the impression” has been rebuilt.

### What the old playbook got wrong

If you built your Meta advertising strategy before Andromeda, chances are it was built around principles that the new system either ignores or actively penalizes.

Here’s what changed:

**Narrow targeting → Broad audiences.** Andromeda’s creative-first matching makes narrow interest targeting largely redundant. The system finds the right people based on creative resonance, not audience definitions. Data from Lebesgue shows [broad targeting](https://confect.io/blog/dynamic-ads-broad-audiences) now delivers 49% higher ROAS compared to [lookalike targeting](https://confect.io/ad-glossary/audience-segmentation) under Andromeda.

**Few polished creatives → Many diverse creatives.** The old system rewarded finding one winning ad and scaling it. Andromeda rewards having 20–30 genuinely different creatives per ad set; mixing formats like [UGC](https://confect.io/ad-glossary/user-generated-content), studio shots, testimonials, product demos, and Catalog Ads. A controlled test by Five Nine Strategy showed that a single ad set with 25 diverse creatives produced 17% more conversions at 16% lower cost versus a traditional 5-ad-set structure.

![meta sequence learning](https://cdn.confect.io/uploads/media/meta_sequence_learning_meta_andromeda.jpg)

**Segmented campaigns → Consolidated structure.** Fragmenting your spend across many narrowly targeted ad sets used to be best practice. Under Andromeda, it starves the algorithm of learning data. [Fewer, broader ad sets](https://confect.io/tactics/advantage-shopping-campaigns-best-setup) with more creative diversity now outperform.

**Pixel-only tracking → Server-side tracking.** Andromeda uses conversion signal quality as a factor in retrieval. Pixel-only tracking now penalizes your ad quality score. Implementing the Conversions API with proper deduplication directly improves how often your ads make it through the retrieval gate.

**Long-running winners → Fast creative rotation.** [Creative fatigue](https://confect.io/ad-glossary/Ad-fatigue) has accelerated dramatically under Andromeda. Effective ad lifespan has compressed from 6–8 weeks pre-Andromeda down to just 2–4 weeks, because precision matching burns through optimal audiences faster. The system finds the best users for your creative quickly - and exhausts them quickly too.

### The rollout timeline

Andromeda didn’t appear overnight. Meta rolled it out in phases:

- **Late 2024:** Meta published the engineering details and began enrolling selected high-spending partner accounts.
- **Early 2025:** The rollout expanded to 18%–42% of ad accounts (our “30% phase”).
- **Mid 2025:** Enrollment reached 58%–82% of accounts (our “70% phase”).
- **October 2025:** Full global deployment completed. Every advertiser on Meta is now operating under Andromeda.

This phased rollout is actually useful for understanding impact, because it lets us compare performance across periods when different percentages of the market were on the new system.

That’s exactly what we did in this study. And the results are clear.

### Why this matters more for eCommerce than any other vertical

Andromeda affects all advertisers on Meta. But eCommerce companies face a unique combination of pressures under the new system:

Your ads are product-based, which means creative diversity isn’t just about different messaging angles; it’s about different products, different formats, different visual approaches to the same catalog.

Your conversion funnel depends on post-click behavior (landing pages, product pages, checkout), and Andromeda is sending fundamentally different traffic than the old system did.

And your competitive landscape is dense. Thousands of eCommerce advertisers all competing for the same retrieval tickets, with the algorithm now deciding who gets in based on creative quality rather than budget or targeting sophistication.

The good news: the data also shows that eCommerce advertisers who adapt, particularly through Catalog Ads, have a structural advantage under Andromeda that other verticals can’t easily replicate.

But first, let’s look at the damage.

## The Andromeda Impact - What the Data Shows

Andromeda has broadly suppressed performance across eCommerce advertisers on Meta. But the damage is not evenly distributed.

The following sections break down what changed - and who got hit - across ROAS, conversion rates, funnel position, advertiser size, price level, ad format, landing page type, catalog size, and ad lifecycle.

Every chart covers the same dataset: 115.7 billion impressions, $834M in ad spend, 3,014 advertisers, 73 countries, 2025.

### The headline: ROAS declined 7% with no sign of recovery

Across all 3,014 advertisers, Return On Ad Spend declined by 7% during the Andromeda rollout.

![Return On Ad Spend has declined 7% during the Andromeda update](https://cdn.confect.io/uploads/media/ROAS%20Return%20On%20Ad%20Spend%20has%20declined%207%20during%20the%20Andromeda%20update.jpg)

The line starts at approximately 9 ROAS at 0% rollout and drops to roughly 8.4 at full deployment. The sharpest decline happens early between 0% and 30% rollout, meaning the initial wave of adoption caused the biggest disruption. From there, it continues drifting downward through the 70% and 100% phases with no recovery signal.

This isn’t a temporary learning dip. It’s a new permanent baseline.

For an advertiser spending $100,000 per month, a 7% ROAS decline translates to roughly $7,000 in lost return - every month - that cannot be recovered by simply increasing budgets.

But 7% is a dangerous average. As we’ll see in the following sections, top performers lost 31% while bottom performers actually improved. Your reality could be far better or far worse than the headline number.

### The real culprit: conversion rates dropped 17%

Here’s what makes the ROAS decline so tricky to diagnose: Andromeda is not making your ads more expensive. It’s making the visitors they deliver less likely to buy.

![Traffic coming from Andromeda ads have a 17 lower Conversion Rate than before the Andromeda update Landing Page Conversion Rate during Andromeda Rollout](https://cdn.confect.io/uploads/media/Traffic%20coming%20from%20Andromeda%20ads%20have%20a%2017%20lower%20Conversion%20Rate%20than%20before%20the%20Andromeda%20update%20Landing%20Page%20Conversion%20Rate%20during%20Andromeda%20Rollout.jpg)

Landing page [conversion rates](https://confect.io/ad-glossary/conversion-rate) fell by 17% across the dataset: from approximately 3.5% at 0% rollout to roughly 2.9% at full deployment.

This reframes the entire problem. The fix doesn’t live inside Meta Business Manager. It lives on your website and landing pages.

Why is this happening? Andromeda uses computer vision and semantic analysis to match creatives to users based on content relevance, not purchase history. It’s reaching people who find your ad interesting, but who may not be actively shopping. The old system leaned heavily on pixel data and past purchase behavior to find high-intent converters. Andromeda deprioritizes those historical signals in favor of real-time creative resonance.

The result: broader reach, colder traffic, lower conversion rates.

For every 1,000 visitors your ads deliver, roughly 5 fewer are completing a purchase compared to pre-Andromeda. That compounds into significant revenue gaps at scale over weeks and months.

The steepest conversion rate decline happens mid-rollout (between 30% and 70%), suggesting that traffic quality degradation lagged behind the initial cost impacts shown in the ROAS chart. By full rollout, the line flattens at approximately 2.9%, establishing a new baseline that advertisers need to plan around.

### The funnel split: prospecting took a 13% hit

Andromeda is disproportionately punishing [prospecting campaigns](https://confect.io/tactics/catalog-ads-in-top-funnel-and-prospecting).

![Top funnel ads have seen a 13 drop in Return On Ad Spend from the Andromeda update](https://cdn.confect.io/uploads/media/Top%20funnel%20ads%20have%20seen%20a%2013%20drop%20in%20Return%20On%20Ad%20Spend%20from%20the%20Andromeda%20update.jpg)

Top-of-funnel prospecting ads saw a 13% ROAS decline, while retargeting remained relatively stable with only a modest dip.

This makes strategic sense. Prospecting campaigns target cold audiences by definition, and Andromeda’s broadened reach means these campaigns now serve even colder users than before. Retargeting campaigns, on the other hand, benefit from a built-in advantage: dynamic product ads show users the exact items they already viewed, giving Andromeda a strong relevance signal that prospecting creatives have to work much harder to replicate.

The gap between retargeting and prospecting ROAS has actually narrowed during the rollout - from about 4.2 points pre-Andromeda to about 4.2 points at full rollout - suggesting Andromeda is blurring traditional funnel boundaries as it increasingly decides on its own who sees what.

The implication for growth strategy is direct: if prospecting gets more expensive and less efficient, the pipeline of new customers feeding your retargeting audiences will shrink over time. Advertisers who gut their prospecting budget to prop up short-term retargeting ROAS will eventually hit a ceiling as their warm audience pools deplete without top-of-funnel replenishment.

### The great equalizer: top performers lost 31%

This is the most alarming finding in the entire study.

![Top performing advertisers have seen a 31 drop in Return On Ad Spend from the Andromeda update](https://cdn.confect.io/uploads/media/Top%20performing%20advertisers%20have%20seen%20a%2031%20drop%20in%20Return%20On%20Ad%20Spend%20from%20the%20Andromeda%20update.jpg)

The advertisers who were winning the most before Andromeda have been punished the hardest. Top performers, the top third of advertisers by ROAS within their industry, saw a 31% collapse in Return On Ad Spend, dropping from approximately 17 to roughly 11.0.

Mid performers barely moved. Bottom performers actually trended slightly upward.

Andromeda has acted as a great equalizer, compressing the performance gap between elite advertisers and everyone else.

Why? Because top performers were typically running hyper-optimized campaigns with a small number of proven creatives and precise audience targeting. That’s the exact opposite of what Andromeda’s creative-first retrieval engine rewards. These accounts relied on deep historical performance data that the old algorithm used to find high-intent converters. Andromeda deprioritizes those signals.

Worse: Andromeda’s entity clustering treats all minor creative variations as a single ad. A top performer running 15 polished variations of one winning concept effectively has one retrieval ticket. A bottom performer with 5 rough but genuinely different concepts has five.

The old playbook that built your competitive advantage is now your biggest liability.

### Size matters, but differently now

The traditional assumption that bigger budgets buy better results on Meta has been flipped.

![Big advertisers are hurt the most from the Andromeda update, due to slow creative approval processes](https://cdn.confect.io/uploads/media/Big%20advertisers%20are%20hurt%20the%20most%20from%20the%20Andromeda%20update,%20due%20to%20slow%20creative%20approval%20processes.jpg)

Mid-sized advertisers (spending $34,400–$172,400 per year on Conversion campaigns) are the clear winners. They’re the only size segment that actually improved ROAS during the Andromeda rollout, climbing from approximately 10.5 to roughly 11.0.

Big advertisers (spending over $172,400/year) declined consistently from approximately 8.7 to around 8.0.

Small advertisers (under $34,400/year) showed the most volatile trajectory - rising, dipping, then recovering - but ended up in a reasonably good position at approximately 10.0.

The reason the PDF slide itself names: **slow creative approval processes.** Big advertisers tend to run fewer, more polished creatives for longer periods. They have multi-layer approval chains, brand compliance reviews, and agency coordination that simply can’t keep pace with Andromeda’s demand for constant creative diversity.

Mid-sized advertisers hit the sweet spot. They have enough budget to generate meaningful conversion volume for Andromeda’s learning, but are still lean enough to iterate quickly on creative.

This is an organizational problem disguised as a platform problem. No amount of media buying optimization will fix it if internal workflows can’t produce and approve new creatives fast enough.

### The pricing sweet spot: mid-priced products win

Andromeda has reshuffled which price tiers perform best on Meta and the result is a complete inversion of the pre-Andromeda hierarchy.

![Shops with mid-priced products are handling Andromeda  better than high-end and affordable shops](https://cdn.confect.io/uploads/media/Shops%20with%20mid-priced%20products%20are%20handling%20Andromeda%20%20better%20than%20high-end%20and%20affordable%20shops.jpg)

[Mid-priced shops](https://confect.io/tactics/catalog-ads-for-mid-end-brands) are the only price segment that improved ROAS during the rollout, climbing from approximately 8 to roughly 9.5. They went from worst to best.

[High-end advertisers](https://confect.io/tactics/catalog-ads-for-high-end-and-luxury-brands) experienced a steep fall, dropping from a dominant ROAS of approximately 12 down to around 10 - a 17% loss.

[Affordable shops](https://confect.io/tactics/catalog-ads-for-affordable-low-cost-and-discount-brands) suffered the most dramatic reversal of all. They went from nearly 10 ROAS pre-Andromeda to roughly 6.5 at full rollout. A catastrophic 35% decline. From second-best to worst.

The three lines converge and cross near the 70% rollout mark, creating a visible inversion where the entire pre-Andromeda pricing hierarchy reshuffles.

Why? Mid-priced products occupy a conversion sweet spot. The purchase decision is neither so cheap that it attracts low-quality impulse clicks, nor so expensive that it requires multiple touchpoints beyond what a single ad can deliver. Andromeda’s broader, colder traffic has lower purchase intent. High-end products suffer because luxury purchases require trust and familiarity that cold audiences don’t have yet. Affordable shops get hurt by CPM compression; as Andromeda expands delivery to broader audiences, the cost to reach users stays similar, but low average order values can’t absorb rising acquisition costs.

### The new ad lifecycle: peak in week one, plateau after

Andromeda has fundamentally changed how ads perform over time.

![Advertisers spending 30-60 of their ad spend on Catalog Ads have seen ROAS decrease by 20](https://cdn.confect.io/uploads/media/Advertisers%20spending%2030-60%20of%20their%20ad%20spend%20on%20Catalog%20Ads%20have%20seen%20ROAS%20decrease%20by%2020.jpg)

Under the old system, ads would ramp up over 2–3 weeks as the algorithm gradually learned who to show them to. Under Andromeda, ads reach peak performance in their first week and then plateau. The traditional belief that patience and “learning phases” lead to progressively better results is no longer supported by the data.

The full Andromeda line starts at approximately 7.8 ROAS in week zero, climbs to around 8.8 by week one, and then flatlines - showing no meaningful improvement through weeks 2 and 3. By week 3, all rollout-stage lines converge between 8.2 and 8.8, regardless of when the ad launched.

This happens because Andromeda’s retrieval engine is extraordinarily efficient at finding the best-fit users for a given creative immediately. It creates a strong initial performance burst, but also depletes the optimal audience faster. Once the system has determined what kind of user responds to a creative, it quickly saturates that segment and has nowhere else to go with the same concept.

The implication: if your ad hasn’t performed by week one, it’s unlikely to improve. Replace it with something genuinely different.

### The landing page inversion: category pages collapsed 24%

This is one of the most immediately actionable findings in the entire study, because changing a landing page URL requires zero creative production and can be done in minutes.

![Ads sending traffic to category landing pages have declined by 24 while product pages and _home have improved slightly](https://cdn.confect.io/uploads/media/Ads%20sending%20traffic%20to%20category%20landing%20pages%20have%20declined%20by%2024%20while%20product%20pages%20and%20_home%20have%20improved%20slightly.jpg)

Category pages were the dominant landing page type before Andromeda, starting at approximately 12.5 ROAS. By full rollout, they had collapsed to roughly 9.5 - a 24% decline and the steepest single-variable drop in the study.

Meanwhile, product pages climbed from approximately 8 to around 9.0. Homepage destinations improved from roughly 6.5 to about 7.5. Both showed modest but consistent gains.

This is a complete inversion of the pre-Andromeda hierarchy.

Why? Andromeda delivers colder, top-of-funnel traffic that lacks brand context. Category pages present too many choices to users who don’t yet know what they’re looking for, creating decision paralysis and higher bounce rates. Product pages work better because they provide a focused, single-product experience that matches the item shown in the ad. Homepages work better because they typically include brand storytelling, social proof, and bestseller highlights that help cold audiences build the confidence to explore further.

Catalog Ads have a structural advantage here. They automatically link each product creative to its specific product page, ensuring perfect ad-to-page relevance without manual landing page management across hundreds of ads.

### Multi-creative formats are weathering Andromeda best

Andromeda has created a clear hierarchy of ad formats.

![Ad formats with multiple creatives have handled Andromeda better than Single Image & Video ads](https://cdn.confect.io/uploads/media/Ad%20formats%20with%20multiple%20creatives%20have%20handled%20Andromeda%20better%20than%20Single%20Image%20&%20Video%20ads.jpg)

[Single Image and Video ads](https://confect.io/blog/single-image-ads-and-single-video-ads-on-meta) dropped from approximately 9 ROAS to roughly 7.5 - a 17% decline that makes them the worst-performing format under Andromeda.

[Collection ads](https://confect.io/blog/collection-ads-and-instant-experiences-on-meta) started at approximately 9.8, peaked above 10.5 at the 70% rollout mark, and settled at roughly 9.2 at full rollout, showing the most resilience.

[Carousel ads](https://confect.io/blog/carousel-ads-for-facebook-and-instagram) held relatively steady, starting at approximately 8.3 and settling at about 8.5 at full rollout. A modest net improvement.

The gap between Collection and Single formats widened from less than 1 ROAS point pre-Andromeda to nearly 2 points at full rollout. The format choice penalty has effectively doubled.

This aligns directly with Andromeda’s core design: the algorithm rewards creative diversity, and multi-creative formats inherently provide multiple visual signals within a single ad unit. A Carousel ad with 10 genuinely different product cards gives the retrieval engine 10 distinct visual touchpoints. A Single Image ad gives it one.

### Bigger catalogs win: 5,000+ products as a competitive moat

Catalog size is now a competitive advantage under Andromeda.

![Advertisers with more products in their Catalogs are performing better with Andromeda](https://cdn.confect.io/uploads/media/Advertisers%20with%20more%20products%20in%20their%20Catalogs%20are%20performing%20better%20with%20Andromeda.jpg)

Advertisers with 5,000 or more products in their catalogs maintained the highest ROAS throughout the rollout, starting at approximately 11.0, peaking near 12 at 70% rollout, and settling back at roughly 11 at full deployment.

The 1,000–5,000 product group remained relatively stable, hovering between 8.5 and 9.0.

Small catalog advertisers with fewer than 1,000 products declined from approximately 8.5 to roughly 7.5 - confirming they’re increasingly disadvantaged.

The performance gap between the largest and smallest catalog groups widened from approximately 2.5 ROAS points pre-Andromeda to nearly 3.5 points at full rollout. Catalog size is becoming a progressively stronger differentiator.

Every product in your catalog is essentially a unique creative that Andromeda can match to a distinct user segment. A catalog with 5,000 products gives the algorithm 5,000 entry points. A static ad account with 20 creatives gives it 20 - or fewer, once entity clustering kicks in.

This finding has profound strategic implications. Catalog size isn’t something you can fake or quickly fix. Andromeda structurally favors retailers and brands with broad product assortments over niche single-product businesses.

For small catalog advertisers: compensate by maximizing creative diversity through multiple Catalog Ad variants with different designs, [overlays](https://confect.io/blog/frames-overlays-meta-catalog-ads-and-dynamic-product-ads), and formats for the same product set. A 500-product catalog with 3 design variants gives you 1,500 creative entities. A meaningful step toward closing the gap.

### The surprising decline of product field enrichment

This one is counterintuitive.

![Enriching Catalogs with more product fields has become less important during Andromeda](https://cdn.confect.io/uploads/media/Enriching%20Catalogs%20with%20more%20product%20fields%20has%20become%20less%20important%20during%20Andromeda.jpg)

Enriching your product catalog with more data fields - which was considered best practice before Andromeda - has become significantly less important.

Catalogs with many product fields (25+) started highest at approximately 9.7 ROAS but declined to roughly 8.6 at full rollout. Catalogs with few fields (under 15) started lowest at approximately 8 but actually improved to roughly 8.5. By full rollout, all three groups sit within a narrow 0.3 ROAS band compared to a 1.7-point spread before Andromeda.

The enrichment advantage has essentially evaporated.

Why? Andromeda’s retrieval engine relies primarily on computer vision and semantic analysis of the ad creative itself - not on structured product feed metadata. The system can now infer product type, style, color, and context directly from the product image, without needing those attributes spelled out in the feed.

This doesn’t mean product data is irrelevant. Accurate core fields like title, price, and availability still matter for basic functionality. But the relative priority of feed enrichment has dropped compared to other levers like creative diversity, catalog size, and ad format selection.

For resource-constrained teams, this is a liberating finding. Your time is better spent producing diverse creative variants and expanding your product count than obsessively perfecting every [custom label](https://confect.io/blog/custom-labels-dynamic-product-ads) and product attribute.

### The bottom line

Andromeda has suppressed performance broadly but the impact varies wildly depending on who you are and what you’re doing.

The worst hit: top performers, big advertisers, affordable products, single image/video ads, category landing pages, and small catalogs.

The most resilient - and in some cases improved: mid-sized advertisers, mid-priced products, multi-creative formats, product page destinations, and large catalogs.

The pattern is consistent across every dimension we measured. Andromeda rewards creative diversity, punishes repetition, favors product-level relevance, and sends broader, colder traffic that demands a different post-click experience.

The question is: what are the advertisers who are winning under Andromeda actually doing differently?

That’s what we’ll look at next.

## What Top Performers Are Doing Differently

Chapter 3 painted a tough picture. But the data also tells a very clear story about what separates the advertisers who are winning under Andromeda from those who are falling behind.

The gaps are not small. And they’re not random. They follow a pattern that shows up across every metric we measured.

Let’s walk through it.

### They’re running 33% more ads

The top-performing third of advertisers run 395 live ads on average. The bottom third runs 296.

![Top perfoming advertisers are launching 33 more ads than bottom performers](https://cdn.confect.io/uploads/media/Top%20perfoming%20advertisers%20are%20launching%2033%20more%20ads%20than%20bottom%20performers.jpg)

That’s a 33% gap - roughly 99 additional live ads at any given time.

This isn’t about throwing more money at the problem. It’s about giving Andromeda’s retrieval engine more creative options to work with. Each genuinely distinct creative gets its own path through the auction. More diverse ads means more chances to be matched with different user segments.

The 99-ad gap compounds over millions of impressions into a significant structural delivery advantage. When any single ad declines after its first-week peak, top performers already have dozens of alternatives ready to absorb that lost delivery. Bottom performers are still relying on a handful of long-running creatives, exactly the pattern Andromeda penalizes.

But here’s the thing: volume without diversity is counterproductive. Andromeda clusters similar-looking ads into a single entity, so 395 ads that all look the same perform no better than 10. The focus has to be on genuinely distinct concepts.

### They’re running 72% more Catalog Ads

The ad volume gap gets far more dramatic when you look at Catalog Ads specifically.

![Top performing advertisers are launching 72 more Catalog Ads than bottom performers](https://cdn.confect.io/uploads/media/Top%20performing%20advertisers%20are%20launching%2072%20more%20Catalog%20Ads%20than%20bottom%20performers.jpg)

Top performers run 67 live Catalog Ads. Bottom performers run 39. That’s a 72% gap - more than double the 33% gap in total ad volume.

This is the clearest signal in the study. Top performers aren’t just running more ads overall. They’re deliberately over-indexing on Catalog Ads specifically.

Why? Because Catalog Ads provide automatic creative diversity at the product level. Each Catalog Ad creative features a unique product image, title, and price that Andromeda treats as a separate entity. A single catalog ad backed by a 2,000-product [catalog](https://confect.io/ad-glossary/product-feed) creates thousands of distinct retrieval opportunities without requiring manual production for each one.

Catalog Ads also solve the creative fatigue problem structurally. As inventory changes, new products enter the catalog and old ones rotate out, providing continuous novelty without manual creative refreshes.

If you currently have fewer than 39 live Catalog Ads, you’re performing below even the bottom performer benchmark.

### They’re spending 117% more on Catalog Ads

It’s not just about running more Catalog Ads. Top performers are putting significantly more budget behind them.

![Top performing advertisers are spending 117 more on Catalog Ads than bottom performers](https://cdn.confect.io/uploads/media/Top%20performing%20advertisers%20are%20spending%20117%20more%20on%20Catalog%20Ads%20than%20bottom%20performers.jpg)

Top performers invest $155,000 on Catalog Ads annually, compared to $72,000 for bottom performers - a 117% gap. Mid performers sit at $118,000, creating a near-linear staircase from bottom to top.

This isn’t simply a function of bigger budgets. Performance groups are defined by ROAS within their industry, not by total spend. These advertisers are choosing to put more money behind Catalog Ads regardless of their overall budget size.

The three-part picture is now complete: top performers run 33% more ads overall, 72% more Catalog Ads specifically, and allocate 117% more budget to Catalog Ads. It’s a compounding commitment at every level.

### They get 60% of their revenue from Catalog Ads

This is the revenue headline.

![Top performing advertisers get 60 of their revenue from Catalog Ads](https://cdn.confect.io/uploads/media/Top%20performing%20advertisers%20get%2060%20of%20their%20revenue%20from%20Catalog%20Ads.jpg)

Top-performing advertisers generate 60% of their total ad revenue from Catalog Ads. Bottom performers generate 38%. That’s a 22 percentage point gap that represents a fundamentally different business model for paid social.

Catalog Ads are no longer a supplementary retargeting tactic for the best advertisers. They are the majority revenue engine, driving more than half of all sales generated through Meta advertising.

The staircase from 38% to 44% to 60% mirrors the spend pattern, but the revenue share exceeds the spend share at every level. Catalog Ads return disproportionately more revenue per dollar invested.

If Catalog Ads represent less than 40% of your revenue, you’re leaving significant money on the table.

### The head-to-head: Catalog Ads vs. Static Ads

So why are Catalog Ads outperforming? Let’s look at the numbers side by side.

The average advertiser in this study produces 3.3 times more static ads than Catalog Ads (341 vs. 103). Yet each Catalog Ad generates 3.6 times more revenue ($30,553 vs. $8,438), 4 times more purchases (210 vs. 51), and nearly 3 times more impressions (475,871 vs. 160,419).

![Many advertisers are over-investing in creating Static Ads - despite Catalog Ads being far easier to scale](https://cdn.confect.io/uploads/media/Many%20advertisers%20are%20over-investing%20in%20creating%20Static%20Ads%20-%20despite%20Catalog%20Ads%20being%20far%20easier%20to%20scale.jpg)

The industry is over-investing creative resources in the wrong format. The majority of creative production effort goes toward static ads; the lower-performing, harder-to-scale type.

One great Catalog Ad design template applied across 500 products generates more output than 50 individual static ads. And Catalog Ads stay live 30% longer on average (6.6 weeks vs. 5.1 weeks), because the product-level rotation provides natural novelty that delays fatigue.

Here’s the head-to-head on performance metrics:

![Catalog Ads are seeing 23 higher Return On Ad Spend and 37 better Cost Per Purchase than Static Ads](https://cdn.confect.io/uploads/media/Catalog%20Ads%20are%20seeing%2023%20higher%20Return%20On%20Ad%20Spend%20and%2037%20better%20Cost%20Per%20Purchase%20than%20Static%20Ads.jpg)

Catalog Ads win on the four metrics that matter most for profitability: ROAS, CPA, CTR, and CPM.

Static Ads lead on conversion rate and average order value but these advantages aren’t enough to offset the efficiency gains Catalog Ads deliver on cost and engagement. The lower conversion rate reflects that Catalog Ads are doing more prospecting work, reaching new audiences where conversion rates are naturally lower. The lower AOV means catalogs drive higher volumes of more accessible purchases rather than relying on fewer high-ticket conversions.

The net result: 23% better ROAS and 37% better CPA.

Don’t be alarmed by the lower conversion rate. The higher CTR and lower CPM mean you’re getting dramatically more traffic at a dramatically lower cost, and the math works out in Catalog Ads’ favor at the bottom line.

### The spend curve: more Catalog Ads = better performance at every level

This is the single most actionable finding in the entire study.

![The more advertisers spend on Catalog Ads, the better performance they typically see](https://cdn.confect.io/uploads/media/The%20more%20advertisers%20spend%20on%20Catalog%20Ads,%20the%20better%20performance%20they%20typically%20see.jpg)

The more advertisers spend on Catalog Ads as a share of total budget, the better their performance across every key metric:

The relationship is not marginal. Advertisers allocating 60–100% of spend to Catalog Ads achieve 44% higher ROAS, 68% lower CPA, and 63% higher CTR compared to those spending less than 30%.

The CPA improvement is staggering. It drops from $100 to $32.2 - meaning the highest Catalog Ad allocators acquire customers for less than one-third the cost.

If you’re currently in the 0–30% tier, moving to 30–60% alone would cut your CPA by more than half. That’s the single highest-ROI budget decision available.

### It works across every industry

You might wonder: does this just apply to certain product categories?

No. The Catalog Ad advantage holds across every single industry vertical in the study. Zero exceptions.

![The more advertisers spend on Catalog Ads, the better performance they typically see across industries](https://cdn.confect.io/uploads/media/The%20more%20advertisers%20spend%20on%20Catalog%20Ads,%20the%20better%20performance%20they%20typically%20see%20\(2\).jpg)

Electronics advertisers see the most dramatic uplift at 131%. Sports achieves the highest absolute ROAS at 16.9 for high Catalog Ad spenders. Even the lowest-performing vertical at high catalog spend (Food & Drinks at 8.6) still significantly outperforms the overall study average.

No matter what you sell, the data says the same thing: advertisers who allocate 60–100% of spend to Catalog Ads consistently outperform those spending under 30%.

### It works across every advertiser size

The budget-size objection doesn’t hold up either.

![Spending more on Catalog Ads is correlated to better performance across all sizes of advertisers](https://cdn.confect.io/uploads/media/Spending%20more%20on%20Catalog%20Ads%20is%20correlated%20to%20better%20performance%20across%20all%20sizes%20of%20advertisers.jpg)

Increasing Catalog Ad spend improves ROAS for small, mid, and big advertisers alike.

Mid-sized advertisers benefit the most, climbing from approximately 8 ROAS at low catalog spend to 13 at high, a 63% improvement. This connects directly to Chapter 3: mid-sized advertisers were already outperforming under Andromeda, and now we see the mechanism. They’re combining their natural agility with heavier Catalog Ad investment.

Big advertisers, identified as the most impacted by Andromeda in Chapter 3, see meaningful recovery from 7 to nearly 10 ROAS when they shift to high Catalog Ad spend. Catalog Ads offer a structural workaround for their biggest problem (slow creative approval) because product catalogs generate diversity automatically, without requiring manual production or approval cycles.

Small advertisers see consistent gains from 8 to 10.5, a 31% uplift that maximizes the impact of every limited dollar.

### Catalog Ads work across the entire funnel

One of the most persistent myths about Catalog Ads is that they’re a [retargeting](https://confect.io/tactics/catalog-ads-in-bottom-funnel-and-retargeting)-only format. The data destroys this completely.

![The more advertisers invest in Catalog Ads, the better performance they see across the whole funnel](https://cdn.confect.io/uploads/media/The%20more%20advertisers%20invest%20in%20Catalog%20Ads,%20the%20better%20performance%20they%20see%20across%20the%20whole%20funnel.jpg)

Increasing Catalog Ad spend improves performance across the entire funnel:

- **Retargeting ROAS** climbs from approximately 9.5 at low catalog spend to roughly 12 at mid, then surges to nearly 19 at high catalog spend. That’s close to doubling.
- **Prospecting ROAS** rises steadily from approximately 6.8 to 7.5 to 10 - a 47% improvement that makes prospecting Catalog Ads perform better than most advertisers’ total account average.

Think of Catalog Ad investment as a [full-funnel](https://confect.io/blog/dynamic-product-ads-in-a-full-funnel-strategy) flywheel. More prospecting catalog spend creates larger retargeting pools. Catalog Ads then convert those retargeting audiences at exponentially higher rates. The combined full-funnel return is far greater than either stage alone.

The retargeting curve is exponential, not linear. The gains accelerate as you move from 30–60% catalog spend to 60–100%. This suggests a compounding effect that rewards the most committed catalog advertisers disproportionately.

### The lifecycle advantage: 20–30% higher ROAS from week zero to week six

The final piece: Catalog Ads don’t just outperform at launch. They maintain their advantage over the entire ad lifecycle.

![Catalog Ads keep over-performing Static Ads over time with a 20-30 margin](https://cdn.confect.io/uploads/media/Catalog%20Ads%20keep%20over-performing%20Static%20Ads%20over%20time%20with%20a%2020-30%20margin.jpg)

Catalog Ads maintain a consistent 20–30% ROAS advantage over Static Ads across every week from launch through week six and beyond.

Catalog Ads start at approximately 9 ROAS in week zero, peak at roughly 11 in week one, then gradually settle to about 9.5 by week six. Static Ads follow a parallel but lower trajectory starting around 7.0, peaking at roughly 8.8 in week two, and declining to about 8 by week six.

The gap never narrows or closes. Not at any point in the lifecycle.

This happens because Catalog Ads have a built-in fatigue resistance mechanism. Even as a Catalog Ad ages, the [product feed](https://confect.io/ad-glossary/product-feed) behind it continues rotating different products to different users. A Static Ad is one creative that fatigues as a unit. A Catalog Ad backed by hundreds of products maintains freshness at the product level.

The practical implication: set different refresh schedules. Static ads should rotate every 2–3 weeks. Catalog Ads can run longer at 4–6 weeks before needing design template refreshes. Don’t pause a well-performing Catalog Ad at 2 weeks just because your static ads need rotation - the data shows catalogs maintain strong performance through week 4 and beyond.

### The pattern is unmistakable

Across every dimension we measured - ad volume, Catalog Ad volume, spend allocation, revenue share, performance metrics, industry, advertiser size, funnel position, and ad lifecycle - the same pattern emerges.

Top performers have built their entire Meta advertising operation around Catalog Ads. They run more of them, spend more on them, earn more from them, and use them across both prospecting and retargeting.

The gap between top and bottom performers isn’t one or two tactical choices. It’s a systematic orientation toward the ad format that Andromeda’s retrieval engine rewards most.

But running more Catalog Ads is just the foundation. The most sophisticated advertisers go further, using five specific advanced tactics that amplify their Catalog Ad performance even more.

That’s what we’ll cover next.

## Five Advanced Catalog Ad Tactics of Top Performers

Running more Catalog Ads and spending more on them is the foundation. But the most sophisticated advertisers in this study go further, using five specific advanced techniques that amplify their Catalog Ad performance even more.

Each of these tactics shows a measurable adoption gap between top and bottom performers. The gaps range from 38% to 103%. And each one comes with real-world case studies proving the impact isn’t theoretical.

Here’s the full picture of what top performers are doing that everyone else isn’t:

- Design Rules: +103%
- Multiple formats: +75%
- Video Catalog Ads: +62%
- Product Assets: +56%
- 5+ Creative Variants: +38%

Let’s look at each one.

### Running 5+ creative variants (+38% adoption gap)

Top performers are 38% more likely to use [5 or more creative variants](https://confect.io/features/multiple-designs) for their Catalog Ads.

![Top performers are 38 more likely to use 5+ variants compared to Bottom Performers](https://cdn.confect.io/uploads/media/Top%20performers%20are%2038%20more%20likely%20to%20use%205+%20variants%20compared%20to%20Bottom%20Performers.jpg)

This is not about minor tweaks to the same design. Five or more variants means running genuinely different visual approaches for the same product catalog: a [price-focused layout](https://confect.io/blog/showing-prices-in-dynamic-product-ads), a lifestyle overlay, a [social proof](https://confect.io/blog/reviews-and-ranking-in-dynamic-product-ads) design, a minimal product-only template, and a [seasonal campaign](https://confect.io/tactics/catalog-ads-black-friday-week-cyber-monday) version.

Why does this matter so much for Andromeda? Because entity clustering treats visually similar Catalog Ad designs as a single creative entity. If you run one design template across your entire catalog, you get one retrieval ticket. Five distinct templates give you five.

Different visual approaches also appeal to different psychological motivators. A price-focused design attracts deal seekers. A lifestyle overlay attracts aspirational buyers. A social proof design attracts risk-averse shoppers. Each variant unlocks a separate audience segment that the others can’t reach.

The adoption gap between bottom and mid performers (+37%) is nearly identical to the gap between bottom and top (+38%), suggesting there’s a threshold effect: once you cross the 5-variant mark, the benefit is immediate.

#### Case study: Vero Moda got a +60% increase in sales

Vero Moda, one of the biggest women’s fashion brands in the world, achieved a 60% increase in sales and a 46% increase in traffic by running multiple distinct Catalog Ad variants simultaneously.

![vero moda dpa design catalog ads fashion women meta overlay](https://cdn.confect.io/uploads/media/vero-moda-dpa-design-catalog-ads-fashion-women-meta-overlay.jpg)

Their approach wasn’t random. They systematically tested different hypotheses, starting with the most impactful changes first:

1. First testing different types of product imagery (model shots vs. packshots vs. combinations)
2. Then testing which product information to include (price vs. no price, category labels vs. [product names](https://confect.io/blog/product-name-in-dynamic-product-ads))
3. Then testing smaller elements (payment methods, styling details)

![vero moda girl catalog ads meta design girls fashion clothing](https://cdn.confect.io/uploads/media/vero-moda-girl-catalog-ads-meta-design-girls-fashion-clothing.jpg)

Their best-performing variant combined a model image with a packshot, giving shoppers both a styled view and a detail view of the product. They also created audience-specific variants for sub-brands: Vero Moda Girl (highlighting age range 6–16), Vero Moda Curve (displaying size range 44–54), and Vero Moda Maternity (featuring adjustable waistbands and stretch fabrics).

![vero moda maternity women fashion dpa catalog ads facebook](https://cdn.confect.io/uploads/media/vero-moda-maternity-women-fashion-dpa-catalog-ads-facebook.jpg)

Each sub-brand variant included tailored messaging that spoke directly to that specific customer segment.

The takeaway: different audiences need different information. Variants let you deliver that personalization at scale.

[Read the full case study here.](https://confect.io/cases/vero-moda-increased-catalog-ads-performance-by-60-with-confect)

![vero moda curve meta catalog ads dpa women fashion](https://cdn.confect.io/uploads/media/vero-moda-curve-meta-catalog-ads-dpa-women-fashion.jpg)

#### Case study: Bed Kingdom & Connective3 achieved a 58% lower CPA

Bed Kingdom, working with agency Connective3, improved CPA by 58% when running multiple Catalog Ad variants simultaneously - proving the approach works beyond fashion, in the home and furniture category.

![Bed Kingdom - kid beds](https://cdn.confect.io/uploads/media/Bed%20Kingdom%20-%20kid%20beds%201.png)

[Read the full case study here.](https://confect.io/cases/how-bed-kingdom-and-connective3-improved-cpa-by-58-with-confect)

### Using multiple placement formats (+75% adoption gap)

Top performers are 75% more likely to use [multiple ad formats](https://confect.io/tactics/meta-adapt-to-placement-story-9-16-catalog-ads) than bottom performers, the second largest adoption gap in this section.

![Top performers are 75 more likely to use Multiple Formats than Bottom performers](https://cdn.confect.io/uploads/media/Top%20performers%20are%2075%20more%20likely%20to%20use%20Multiple%20Formats%20than%20Bottom%20performers.jpg)

Using multiple formats means creating Catalog Ad designs optimized for different aspect ratios and placements: 1:1 for Feed, 4:5 for mobile Feed, and [9:16](https://confect.io/ad-glossary/9x16-aspect-ratio) for [Stories and Reels](https://confect.io/features/story-catalog-ads). Instead of uploading one square image and letting Meta crop it awkwardly for vertical placements, you give the algorithm a natively designed creative for each surface.

This matters for two reasons.

First, a single 1:1 square creative forced into a 9:16 Stories placement gets cropped or letterboxed. It looks bad, reduces engagement, and Andromeda’s ranking system interprets that weaker performance as a lower-quality creative signal - deprioritizing your ad.

Second, multiple formats effectively multiply your entity count. A product shown in 1:1 Feed format, 4:5 mobile format, and 9:16 Stories format registers as three distinct visual entities in Andromeda’s retrieval system, tripling your retrieval opportunities from a single product.

Bottom performers typically upload one format and rely on Meta’s automatic cropping. That’s leaving performance on the table.

#### Case study: SOFACOMPANY got a +85% higher ROAS and a +28% higher AOV

SOFACOMPANY achieved 85% higher ROAS and 28% higher average order value simply by creating [placement-adapted formats](https://confect.io/tactics/meta-adapt-to-placement-story-9-16-catalog-ads) for their Catalog Ads across 1:1, 4:5, and 9:16 ratios.

![Designed for 1_1 and 9_16 instead of simply resized](https://cdn.confect.io/uploads/media/Designed%20for%201_1%20and%209_16%20instead%20of%20simply%20resized%20\(2\).png)

The designs were tailored for each placement, not just resized - ensuring the product was always prominent, the text always readable, and the layout always native to the viewing context.

[Read the full case study here.](https://confect.io/catalog-ad-of-the-week/SOFACOMPANY)

#### Case study: LEO LIN & Elephant Room achieved a +82% higher ROAS and a +81% higher CVR

Australian luxury fashion brand LEO LIN, working with agency Elephant Room, achieved 82% higher ROAS and an 81% higher conversion rate when using format-adapted Catalog Ads - proving the impact is consistent across very different product categories and price points.

![Adaptability & using fashion editorial aesthetics](https://cdn.confect.io/uploads/media/Adaptability%20&%20using%20fashion%20editorial%20aesthetics.png)

[Read the full case study here.](https://confect.io/catalog-ad-of-the-week/LEO-LIN-and-Elephant-Room)

### Using Design Rules (+103% adoption gap)

This is the biggest behavioral differentiator between top and bottom performers in the entire study. Top performers are 103% more likely to use [Design Rules](https://confect.io/features/assets-design-rules), more than double the adoption rate of bottom performers.

![Top performers are 103 more likely to use Design Rules than Bottom performers](https://cdn.confect.io/uploads/media/Top%20performers%20are%20103%20more%20likely%20to%20use%20Design%20Rules%20than%20Bottom%20performers.jpg)

Design Rules allow advertisers to dynamically change creative elements based on product-level data. A [sale badge](https://confect.io/blog/showing-discounts-in-dynamic-product-ads) appears only when a product is actually discounted. A seasonal message activates only during campaign periods. A low-stock urgency signal shows only when inventory is running thin. All of this happens automatically without manually swapping creatives.

This is powerful for Andromeda because each conditional variation creates a genuinely different visual output. A product shown with a sale badge, the same product shown with a seasonal overlay, and the same product shown with a social proof element register as three different visual entities in the retrieval system. One design template with 4 conditional rules can produce dozens of visually distinct outputs depending on product data.

At 103%, this is the largest gap of any advanced feature, far exceeding 5+ variants at 38%, multiple formats at 75%, product assets at 56%, and video catalog ads at 62%.

#### Case study: Humac and their +42% higher conversion rate

Humac, the biggest Apple retailer in Scandinavia, improved conversion rates by 42% and click-through rates by 23% during Christmas using Design Rules to dynamically adapt their Catalog Ads messaging.

![humac meta catalog ads for facebook christmas buy now pay later](https://cdn.confect.io/uploads/media/humac-meta-catalog-ads-for-facebook-christmas-buy-now-pay-later-1.jpg)

Their approach was layered and time-sensitive:

- **December 1st:** Catalog Ads automatically switched from the always-on design to a Christmas design, highlighting 100-day return rights and Buy Now Pay Later options - removing friction for gift buyers.
- **December 18th:** The design shifted again to emphasize Click & Collect availability through December 23rd, answering the number one concern of late shoppers: “Will it arrive in time?”
- **December 24th:** The design automatically reverted to the always-on template.

All of this was set up in advance using Confect’s scheduled design rules. No manual creative swaps. No resetting Meta’s learning phase. The ads adapted automatically to the most relevant message for that moment in time.

They also used product-level rules: for products above their average Buy Now Pay Later order value, the design highlighted monthly payment amounts. For products below that threshold, it emphasized the 100-day return guarantee instead. Different products, different consumer concerns, different messaging, all automatic.

[Read the full case study here.](https://confect.io/cases/humac-increased-catalog-ads-performance-by-42-with-confect)

#### Case study: Charli & Prospa - a +313% increase in new customer purchases

Fashion brand Charli, working with agency Prospa, achieved a 313% increase in new customer purchases by using Design Rules to add contextual messaging like best-selling badges and seasonal collection labels to their Catalog Ads. That’s not a typo, 313%.

![](https://cdn.confect.io/uploads/media/Charli%20Story%20format.png)

[Read the full case study here.](https://confect.io/cases/how-charli-prospa-achieved-a-313-increase-in-new-customer-purchases)

### Using Product Assets (+56% adoption gap)

Top performers are 56% more likely to use [Product Assets](https://confect.io/blog/product-assets-in-dynamic-product-ads) in their Catalog Ads.

![Top performers are 56 more likely to use Product Assets than Bottom performers](https://cdn.confect.io/uploads/media/Top%20performers%20are%2056%20more%20likely%20to%20use%20Product%20Assets%20than%20Bottom%20performers.jpg)

Product Assets are dynamic visual elements pulled from product-level data - [brand logos](https://confect.io/blog/brand-in-dynamic-product-ads), certification badges, color swatches, lifestyle imagery - that are automatically overlaid onto Catalog Ad creatives, adding rich visual context without manual design work per product.

The adoption pattern here is unique. Mid performers are only 6% ahead of bottom performers, the smallest inter-tier gap of any advanced feature. But top performers leap 56% ahead. This suggests Product Assets are a late-stage optimization that the very best advertisers have discovered, while the broader market hasn’t caught on yet.

That gap is your opportunity. Because most of your competitors haven’t implemented this, there’s a significant first-mover advantage available.

Product Assets add visually distinct elements that Andromeda’s computer vision can detect. A product shown with a brand logo registers as a different visual entity than the same product without one. Brand logos and certification badges also act as instant trust signals for cold audiences who don’t yet know your store but recognize the product brand - directly addressing the conversion rate challenge from Andromeda’s broader traffic.

#### Case study: HiFi Klubben made a +48% increase in ROAS

HiFi Klubben, a premium electronics retailer, achieved a 48% increase in ROAS by dynamically displaying manufacturer brand logos like Denon and NAD on their Catalog Ads.

![hifi klubben circled price catalog ad example headphones and vinyl player](https://cdn.confect.io/uploads/media/hifi-klubben-circled-price-catalog-ad-example-headphones-and-vinyl-player.jpg)

For a [multi-brand retailer](https://confect.io/tactics/catalog-ads-for-multi-brand-retailers) selling products from many manufacturers, showing each brand’s logo builds trust that a generic retailer creative can’t match - especially when reaching cold audiences through Andromeda.

[Read the full case study here.](https://confect.io/catalog-ad-of-the-week/hifi-klubben)

#### Case study: Bulk increased ROAS by +43%

Bulk, a health and fitness brand, achieved a 43% increase in ROAS by combining Product Assets with dynamic social proof. Each product in their Catalog Ads is paired with a real customer review quote, reviewer name, profile photo, and “Verified Purchase” badge, all pulled automatically from product-level data.

![attention grabbing background bulk facebook catalog ad example](https://cdn.confect.io/uploads/media/attention-grabbing-background-bulk-facebook-catalog-ad-example.jpg)

The reviews aren’t generic. They’re matched to each product’s specific benefits and common objections: “Tastes great” for protein powder, “Pushing heavier weights” for creatine, “This is like rocket fuel” for pre-workout.

The result: testimonial-powered Catalog Ads at scale, with zero manual design per product.

[Read the full case study here.](https://confect.io/catalog-ad-of-the-week/bulk)

### Using Video Catalog Ads (+62% adoption gap)

Top performers are 62% more likely to use [Video Catalog Ads](https://confect.io/blog/video-catalog-ads-on-meta) - the fifth and final advanced tactic.

![Top performers are 62 more likely to use Video Catalog Ads than Bottom performers](https://cdn.confect.io/uploads/media/Top%20performers%20are%2062%20more%20likely%20to%20use%20Video%20Catalog%20Ads%20than%20Bottom%20performers.jpg)

[Video Catalog Ads](https://confect.io/product/video) combine the product-level dynamic personalization of Catalog Ads with the engagement power of video. They simultaneously satisfy Andromeda’s demand for creative diversity and Meta’s aggressive push toward video-first content across Reels and Stories.

Like Product Assets, the adoption pattern shows a split: mid performers are only 21% ahead of bottom performers, but top performers leap to 62%. This is an advanced capability that the most sophisticated advertisers have embraced while the majority of the market lags behind.

Video Catalog Ads register as entirely different entity types in Andromeda’s clustering system compared to static Catalog Ads of the same product. That effectively doubles the retrieval opportunities for any product that has both a static and video creative.

Andromeda’s computer vision extracts richer signals from video than from static images - motion patterns, product demonstration sequences, visual storytelling cues - giving the retrieval engine more data for precise user matching.

#### Case study: Baum und Pferdgarten & Besocial got a +36% higher ROAS with Product Level Videos

Baum und Pferdgarten, working with agency Besocial, achieved 36% higher ROAS when using Video Catalog Ads that dynamically animated product images into short video sequences. No expensive video shoots required - the videos were generated automatically from static product imagery, making the approach scalable across the entire catalog.

[Read the full case study here.](https://confect.io/cases/BeSocial-increased-ROAS-by-36-for-Baum-und-Pferdgarten-with-Confect)

### The compounding effect

Each of these five tactics is powerful on its own. But the real advantage comes from combining them.

A Catalog Ad using all 5 advanced tactics - 5+ design variants, multiple placement formats, Design Rules, Product Assets, and Video - creates the most complete creative ecosystem that Andromeda can work with. Each layer multiplies the number of distinct visual entities the retrieval engine can evaluate, giving you exponentially more paths through the auction.

Think of it as a multiplication problem:

**500 products** × **5 design variants** × **3 placement formats** × **3 Design Rules** × **2 formats** (static + video) = **tens of thousands of unique creative combinations.**

That’s tens of thousands of retrieval tickets. All from one product catalog.

No amount of manual static ad production can compete with that kind of scale.

So feed the Andromeda Machine. 
That in turn would mean you have a large volume of content like ads to feed it. Since the new update favors creative that looks as similar to content as possible. So building a content producing system is of great importance. 