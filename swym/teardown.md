# Swym Product Teardown

Oct 7, 2026 · Prashant Kumar

Swym is the most-installed wishlist app on Shopify, and it is trying to turn that position into something bigger: the place where a store records what each shopper wants before they buy, and passes that signal to the store's email, text-message and in-store tools. The product is strong and proven. Its weakest point is commercial: pricing is capped by usage, and when a store runs past its cap the wishlist is switched off on the live storefront.

## How to read this document

Every important claim carries one of three labels.

- **FACT** — a source I opened says this directly. The link sits beside the claim or in the source register (Part 65).
- **INFERENCE** — my reasoned conclusion from the facts.
- **HYPOTHESIS** — a plausible reading that public information cannot confirm.

Recommendations, scores and rankings are my judgement, not facts. Where a number does not exist in public, I write “Not publicly available.” I have not operated a live Swym account. The workflow and UX analysis is built from Swym's help centre, release notes, App Store listings and merchant reviews, and I say so again where it matters.

A few terms appear throughout. Each is explained once here.

| Term | Plain meaning |
| --- | --- |
| Merchant | The online store. The merchant is Swym's paying customer. |
| Shopper | The store's customer. Shoppers use the wishlist but never pay Swym. |
| Wishlist action | Swym's billing unit. One product added to a wishlist counts as one action. |
| Intent signal | Any sign that a shopper wants a specific product: a save, a restock sign-up, repeated views. |
| Zero-party data | Information a shopper gives the store on purpose, such as saving a product. It differs from data collected by tracking. |
| ESP (email service provider) | The tool that sends a store's marketing emails and texts. Klaviyo is the most common one on Shopify. |
| Flow | An automated message sequence inside an ESP. An event starts it, such as “the price dropped on a saved product”. |
| BIS | Back in stock. |
| PDP (product detail page) | The page for a single product. |
| POS (point of sale) | The till system in a physical shop. Shopify sells one. |
| Shopify Plus | Shopify's plan for large stores. |
| BFCM | Black Friday and Cyber Monday, the peak sales weekend. |
| PLG (product-led growth) | Customers find, try and buy the product themselves, with no salesperson. |
| ICP (ideal customer profile) | The type of customer the product fits best. |
| API, SDK, webhook | Three ways for software to talk to software. An API answers requests. An SDK is ready-made code for using an API. A webhook pushes a message when something happens. |
| Headless store | A store whose front end is custom-built and only uses Shopify behind the scenes. |

## Part 1 — Executive summary

### The 12 answers

1. **What is the product?** Swym is a family of Shopify apps that let shoppers save products they are not ready to buy, and let the store follow up. FACT: Swym publishes three apps: Wishlist Plus, Back in Stock Alerts, and Gift Lists and Registries ([Shopify developer page](https://apps.shopify.com/partners/developer-ca6a967f09890f68)). Wishlist Plus is the flagship, with 1,481 reviews at 4.7 stars since its July 2016 launch ([App Store listing](https://apps.shopify.com/swym-relay)).
2. **Who is it for?** Shopify stores where people browse and compare before they buy. FACT: Swym markets to four verticals: fashion, beauty, home and jewellery ([homepage](https://www.getswym.com/)). FACT: Store Leads detects the app on 64,525 Shopify stores, 37.4% of them apparel ([Store Leads](https://storeleads.app/reports/shopify/app/swym-relay)). The buyer is usually the person who runs ecommerce or retention marketing.
3. **What problem does it solve?** Most visitors leave a store without buying, and the store keeps no record of which product each one wanted. Swym records the product, links it to an email or phone number where it can, and sends a message when something changes: time passes, the price drops, or stock returns.
4. **Why do customers pay?** A message about a product the shopper chose converts far better than a general newsletter, and the fee is small next to the sales recovered. FACT: Swym's own case studies report returns of 16.6 times to 239 times the fee ([homepage](https://www.getswym.com/)). INFERENCE: those are best cases. They count any order that followed a Swym message, not only orders that would not have happened anyway.
5. **Core value proposition.** Turn “not yet” into a later sale, automatically, using what the shopper already told the store.
6. **Primary workflow.** Shopper saves a product → Swym stores it against an anonymous browser ID or a customer account → the shopper shares an email or phone number → Swym sends an event to the store's ESP or its own mailer → a reminder or alert goes out → the shopper returns and buys → the merchant sees revenue credited to the wishlist.
7. **Core product loop.** More saves → more identified shoppers with product-level signals → more triggered messages → more recovered orders → the merchant sees revenue in the dashboard → the merchant turns on more capture points and more flows → more saves.
8. **What makes it successful?** Three things. First, distribution: ten years in the Shopify App Store, the “Built for Shopify” badge and Shopify Plus certification. Second, the widest set of ESP connections in its category (FACT: 20+ named partners on the [technology partners page](https://www.getswym.com/technology-partners)). Third, it captures saves from shoppers who are not logged in, which is where most traffic sits.
9. **Biggest weaknesses.** (a) Usage caps: when a store exceeds its monthly quota, the wishlist is paused on the live storefront (FACT: [help centre](https://help.getswym.com/en/articles/11959983-wishlist-plus-pricing-features)). (b) The value is not obvious to merchants without effort, which Swym itself admits in a [job post](https://jobs.weekday.works/wkdypfybxt). (c) Most of the revenue impact depends on a second tool, the ESP. (d) A steady stream of 1-star reviews in 2026 about its auto-save feature using up quota, bugs and slow support.
10. **Biggest opportunities.** Become the store's system of record for shopper intent rather than a button; feed that data into merchandising and stock decisions; grow the in-store selling tools; fix pricing so that growth in usage feels like a win for the merchant.
11. **Biggest threats.** Shopify shipping a native wishlist; rivals with unlimited usage or free plans; ESPs such as Klaviyo capturing intent themselves; and AI shopping assistants that reduce browsing on the storefront, where Swym collects its data.
12. **What makes it hard to replace?** For a small store, very little. For a larger one: years of shopper wishlists, ESP flows built on Swym's event names, custom builds on its API, and in-store staff workflows.

### A. The 30-second explanation

Swym adds a wishlist, a “save for later” button and “notify me when back in stock” sign-ups to Shopify stores. Each save tells the store which product a shopper wants. Swym passes that to the store's email and text tools, so the shopper gets a reminder, a price-drop alert or a restock alert. Stores pay about US$30 to US$100 a month, more at high volume, because those alerts bring back sales that would otherwise be lost.

### B. The 2-minute explanation

Swym Corporation was founded in 2012 and went through the Techstars Seattle accelerator in 2017. FACT: it reports 48,000 merchants in close to 100 countries and a remote team of 80+ people in India and the US ([about page](https://www.getswym.com/about-us)). FACT: it has raised only about US$1.29 million in outside money ([CB Insights](https://www.cbinsights.com/company/swym/financials)). INFERENCE: a team that size cannot run on that little capital, so the company funds itself from customer revenue.

The product has two halves. The shopper-facing half is a set of small storefront features: wishlist buttons, save for later in the cart, restock sign-up forms, gift registries, and an automatic save after repeated product views (“Smart Save”). The merchant-facing half turns those saves into events, segments and reports, and sends them to marketing tools, Shopify's automation tool (Shopify Flow), Meta ads and the shop till.

Swym sells by subscription through the Shopify App Store. FACT: Wishlist Plus costs US$29.99, US$59.99 or US$99.99 a month, with custom Enterprise pricing above that, and each tier carries a monthly cap on wishlist actions ([pricing page](https://www.getswym.com/pricing)). Customers find it mainly through App Store search, agencies and its Klaviyo partnership.

Its position is strong but not safe. It is the most-reviewed wishlist-only app, yet its main rival Swish charges by Shopify plan with unlimited usage, and free or bundled alternatives exist. The strategic question is whether Swym can become the store's “intent data layer” before the wishlist button itself becomes a free commodity.

### C. The 5-minute explanation

**Where it came from.** FACT: in 2017 Swym pitched itself as a way for small stores to recognise the same shopper across devices without a login, was adding about 100 stores a week, and got every customer through Shopify ([GeekWire, April 2017](https://www.geekwire.com/2017/techstars-seattle-demo-day-favorite-pitches-9-coming-startups/)). INFERENCE: “cross-device continuity” was the technology, and the wishlist turned out to be the product merchants would install and pay for. The anonymous-shopper identity system built for the first idea is still the base of the product today.

**What it does now.** A shopper clicks a heart, or moves a cart item to “save for later”, or asks to be told when a size is back. Swym also saves a product automatically once a shopper has viewed it five times (FACT: [Smart Save help article](https://help.getswym.com/en/articles/13274798-smart-save)). Each of these is stored as an intent signal. When the shopper has shared an email or phone number, Swym can trigger messages: a reminder after 24 hours, a price-drop alert, a low-stock alert, a restock alert. Larger stores send these through their own ESP so the messages match the rest of their marketing.

**How it makes money.** Each plan allows a set number of wishlist actions per month: 3,000, 10,000 or 25,000. Higher plans also unlock integrations and developer access. A store that grows, or that turns on Smart Save, uses more actions and must move up. INFERENCE: this is the main way revenue per customer grows. It is also the main source of anger in reviews, because hitting the cap pauses the wishlist for shoppers.

**Why merchants stay.** Shopper wishlists build up over years. Flows in the ESP depend on Swym's events. Stores on the top plans often have custom code on Swym's API. Leaving means migrating saved lists, rebuilding flows and re-testing the theme.

**Why merchants leave.** They hit a cap and see a 2 to 3 times price jump; they never connect an ESP and so never see revenue; the button breaks on their theme or under cookie-consent rules; or a cheaper app does the visible part of the job.

**Where it is going.** Release notes from 2025 and 2026 show a clear direction: less “wishlist widget”, more “intent data that feeds every tool”. FACT: recent launches include Shopify Flow triggers, wishlist data inside Shopify customer segments, Meta ads audiences, a structured data feed into Klaviyo (“Klaviyo Objects”, early access), an AI setup assistant and setup through Shopify's Sidekick assistant ([product updates](https://www.getswym.com/product-updates)).

**What I would do as the PM.** Fix the pricing mechanics first, so that no merchant's storefront ever breaks because of a billing limit. Then make the first recovered sale visible inside the first two weeks. Then prove the revenue claim with a controlled test rather than attribution. Details are in Parts 41 to 44.

## Part 2 — Company and product context

Swym is a small, private, revenue-funded company that has spent ten years on one platform, Shopify. That shapes almost every product decision described later.

### Company facts

| Item | What is known | Label and source |
| --- | --- | --- |
| Founded | 2012 | FACT — [about page](https://www.getswym.com/about-us) |
| Founder | Arvind Krishnan, co-founder and CEO. Earlier he held general-management roles at Microsoft and Yahoo on digital and mobile advertising products. Other co-founders are not confirmed in the sources I opened. | FACT — [TIGER 21 speaker bio](https://tiger21.com/presenter/arvind-krishnan-swym-corporation/) |
| Headquarters | Shopify lists the developer in Seattle, Washington. A job board lists Plano, Texas. The company calls itself fully remote, with people in six locations across India and the US. The product team is described as Bengaluru-based. | FACT — [App Store listing](https://apps.shopify.com/swym-relay), [about page](https://www.getswym.com/about-us), [job post](https://jobs.weekday.works/wkdypfybxt) |
| Status | Private. Techstars Seattle, class of 2017. | FACT — [about page](https://www.getswym.com/about-us) |
| Funding | About US$1.29 million across 8 small rounds. The last known round was a US$0.15 million convertible note in March 2021. Investors named: Techstars, Techstars Ventures, Right Side Capital Management, GSF India, Powerhouse Ventures. | FACT — [CB Insights](https://www.cbinsights.com/company/swym/financials). A job board shows US$775K instead; both figures are small. |
| Team size | “80+ people” according to Swym. Third-party listings range from 39 to the 51–200 band. | FACT (company claim) — [about page](https://www.getswym.com/about-us) |
| Customers | Swym claims 48,000 merchants in close to 100 countries. Store Leads detects Wishlist Plus on 64,525 Shopify stores and Back in Stock Alerts on 23,167. | FACT — [about page](https://www.getswym.com/about-us), [Store Leads: Wishlist Plus](https://storeleads.app/reports/shopify/app/swym-relay), [Store Leads: Back in Stock](https://storeleads.app/reports/shopify/app/watchlist) |
| Named customers | Steve Madden, Party City, Gymshark, Vera Bradley and Petal & Pup are the highest-ranked stores Store Leads detects. Swym's site shows logos including Princess Polly, Reebok, DKNY, Sol de Janeiro and King Arthur Baking. | FACT — [Store Leads](https://storeleads.app/reports/shopify/app/swym-relay), [homepage](https://www.getswym.com/) |
| Main markets | United States 27.3% of detected stores, United Kingdom 8.5%, India 7.0%, France 6.6%. | FACT — [Store Leads](https://storeleads.app/reports/shopify/app/swym-relay) |
| Platforms | Shopify, BigCommerce, Magento and others are advertised. In practice the base is almost entirely Shopify; the BigCommerce listing has 13 reviews and was last updated in August 2024. | FACT — [pricing page](https://www.getswym.com/pricing), [BigCommerce listing](https://www.bigcommerce.com/apps/wishlist-plus/) |
| Revenue model | Monthly or yearly subscriptions billed through Shopify, tiered by usage. Paid customisation work from US$50 an hour. Custom Enterprise contracts. | FACT — [pricing page](https://www.getswym.com/pricing), [customisation services](https://www.getswym.com/customization-services) |
| Revenue | Not publicly available. | See the estimate below. |

### What can be inferred about revenue

Revenue is not published, so I estimate a range from two directions and show the working. Both are HYPOTHESIS.

- **From costs.** Swym says it has 80+ people, mostly in India. I assume a fully loaded cost of US$40,000 to US$80,000 per person a year for an India-heavy software team. 80 × US$40,000 is US$3.2 million; 80 × US$80,000 is US$6.4 million. The company has raised only about US$1.3 million in total, so revenue must cover that payroll.
- **From customers.** I assume 10,000 to 25,000 of the installed stores pay, at an average of US$40 to US$60 a month across all three apps. 10,000 × US$40 × 12 is US$4.8 million. 25,000 × US$60 × 12 is US$18 million.

Both routes land in the same place: yearly revenue somewhere between the mid single-digit millions and the high teens of millions of dollars. The paying share is the weakest assumption. Only Swym's billing data would settle it.

### Product timeline

| Year | Event | Strategic significance |
| --- | --- | --- |
| 2012 | Swym is founded. | The original idea was continuity: let a shopper pick up on one device where they left off on another. |
| July 2016 | Wishlist Plus launches on the Shopify App Store. | The wishlist becomes the wedge. It is the feature merchants search for and install. |
| October 2016 | Back in Stock Alerts launches. | A second intent signal: demand for products the store cannot sell today. |
| 2017 | Techstars Seattle. The pitch is cross-device shopper tracking for small stores. Reported traction: 30% month-on-month growth, about 100 new stores a week, every customer acquired through Shopify. The CEO names mid-to-large retailers and other platforms as the goal. | Shopify is already the only channel that works. The move up-market is stated early. |
| 2017–2021 | A string of small funding rounds; the last known one in March 2021. | The company learns to live on revenue. This favours steady, low-risk product choices. |
| March 2023 | Gift Lists and Registries launches. | A third app. It tests whether shared lists can bring new shoppers to a store. |
| September 2024 | Swym replies to a review confirming it is enforcing plan quotas on an existing customer. | Usage caps start to bite. Pricing becomes a source of friction. |
| March 2025 | Smart Save launches: products are saved automatically after repeated views. A new insights dashboard ships. | Capture no longer depends on the shopper clicking a heart. It also raises the number of billable actions. |
| June–August 2025 | Shopify POS upgrades, quotes built from wishlists, B2B features (quantities, request a quote), Meta ads audiences, one-click Klaviyo flows. | The product stretches from marketing into selling, in store and to business buyers. |
| January 2026 | ESP auto-detection, a built-in email sender, and a Customer tab showing each shopper's saved products. | Swym reduces its dependence on a second tool for stores that have none. |
| February 2026 | Klaviyo Preferred Partner status. Wishlist counts exposed as Shopify product data. Shopify Markets support for Enterprise. | The Klaviyo relationship becomes a go-to-market channel. |
| First half of 2026 | The free Wishlist Plus plan disappears and the entry price moves from US$19.99 to US$29.99. A competitor's blog dates this to February 2026; the App Store listing shows no free plan by July 2026. | Swym chooses revenue per merchant over volume of installs. |
| March 2026 | Swym announces 1 billion shopper intent actions. Setup through Shopify Sidekick, Shopify Flow triggers, and a usage and quota dashboard ship. | The story changes from “wishlist app” to “intent data”. |
| April–July 2026 | AI assistant in the dashboard, wishlist insights inside Shopify admin, a wishlist that works before cookie consent, two-minute Klaviyo setup with draft flows, buttons that match the theme automatically. | Effort goes into setup, activation and making value visible. |
| August–September 2026 | Klaviyo Objects in early access for Premium and Enterprise plans. | Wishlist data becomes usable by every Klaviyo flow, not only wishlist flows. |

Sources for the timeline: [Wishlist Plus listing](https://apps.shopify.com/swym-relay), [Back in Stock listing](https://apps.shopify.com/watchlist), [Registry listing](https://apps.shopify.com/swym-registry), [GeekWire](https://www.geekwire.com/2017/techstars-seattle-demo-day-favorite-pitches-9-coming-startups/), [CB Insights](https://www.cbinsights.com/company/swym/financials), [review and reply, 2024](https://apps.shopify.com/reviews/1518056), [Listify blog](https://listifyregistry.com/blog/migrating-from-swym-registry-to-listify), and Swym's [product updates](https://www.getswym.com/product-updates).

### How the strategy has evolved

The history falls into four phases. The phase boundaries are my INFERENCE; the events inside them are facts from the timeline.

1. **A technology looking for a product (2012–2016).** Swym built a way to recognise an anonymous shopper across visits and devices.
2. **The wedge (2016–2021).** Wishlist and restock apps with a free plan spread through the App Store. Installs grew quickly and cheaply.
3. **Moving up-market (2021–2024).** Enterprise ESP connections, developer APIs, a security trust centre and an Enterprise plan arrived to serve Shopify Plus brands.
4. **The intent platform, with tighter monetisation (2025 onward).** Smart Save, Shopify Flow, Klaviyo and AI features reposition the product. In the same period quotas are enforced and the free plan is removed.

**The main trade-off.** Removing the free plan optimised for revenue per merchant and a lower support and hosting load. It sacrificed top-of-funnel volume and some goodwill. INFERENCE: this was rational for a company with little outside capital and a large free base to serve. The early cost is visible: Store Leads shows installs up 23.9% year on year but flat (0.0%) quarter on quarter.

## Part 3 — Product positioning

Swym calls itself a “shopper engagement platform”. Its customers mostly call it a wishlist app. The gap between those two descriptions is the central positioning issue.

| Element | Assessment |
| --- | --- |
| Product category | Ecommerce apps for Shopify. Shopify files Wishlist Plus under “Wishlists”, with a second category of “Selling in person” (FACT: [App Store listing](https://apps.shopify.com/swym-relay)). |
| Subcategory | Saved-intent capture and follow-up: wishlist, save for later, restock alerts, gift registry. |
| Primary job to be done | Recover sales from shoppers who showed interest in a product and left without buying. |
| Secondary jobs | Grow the list of shoppers the store can contact. Learn which products are in demand. Connect online browsing to in-store selling. Support gifting. |
| Core value proposition | Know what each shopper wants, and bring them back automatically. |
| Differentiated value proposition | Captures saves from shoppers who are not logged in, sends them to 20+ marketing tools, and is built for large Shopify Plus stores (developer access, till integration, multi-country support). |
| Brand promise | “Engage shoppers. Improve conversions. Maximize sales.” (FACT: [homepage](https://www.getswym.com/) headline) |
| Strategic positioning | The premium, data-led option. A partner to Shopify and Klaviyo, not a rival to either. |
| Category narrative | Paid advertising is getting more expensive and less effective, so brands should collect intent data inside their own store. FACT: the homepage says this almost word for word. |

**Positioning statement.** For Shopify brands in fashion, beauty, home and jewellery, whose shoppers browse several times before buying and mostly leave without a trace, Swym is a shopper-intent platform that records what each shopper wants and brings them back through the store's own marketing channels, unlike a basic wishlist button or generic abandoned-cart emails, because it captures saves from anonymous shoppers and connects them to the store's marketing tools, automation and till.

### Is the positioning credible?

**What the company claims.** FACT: the site says Swym is “the shopper engagement platform of choice”, calls Wishlist Plus “the best Wishlist available”, and states that “Wishlist increases sales by 20–30%” and that alerts get a “30 to 35% click-through rate” ([homepage](https://www.getswym.com/)).

**What customers appear to value.** FACT: Shopify's AI-generated summary of the reviews says merchants describe “a simple, reliable wishlist solution”, and praise alerts, the Klaviyo integration and “consistently fast, expert support, often with quick custom design fixes” ([App Store listing](https://apps.shopify.com/swym-relay)). INFERENCE: merchants buy a wishlist and stay for the support and the Klaviyo link. The word “platform” is Swym's, not theirs.

**Where it is strong.** The enterprise story holds up: named large brands, Shopify Plus certification, enterprise ESP connections and a developer API. I found no other wishlist-only app listing the same breadth.

**Where it is weak.** Two places.

- The “20–30% more sales” claim is not supported by anything public. The older wording on the [BigCommerce listing](https://www.bigcommerce.com/apps/wishlist-plus/) is that wishlist *users* convert 20–30% better. That is a different claim. Shoppers who save products were already more interested than average, so their higher conversion does not show the wishlist caused it.
- The “platform” claim outruns the product for small stores. A store on the US$29.99 plan gets a wishlist and a basic mailer. The Klaviyo connection sits on higher plans on the [pricing page](https://www.getswym.com/pricing).

**Over-positioned or under-positioned?** Both, in different places. It is over-positioned as a platform to small merchants, who experience a widget with a usage meter. It is under-positioned on two assets that are hard to copy: privacy-compliant capture of anonymous shoppers, and product-level demand data that could guide buying and pricing decisions.

## Part 4 — Ideal customer profile

The best-fit customer is a Shopify brand with a real catalogue, steady traffic, an ESP already in use, and products people think about before buying.

### Firmographic characteristics

| Dimension | Best fit | Evidence and label |
| --- | --- | --- |
| Industry | Apparel first, then home and garden, beauty, jewellery. | FACT: 37.4% apparel, 13.7% home and garden, 10.7% beauty and fitness among detected stores ([Store Leads](https://storeleads.app/reports/shopify/app/swym-relay)). Swym has a landing page for each of the four verticals. |
| Catalogue size | 100 to 5,000 products. | FACT: 23.0% of detected stores list 250–999 products, 16.6% list 100–249, 15.1% list 1,000–4,999 ([Store Leads](https://storeleads.app/reports/shopify/app/swym-relay)). |
| Traffic | Roughly 20,000+ sessions a month. | HYPOTHESIS. A wishlist needs volume. If 3% of sessions save a product (my assumption), 20,000 sessions gives 600 saves a month, enough for alerts to produce visible orders. |
| Revenue | Not publicly available. INFERENCE: about US$1 million to US$100 million in online sales. | Plans run from “growing brands” to “high-growth Shopify Plus brands with global storefronts” ([pricing page](https://www.getswym.com/pricing)). |
| Geography | United States, United Kingdom, India, France, Australia. | FACT: [Store Leads](https://storeleads.app/reports/shopify/app/swym-relay) country split. |
| Growth stage | Past the launch phase and starting to invest in repeat purchases. | INFERENCE from case studies, which feature CRM and ecommerce directors. |
| Business model | Direct-to-consumer brands and multi-brand retailers. Often with physical shops. Some sell to business buyers too. | FACT: case studies cover retail stores (Ruby) and trade ordering (Mikasa Hospitality) on the [homepage](https://www.getswym.com/). |
| Employee count | Not publicly available. INFERENCE: 5 to 500. | — |

**Why these verticals.** They share four traits. Purchases are considered, not impulsive. Sizes and colours sell out, which creates restock demand. Prices change with seasons and sales, which makes price-drop alerts useful. Gifting is common.

**Poor fit.** Single-product stores, low-price consumables bought on impulse, subscription or replenishment brands, and stores with very little traffic.

### Organisational characteristics

| Role | Who it usually is | What they care about |
| --- | --- | --- |
| Economic buyer and decision maker | The founder at a small store. The head or director of ecommerce at a larger one. | Revenue per visitor and the total cost of apps. |
| Champion | The CRM or retention marketing lead. FACT: Swym's testimonials come from a CRM Manager, a CRM Team Lead and a Campaigns Director ([homepage](https://www.getswym.com/)). | More people to message, and messages that convert. |
| End users on the merchant side | The marketer who builds flows, the merchandiser who reads demand reports, shop-floor staff using the till. | Speed, reliable data, no code. |
| Administrator | The ecommerce manager, an in-house Shopify developer, or an agency. | A button that matches the theme and does not slow the site. |
| Finance | The owner, or a finance lead who reviews the Shopify bill. | Predictable cost. Swym bills through Shopify, so there is no separate vendor to set up. |
| Security, legal, procurement, IT | Involved only at Enterprise level. | Data-processing terms, cookie consent, a security report, uptime. |
| Influencer | The store's Shopify agency. FACT: Swym says 200+ agencies are in its programme ([agency programme](https://www.getswym.com/agency-program)). | Tools that install cleanly and do not generate support tickets for the agency. |

### Behavioural characteristics

- **Existing tools.** Shopify plus an ESP, almost always. Klaviyo is the one Swym builds for first.
- **Existing workflows.** The store already sends abandoned-cart emails. It has nothing for shoppers who never reached the cart.
- **Workflow maturity.** Medium. Someone on the team can build a flow from a template.
- **Pain intensity.** Moderate and constant. It spikes when a popular product sells out and around BFCM.
- **Frequency of the problem.** Every visit. Most sessions end without a purchase.
- **Technical sophistication.** Low to medium. Setup must be no-code. Developers appear only for headless stores and custom designs.
- **Integration requirements.** The ESP link is essential. The till matters for brands with shops. Multi-currency and multi-language support matters for international brands.
- **Compliance requirements.** Cookie-consent rules in the EU and UK, consent rules for marketing texts, and accessibility. FACT: Swym published an accessibility conformance report against the WCAG 2.1 AA standard in April 2026 ([product updates](https://www.getswym.com/product-updates/april-2026)).

### Trigger events

These are the moments when a store starts looking. All are INFERENCE unless marked.

1. A hero product keeps selling out and customers email to ask when it returns.
2. Advertising costs rise, and leadership asks the team to earn more from existing traffic. FACT: this is Swym's own sales narrative.
3. The store hires its first retention marketer or adopts Klaviyo.
4. The store moves to Shopify, upgrades to Shopify Plus, or redesigns its theme with an agency.
5. BFCM planning starts. FACT: Swym ships a BFCM readiness checklist inside the app ([August 2025 update](https://www.getswym.com/product-updates/august-2025)).
6. The brand opens physical shops and wants staff to see what a customer saved online.
7. A cheaper wishlist app stops being enough. FACT: one agency testimonial calls Wishlist Plus “a big upgrade over the budget wishlist” its client used before ([about page](https://www.getswym.com/about-us)).
8. The brand starts selling in several countries and needs each market's currency and language.
9. Shoppers ask for a wishlist directly.

## Part 5 — User personas

Swym has two sets of users: people inside the merchant's business, who buy and configure it, and shoppers, who generate all the usage but never see a bill. The personas below are my INFERENCE from case studies, testimonials, feature design and reviews.

| Persona | Role in the purchase | Goals | Pain points | Main job | How often they use it | Features that matter | Success measure | Buying influence |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Founder-owner of a small store | Economic buyer, decision maker and admin | More sales without more ad spend | No time; a growing pile of app bills | Add the wishlist customers keep asking for | A weekly glance | One-click setup, built-in mailer, price | Orders from reminders versus the fee | Decides alone |
| Head of ecommerce at a larger brand | Economic buyer and decision maker | Higher conversion and revenue per visitor | Too many apps, site speed, vendor risk | Recover demand at scale, safely | Monthly review | Reliability, reporting, Shopify Plus features | Revenue influenced, conversion lift | Final say |
| Retention or CRM marketer | Champion and power user | A bigger contactable audience; more revenue from flows | General flows are saturated; no product-level intent | Trigger the right message for the right product | Daily, mostly inside the ESP | Klaviyo events, segments, price-drop and restock triggers | Flow revenue, open and click rates | Strong recommender |
| Merchandiser or buyer | Regular user | Stock and discount the right products | No signal for products that are wanted but not bought | Read demand before committing stock | Weekly | Most-wishlisted report, restock demand, insights inside Shopify admin | Sell-through, fewer stockouts | Low to medium |
| Shopify developer or agency | Admin and implementer | An on-brand, fast storefront with nothing broken | Theme conflicts, script weight, custom requests | Install cleanly and customise | At setup and at redesigns | Theme blocks, editable button code, JavaScript SDK, REST API | Launch with no support tickets | Can recommend or veto |
| Shop-floor associate or stylist | End user in store | Close the sale with context | Cannot see what the customer liked online | Serve a walk-in customer personally | Daily, in stores that use it | Till extension, in-store lists, notes, share by email | Assisted sales | None |
| Sales rep for trade or high-value clients | Occasional user | Turn a shortlist into an order | Manual quotes | Build a quote or draft order from a list | Per deal | Quotes, draft orders, list collaboration | Quote-to-order rate | Low |
| Security, legal or IT reviewer | Gatekeeper at Enterprise level | No compliance or data incident | Third-party scripts handling personal data | Approve the vendor | Once, at purchase | Trust centre, consent handling, data terms | No findings | Veto |
| Shopper | External user | Remember a product; wait for a price or a size; hint at gifts | Forced logins; forgetting what they liked | Save in one click and hear when something changes | Occasional | Save without login, alerts, sharing | Finds the item again | None, but drives all usage |
| Gift giver | External user | Buy something the recipient wants | Guessing | Buy from a shared list | Rare | Shared list or registry, purchase tracking | Gift bought without duplication | None |

### Conflicts between personas, and how the product handles them

- **The marketer wants maximum capture; the owner wants a predictable bill; the shopper wants control.** Smart Save serves the marketer by saving products automatically. Each auto-save uses quota, which hurts the owner. The product's answer is partial. FACT: Smart Save is a single toggle, limited by default to logged-in shoppers, and shoppers can undo a save or switch it off for themselves ([help article](https://help.getswym.com/en/articles/13274798-smart-save)). But auto-saves still count toward the paid quota.
- **The marketer wants to capture before consent; legal wants consent first.** FACT: since spring 2026 the wishlist can load before cookie consent and keep saves on the shopper's device until they log in ([May 2026 update](https://www.getswym.com/product-updates/may-2026)). This is a real resolution of the conflict.
- **The developer wants light, native code; the marketer wants more widgets.** Swym uses Shopify's theme extensions and holds the “Built for Shopify” badge, which carries performance requirements. Button code is editable in the admin since February 2026.
- **The ecommerce head wants one view; the marketer lives in the ESP.** Swym answers with its own dashboards, a wishlist panel on product pages inside Shopify admin, and answers through Shopify's Sidekick assistant.
- **Enterprise wants control; small stores want simplicity.** Plan gating handles this. Developer access starts at the US$99.99 plan.

## Part 6 — Jobs to be done

The jobs are ranked by how much revenue they explain. The ranking is my judgement.

### Functional jobs

| Rank | Job | When… | I want to… | So that… |
| --- | --- | --- | --- | --- |
| 1 (primary) | Recover interested shoppers | a shopper shows interest in a product and leaves | reach them at the right moment about that product | I win a sale I would otherwise lose |
| 2 (secondary) | Capture demand during stockouts | a product or size is sold out | collect who wants it and tell them the moment it returns | a stockout does not become a lost customer |
| 3 (secondary) | Grow the contactable audience | anonymous visitors browse my store | give them a reason to share an email or phone number | I can reach them again without paying for another ad |
| 4 (supporting) | Read demand | I plan purchasing and promotions | see which products people want but have not bought | I stock and discount the right items |
| 5 (supporting) | Personalise campaigns and ads | I build a campaign | target people by what they saved | my messages are relevant and my ad money is not wasted |
| 6 (supporting) | Sell in person with context | a known customer walks into the shop | see what they saved online and add to it | the associate can serve them personally |
| 7 (supporting) | Enable gifting | a shopper has an occasion coming | let them share a list | their friends and family buy from my store |
| Shopper's job | Save for later | I like something but am not ready to buy | save it in one click without creating an account | I can find it again and hear if the price or stock changes |

### Emotional jobs

- The owner wants to feel less dependent on advertising platforms they do not control.
- The marketer wants confidence that departing visitors are not simply wasted.
- The shopper wants relief from the worry of losing track of something, or missing their size.

### Social jobs

- The marketer wants to show leadership a number: revenue influenced by their flows.
- The brand wants to look as polished as larger competitors. In fashion a wishlist is expected.
- The shopper wants to share taste, or drop a hint before a birthday.

## Part 7 — Customer problem analysis

Before Swym, the merchant has good tools for shoppers who reach the cart and almost nothing for the much larger group who do not. Each problem below follows the same nine points.

### Problem 1 — Interested shoppers leave without a trace

- **Current process:** Nothing happens. The session ends.
- **Workaround:** Paid retargeting ads, or an email pop-up offering a discount.
- **Cost of the workaround:** Ad spend on every return visit, and margin given away in discounts.
- **Frequency:** Every day. Most sessions on any store end without a purchase.
- **Severity:** High in total, invisible per visit.
- **Users affected:** The marketer and the owner.
- **Business impact:** Traffic that was paid for is lost.
- **Why existing solutions fail:** Abandoned-cart emails only reach shoppers who added to cart and are already identified. Pop-ups are generic and interrupt. Ads do not know which product the shopper cared about most.
- **How Swym addresses it:** The save button gives the shopper their own reason to identify themselves, and ties that identity to a specific product.

### Problem 2 — Stockouts turn away ready buyers

- **Current process:** A “sold out” label. Customers email support to ask when it returns.
- **Workaround:** A spreadsheet of names, or the ESP's basic restock form.
- **Cost:** Support time, and the sale goes to a competitor.
- **Frequency:** Constant in apparel, where single sizes sell out.
- **Severity:** High. These shoppers were ready to pay.
- **Users affected:** Support, marketing, merchandising.
- **Business impact:** Lost sales and no measure of unmet demand.
- **Why existing solutions fail:** Manual lists do not scale. Basic forms often miss size-level sign-ups, text messages and in-store sign-ups.
- **How Swym addresses it:** Sign-ups at the level of each size or colour, automatic alerts on restock, alerts sent in batches so limited stock is not oversold, and sign-ups taken at the till (FACT: [pricing page](https://www.getswym.com/pricing) feature list).

### Problem 3 — No demand signal before the purchase

- **Current process:** Merchandisers look at sales and page views.
- **Workaround:** Analytics reports and instinct.
- **Cost:** Over-buying the wrong products; under-buying the wanted ones.
- **Frequency:** Every buying and promotion cycle.
- **Severity:** Medium to high for seasonal categories.
- **Users affected:** Merchandisers and buyers.
- **Business impact:** Markdowns and stockouts.
- **Why existing solutions fail:** Sales data shows what sold. It cannot show what people wanted and did not buy because of price or a missing size.
- **How Swym addresses it:** A most-wishlisted report, save counts and potential revenue on each product inside Shopify admin, and wishlist counts usable for a “most wishlisted” collection (FACT: [February](https://www.getswym.com/product-updates/february-2026) and [April 2026](https://www.getswym.com/product-updates/april-2026) updates).

### Problem 4 — Marketing messages are generic

- **Current process:** The same newsletter goes to everyone.
- **Workaround:** Segments built on purchase history.
- **Cost:** Falling open rates and unsubscribes.
- **Frequency:** Every campaign.
- **Severity:** Medium.
- **Users affected:** The retention marketer.
- **Business impact:** Lower revenue per message sent.
- **Why existing solutions fail:** Purchase history says nothing about people who have not bought yet.
- **How Swym addresses it:** Events and segments based on saved products flow into the ESP, Shopify's customer segments and Meta ads.

### Problem 5 — Online browsing and the physical shop are disconnected

- **Current process:** Staff ask the customer what they are looking for.
- **Workaround:** Notes in a notebook, or a stylist's memory.
- **Cost:** A generic in-store experience; the visit ends at the door.
- **Frequency:** Every store visit by an online customer.
- **Severity:** Medium, and higher for premium brands.
- **Users affected:** Associates and store managers.
- **Business impact:** Missed assisted sales.
- **Why existing solutions fail:** Till systems hold orders, not interest.
- **How Swym addresses it:** Staff see the customer's wishlist on the till, build an in-store list with notes, and email it before the customer leaves (FACT: [March 2026 update](https://www.getswym.com/product-updates/march-2026)).

### Summary

| Customer problem | Existing workaround | Product solution | Value created |
| --- | --- | --- | --- |
| Interested shoppers leave unidentified | Retargeting ads, discount pop-ups | Wishlist and Smart Save that capture product-level intent, with or without login | More shoppers the store can contact, each tied to a product |
| Stockouts lose ready buyers | Spreadsheets, basic restock forms | Size-level restock sign-ups with automatic and batched alerts | Sales recovered at restock; a measure of unmet demand |
| No pre-purchase demand signal | Sales and page-view reports | Most-wishlisted reports and product-level insights in Shopify admin | Better buying and promotion decisions |
| Generic marketing | Segments by purchase history | Saved-product events and segments in the ESP, Shopify and Meta | Higher revenue per message and per ad dollar |
| Online and in-store disconnected | Staff memory and notes | Wishlists and curated lists on the shop till | More assisted sales; visits that continue online |
| Shoppers use the cart as a wishlist | Open tabs and screenshots | Save for later in the cart | Cleaner carts; saved items that can trigger reminders |

**The full chain, for the primary job.** Problem: a shopper likes a jacket but will not pay full price. Capability: a heart button that works without login, plus a price-drop trigger. Behaviour: the shopper saves it and enters an email to keep the list; the marketer leaves a price-drop flow running. Outcome: when the jacket goes on sale, the shopper gets an email about that jacket and buys. Business value: a sale at a planned markdown, with no extra ad spend and no blanket discount code.

## Part 8 — Product architecture

Swym is best understood as three layers on a shared platform: capture what shoppers want, act on it through marketing, and act on it through selling. The grouping is mine; the features inside it are facts from Swym's site, help centre and listings.

```
Swym
├── CAPTURE (what shoppers see on the storefront)
│   ├── Wishlist Plus  (flagship app)
│   │   ├── Wishlist buttons on product, collection and quick-view pages
│   │   ├── Multiple named lists
│   │   ├── Guest wishlists (no login), with email capture
│   │   ├── Wishlist page, side drawer and header icon
│   │   ├── Wishlists inside Shopify customer accounts
│   │   ├── Sharing by email, social media, text or link
│   │   ├── Save for Later (in the cart)
│   │   ├── Smart Save (automatic save after repeated views)
│   │   └── Save education nudge and pop-up
│   ├── Back in Stock Alerts  (separate app, separate bill)
│   │   ├── 'Notify me' sign-up, per size or colour
│   │   ├── Pre-order and coming-soon alerts
│   │   └── Sign-up at the shop till
│   └── Gift Lists and Registries  (separate app, separate bill)
│       ├── Occasion registries with shareable links
│       ├── Gift tracking and thank-you notes
│       └── Address privacy at checkout
├── ACTIVATE  ('Swym for Marketing')
│   ├── Triggers: wishlist reminder, save-for-later reminder, price drop,
│   │   low stock, back in stock, frequently browsed, wishlist summary
│   ├── Swym Mailer (built-in email sender)
│   ├── Customer segments
│   ├── Meta ads audiences
│   └── Klaviyo Objects (early access)
├── SELL  ('Swym for Sales')
│   ├── Shop till extension: view wishlists, build in-store lists, notes, share
│   ├── Customer tab: each shopper's saved products
│   ├── Quotes, draft orders and invoices built from lists
│   └── Trade buying: quantities on lists, request a quote
└── PLATFORM
    ├── Integrations: email, text, push, mobile app (Tapcart), page builders
    ├── Analytics: home dashboard, insights, sent-alert report, CSV export,
    │   product insights inside Shopify admin, wishlist count as product data
    ├── Administration: configurations, button editor, languages,
    │   usage and quota view, plan and billing
    ├── Security and privacy: cookie-consent modes, trust centre
    ├── Automation: Shopify Flow triggers and templates
    ├── AI: setup and questions through Shopify Sidekick, AI assistant,
    │   AI weekly report (early access)
    └── Developer: REST API, JavaScript SDK, custom webhooks (Enterprise),
        documentation server for AI coding tools
```

Sources: [homepage](https://www.getswym.com/), [plan comparison](https://help.getswym.com/en/articles/11959983-wishlist-plus-pricing-features), [Swym for Sales](https://www.getswym.com/platform/swym-for-sales), [developer docs](https://developers.getswym.com/docs/swym-guides-landing), [product updates](https://www.getswym.com/product-updates).

### How the pieces are classified

- **Core product:** Wishlist Plus capture plus the triggers that follow it.
- **Core modules:** wishlist buttons and lists, guest identity, alerts, ESP integrations.
- **Supporting modules:** Back in Stock Alerts, Gift Lists and Registries, Swym for Sales.
- **Platform capabilities:** integrations, analytics, Shopify Flow, developer tools.
- **Administrative capabilities:** configuration, usage tracking, billing.
- **AI capabilities:** setup help and reporting. AI does not sit in the core capture or alert logic. Part 24 covers this.

### The strategic role of each module

| Module | Strategic role | Label |
| --- | --- | --- |
| Wishlist buttons and lists | The wedge. It is the feature merchants search for, so it drives installs. It is also where the data starts. | INFERENCE |
| Guest identity | The technical asset. Swym gives each shopper an ID and merges a guest session into the account when they log in (FACT: [developer docs](https://developers.getswym.com/docs/swym-guides-landing)). Without it, only logged-in shoppers could save, and most shoppers are not logged in. | FACT plus INFERENCE |
| Smart Save | Raises signal volume without shopper effort. FACT: Swym says it triples wishlist actions on average ([help article](https://help.getswym.com/en/articles/13274798-smart-save)). It therefore also pushes merchants toward higher plans, and it is the feature most often named in recent 1-star reviews. | FACT plus INFERENCE |
| Save for Later | Extends capture to the cart, where intent is highest. | INFERENCE |
| Back in Stock Alerts | A second way into the account, with the strongest intent signal of all. FACT: it has its own listing (443 reviews) and Store Leads shows its installs down 9.0% in a year. | FACT |
| Gift Lists and Registries | Brings new shoppers through sharing. Small today: 38 reviews since March 2023. | FACT plus INFERENCE |
| Triggers and the built-in mailer | Turns data into revenue. The mailer lets a store with no ESP get value on day one. | INFERENCE |
| ESP integrations | Where larger stores realise the value. Also the main reason to upgrade from the entry plan. | INFERENCE |
| Segments and Meta ads | Carries intent into paid media, a second budget line inside the merchant. | INFERENCE |
| Swym for Sales | Differentiation for brands with shops or high-touch selling. FACT: a “Lite” version is included and “Advanced” plans are paid add-ons ([Swym for Sales](https://www.getswym.com/platform/swym-for-sales)). | FACT plus INFERENCE |
| Analytics | Proves the value, which protects renewals. Swym's own job post says making value obvious is still an open problem. | FACT plus INFERENCE |
| Shopify Flow | Makes Swym a building block in the merchant's automations. Each workflow built on it raises the cost of leaving. | INFERENCE |
| AI layer | Lowers setup effort and points merchants at features they have not switched on. | INFERENCE |
| Developer platform | Keeps enterprise and headless stores, and justifies the top self-serve plan. | INFERENCE |
| Customisation services | Removes adoption blockers for brands with design demands. FACT: from US$50 an hour ([customisation services](https://www.getswym.com/customization-services)). | FACT |

**A structural point.** The three apps are billed separately on three different meters: wishlist actions, alert requests and active registries. INFERENCE: this reflects how the Shopify App Store works, where each listing ranks for its own search terms. The cost is a split experience for a merchant who wants all three.

## Part 9 — Complete feature breakdown

Eleven features carry the product. Each is analysed on the same sixteen points. Workflows are reconstructed from Swym's help centre and release notes, not from hands-on use. AI features are covered in Part 24.

### 1. Wishlist button and lists

- **Purpose:** Let a shopper save a product to a list from a product page, a collection page or a quick-view window.
- **Target user:** Shoppers. The store admin configures it.
- **Customer problem:** Interested shoppers leave no trace.
- **User workflow:** (1) The shopper taps the heart. (2) The product is saved against their browser ID or their account. (3) A prompt may ask for an email to keep the list. (4) The shopper opens the list from the header icon, a side drawer or their account page. (5) They add to cart from the list.
- **Inputs:** A click. Optionally an email or phone number and a list name.
- **Actions:** Add, remove, create lists, move items, add to cart, share by email, social media, text or link.
- **Outputs:** A saved-item record, an event for marketing tools, and a save count on the product.
- **Dependencies:** Theme integration, cookie-consent state, guest identity.
- **Frequency:** Daily for the store. Occasional for any one shopper.
- **User value:** A memory aid that needs no account.
- **Business value:** Each save names a product and ties it to a person the store may be able to contact.
- **Differentiation:** Table stakes. Rivals such as Wishlist Hero also allow saving without login.
- **UX considerations:** FACT: with the classic button style, the button is hidden until cookie consent and removed if the shopper declines ([help article](https://help.getswym.com/en/articles/16093297-how-wishlist-plus-handles-cookies-and-cookie-consent)). A 2026 review reports the button missing across browsers. The timing of the email prompt is a trade-off: too early annoys, too late loses the identity.
- **Technical complexity:** Working across thousands of themes; merging a guest's list into their account; staying fast on every page.
- **Potential metrics:** Saves per 100 sessions; share of saves from identified shoppers; list-to-cart rate; share of page loads where the button rendered.
- **Feature maturity:** Mature.

### 2. Smart Save

- **Purpose:** Save a product automatically once a shopper has viewed it several times.
- **Target user:** Shoppers who never click a heart. The marketer switches it on.
- **Customer problem:** Most interested shoppers never use a wishlist button.
- **User workflow:** (1) The shopper views a product page five times; the merchant can change the number. (2) After 30 more seconds on the page, Swym saves it. (3) A notice appears with an Undo option. (4) The item shows under a “Saved for you” tab. (5) A shopper who keeps undoing is asked whether to stop the feature for them.
- **Inputs:** Page-view history, the view threshold, and whether guests are included.
- **Actions:** The merchant sets the toggle, threshold, notice position and wording. The shopper can undo or opt out.
- **Outputs:** Saved items marked as automatic, events for marketing tools, and revenue split between automatic and manual saves.
- **Dependencies:** Wishlist, shopper identity, plan quota.
- **Frequency:** Continuous.
- **User value:** Zero effort. The risk is that some shoppers feel watched.
- **Business value:** FACT: Swym reports three times as many wishlist actions on average and fewer than 0.5% undone ([help article](https://help.getswym.com/en/articles/13274798-smart-save)). These are company figures.
- **Differentiation:** Differentiated. I found no equivalent in the rival listings I checked, which is not proof that none exists.
- **UX considerations:** FACT: three 1-star reviews in 2026 say it was on by default and used up their quota, one of them before the store had launched ([review](https://apps.shopify.com/reviews/2268711)). Defaults were tightened during 2026: it now applies to logged-in shoppers only by default and is off by default on the Starter plan ([August 2026 update](https://www.getswym.com/product-updates/august-2026)).
- **Technical complexity:** Counting views per shopper and product across sessions; excluding bots and the store's own staff; respecting consent.
- **Potential metrics:** Undo rate; opt-out rate; purchase rate of automatic versus manual saves; share of quota used by Smart Save.
- **Feature maturity:** Advanced in idea, still being tuned in practice.

### 3. Save for Later

- **Purpose:** Move a cart item to a saved list instead of deleting it.
- **Target user:** Shoppers editing their cart.
- **Customer problem:** Shoppers use the cart as a wishlist, and removals are lost demand.
- **User workflow:** (1) The shopper removes an item or taps “save for later”. (2) The item moves to a saved section on the cart page. (3) A reminder may follow. (4) One click returns it to the cart.
- **Inputs:** A cart line item.
- **Actions:** Save, move back, remove.
- **Outputs:** A saved item, which counts as a wishlist action, and a “cart saved” event.
- **Dependencies:** Cart-page integration. FACT: the inline version announced in July 2026 is implemented through developer documentation.
- **Frequency:** Once per cart session at most.
- **User value:** A tidy cart without losing anything.
- **Business value:** Keeps demand at the point of highest intent.
- **Differentiation:** Differentiated among wishlist apps. Shoppers already expect it from large retailers.
- **UX considerations:** Carts are the most customised part of a theme. Making saving too easy could lower today's order value.
- **Technical complexity:** Cart drawers differ on every theme.
- **Potential metrics:** Share of cart removals that are saved; purchase rate of saved items within 30 days; effect on average order value.
- **Feature maturity:** Mature.

### 4. Back in stock alerts

- **Purpose:** Let shoppers ask to be told when a sold-out product or size returns.
- **Target user:** Shoppers on sold-out pages; marketers; staff at the till.
- **Customer problem:** Stockouts turn away ready buyers.
- **User workflow:** (1) The shopper opens a sold-out product. (2) They pick a size. (3) They enter an email or phone number. (4) Swym watches stock. (5) On restock an alert goes out, optionally in batches. (6) The shopper buys.
- **Inputs:** Product variant and contact details.
- **Actions:** The merchant chooses automatic or manual sending, batch size, templates and stock rules across locations.
- **Outputs:** Alerts, a sign-up count per product, and marketing opt-ins.
- **Dependencies:** Shopify stock data, an ESP or Swym's mailer, and the separate Back in Stock subscription.
- **Frequency:** Event-driven, in bursts at restock.
- **User value:** No need to keep checking.
- **Business value:** Recovered sales and a count of unmet demand. FACT: one case study reports 16.6 times return ([homepage](https://www.getswym.com/)).
- **Differentiation:** Table stakes in a crowded category. Specialist rivals have several thousand reviews each. Swym's edge is enterprise ESP links and shared data with the wishlist.
- **UX considerations:** FACT: a review on the [listing](https://apps.shopify.com/watchlist) reports stock-sync delays that hurt campaign timing.
- **Technical complexity:** Reacting to stock changes at scale, sending in order, handling several stock locations.
- **Potential metrics:** Sign-ups per sold-out page view; alert-to-purchase rate; minutes from restock to alert; revenue recovered.
- **Feature maturity:** Mature.

### 5. Triggers and the built-in mailer

- **Purpose:** Send a message automatically when time passes, or when the price or stock of a saved product changes.
- **Target user:** The marketer or owner.
- **Customer problem:** Saved items do nothing unless someone follows up.
- **User workflow:** (1) Switch on a trigger. (2) Choose the channel: Swym's mailer or an ESP. (3) Edit the template. (4) Swym checks saved items against catalogue changes. (5) Messages go out. (6) A report lists every send.
- **Inputs:** Saved items, catalogue prices and stock, shopper contacts, templates.
- **Actions:** Enable or disable each trigger, set timing, edit templates, add a summary digest on higher plans.
- **Outputs:** Emails, texts or push messages, and a sent-alert report with export.
- **Dependencies:** An identified shopper and a monthly send allowance.
- **Frequency:** Continuous and automatic.
- **User value:** Set up once.
- **Business value:** FACT: Swym claims a 30–35% click-through rate on alerts ([homepage](https://www.getswym.com/)). Company figure, not independently verified.
- **Differentiation:** Table stakes. Swish and Wishlist Hero list price-drop and stock alerts too.
- **UX considerations:** FACT: alerts now run for 90 days after a save, up from 30 ([August 2025 update](https://www.getswym.com/product-updates/august-2025)). Too many alerts cause unsubscribes.
- **Technical complexity:** Watching price and stock for a very large number of saved items without duplicate sends.
- **Potential metrics:** Open, click and purchase rates per trigger; revenue per send; unsubscribe rate; share of merchants with at least one trigger live.
- **Feature maturity:** Mature.

### 6. ESP integrations, Klaviyo first

- **Purpose:** Pass intent events into the store's marketing tool so its flows and segments can use them.
- **Target user:** The retention marketer.
- **Customer problem:** Marketing messages are generic.
- **User workflow (Klaviyo):** (1) Open Integrations. (2) Connect Klaviyo, about two minutes. (3) Swym creates the core flows as drafts with templates. (4) The marketer reviews them and switches them live. (5) Events start arriving.
- **Inputs:** Authorisation to the ESP account.
- **Actions:** Choose which alerts go through the ESP; edit flows there.
- **Outputs:** Events such as added to wishlist, price drop, low stock, back in stock and shared wishlist, each with product details. FACT: draft flows include a 24-hour wishlist reminder, back in stock, low stock, cart saved, frequently browsed and price drop ([July 2026 update](https://www.getswym.com/product-updates/july-2026)).
- **Dependencies:** FACT: the Klaviyo link needs the Pro plan or above ([Klaviyo integration page](https://www.getswym.com/integrations/klaviyo)). Enterprise ESPs such as Braze need the Enterprise plan ([Braze docs](https://braze.com/docs/partners/ecommerce/loyalty/swym/)).
- **Frequency:** Set up once; runs all the time.
- **User value:** The marketer stays in the tool they already know.
- **Business value:** This is where larger stores realise most of the revenue.
- **Differentiation:** The Klaviyo link itself is table stakes. The breadth is differentiated: 20+ partners and Klaviyo Preferred Partner status.
- **UX considerations:** FACT: for some enterprise tools the merchant sends API keys to Swym's support team, who set it up ([Braze docs](https://braze.com/docs/partners/ecommerce/loyalty/swym/)). That is not self-serve.
- **Technical complexity:** Every ESP models events differently, and each connection must be maintained.
- **Potential metrics:** Share of paying merchants with an ESP connected; days from install to first ESP-sent message; flow revenue; integration error rate.
- **Feature maturity:** Advanced.

### 7. Shopify Flow integration

- **Purpose:** Let wishlist events start automations in Shopify's own workflow builder, and let other apps add items to wishlists.
- **Target user:** The ecommerce operations lead or marketer.
- **Customer problem:** Wishlist data is locked inside one app.
- **User workflow:** (1) Open the Automations page in Swym. (2) Pick a template, or build in Flow. (3) Choose a trigger, for example “wishlist value above a threshold”. (4) Choose an action: tag the customer, assign a sales rep, alert the team, award loyalty points.
- **Inputs:** Swym triggers and the merchant's rules.
- **Actions:** Tagging, internal alerts, messages through Shopify Email, adding quiz results or loyalty rewards to a wishlist.
- **Outputs:** Customer tags, notifications and updated lists.
- **Dependencies:** Shopify Flow being available on the merchant's Shopify plan.
- **Frequency:** Built once; runs continuously.
- **User value:** Wishlist data works with loyalty, review and support apps without a custom link to each.
- **Business value:** Every workflow built on Swym makes it harder to remove.
- **Differentiation:** Differentiated in depth. Growave also supports Flow.
- **UX considerations:** Building in Flow needs some logic skill; templates added in June 2026 reduce that. FACT: the launch note tells merchants to email support if Swym does not appear among Flow's connectors ([March 2026 update](https://www.getswym.com/product-updates/march-2026)).
- **Technical complexity:** Event volume. FACT: events sent through Flow count toward the plan's send allowance ([plan comparison](https://help.getswym.com/en/articles/11959983-wishlist-plus-pricing-features)).
- **Potential metrics:** Merchants with at least one active workflow using Swym; workflow runs per month.
- **Feature maturity:** Basic. Launched March 2026.

### 8. Analytics and attribution

- **Purpose:** Show what shoppers save, what was sent, and what revenue followed.
- **Target user:** The owner, the head of ecommerce and the merchandiser.
- **Customer problem:** The merchant cannot tell whether the app pays for itself.
- **User workflow:** (1) Open the app. (2) The home dashboard shows a revenue summary once there is revenue. (3) “Know how” opens a breakdown by automatic and manual saves. (4) Insights shows the most-saved products and usage against quota. (5) Export to a spreadsheet file.
- **Inputs:** Saves, sends and orders.
- **Actions:** Filter by date, alert type and product; export.
- **Outputs:** Realised and potential revenue, top products, a sent-alert log, usage and quota, and a wishlist panel on each product inside Shopify admin.
- **Dependencies:** Access to order data, which the app requests at install.
- **Frequency:** Weekly or monthly.
- **User value:** Evidence to show a manager.
- **Business value:** Justifies renewal and upgrade.
- **Differentiation:** Table stakes at dashboard level. A controlled test that proves extra revenue would be differentiated; I found no evidence that Swym or its rivals offer one.
- **UX considerations:** FACT: the revenue summary does not appear until real revenue exists ([help article](https://help.getswym.com/en/articles/13274798-smart-save)), so a new merchant sees nothing at the moment they most need reassurance. FACT: one August 2026 review says reports lagged hours or days behind live activity ([review](https://apps.shopify.com/reviews/2341712)).
- **Technical complexity:** Linking anonymous saves to later orders; deciding which orders to credit; keeping reports fresh at high volume.
- **Potential metrics:** Share of merchants who open the dashboard monthly; days to first credited order; report delay.
- **Feature maturity:** Mature in features. Weak relative to how much depends on it.

### 9. Swym for Sales

- **Purpose:** Give sales staff, in store or remote, each customer's saved products and tools to curate lists for them.
- **Target user:** Shop associates, stylists and sales reps.
- **Customer problem:** Online browsing and the physical shop are disconnected.
- **User workflow:** (1) The associate opens the customer on the Shopify till. (2) They see the wishlist, recently viewed products and any active online cart. (3) They build an in-store list and add notes such as size or occasion. (4) They email the list to the customer. (5) The customer buys online later. A rep can also turn a list into a quote or draft order.
- **Inputs:** The customer's identity, products, notes.
- **Actions:** View, create and share lists; create quotes and invoices with discounts.
- **Outputs:** A shared-list email, a draft order, and performance reports by shop and associate.
- **Dependencies:** Shopify's till system. FACT: a Lite version is included; Advanced plans are paid add-ons ([Swym for Sales](https://www.getswym.com/platform/swym-for-sales)).
- **Frequency:** Daily in shops that adopt it.
- **User value:** The associate looks informed and can follow up.
- **Business value:** A shop visit that ends without a sale can still convert online.
- **Differentiation:** Differentiated. I did not see it in the rival wishlist listings I checked.
- **UX considerations:** It adds steps at a busy till. It needs staff training and a reason for staff to bother.
- **Technical complexity:** Limits of till extensions; matching an in-store customer to an online profile.
- **Potential metrics:** Share of in-store customers with a list viewed or created; lists shared per associate; purchase rate of shared lists.
- **Feature maturity:** Basic to mature. Still developing.

### 10. Gift lists and registries

- **Purpose:** Let a shopper build a list for an occasion and share it so that others buy from it.
- **Target user:** Shoppers with weddings, babies or holidays ahead, and the people buying for them.
- **Customer problem:** Gift buyers guess, and often buy elsewhere.
- **User workflow:** (1) Create a registry with an occasion and date. (2) Add products. (3) Share the link. (4) Gift givers buy; the recipient's address stays hidden at checkout. (5) The registry marks what has been bought. (6) The recipient sends thank-you notes.
- **Inputs:** Event details and a delivery address.
- **Actions:** Run several registries; offer discounts to gift givers.
- **Outputs:** Orders linked to a registry, and occasion reports.
- **Dependencies:** Checkout integration and a separate subscription.
- **Frequency:** Seasonal.
- **User value:** The recipient gets what they want without duplicates.
- **Business value:** Gift givers are new customers the store did not pay to acquire.
- **Differentiation:** Table stakes inside the registry category.
- **UX considerations:** The gift giver is a first-time visitor, so their path must be very simple.
- **Technical complexity:** Hiding addresses at checkout; matching orders back to registry items.
- **Potential metrics:** Registries created; gift givers per registry; share of gift givers who are new customers.
- **Feature maturity:** Basic. FACT: 38 reviews since March 2023, English only ([listing](https://apps.shopify.com/swym-registry)).

### 11. Developer APIs

- **Purpose:** Let developers build custom wishlist experiences and connect other systems.
- **Target user:** In-house developers, agencies, headless stores and mobile apps.
- **Customer problem:** The standard widgets do not fit a custom storefront.
- **User workflow:** (1) Get access on the Premium plan or above. (2) Create a shopper ID. (3) Call the list and item endpoints, or use the JavaScript SDK. (4) Build the interface.
- **Inputs:** Store credentials and shopper identity.
- **Actions:** Create, update and delete lists; add and remove items; share; manage restock sign-ups. FACT: recently viewed products and saved carts are marked beta ([developer docs](https://developers.getswym.com/docs/swym-guides-landing)).
- **Outputs:** Data responses; custom webhooks on Enterprise.
- **Dependencies:** The Premium plan (US$99.99) or above.
- **Frequency:** At build time, then continuously in production.
- **User value:** Full control of design and behaviour.
- **Business value:** Keeps enterprise and headless accounts, which are the hardest to win back once lost.
- **Differentiation:** Differentiated against budget apps. Swish and Growave also support headless stores on their top plans.
- **UX considerations:** FACT: the docs publish an index for AI tools and a documentation server that AI coding assistants can query ([docs](https://developers.getswym.com/docs/mcp)). Rate limits are not stated on the landing page.
- **Technical complexity:** Keeping old integrations working as the API changes.
- **Potential metrics:** Stores with live API traffic; API error rate; time to a first successful call.
- **Feature maturity:** Advanced.

## Part 10 — End-to-end user journeys

The merchant's journey is short at the start and stalls in the middle: installing takes minutes, but value only appears after an automated message is switched on and a shopper responds. Rows marked FACT cite a source; the rest is INFERENCE from how Shopify apps are bought and from Swym's documentation.

| Stage | User goal | What the user does | What the system does | Friction and likely drop-off | Stakeholders | Product opportunity | Metric |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 1. Discovery | Find a wishlist for the store | Searches the Shopify App Store, asks their agency, or notices the feature on another brand's site | The listing shows 1,481 reviews, the “Built for Shopify” badge and “Popular with stores like yours” (FACT) | “From US$29.99/month” sits next to free rivals in “More apps like this” | Owner, marketer, agency | Clear “why pay” message on the listing | Listing views to installs |
| 2. Evaluation | Decide if it is worth the money | Reads reviews and pricing, tries the demo store, compares with Swish | Pricing cards, a public demo store, case studies | The merchant cannot translate “3,000 wishlist actions” into their own traffic | Owner, marketer | A usage estimator based on the store's sessions | Install rate |
| 3. Trial or demo | See it working on my store | Installs and starts the 30-day trial; large brands book a demo | Onboarding, setup through Shopify Sidekick, a summary of features switched on by default (FACT) | Theme fit; many options. FACT: a September 2026 review says installing is “almost more complicated with the new AI stuff” | Owner, developer | A preview inside the merchant's own theme | Button live within 24 hours |
| 4. Purchase | Approve the charge | Accepts the charge through Shopify at install; Enterprise needs a call and a quote | Shopify bills after the trial | Shopify Plus stores must start on Pro (FACT). FACT: one reviewer waited a week for a call to get a price above the top self-serve plan | Owner, finance | A published price above 25,000 actions | Trial-to-paid rate |
| 5. Implementation | Make it look native | Places buttons, styles them, adds a wishlist page and header icon; uses a developer for custom work | Theme blocks, editable button code, paid customisation from US$50 an hour (FACT) | Theme conflicts; waiting on support for fixes | Developer, agency, Swym support | Automatic checks that the button renders on every template | Days to go live; tickets per install |
| 6. Onboarding | Get alerts running | Switches on triggers; connects the ESP; reviews draft flows | A setup panel, ESP auto-detection, an AI assistant that lists unused features (FACT) | Flows are created as drafts. If nobody publishes them, nothing is sent and nothing looks broken | Marketer | A “nothing is sending yet” warning with one-click publish | Share with a live trigger by day 14 |
| 7. First value | See evidence that it works | Checks the dashboard | First saves appear. A revenue summary shows once revenue exists (FACT) | Low-traffic stores wait weeks | Owner, marketer | Show potential revenue from day one | Days to first save and to first credited order |
| 8. Activation | Reach the point where it runs itself | Leaves triggers running | Alerts go out when price or stock changes | The merchant never connects an ESP and never sees an alert sent | Marketer | Default-on mailer for stores without an ESP | Activation rate (defined below) |
| 9. Habit formation | Fold it into the weekly routine | The marketer reads flow revenue in the ESP; the merchandiser reads the most-saved list | Reports; an AI weekly report in early access (FACT) | The product runs in the background. Nothing brings the merchant back into Swym | Marketer, merchandiser | A weekly summary that names actions to take | Monthly active admins; report opens |
| 10. Expansion | Get more volume or more capability | Upgrades when quota warnings arrive; adds Back in Stock or the sales tools | Warnings at 50%, 75%, 90% and 100%; a usage panel with an upgrade button (FACT) | A forced upgrade feels like a penalty. Above the top plan the price is hidden | Owner, finance | Soft limits and automatic overage | Upgrade rate; share of accounts above 75% of quota |
| 11. Renewal | Keep or cut during a cost review | Nothing, if on a monthly plan; it renews automatically | Yearly plans at 17% off (FACT); Enterprise contracts | App audits when the Shopify bill is reviewed | Owner, finance | A renewal summary of revenue credited | Retention; share on yearly plans |
| 12. Churn | Stop paying or switch | Uninstalls from Shopify admin | Shoppers' saved lists disappear from the storefront | FACT: a downgrade is blocked when stored items exceed the lower plan's limit, which leaves uninstalling as the only way to pay less | Owner | A pause or low-cost holding plan | Churn by stated reason |

Sources for the FACT cells: [App Store listing](https://apps.shopify.com/swym-relay), [plan comparison](https://help.getswym.com/en/articles/11959983-wishlist-plus-pricing-features), [Smart Save help](https://help.getswym.com/en/articles/13274798-smart-save), [customisation services](https://www.getswym.com/customization-services), [product updates](https://www.getswym.com/product-updates), [review, May 2025](https://apps.shopify.com/reviews/1745375).

### The aha moment

INFERENCE: the aha moment is the first time a merchant sees an order credited to a wishlist alert. A weaker, earlier version is seeing a ranked list of the products shoppers want. Swym's own design supports this reading: the home dashboard shows a revenue figure as soon as one exists.

### The activation event

Swym does not publish its definition. My proposal:

- **Activation event:** the first automated reminder or alert delivered to an identified shopper.
- **Activation threshold:** within 30 days of install, at least one trigger live and at least 50 saves from shoppers the store can contact.

The reasoning for 50: an alert can only produce a sale if it reaches someone. If about one in twenty alerted shoppers buys (my assumption, to be replaced with real data), 50 contactable saves should produce two or three orders. That is enough for the merchant to notice. Both numbers are HYPOTHESIS and should be tested against retention data.

### Behaviours that likely predict long-term retention

All HYPOTHESIS, ordered by my confidence.

1. An ESP is connected and at least two triggers are live.
2. More than 30% of saves come from shoppers the store can contact.
3. Saving is available in more than one place: product page, collection page and cart.
4. Usage sits comfortably below the cap, between about 30% and 70% of quota.
5. A second Swym app is installed.
6. The store is on a yearly plan.
7. The store has custom code on the API, or staff using the till extension.

## Part 11 — User flow analysis

Four flows explain the product: the merchant's path to first value, the shopper's path from save to purchase, the quota path, and the in-store path.

### Flow A — Merchant: install to first value

```
Find Wishlist Plus in the Shopify App Store
↓
Install and approve the 30-day trial
↓
Place the wishlist button (setup panel, theme editor, or ask Sidekick)
↓
Review the features Swym switched on by default
↓
Connect Klaviyo, or keep Swym's built-in mailer
↓
Publish the draft flows
↓
Shoppers save products
↓
First reminder or alert is delivered
↓
First order is credited on the home dashboard
```

| Step | User intent | System response | Friction and mental effort | Failure mode | Opportunity |
| --- | --- | --- | --- | --- | --- |
| Install | Try it | Trial starts; charge approved through Shopify | Low | Leaves at the price screen | Show expected return before the charge |
| Place the button | Make it visible | Button appears on product pages | Medium: where to put it, which style | Button does not render on the theme | Automatic render check per template |
| Review defaults | Understand what is on | A summary with a Manage link for each feature | Medium: unfamiliar terms such as Smart Save | Merchant misses that automatic saves use quota | State the quota effect beside the toggle |
| Connect the ESP | Use my own email tool | Draft flows are created in Klaviyo | Medium: two tools open at once | Authorisation expires; flows stay as drafts | A status line: “0 flows live” |
| Publish flows | Start sending | Events begin to trigger messages | Low once found | Never done | One-click publish from inside Swym |
| Wait for saves | See activity | Saves appear in reports | Low, but slow | Low traffic means no saves | Education nudge for shoppers; Smart Save |
| First alert and order | Proof | Revenue shows on the dashboard | None | No identified shoppers, so no alert can be sent | Stronger email capture at the moment of saving |

### Flow B — Shopper: save to purchase

```
Browse a product page
↓
Tap the heart   (or view the product 5 times → Smart Save)
↓
Product is saved against the browser ID
↓
Prompt: add an email to keep your list
↓                          ↘
Shopper identified           Shopper stays anonymous
↓                            (list works on this browser only; no messages possible)
Event goes to the ESP or mailer
↓
Trigger fires: 24-hour reminder, price drop, low stock or back in stock
↓
Shopper clicks through to the product or the list
↓
Adds to cart and buys
↓
Order is credited to the wishlist
```

| Step | User intent | System response | Friction and mental effort | Failure mode | Opportunity |
| --- | --- | --- | --- | --- | --- |
| Tap the heart | Remember this | Heart fills; item saved | Very low | Button hidden until cookie consent on the classic style (FACT) | Use the consent-friendly mode by default |
| Email prompt | Keep the list | Email stored; optional marketing opt-in | Medium: “why do you need my email?” | Shopper dismisses it and stays anonymous | Ask at a better moment, such as on the second save |
| Receive the message | Decide again | Email or text with the saved product | Low | Message lands weeks later, after interest has gone | Timing by product type |
| Return and buy | Complete the purchase | Product or list page | Low | Size no longer in stock | Offer a restock sign-up in the same message |

### Flow C — Quota

```
Usage reaches 50% → 75% → 90% → 100%   (a notice at each point)
↓
At 100%: the wishlist is paused on the storefront
↓
Merchant upgrades (takes effect at once)   or   waits for the monthly reset
↓
Above 25,000 actions a month: contact sales for an Enterprise quote
```

FACT: this is how the [plan comparison](https://help.getswym.com/en/articles/11959983-wishlist-plus-pricing-features) describes it. The failure mode is severe: shoppers lose a feature mid-month, and the merchant learns about a billing limit from their own customers.

### Flow D — In store

```
Customer walks in → associate opens their profile on the till
↓
Associate sees the wishlist and recently viewed products
↓
Associate builds an in-store list and adds notes
↓
Associate emails the list to the customer
↓
Customer buys online later
```

### The six paths that matter

1. **Shortest path from signup to first value.** Flow A using Swym's own mailer. A busy store could see a first reminder sent within a day.
2. **Shortest path from first value to recurring value.** Switch on the price-drop and restock triggers. After that, every sale and every restock sends alerts with no further work.
3. **Most important recurring workflow.** The automated loop in Flow B. No person runs it.
4. **Most valuable workflow.** A restock or price-drop alert on a product many shoppers saved. These shoppers have already chosen the product.
5. **Most complex workflow.** A custom storefront built on the API, with an enterprise ESP and several countries. It needs the merchant's developers, the ESP team and Swym's support.
6. **Most failure-prone workflow.** Two candidates: the quota pause in Flow C, and the hand-off from anonymous to identified in Flow B. The second is the larger silent loss, because a save from someone the store cannot contact produces no message at all.

## Part 12 — UX and UI analysis

The shopper-facing experience is light and well judged. The merchant-facing experience is weakest exactly where money is involved: limits, defaults and proof of value. This critique is built from documentation, release notes and reviews. I have not clicked through the admin myself, so treat layout details as INFERENCE.

### Information architecture

- **Navigation.** The app sits inside Shopify admin. Documentation names these areas: Home dashboard, Analytics or Insights, Configurations, Marketing (with Automations), Integrations, Customers, and Plan & Billing.
- **Hierarchy.** Settings are grouped by merchant goal, for example “Help Shoppers Save Favorites”. That is friendlier than a feature list. It is also deep: reaching the Smart Save setting takes Configurations → Features → Help Shoppers Save Favorites → Smart Save → Settings (FACT: [help article](https://help.getswym.com/en/articles/13274798-smart-save)).
- **Search.** Not publicly documented.
- **Discoverability.** An AI assistant reviews the setup and points out unused features and unconnected integrations (FACT: [April 2026 update](https://www.getswym.com/product-updates/april-2026)).
- **Organisation.** Wishlist, restock alerts and registries are three apps with three admin areas.
- **Information density.** Not assessable without access.
- **Naming.** Documentation uses “Insights” and “Analytics” for the same area, and both “Saved for you” and “Save for you”.

### Interaction design

- **Number of clicks.** Saving a product takes one click for the shopper. Connecting Klaviyo takes about two minutes. Changing a core setting takes four or five clicks.
- **Forms.** The only shopper form is the email or phone prompt.
- **Defaults.** Two defaults matter. Smart Save has been on by default for many merchants. Marketing flows are created as drafts. The first default spends the merchant's quota without asking. The second protects against unwanted sends but hides value.
- **Bulk actions.** Exports to spreadsheet files, including a streaming export for very large alert logs.
- **Automation.** Strong. Triggers and Shopify Flow do the recurring work.
- **Error handling.** Quota warnings at four levels, and a one-click banner to re-authorise Klaviyo. The weak point is the outcome at 100%: the feature is paused for shoppers.
- **Confirmations.** Before the Klaviyo connection, Swym shows what is about to happen (FACT: [August 2026 update](https://www.getswym.com/product-updates/august-2026)).
- **Undo and recovery.** Shoppers can undo an automatic save. Merchants have less recovery: when stored items reach the plan limit the oldest records are removed, and a downgrade can be blocked.

### Usability

- **Learning curve.** Low for the basic wishlist. Medium once marketing flows are involved.
- **Cognitive load.** High around limits. A merchant must track monthly wishlist actions, lifetime stored items and monthly sends.
- **Complexity.** Rising. One September 2026 reviewer, a repeat installer, found setup harder than before.
- **Consistency.** Buttons now copy the theme's own button style automatically (July 2026).
- **Accessibility.** FACT: Swym published a conformance report against the WCAG 2.1 AA accessibility standard in April 2026.
- **Discoverability for shoppers.** Addressed by an education nudge that prompts browsing shoppers to save.

### Enterprise UX

| Area | Finding |
| --- | --- |
| Permissions and roles | Not publicly documented for Swym's own admin. INFERENCE: it relies on Shopify's staff permissions. |
| Approval workflows | Not materially applicable. The product is configured by one or two people, not routed for approval. |
| Audit logs | A log of every alert sent exists. A log of configuration changes is not publicly documented. |
| Admin controls | Per-feature toggles, consent modes, language settings. |
| Configuration | Editable button code in the admin; full API on the top plans. |
| Governance | Consent handling follows Shopify's own consent system. Multi-country support is limited to Enterprise. |

### Top 10 UX strengths

1. Saving takes one click and needs no account.
2. Shoppers control automatic saving: undo once, or switch it off for themselves.
3. The wishlist can work before cookie consent by keeping saves on the device.
4. Klaviyo connects in about two minutes, with draft flows and a preview of what will change.
5. Setup can be done by describing what you want to Shopify's Sidekick assistant.
6. Buttons inherit the theme's own button shape and font.
7. Button code can be edited in the admin with no support ticket.
8. A usage panel shows how much quota is left and how long it will last.
9. Wishlist data appears where merchants already work: on product pages in Shopify admin, in customer segments and in the ESP.
10. After onboarding, a summary lists what was switched on by default, each with a Manage link.

### Top 10 UX weaknesses

| # | Weakness | Likely user and business impact |
| --- | --- | --- |
| 1 | The wishlist is paused on the live storefront at 100% of quota. | Shoppers meet a broken feature. The merchant hears about a billing limit from customers. Quota and pricing form one of the two largest themes in 1-star reviews. |
| 2 | Three overlapping limits: monthly actions, lifetime stored items, monthly sends. | Merchants cannot forecast cost. Support has to explain it. |
| 3 | A default that spends the merchant's quota (Smart Save). | Loss of trust. FACT: at least three 1-star reviews in 2026 name it. |
| 4 | Value is invisible early: revenue is hidden until it exists, and flows start as drafts. | Trials end before the merchant sees proof. |
| 5 | Button display is fragile across themes and consent settings. | Saves are silently lost. Merchants are told “it works on our end”. |
| 6 | The oldest saved items are deleted when the storage limit is reached. | Shoppers' older lists shrink without notice. |
| 7 | Downgrades are blocked when stored items exceed the lower plan's limit. | The merchant feels trapped and uninstalls instead. |
| 8 | Three apps, three bills, three admin areas. | A split experience and a harder cross-sell. |
| 9 | Some integrations need Swym's support team to set up. | Days of waiting before value. |
| 10 | Deep settings, uneven naming and weak translation options. | Slower setup. FACT: a June 2026 1-star review cites translation. |

## Part 13 — Onboarding and activation

Installing is fast. The delay is between “button live” and “first message sent”, and that is where most trial stores are likely lost.

| Step | What exists today | Label |
| --- | --- | --- |
| Signup | No separate account. The merchant installs through Shopify and grants data access, which includes customers, products, orders and the theme. | FACT — [App Store listing](https://apps.shopify.com/swym-relay) |
| Trial | 30 days on every paid plan. No free plan for Wishlist Plus. | FACT |
| Demo | A public demo store, and a “Book a demo” form for larger brands. | FACT — [homepage](https://www.getswym.com/) |
| Setup | A setup panel, setup through Sidekick, and automatic style matching. | FACT — product updates |
| Data import | The listing mentions import and export of lists. A guided migration from rival apps is not publicly documented. | FACT plus gap |
| Integrations | The app detects the store's ESP and recommends the matching connection. | FACT — [January 2026 update](https://www.getswym.com/product-updates/january-2026) |
| Invitations | Not materially applicable. This is not a tool that spreads by inviting colleagues. | — |
| Configuration | Defaults are applied, then summarised. | FACT |
| Templates | Email templates, draft Klaviyo flows, Shopify Flow templates, and 14 written playbooks. | FACT — [August 2026 update](https://www.getswym.com/product-updates/august-2026) |
| Guided setup | An AI setup assistant that also diagnoses storefront problems, and a BFCM readiness checklist. | FACT — [June 2026 update](https://www.getswym.com/product-updates/june-2026) |
| Education and training | Webinars, a campaign calendar, Klaviyo office hours. Training for shop staff is not documented. | FACT plus gap |

### Time to first value

These are my estimates, with the reasoning.

- **Button live:** minutes.
- **First save:** the same day for a store with about 1,000 sessions a day, if roughly 3% of sessions save something (assumption).
- **First message sent:** about a day later, because the standard reminder waits 24 hours.
- **First credited order:** between a few days and three weeks, depending on traffic and on how many savers shared an email.

INFERENCE: the 30-day trial is sized to cover this wait.

### Onboarding drop-off points

1. The price screen at install, now that there is no free plan.
2. The button not appearing correctly on the theme.
3. No ESP connected. FACT: the Klaviyo link needs the Pro plan, so Starter stores rely on Swym's own mailer.
4. Flows left as drafts.
5. Too few identified shoppers, so no alert can be sent.
6. The trial ending with no revenue figure on screen.

### Recommended improvements

| Rank | Improvement | Impact | Effort | Confidence |
| --- | --- | --- | --- | --- |
| 1 | A “nothing is sending yet” warning with one-click publishing of default reminders | High | Low | High |
| 2 | A day-one view of potential revenue: the value of saved items and a projected recovery, replaced by real numbers as they arrive | High | Low to medium | Medium |
| 3 | A usage estimator at plan selection, and no metering of automatic saves during the trial | High | Medium | High |
| 4 | An automatic storefront check that the button renders on each page type and consent state, with an alert when it does not | High | Medium | Medium |
| 5 | Tests on when and how the email prompt appears | High | Medium | Medium |
| 6 | Exclude staff, developer and pre-launch traffic from metering | Medium | Low | High |
| 7 | A trial-end summary: saves, contactable shoppers, alerts sent, orders | Medium | Low | Medium |
| 8 | A guided import from rival wishlist apps | Medium | Medium | Medium |
| 9 | One onboarding across wishlist, restock alerts and registries | Medium | High | Low |

## Part 14 — Retention

Merchants keep Swym because it becomes embedded, not because they use it every day. Retention rests on accumulated shopper lists and on marketing flows that depend on Swym's events. The whole of this part is INFERENCE unless marked; Swym publishes no retention figures.

| Retention driver | Strength | Why |
| --- | --- | --- |
| Habit formation | Weak for merchants | The product runs in the background. Few people open it daily. |
| Workflow dependency | Strong on higher plans | ESP flows, Shopify Flow automations and till routines all start from Swym events. |
| Data accumulation | Strong | Saved lists and restock sign-ups build up for years. FACT: plans store 15,000 to 125,000 items. |
| Collaboration | Weak | Limited to list sharing between a sales rep and a customer. |
| Integrations | Strong | 20+ marketing tools. Each connection is something to rebuild elsewhere. |
| Switching costs | Low for small stores, high for large ones | See Part 49. |
| Institutional knowledge | Moderate | Flows, templates and playbooks are tuned over time. |
| Reporting | Moderate | “Revenue from wishlist” enters the marketer's monthly report. |
| Compliance | Moderate at Enterprise | A vendor that has passed security review is costly to replace. |
| Automation | Strong | Alerts fire with no human effort, so there is no daily reason to question the tool. |
| Network effects | None | A shopper's list on one store has no link to another store. |
| Ecosystem effects | Moderate | Partner status with Shopify and Klaviyo keeps Swym recommended. |

### Retention loops

**Loop 1 — Proof of revenue.** This is the main loop.

```
Shoppers save products
↓
Saved items accumulate
↓
Price and stock changes trigger alerts
↓
Alerts bring orders
↓
The dashboard shows credited revenue
↓
The merchant keeps the app and adds more places to save
↓
More saves
```

**Loop 2 — Shopper expectation.**

```
A shopper builds a list on the store
↓
They return to it through their account page and alert emails
↓
They expect it to be there
↓
The merchant cannot remove the feature without disappointing loyal shoppers
```

**Loop 3 — Integration lock-in.**

```
The merchant connects an ESP
↓
Flows and segments are built on Swym's events
↓
Those flows earn revenue that shows in the ESP's own reports
↓
More flows are built
↓
Removing Swym would break them
```

**Loop 4 — Demand insight.** Weak today, and the largest untapped loop.

```
Saves reveal which products are wanted
↓
The merchandiser restocks or discounts those products
↓
Availability and price improve
↓
More saved items convert, and more shoppers save
```

**Loop 5 — Shop to online.**

```
An associate builds and shares a list
↓
The customer buys online
↓
The sale is credited to the associate or shop
↓
Associates use the tool again
```

**Loop 6 — The quota loop, which works against retention.**

```
The store succeeds and saves increase
↓
Monthly quota fills faster
↓
The merchant must upgrade, or the wishlist pauses
↓
Success feels like a penalty
↓
The merchant looks at rivals with no usage cap
```

Every other loop gets stronger with usage. This one gets worse with usage. That makes pricing mechanics a retention problem, not only a revenue question.

## Part 15 — Virality and network effects

Swym has almost no virality in the usual sense. Its growth engine is marketplace ranking plus partners.

| Mechanism | Present? | Notes |
| --- | --- | --- |
| Invitations | No | Merchants do not invite other merchants. |
| Collaboration | No | Not a team tool. |
| Sharing | Yes, but it benefits the merchant | A shopper who shares a wishlist or registry sends visitors to the store, not to Swym. |
| External users | Yes | Shoppers and gift givers. |
| Referrals | Through agencies | FACT: 200+ agencies in a free programme that pays them as their clients grow ([agency programme](https://www.getswym.com/agency-program)). The commission rate is not published. |
| Direct network effects | None | — |
| Data network effects | Weak today | FACT: Swym has passed 1 billion intent actions and publishes benchmark reports from that data. HYPOTHESIS: the same data could train better timing or product ranking, but no shipped feature shows this yet. |
| Marketplace effects | Strong | More installs and reviews lift App Store ranking, which brings more installs. This is the closest thing to a flywheel. |
| Partner effects | Strong | Swym appears in the partner directories and documentation of Klaviyo, Braze, Iterable, Attentive and Bloomreach. |
| Ecosystem effects | Moderate | Shopify features the app in three editorial collections on its listing (FACT: [App Store listing](https://apps.shopify.com/swym-relay)). |

### Which growth model is this?

**Hybrid.** Three motions run side by side.

- **Product-led, through a marketplace, for small and mid-sized stores.** A merchant searches “wishlist”, installs, starts a trial and is billed through Shopify. No salesperson is involved. FACT: in 2017 the CEO said every customer came through Shopify.
- **Partner-led.** Agencies recommend it during store builds, and the Klaviyo relationship produces joint guides, webinars and event presence.
- **Sales-assisted for Enterprise.** A demo form, custom pricing, a dedicated customer success manager and round-the-clock support.

It is not community-led: I found no public forum or user community. It is not marketing-led in the paid sense either; the visible marketing is content, such as playbooks, benchmark reports and a campaign calendar.

**Why the hybrid fits.** The price is too low to pay for a salesperson on a US$30 account, so small stores must serve themselves. Large brands will not hand shopper data to a tool without a security review and a named contact, so they need people.

## Part 16 — Business model

Swym sells tiered subscriptions where each tier is a usage allowance plus a set of features. It is not pay-as-you-go: there is no overage charge, only a forced move to the next tier.

| Model | Used? | How |
| --- | --- | --- |
| Subscription | Yes | Monthly or yearly, billed through Shopify. Yearly saves 17%. |
| Usage-based | Partly | Tiers are capped by monthly wishlist actions, stored items and sends. FACT: extra quota cannot be bought separately. |
| Seat-based | No | Staff accounts are not counted. |
| Tiered | Yes | Starter, Pro, Premium, Enterprise. |
| Module-based | Yes | Wishlist Plus, Back in Stock Alerts and Gift Registries are billed separately. Advanced sales tools are a paid add-on. |
| Transaction pricing | No | Swym takes no share of the sales it helps recover. |
| Services | Small | Customisation from US$50 an hour. |

### The seven questions

1. **Who pays?** The merchant, on their Shopify bill.
2. **What exactly are they paying for?** A monthly allowance of wishlist actions, access to features and integrations, and a level of support.
3. **What makes the bill increase?** More traffic. Switching on Smart Save, which Swym says triples actions. Needing Klaviyo, which requires Pro. Needing developer access, which requires Premium. Being on Shopify Plus, where Pro is the minimum. Adding the restock or registry apps.
4. **What causes expansion?** Tier upgrades forced by quota, a second or third app, the Enterprise plan, and the advanced sales add-on.
5. **What causes contraction?** Downgrades and dropping a second app. FACT: a downgrade is blocked if stored items exceed the lower plan's limit, so contraction is mechanically limited.
6. **What causes churn?** Covered in Part 37.
7. **Does the pricing metric match customer value?** Only partly. A wishlist action is an input, not a result. A save from a shopper the store cannot contact uses quota and can never trigger a message. An automatic save uses quota without the shopper acting. INFERENCE: the metric was chosen because it grows with store traffic, and so with ability to pay, and because it is easy to count. What it sacrifices is predictability and a sense of fairness.

## Part 17 — Pricing

All prices are in US dollars and were read on 7 October 2026 from the [pricing page](https://www.getswym.com/pricing), the [App Store listing](https://apps.shopify.com/swym-relay) and the [plan comparison](https://help.getswym.com/en/articles/11959983-wishlist-plus-pricing-features).

### Wishlist Plus

| Plan | Target customer | Price | Main features | Limits | Upgrade trigger |
| --- | --- | --- | --- | --- | --- |
| Starter | “Growing brands” | $29.99 a month, or $299.99 a year | Wishlists on product and collection pages, save for later, Smart Save, multiple lists, social and email sharing, email capture, reminders, price-drop and stock alerts through Swym's mailer, till integration | 3,000 actions a month; 15,000 stored items. Not available to Shopify Plus stores | Passing 3,000 actions, or wanting Klaviyo |
| Pro (“most popular”) | “Ambitious brands” | $59.99 a month, or $599.99 a year | Everything in Starter, plus Klaviyo, Attentive, Tapcart and Omnisend, Meta ads retargeting, customer segments, wishlist summary alerts, priority support | 10,000 actions a month; 50,000 stored items | Passing 10,000 actions, or needing developer access |
| Premium | “Large brands needing API access” | $99.99 a month, or $999.99 a year | Everything in Pro, plus REST API, JavaScript SDK, custom data models, advanced configuration, support replies within 4 hours on weekdays | 25,000 actions a month; 125,000 stored items | Passing 25,000 actions, or needing enterprise ESPs or multi-country support |
| Enterprise | “High-growth Shopify Plus brands with global storefronts” | Custom. One reviewer was quoted $299 a month in 2025 ([review](https://apps.shopify.com/reviews/1745375)); treat as an anecdote | Everything in Premium, plus enterprise ESPs, Shopify Markets, custom webhooks, premium hosting, a dedicated success manager, 24×7 support with 2-hour replies | “100,000+” a month on the pricing page; “250,000+” in the help centre | — |

### Back in Stock Alerts

| Plan | Price | Main features | Limit |
| --- | --- | --- | --- |
| Free | $0 | Manual alerts, size-level sign-ups, reports. Shown on Swym's pricing page but not on the App Store listing, where one reviewer says the app became paid-only | 50 alert requests a month |
| Starter | $19.99 a month, or $199.99 a year | Automatic alerts, Klaviyo and Omnisend, pre-order alerts, email opt-ins | 1,000 alert requests a month |
| Pro | $59.99 a month, or $599.99 a year | Mailchimp, Facebook pixel, batch sending, custom branding, till support | 10,000 a month |
| Premium | $99.99 a month, or $999.99 a year | Custom email templates, several stock locations, JavaScript API, advanced stock controls | 25,000 a month |
| Enterprise | Custom | Enterprise integrations, dedicated success manager | Unlimited |

Source: [pricing page](https://www.getswym.com/pricing), [Back in Stock listing](https://apps.shopify.com/watchlist).

### Gift Lists and Registries

| Plan | Price | Limit |
| --- | --- | --- |
| Free | $0 | 5 active registries |
| Starter | $15 a month | 25 active registries |
| Pro | $50 a month | 100 active registries |
| Premium | $99 a month | 250 active registries |

Source: [Registry listing](https://apps.shopify.com/swym-registry).

### Evaluation

- **Free plan.** None for Wishlist Plus. It was removed in the first half of 2026.
- **Free trial.** 30 days on every paid plan, long for this category.
- **Cost per action.** $29.99 ÷ 3,000 is about 1.0 cent. $59.99 ÷ 10,000 is about 0.6 cents. $99.99 ÷ 25,000 is about 0.4 cents. The unit price falls with volume.
- **Step size.** The steps are steep. One action past 3,000 doubles the bill. One past 10,000 adds 67%. One past 25,000 moves the merchant to a quote; if the $299 anecdote is typical, that is roughly a tripling.
- **Against rivals.** FACT: Swish charges $29, $49 or $99 a month by Shopify plan with unlimited saved items on its paid tiers ([Swish listing](https://apps.shopify.com/wishlist-king)). FACT: Wishlist Hero charges $29 for 10,000 additions a month ([listing](https://apps.shopify.com/wishlist-hero)). For 10,000 actions Swym costs about twice Wishlist Hero, and a mid-traffic store on a standard Shopify plan pays Swym two to three times what it would pay Swish.
- **Packaging.** Klaviyo sits on Pro. That is a strong upgrade trigger. It also means Starter merchants are cut off from the channel where most value is realised, which should make them more likely to leave. This trade-off deserves a test.
- **Upgrade friction.** Self-serve up to Premium. Above that, a sales call.
- **Enterprise pricing.** Hidden. INFERENCE: it is priced per account by volume and support needs.
- **Inconsistencies in the published material.** The Enterprise threshold is stated two ways. The free restock plan appears on the website but not on the listing. The help centre describes marketing integrations under Starter in the text but under Pro in its table. Small errors like these erode trust on a pricing page.

### Is the product priced according to the value it creates?

No, in both directions.

- **For engaged mid-sized and large stores it is priced far below value.** If the published case studies are even roughly right, Swym keeps between 0.4% and 6% of the revenue it is credited with. The working: a 239-times return means the fee is 1 ÷ 239, about 0.4%, of credited revenue; a 16.6-times return means 1 ÷ 16.6, about 6%.
- **For small or low-traffic stores it is priced above perceived value.** They pay $30 a month for a button few shoppers use, with no ESP link to turn saves into sales.

The price level is not the main problem. The metric and the feature gates are.

## Part 18 — Unit economics

Swym is private and publishes none of these figures. The table states what is known, what can be inferred, and what data would settle it. Each term is defined in its row.

| Measure | Meaning | Reported? | What can be inferred |
| --- | --- | --- | --- |
| ARPU | Average revenue per paying merchant per month | Not publicly available | List prices run from $15 to $99.99 per app. HYPOTHESIS: a blended $40 to $70 for self-serve accounts, with Enterprise several times higher. |
| CAC | Cost to acquire one paying customer | Not publicly available | INFERENCE: low. Acquisition is mostly App Store search, agencies and partner content. The real costs are support during trials and the partner team. |
| Gross margin | Share of revenue left after the direct cost of serving customers | Not publicly available | INFERENCE: hosting is material, because Swym's script runs on storefront pages and peaks above 1 million requests a minute (FACT, [homepage](https://www.getswym.com/)). Shopify also takes a share of app revenue above a threshold; as far as I know it is 15% above the first US$1 million, which I did not verify. |
| LTV | Total gross profit from one customer over their life | Not publicly available | Formula: ARPU × gross margin ÷ monthly churn. Illustration only: $50 × 75% ÷ 3% = $1,250. All three inputs are my assumptions. |
| NRR | Net revenue retention: revenue from last year's customers today, including upgrades, as a share of what they paid then | Not publicly available | INFERENCE: quota-forced upgrades push it up; small-store closures pull it down. |
| GRR | Gross revenue retention: the same, ignoring upgrades | Not publicly available | INFERENCE: limited by the high failure rate of small online stores, which no app controls. |
| Churn | Share of customers lost per period | Not publicly available | Signals only. FACT: Store Leads shows Wishlist Plus installs up 23.9% in a year but flat in the last quarter, and Back in Stock installs down 9.0% in a year. |
| Expansion | Extra revenue from existing customers | Not publicly available | Mechanism is clear: tier steps, extra apps, Enterprise. |
| Payback period | Months of gross profit needed to recover CAC | Not publicly available | INFERENCE: short, because CAC is low. |

**Data needed to replace these guesses:** paying merchants by plan; trial-to-paid conversion; monthly customer and revenue churn by signup cohort; share of revenue from Enterprise; support cost per merchant; hosting cost per million actions; fees paid to Shopify.

## Part 19 — Go-to-market strategy

Swym's go-to-market model is a hybrid led by the Shopify App Store, reinforced by partners, with a small sales-assisted layer for large brands. “Go-to-market” here means how the company finds customers and gets them to pay.

| Channel | Evidence | Assessment |
| --- | --- | --- |
| Marketplace (Shopify App Store) | FACT: 1,481 reviews, “Built for Shopify” badge, three editorial features, every website button leads to the listing. | The primary channel. Ranking for “wishlist” is the single most valuable asset. |
| Search and content | FACT: a blog, benchmark statistics pages, 14 playbooks, a yearly campaign calendar, and a report co-written with Klaviyo. | Aimed at retention marketers rather than store owners. Builds credibility with the champion. |
| Paid acquisition | Not publicly available. I found no evidence of significant paid advertising. | Probably minor. |
| Outbound sales | Not publicly available. | Probably minor. A current job post describes outreach to existing merchants, not cold prospecting. |
| Inbound | FACT: a “Book a demo” form and live webinars. | Serves larger brands that want a conversation. |
| Partnerships | FACT: Klaviyo Preferred Partner since February 2026; 20+ marketing-tool partners; listed in partners' own documentation. | The second engine. Swym's value is realised inside the ESP, so the ESP's audience is the right audience. |
| Agencies | FACT: 200+ agencies, with named partners including Domaine and The Working Party. | Agencies decide the app stack during store builds. |
| Events | FACT: present at Klaviyo's K:BOS conference and at Style & Scale in 2026. | Follows the partner strategy. |
| Referrals | Through agencies only. | No merchant-to-merchant referral scheme is visible. |
| Product-led acquisition | Shoppers and merchants see the wishlist on other stores. | Passive. Whether lower plans show Swym branding is not confirmed. |
| Enterprise sales | FACT: custom pricing, dedicated success manager, 24×7 support. | A thin layer over a self-serve base. |

Sources: [App Store listing](https://apps.shopify.com/swym-relay), [homepage](https://www.getswym.com/), [agency programme](https://www.getswym.com/agency-program), [February](https://www.getswym.com/product-updates/february-2026) and [August 2026](https://www.getswym.com/product-updates/august-2026) updates.

### Why this model fits the product

- **The price forces self-service.** A US$30 account cannot pay for a salesperson. The marketplace does the selling and Shopify does the billing.
- **The buyer is already in the marketplace.** A merchant who wants a wishlist searches the App Store first.
- **The value is realised next door.** Most revenue comes through the ESP, so co-marketing with Klaviyo reaches the people who feel the benefit.
- **Large brands need people.** They ask for a security review, a contract and a named contact.

**The exposure.** One marketplace and one ESP partner carry most of the weight. A ranking change by Shopify, or a product move by Klaviyo, would hit acquisition directly.

## Part 20 — Sales motion

The sales motion changes from no human contact at the bottom to a consultative sale at the top. Swym publishes nothing about its sales team, so cycle lengths are estimates.

| Segment | Motion | Buying committee | Sales cycle | Procurement and security | Implementation |
| --- | --- | --- | --- | --- | --- |
| Small stores (Starter) | Self-serve install | The owner | Minutes to days | None. Billed through Shopify | Self-setup, with chat support |
| Mid-market and smaller Shopify Plus (Pro, Premium) | Self-serve, with an optional demo and support-led onboarding | Head of ecommerce, CRM marketer, developer or agency | Days to a few weeks; the 30-day trial sets the pace | Light | Agency or Swym's paid customisation |
| Enterprise | Sales-assisted | Adds IT, security, legal and the ESP owner | HYPOTHESIS: several weeks to a few months | Security review and data-processing terms | Integrations set up by Swym's team, a dedicated success manager |

**Roles.** The number of account executives or sales development reps is not publicly available. FACT: the booking link in the August 2026 release note goes to a “customer success team” calendar. INFERENCE: sales and customer success are blended in one small team, which is normal for a company of this size.

**How the motion changes with customer size.** Three things change. More people must agree. The question moves from “does it work?” to “is it safe and will it scale?”. And price moves from a public card to a negotiated quote.

**A visible weak spot.** FACT: one merchant who outgrew the Pro quota reports waiting a week for a call to learn the next price ([review](https://apps.shopify.com/reviews/1745375)). A sales-assisted step placed in the middle of a self-serve journey loses customers who were ready to pay.

## Part 21 — Customer success

Support is Swym's most praised feature and, in 2026, a growing complaint. Both facts come from the same review page.

| Area | What exists | Label |
| --- | --- | --- |
| Implementation | Self-serve. Support fixes theme and design issues on request. Paid customisation for larger work. | FACT — reviews, [customisation services](https://www.getswym.com/customization-services) |
| Onboarding | In-app setup, an AI assistant, and bookable calls. | FACT — product updates |
| Training | Webinars, playbooks, office hours with Klaviyo. | FACT |
| Support levels | Starter: chat and email on weekdays, typical reply in 24 to 48 business hours. Pro: priority. Premium: under 4 hours on weekdays. Enterprise: 24×7, under 2 hours. | FACT — [plan comparison](https://help.getswym.com/en/articles/11959983-wishlist-plus-pricing-features) |
| How support works | “When a merchant ticket arrives, AI drafts the first response.” | FACT — [job post](https://jobs.weekday.works/wkdypfybxt) |
| Customer success | A dedicated manager on Enterprise only. | FACT — [pricing page](https://www.getswym.com/pricing) |
| Account management and expansion | Quota warnings in the product; calls with the success team. | FACT plus INFERENCE |
| Renewal | Automatic through Shopify. | FACT |

### High-touch, low-touch or tech-touch?

**Hybrid, by plan.** “Tech-touch” means help delivered by software alone. “Low-touch” means a shared human team. “High-touch” means a named person.

- Starter is tech-touch with a slow human backstop.
- Pro and Premium are low-touch.
- Enterprise is high-touch.

The prices leave no other choice.

### Two observations

- **Support is doing work the product should do.** Many 5-star reviews thank a named agent for making the button fit the theme. That is good service. It is also a sign that self-serve theme fit is not yet reliable. Each such fix costs staff time on a US$30 account.
- **The strain is showing.** FACT: 1-star reviews from October 2025 to February 2026 describe unresponsive live chat and support insisting everything works ([1-star reviews](https://apps.shopify.com/swym-relay/reviews?ratings%5B%5D=1)). INFERENCE: a support model that leans on AI-drafted replies saves cost, and risks the one thing reviewers consistently praise.

## Part 22 — Integration ecosystem

Integrations are the product's strongest differentiator. Swym's data is only worth something once it reaches the tool that sends the message. Partner names below are FACT from the [technology partners page](https://www.getswym.com/technology-partners), the [App Store listing](https://apps.shopify.com/swym-relay) and the [pricing page](https://www.getswym.com/pricing).

### The map

| Category | Integrations | Notes |
| --- | --- | --- |
| Identity | Shopify customer accounts; Swym's own shopper ID | Single sign-on and user provisioning for staff are not materially applicable. Merchant staff reach Swym through their Shopify login. |
| Productivity | None | Not materially applicable. Swym does not connect to calendars, documents or chat tools. |
| CRM and marketing automation | Klaviyo, Omnisend, Mailchimp, Brevo, Dotdigital, Braze, Iterable, Emarsys, Listrak, Ometria, Sailthru, Cordial, Bluecore, Bloomreach, Retention Science | In ecommerce the ESP plays the role a CRM plays elsewhere. This is the core category. |
| Text and push messaging | Attentive, Postscript, Twilio, Yotpo SMS, PushOwl | — |
| Advertising | Meta (Facebook and Instagram) | Saved-product audiences for retargeting. Pro plan and above. |
| Finance | None | Not materially applicable. Billing runs through Shopify. |
| HR | None | Not materially applicable. |
| Data | Spreadsheet exports; wishlist counts as Shopify product data; wishlist data in Shopify customer segments | Connections to data warehouses or business-intelligence tools are not publicly documented. |
| Developer | REST API, JavaScript SDK, custom webhooks on Enterprise | See Part 23. |
| Marketplace and third-party apps | Tapcart (mobile apps), PageFly, GemPages and Design Packs (page builders), Wiser (recommendations), Joy Loyalty | — |
| Shopify's own surfaces | Shop till (POS), Flow, Customer Accounts, Checkout, Admin, Sidekick, Markets | The deepest set of integrations after the ESPs. |
| Commerce platforms | Shopify, Shopify Plus, BigCommerce, Magento, Salesforce Commerce Cloud, Oracle Commerce Cloud | Listed by Swym. In practice the installed base is almost entirely Shopify. |

### The integrations that matter most

| Integration | Why customers need it | Workflow it enables | Strategic importance | Effect on switching cost | Competitive significance |
| --- | --- | --- | --- | --- | --- |
| Klaviyo | It is where the store's emails and texts are built and measured | Saved-product events start flows; shoppers are segmented by what they saved | Critical. It is both the value channel and a marketing channel for Swym | High. Flows are built on Swym's event names | Rivals also connect to Klaviyo. Swym's partner status and draft flows are the edge |
| Enterprise ESPs (Braze, Iterable, Emarsys and others) | Large brands will not change their marketing platform for a wishlist | The same events reach the brand's existing platform | High. It is the gate to the Enterprise plan | High. Set up jointly with Swym's team | Strong. I found no rival wishlist app listing this range |
| Attentive and Postscript | Text messages get read quickly, which suits restock alerts | Restock and price-drop texts | Medium | Medium | Moderate |
| Shopify Flow | Merchants want wishlist data to work with loyalty, support and tagging | Tag high-intent customers, alert staff, reward purchases of saved items | High and rising | Medium, rising with each workflow | Growave also supports Flow |
| Shop till (POS) | Brands with shops want staff to see online interest | In-store lists, restock sign-ups at the till | Medium. Niche but differentiating | Medium. Staff habits form around it | Strong in this category |
| Tapcart | Brands with a mobile app need the same wishlist there | One list across website and app; push alerts | Medium | Medium | Swish lists Tapcart too |
| Meta ads | Retargeting needs to know the product | Ads showing the exact saved product | Medium | Low | Wishlist Hero offers pixel tracking |
| Shopify Markets | International brands need the right currency and language in each alert | Market-specific campaigns | Medium. Enterprise only today | Low | A gap: Swish lists Markets on its standard listing |

## Part 23 — API and platform strategy

Swym is moving from an application to a platform component. It exposes its data through events and APIs so that other tools can act on it. It is not becoming a platform with its own ecosystem: nobody builds apps on top of Swym.

| Element | What exists | Label |
| --- | --- | --- |
| APIs | A REST API and a JavaScript SDK covering lists, items, sharing, comments and restock sign-ups. Recently viewed products and saved carts are in beta. | FACT — [developer docs](https://developers.getswym.com/docs/swym-guides-landing) |
| Shopper identity | Each shopper gets a Swym ID. Guest and logged-in sessions can be merged. | FACT — developer docs |
| Webhooks | Custom webhooks on Enterprise. | FACT — [pricing page](https://www.getswym.com/pricing) |
| SDKs | JavaScript. A native mobile SDK is not documented on the landing page; mobile is served through Tapcart. | FACT plus gap |
| Developer platform | A docs site, an index for AI tools, and a documentation server that AI coding assistants can query. It serves documentation only, not live shopper data. | FACT — [docs](https://developers.getswym.com/docs/mcp) |
| Automation | Shopify Flow triggers and actions. | FACT |
| Custom integrations | Custom data models on Premium; “full suite of data integrations” on Enterprise. | FACT — pricing page |
| Data export | Spreadsheet export of alert logs; list export; the API. | FACT |
| Data import | Through the API, and through Flow actions that add items to a wishlist. | FACT — [March 2026 update](https://www.getswym.com/product-updates/march-2026) |
| Marketplace | None of its own. | INFERENCE |

### Direction of travel

**Application → platform component.** In 2016 Swym was a widget with its own alerts. By 2026 it publishes events to 20+ tools, to Shopify Flow and into Klaviyo as structured objects, and offers an API for custom storefronts.

### Strategic implications

1. **Value moves from the screen to the data.** If other tools can draw a heart button, Swym's worth is the accuracy and reach of its intent data. That argues for investing in identity and signal quality over more widgets.
2. **The hosts could absorb the function.** Swym's platform strategy runs on Shopify's and Klaviyo's building blocks. Both companies could ship the capture step themselves.
3. **Pricing has not followed.** Developer access starts at US$99.99 a month. INFERENCE: this protects revenue from large accounts, and slows adoption by developers and agencies who would otherwise standardise on Swym.
4. **The AI opening is still empty.** The documentation server helps developers write code. It does not let a shopping assistant read a shopper's saved products. That would be a real platform move, and it is discussed in Part 24.

## Part 24 — AI strategy

AI at Swym is a feature enhancement and an internal way of working. It is not yet the core of the product's value. The capture and alert logic that earns the revenue runs on rules.

### What exists

| AI capability | Status | Source |
| --- | --- | --- |
| Setup through Shopify Sidekick: describe the button you want and Shopify's assistant configures it | Live for new installs since March 2026 | FACT — [March 2026 update](https://www.getswym.com/product-updates/march-2026) |
| Sidekick answers questions about saved products and conversion | Live since July 2026 | FACT — [July 2026 update](https://www.getswym.com/product-updates/july-2026) |
| Swym AI assistant: reviews the setup and lists unused features and unconnected integrations | Live since April 2026 | FACT — [April 2026 update](https://www.getswym.com/product-updates/april-2026) |
| AI setup assistant: guides configuration and diagnoses storefront problems | Live since June 2026 | FACT — [June 2026 update](https://www.getswym.com/product-updates/june-2026) |
| AI weekly report: a Monday summary of revenue opportunities in the wishlist data | Early access, Pro and above | FACT — [May 2026 update](https://www.getswym.com/product-updates/may-2026) |
| In-stock recommendations in restock alerts, described as AI-powered | Live | FACT — [Back in Stock listing](https://apps.shopify.com/watchlist) |
| Documentation server and index for AI coding tools | Live | FACT — [docs](https://developers.getswym.com/docs/mcp) |
| Internal use: AI drafts first replies to support tickets, briefs and code | Stated working practice | FACT — [job post](https://jobs.weekday.works/wkdypfybxt) |
| Smart Save | Rule-based, not AI: a fixed number of views plus 30 seconds | FACT — [help article](https://help.getswym.com/en/articles/13274798-smart-save) |

Not found in public material: a writing assistant for campaign copy, AI search, autonomous agents acting for the merchant, or models that predict which saved items will convert.

### The four AI-related features in detail

**A. Setup through Sidekick**

1. **User problem:** Configuration takes many steps and some theme knowledge.
2. **Input:** The merchant's request in plain language.
3. **AI processing:** Shopify's assistant interprets the request and applies Swym settings. The exact mechanism is not documented.
4. **Output:** Button style, placement and colours; save-for-later widget; header icon.
5. **User action:** Check the storefront and adjust.
6. **Value:** Faster time to a live button.
7. **Accuracy requirements:** Moderate. A wrong placement is visible and easy to reverse.
8. **Human oversight:** The merchant previews the result.
9. **Risk:** Low. FACT: one repeat installer found setup harder with “the new AI stuff”.
10. **Competitive differentiation:** Short-lived. Shopify offers Sidekick to every app.

**B. AI assistant and setup diagnostics**

1. **User problem:** Merchants do not know which features are unused, or why a button is not showing.
2. **Input:** The store's configuration and a scan of the storefront.
3. **AI processing:** Compares the setup with an expected state and explains gaps in words.
4. **Output:** A list of unused features, missing connections and diagnosed faults.
5. **User action:** Switch features on; fix the fault.
6. **Value:** Higher activation and fewer support tickets.
7. **Accuracy requirements:** High. A wrong diagnosis wastes time and repeats the “support says it works” complaint.
8. **Human oversight:** The merchant decides; support is the backstop.
9. **Risk:** It recommends features that use the merchant's quota, which is a conflict of interest if not disclosed.
10. **Competitive differentiation:** Moderate.

**C. AI weekly report**

1. **User problem:** Nobody opens the dashboard, so wishlist data is not acted on.
2. **Input:** Saves, restock sign-ups, catalogue, prices and stock.
3. **AI processing:** Scans for opportunities and writes a summary.
4. **Output:** A weekly report with recommended actions and trends.
5. **User action:** Restock, discount or launch a campaign.
6. **Value:** A weekly habit, and a reason for the merchandiser to care.
7. **Accuracy requirements:** High. The advice moves stock and price.
8. **Human oversight:** A person decides every action.
9. **Risk:** Generic advice that is ignored, or a wrong number that damages trust.
10. **Competitive differentiation:** Potentially the strongest, because it rests on data only Swym holds. It is still a pilot.

**D. Smart Save, the “smart” feature that is a rule**

1. **User problem:** Interested shoppers do not click save.
2. **Input:** Product-view counts per shopper.
3. **Processing:** A threshold, not a model.
4. **Output:** An automatic save.
5. **User action:** The shopper can undo.
6. **Value:** More signals to act on.
7. **Accuracy requirements:** High. A wrong save costs the merchant quota and may irritate the shopper.
8. **Human oversight:** Shopper undo; merchant-set threshold.
9. **Risk:** FACT: Swym cites an undo rate below 0.5% as proof of accuracy. INFERENCE: that is weak proof, because most people ignore small notices whether or not they agree with them.
10. **Competitive differentiation:** Real today, easy to copy.

### What role does AI play?

| Role | Verdict |
| --- | --- |
| Core product value | No |
| Feature enhancement | Yes. Setup, diagnostics and reporting |
| Marketing layer | Partly. “AI-powered” appears on features whose logic is not explained |
| Strategic platform shift | Not yet |

### What parts of this product could AI commoditise?

- **The widget.** AI coding tools make a basic save button and list page cheap to build. A third-party guide already publishes four do-it-yourself methods with code ([Notify Me blog](https://notify-me.io/post/shopify-wishlist-without-app)).
- **Setup and customisation services.** Sidekick and coding assistants replace hourly design fixes.
- **First-line support.** Already happening inside Swym.
- **Flow and template building.** ESPs can generate flows with their own AI.
- **The need for an explicit save.** If a model can infer intent from browsing alone, the heart button matters less, and any tool with browsing data can do the inferring. Shopify and Klaviyo both have that data.
- **The storefront itself, in part.** FACT: Shopify opened “agentic storefronts” in 2026 so that AI assistants can find and buy products ([Shopify agentic storefronts explainer](https://shugert.com.mx/resources/shopify-agentic-storefronts-product-data)). HYPOTHESIS: if shoppers ask an assistant to watch a product and report a price drop, the wishlist moves off the merchant's site.

### What parts could AI make more valuable?

- **The data.** A billion labelled signals, each with a product, a shopper and an outcome, is the raw material for models that predict which saved items will convert, at what price and when.
- **Demand forecasting.** Saves and restock sign-ups are an early signal of sales.
- **Intent that assistants can read.** With consent, a merchant-side record of what each shopper wants could feed the brand's chat assistant, its shop staff and outside shopping assistants.
- **Questions in plain language.** “Which products are saved most but bought least?” is easier to ask than to build as a report.

## Part 25 — Data strategy

Swym's data is valuable to each merchant and builds up over time. It is not yet a moat across merchants.

| Stage | What happens | Label |
| --- | --- | --- |
| Generated | Saves by product and size, list names, how the save happened (manual, cart, automatic), repeat views, restock sign-ups, shares, alerts sent, in-store lists and notes | FACT — docs and help centre |
| Collected from shoppers | Name, email, phone; location, IP address, browser, browsing behaviour, a client ID cookie | FACT — [App Store listing](https://apps.shopify.com/swym-relay) data-access section |
| Collected from the store | Customers, products and stock, orders for the last 60 days, discounts, theme, market settings | FACT — same |
| Stored | 15,000 to 125,000 items by plan; the oldest are removed at the limit. A guest ID cookie lasts up to 365 days | FACT — [plan comparison](https://help.getswym.com/en/articles/11959983-wishlist-plus-pricing-features), [cookie article](https://help.getswym.com/en/articles/16093297-how-wishlist-plus-handles-cookies-and-cookie-consent) |
| Processed | Saved items are matched against price and stock changes; orders are matched to earlier saves | INFERENCE from features |
| Analysed | Reports and segments per merchant; benchmark reports across merchants | FACT — product updates |
| Exported | Spreadsheet files, the API, events to ESPs, Shopify product data and customer segments | FACT |
| Portability | Lists can be imported and exported. Moving flows and history to a rival still takes work | FACT plus INFERENCE |
| Ownership | Not verified. I did not open the privacy policy or data-processing terms. INFERENCE: the merchant owns the shopper data and Swym processes it | — |

### Is there a data flywheel?

**Inside one merchant: yes.**

```
More saves
↓
Better segments and more alerts
↓
More recovered orders
↓
The merchant adds capture points
↓
More saves
```

**Across merchants: not proven.** The cross-merchant data produces benchmark reports today. No shipped feature shows one merchant's results improving because of another merchant's data.

### Is there a meaningful data moat?

FACT: Swym's job post says “the data moat is real and widening”. My assessment is more cautious, for three reasons.

1. The data belongs to each merchant and can leave with them.
2. Intent data is perishable. A save from six months ago says little about today.
3. Rivals collect the same kinds of signal.

INFERENCE: the real moat today is distribution and integrations. Data becomes a moat only if Swym trains models on the combined data set that a new entrant could not match.

## Part 26 — Security, privacy and compliance

Swym's privacy handling is unusually well documented. Its security claims could not be fully checked, because the trust centre did not load for me.

| Area | Status | Label |
| --- | --- | --- |
| Authentication | Merchant staff through Shopify admin. Shoppers through a guest ID cookie or their Shopify customer login | FACT |
| Authorisation and role-based access | Not publicly documented for Swym's admin | Gap |
| Single sign-on and user provisioning | Not materially applicable; handled by Shopify | — |
| Audit logs | A full log of alerts sent. No documented log of configuration changes | FACT plus gap |
| Encryption | Not verified | — |
| Data residency | Not publicly available in the sources I could open | — |
| SOC 2 (an independent audit of security controls) | The homepage shows an AICPA SOC badge and links to a trust centre. The report type is not confirmed | FACT (badge only) |
| ISO 27001 | No evidence found | — |
| GDPR | A GDPR badge. Consent follows Shopify's own consent system. Swym publishes its full cookie list and offers modes that work before consent by storing saves on the device | FACT — [cookie article](https://help.getswym.com/en/articles/16093297-how-wishlist-plus-handles-cookies-and-cookie-consent) |
| HIPAA | Not materially applicable. No health data | — |
| Accessibility | A conformance report against WCAG 2.1 AA, April 2026 | FACT |
| Vulnerability disclosure | A published policy | FACT — site footer |
| Availability | 99.993% uptime over 90 days, by Swym's own figure; a public status page | FACT (company claim) |
| Enterprise controls | “Enterprise security and compliance” and premium hosting on the Enterprise plan; details not public | FACT (claim) |
| Data access requested | Broad: the app can edit customers, products, orders, discounts and the theme | FACT — [App Store listing](https://apps.shopify.com/swym-relay) |

### How this affects the business

- **Enterprise sales.** A security badge and data terms are entry tickets. Without them the Enterprise plan could not be sold.
- **Procurement.** The broad data access will draw questions from security reviewers. INFERENCE: it is needed for quotes, discounts on registries and theme placement, and Swym should say so plainly.
- **Customer trust.** Publishing the cookie list and an accessibility report are concrete, checkable signals.
- **Switching costs.** A vendor that has passed review is costly to replace, which helps retention at the top end.
- **Product adoption.** The consent-friendly modes raise capture in Europe, where a hidden button would otherwise lose most saves.

## Part 27 — Competitive landscape

Swym leads the wishlist category on installs and reviews, and is squeezed from four sides: a premium rival with flat pricing, cheap and free apps, bundled suites, and the platforms it depends on. Ratings and prices were read from each Shopify listing on 7 October 2026 unless stated.

FACT: one third-party data set ranks Swym the number one wishlist app on Shopify, used about 8.3 times as often as the next one, Wishlist Hero ([Shop Theme Detector](https://shopthemedetector.com/shopify-apps/swym-wishlist)). Its store counts differ from Store Leads, so I rely on the ranking and not on its percentages.

### Direct competitors

| Competitor | ICP | Core strength | Weakness | Pricing | Differentiator | Strategic threat |
| --- | --- | --- | --- | --- | --- | --- |
| [Swish](https://apps.shopify.com/wishlist-king) (formerly Wishlist King). 4.9 stars, 289 reviews, launched 2015 | Design-conscious brands, including Shopify Plus | Every feature on every plan; unlimited saved items on paid plans; free setup and customisation | Fewer marketing tools listed; the Plus plan is capped at 100,000 monthly sessions | Free on Basic Shopify with 500 lifetime saves; then $29, $49 or $99 a month by Shopify plan | A price the merchant can predict | High. FACT: a reviewer names it as where they went after hitting Swym's cap |
| [Wishlist Hero](https://apps.shopify.com/wishlist-hero). 4.7 stars, 416 reviews, launched 2019 | Small stores on a budget | A real free plan with 500 additions a month; paid plans from $4 | Tops out at 10,000 additions a month; fewer integrations | Free, $4, $17, $29 a month | Lowest cost with alerts and an API | Medium. Takes the low end |
| [Growave](https://apps.shopify.com/growave). 4.8 stars, 1,294 reviews, launched 2014 | Stores that want loyalty, reviews, referrals and wishlist in one tool | One bill and one data set for several retention jobs | The wishlist is one module among many; price jumps from $15 to $199 to $499 | Free up to 200 orders a month; then $15, $199, $499, priced by orders | The bundle | Medium to high. A merchant consolidating apps can drop Swym |
| [Wishlist by Square](https://apps.shopify.com/wishlist-by-square). 5.0 stars, 123 reviews, launched June 2025 | Stores that only want a button | Free | No listed integrations with marketing tools | Free | Price | Medium and rising. Shopify shows it beside Swym's listing. The developer is “Square Apps”; any link to the payments company is not verified |
| Vitals (all-in-one app suite) | Small stores that want dozens of features in one app | Breadth | Depth of the wishlist module not verified | Not checked | The bundle | Medium. Figures are from Vitals' own [blog](https://content.vitals.app/blog/best-shopify-wishlist-apps) |

**Restock alerts.** In this sub-category Swym is a small player. A June 2026 comparison lists STOQ at 5.0 stars with about 3,700 reviews, Notify Me! at 4.9 with about 3,800, and Appikon at 4.8 with 2,000+ ([Koala Apps](https://koala-apps.io/blog/best-shopify-apps/back-in-stock/)). Swym's restock app has 443 reviews on its own listing. Several rivals offer free plans and pre-orders.

**Registries.** Gift Reggie is the established name, with about 170 reviews at 4.8 stars according to third-party comparisons.

### Indirect competitors

| Competitor | What part of the problem it solves | Threat |
| --- | --- | --- |
| Klaviyo and other ESPs | Messages to shoppers who browsed or abandoned a cart; a built-in restock flow | High over time. The ESP owns the sending and could add the capture |
| Shopify itself | Abandoned-checkout emails, customer accounts, Flow, the Shop app | High if it ships a native wishlist. FACT: as of mid-2026 third-party guides state Shopify has none ([Notify Me blog](https://notify-me.io/post/shopify-wishlist-without-app)) |
| Loyalty and review suites | Retention budget and the marketer's attention | Medium |
| Retargeting ads | Bringing back visitors without knowing them | Medium. This is the spend Swym's pitch aims to replace |

### Substitutes

- Doing nothing, and accepting the loss.
- Shoppers using the cart, open tabs or screenshots as a wishlist.
- A do-it-yourself button built by a developer or agency.
- A spreadsheet of restock requests managed by support staff.

### Emerging competitors

- **AI shopping assistants.** HYPOTHESIS: an assistant that remembers what a shopper wants and watches prices replaces the on-site wishlist for some shoppers.
- **A native Shopify feature.** Not announced, as far as I could find.
- **AI-generated custom apps.** Coding assistants lower the cost of building a basic wishlist in-house.

## Part 28 — Competitive feature matrix

Key: ✓ strong, \~ partial, × absent, ? unclear. A “?” means I found no evidence either way on the listings I read. It does not mean the feature is missing.

| Capability | Swym | Swish | Wishlist Hero | Growave | Vitals |
| --- | --- | --- | --- | --- | --- |
| Save without login | ✓ | ? | ✓ | ? | ? |
| Multiple lists | ✓ | ✓ | ? | ? | ? |
| Save for later in the cart | ✓ | ? | ? | ? | ? |
| Automatic save from browsing | ✓ | ? | ? | ? | ? |
| Price-drop and stock alerts | ✓ | ✓ | ✓ | ? | \~ |
| Built-in email sender | ✓ | ? | \~ | ? | \~ |
| Klaviyo integration | ✓ (Pro and above) | ✓ | ✓ ($17 plan and above) | ✓ | ? |
| Enterprise ESPs (Braze, Iterable, Emarsys) | ✓ (Enterprise) | ? | ? | ? | ? |
| Shopify Flow | ✓ | ? | ? | ✓ | ? |
| Shop till (POS) | ✓ | ? | ? | ✓ | ? |
| Customer accounts | ✓ | ✓ | ? | ✓ | ? |
| Shopify Markets | \~ (Enterprise only) | ✓ | \~ | ? | ? |
| Headless stores and API | ✓ ($99.99 and above) | ✓ (Plus plan) | \~ | ✓ ($499 plan) | ? |
| Mobile app through Tapcart | ✓ | ✓ | ? | ? | ? |
| Meta ads audiences | ✓ (Pro and above) | ? | \~ | ? | ? |
| Gift registry | \~ (separate app) | ? | ? | ? | ? |
| In-store selling tools | ✓ | ? | ? | ? | ? |
| Loyalty and reviews in the same product | × | ? | ? | ✓ | ✓ |
| Unlimited usage on paid plans | × | ✓ | × | \~ | ? |
| Free plan | × | \~ (Basic Shopify stores only) | ✓ | ✓ | ? |
| “Built for Shopify” badge | ✓ | ✓ | ✓ | ✓ | ? |
| Setup through Shopify Sidekick | ✓ | ? | ? | ? | ? |
| Free setup and customisation | \~ | ✓ | ? | \~ | ? |

Sources: the five listings linked in Part 27, and Swym's [plan comparison](https://help.getswym.com/en/articles/11959983-wishlist-plus-pricing-features).

**Reading the matrix.** Swym is the widest product. Two of its three × marks are commercial, not functional: no unlimited usage and no free plan. That is where rivals attack.

## Part 29 — Competitive positioning

### Rival by rival

| Rival | Why a customer would choose the rival | Why a customer would choose Swym instead |
| --- | --- | --- |
| Swish | A flat price with no cap on saved items, free design work, and every feature on every plan | A wider set of marketing tools, in-store tools, automatic saving, and a longer record with very large brands |
| Wishlist Hero | It is free or nearly free and does the visible job | Reliability at volume, enterprise connections, and far more capacity |
| Growave | One app and one bill for loyalty, reviews and wishlist | Depth in intent capture and alerts; no need to adopt a whole suite |
| A free app or a do-it-yourself build | No cost | Alerts, identity capture and integrations, which are where the revenue comes from |
| A restock specialist such as STOQ or Notify Me! | Pre-orders, a free plan and a much larger review base | One data set shared with the wishlist, and enterprise ESP links |
| Klaviyo's own features | No extra app or bill | Signals Klaviyo cannot see by itself: explicit saves, saves by anonymous shoppers, and in-store lists |

### Summary

- **Table stakes.** A save button, a wishlist page, sharing, basic alerts, a Klaviyo link, the “Built for Shopify” badge.
- **Swym's differentiators.** Breadth of marketing integrations; automatic saving; in-store and trade selling tools; consent-friendly capture; enterprise support and security posture; scale proven on large brands.
- **Swym's weaknesses.** Usage caps with a hard pause; no free tier; Klaviyo and API gated to higher plans; three separately billed apps; uneven support quality in 2026.
- **Moats.** Marketplace ranking and review count; partner status with Shopify and Klaviyo; accumulated shopper lists; integrations that take years to build and maintain.
- **White spaces.** Proof of extra revenue through controlled tests. Demand intelligence for merchandisers. Intent data that AI assistants can read. Vertical playbooks for jewellery gifting or long furniture purchase cycles. Reorder lists for trade buyers.
- **Competitive vulnerabilities.** A rival advertising “unlimited, no caps”. A free button from a well-known name. A native Shopify feature. Klaviyo capturing saves itself.

## Part 30 — SWOT

Each item is tied to a fact from earlier parts. The grouping into four boxes is my judgement.

### Strengths

- **Distribution lead.** 1,481 reviews against 289 for Swish and 416 for Wishlist Hero, which is about five times and three and a half times as many. Store Leads detects it on 64,525 stores.
- **Integration breadth.** 20+ marketing tools and Klaviyo Preferred Partner status.
- **Enterprise credibility.** Steve Madden, Gymshark and Vera Bradley are detected users; Shopify Plus certification; a published uptime of 99.993%.
- **Privacy-aware capture.** Saves work for anonymous shoppers and, since 2026, before cookie consent.
- **Shipping pace.** A dated release note every month since February 2025.
- **Low capital needs.** About US$1.3 million raised in total. INFERENCE: the company answers to customers, not to a funding clock.

### Weaknesses

- **Pricing mechanics.** A hard pause at quota and steep tier steps.
- **Value is hard to see.** Swym's own job post lists “making our value immediately obvious to merchants” as an open problem.
- **Platform concentration.** The base is almost entirely on Shopify.
- **A split product.** Three apps, three meters, three bills.
- **A weak second app.** Back in Stock installs fell 9.0% in a year, in a sub-category where specialists have eight times the reviews.
- **Support under strain.** A cluster of 1-star reviews about slow or dismissive support from late 2025.
- **Limited capital for large bets.** The same thrift that is a strength restricts acquisitions and long research projects.

### Opportunities

- **Become the intent data layer.** Klaviyo Objects, Shopify Flow and customer segments already point this way.
- **Serve the merchandiser.** Wishlist counts as product data and insights inside Shopify admin are early steps toward demand planning.
- **AI on data only Swym holds.** The weekly report pilot.
- **Shop-floor selling.** The advanced sales tools are already a paid add-on.
- **Vertical solutions.** Named as a goal in the job post.
- **Pricing redesign.** Could lift both trial conversion and expansion revenue.
- **International stores.** Multi-country support is Enterprise-only today, and Shopify features the app in a collection for Japanese merchants.

### Threats

- **A native Shopify wishlist.**
- **Klaviyo capturing saves itself.**
- **Flat-price and free rivals.** Swish at US$29 to US$99 with unlimited saves; a free app shown on Swym's own listing page.
- **AI shopping assistants** that reduce storefront visits, where the data is collected.
- **Browser limits on cookies.** INFERENCE: an anonymous list depends on a cookie that lasts up to 365 days; browsers that shorten cookie life would shorten the life of anonymous lists.
- **App consolidation.** When merchants cut costs, single-purpose apps are reviewed first.

## Part 31 — Porter's five forces

The five forces describe how much profit an industry lets its players keep. For Swym, the dominant force is supplier power, because one supplier controls distribution, billing and the rules.

| Force | Level | Why | Label |
| --- | --- | --- | --- |
| Competitive rivalry | High | Dozens of wishlist apps. The basic feature is identical. Rivals compete on price, down to free | FACT (listings) plus INFERENCE |
| Supplier power | High | Shopify supplies the customers, the billing, the technical interfaces and the quality badge. Klaviyo is a second critical supplier of value. Cloud hosting is a commodity | INFERENCE |
| Buyer power | Medium to high | Small stores pay monthly and can uninstall in one click. Prices are public. Large brands have less power once Swym is embedded in their flows | INFERENCE |
| Threat of substitutes | Medium | Bundled suites, do-it-yourself builds, or doing nothing. AI assistants may add a stronger substitute | INFERENCE |
| Threat of new entrants | High at the low end, low at the top | A free app reached 123 reviews about 15 months after launch. Enterprise integrations, security reviews and references take years | FACT plus INFERENCE |

### Strategic implications

1. **Do not fight over the button.** The low end has no entry barriers. Profit sits where entry is hard: enterprise integrations and data products.
2. **Treat supplier dependence as the main risk.** Stay useful to Shopify and Klaviyo, and build value they would rather partner for than rebuild.
3. **Remove the easy attack.** As long as a cap can pause the storefront, every rival has a ready sales line.
4. **Raise switching costs honestly.** Through workflows and results, not through blocked downgrades.

## Part 32 — Moats and defensibility

Swym's defences are distribution and integrations. Its data and technology are weaker defences than its own messaging suggests.

| Potential moat | Rating | Why |
| --- | --- | --- |
| Network effects | Weak | One store's wishlist adds nothing to another store's |
| Data | Moderate | Deep history per merchant; no proven benefit across merchants |
| Switching costs | Moderate | Low for a small store, high for an enterprise with flows and custom code |
| Brand | Moderate | Known to Shopify agencies and retention marketers; invisible to shoppers |
| Distribution | Strong | Ten years of reviews and ranking, plus placement in partners' directories |
| Ecosystem | Moderate | Partner status is valuable and can be withdrawn |
| Integrations | Strong | 20+ connections that each need building, certifying and maintaining |
| Scale | Moderate | Infrastructure proven at over 1 million requests a minute |
| Workflow lock-in | Moderate | ESP flows, Shopify Flow automations, till routines |
| Proprietary technology | Weak to moderate | Know-how in anonymous identity, consent and theme compatibility. No evidence of patents on it |
| Regulatory barriers | Weak | Compliance is a cost of doing business, not a wall |

### Could a well-funded startup recreate this product today?

**The features, yes, within months.** AI-assisted development makes a wishlist, alerts and a Klaviyo link quick to build.

**What would still be hard to copy:**

1. Ten years of App Store reviews and the ranking they produce.
2. More than twenty maintained integrations, and the partner standing that comes with them.
3. Knowledge of how thousands of Shopify themes break a storefront widget.
4. The installed base, and the shopper lists stored inside it.
5. Enterprise references and a security record.

**The more realistic danger is not a copy.** A rival does not need to match Swym. Swish attacks with a simpler price. A free app attacks with no price. And the companies best placed to replace Swym are its two hosts, which already hold the shopper, the catalogue and the sending.

## Part 33 — Product-led growth

Swym has a strong product-led engine for getting installed and a weak one for getting activated. Product-led growth works at the top of its funnel, not all the way through. Swym publishes no funnel numbers, so the assessment column is INFERENCE.

The funnel below uses the AARRR model: acquisition, activation, retention, revenue, referral. Engagement is added between activation and retention.

| Stage | What happens at Swym | Assessment |
| --- | --- | --- |
| Acquisition — how merchants enter | App Store search for “wishlist”, an agency recommendation, or Klaviyo partner content. Entry is a one-click install with a 30-day trial | Strong. The removal of the free plan has probably cut install volume; Store Leads shows installs flat in the latest quarter |
| Activation — the behaviour that predicts value | A live button, saves from shoppers the store can contact, and at least one automated message switched on | Weak. See the bottleneck below |
| Engagement — what is done repeatedly | Shoppers save. The system sends alerts. Merchants themselves do little | Fine for value, poor for visibility |
| Retention — why they stay | Stored lists, flows built on Swym's events, shopper expectation | Moderate to strong for activated accounts |
| Revenue — how usage becomes money | Quota tiers, and integrations gated to higher plans | Effective, with a cost in goodwill |
| Referral — how users bring others | Agencies only | Weak |

### The likely bottleneck: activation

Three pieces of evidence point to the same place.

1. FACT: Swym's job post names “making our value immediately obvious to merchants without making them hunt for it” as an unsolved problem.
2. FACT: most 2026 releases target setup and first value: Sidekick setup, an AI assistant, two-minute Klaviyo connection, draft flows, an education nudge and a revenue summary. Teams build where the funnel leaks.
3. FACT: flows are created as drafts, and the Klaviyo link needs the Pro plan. Both delay the first sent message.

A second bottleneck sits inside activation: the share of saves that come from shoppers the store can actually contact.

## Part 34 — North Star Metric

A North Star Metric is the single number that best captures the value customers receive. My recommendation:

**Recovered saved-product orders per month.** Count every order, across all merchants, that contains a product the shopper had saved or signed up for through Swym, and that followed a Swym-triggered message within a set window such as seven days.

### Why this metric

- **It measures the customer's outcome.** Merchants pay to recover sales. This counts recovered sales.
- **It cannot grow unless the whole chain works.** Capture, identity, activation and message quality all have to function.
- **It resists inflation.** FACT: Swym celebrates “1 billion intent actions”. That number rises when automatic saving is switched on, whether or not anyone buys.
- **It matches how Swym says it measures people.** FACT: the job post lists “merchant activation, workflow adoption, and product outcome attribution” as the success categories.

**Its limit.** It counts orders that followed a message, not orders that happened because of one. It should be paired with holdout tests, where a small group of shoppers receives no message, to estimate the true extra orders.

### How it breaks down

```
Recovered saved-product orders
  = active merchants
  × saves per merchant
  × share of saves from contactable shoppers
  × messages delivered per contactable save
  × orders per message delivered
```

| Type | Metrics |
| --- | --- |
| Input metrics | Merchants with a correctly rendering button; saves per 100 sessions; share of saves from contactable shoppers; share of paying merchants with at least one live trigger; messages per contactable save; orders per message |
| Leading indicators | Days from install to first live trigger; ESP connected within 7 days; number of trigger types live; share of saves that are contactable in week one |
| Lagging indicators | The North Star itself; recovered revenue in dollars; customer retention; net revenue retention |
| Guardrail metrics | Shopper unsubscribe and complaint rates; Smart Save undo and opt-out rates; storefront speed impact; number of quota pauses; support satisfaction; share of new reviews that are 1-star |

## Part 35 — Product metrics

Each metric is defined for this product, not in general.

| Category | Metric | Definition for Swym |
| --- | --- | --- |
| Acquisition | Traffic | Views of the App Store listing, by source: search, category, partner link |
| Acquisition | Leads | Demo requests from Shopify Plus brands |
| Acquisition | Signup conversion | Installs divided by listing views; trial starts divided by installs |
| Acquisition | CAC | Sales, marketing and partner cost divided by new paying merchants |
| Activation | Setup completion | Share of installs with a button live on product pages within 24 hours |
| Activation | First value | Share of installs with a first alert delivered to a contactable shopper within 14 days |
| Activation | Time to value | Median days from install to first credited order |
| Engagement | Daily, weekly, monthly actives | For shoppers: unique savers. For merchants: admins who open the app. Daily merchant use is not a sensible target for a background tool |
| Engagement | Feature adoption | Share of merchants using Smart Save, Save for Later, each trigger type, Flow, the till extension |
| Engagement | Workflow completion | Share of saves that end in a message; share of messages that end in an order |
| Retention | Customer retention | Share of paying merchants still paying after 3, 6 and 12 months |
| Retention | Revenue retention | Gross and net revenue retention by signup cohort |
| Retention | Cohort retention | Retention split by activation status, plan and vertical |
| Retention | Churn | Uninstalls and cancellations, tagged with a reason |
| Monetisation | Conversion | Trial-to-paid rate |
| Monetisation | ARPU | Average monthly revenue per paying merchant, across all three apps |
| Monetisation | Expansion | Upgrade rate; share of merchants with a second app |
| Monetisation | NRR | Net revenue retention, split into forced upgrades at quota and chosen upgrades for features |
| Product quality | Errors | Share of storefront page loads where the button failed to render |
| Product quality | Latency | Time the script adds to page load; delay between a restock and the alert |
| Product quality | Failed workflows | Alerts not sent because of quota, expired ESP authorisation or missing consent |
| Product quality | Support tickets | Tickets per 100 active merchants, by cause |
| Satisfaction | NPS | Willingness to recommend, asked of the champion and the owner separately |
| Satisfaction | CSAT | Satisfaction after each support contact |
| Satisfaction | CES | Effort score after setup and after connecting an ESP |

## Part 36 — Product funnel

```
Awareness
↓
Listing or website visit
↓
Install or demo
↓
Activation (button live, trigger on)
↓
First value (first credited order)
↓
Regular usage (alerts running every week)
↓
Paid conversion (trial ends)
↓
Expansion (higher tier, second app)
↓
Renewal
```

| Stage | User goal | Company goal | Key metric | Drop-off risk | Improvement opportunity |
| --- | --- | --- | --- | --- | --- |
| Awareness | Learn that saves can be turned into sales | Be the name attached to “wishlist” on Shopify | Share of category searches | A free or bundled app is found first | Own the argument for why alerts matter, not the button |
| Listing or website visit | Judge fit quickly | Earn the install | Listing-to-install rate | Price shown without context | A return estimate on the listing |
| Install or demo | Try it at low risk | Start a qualified trial | Trial starts | Leaves at the charge approval | State clearly that nothing is charged for 30 days |
| Activation | Get it working | Reach a live trigger | Share activated by day 14 | Draft flows never published | One-click publish; default mailer |
| First value | See proof | Show a credited order | Days to first credited order | Too few contactable shoppers | Better email capture |
| Regular usage | Let it run | Keep alerts flowing | Messages per week per merchant | Expired ESP connection, unnoticed | Health alerts |
| Paid conversion | Decide to keep paying | Convert the trial | Trial-to-paid rate | No revenue visible at day 30 | Trial-end summary |
| Expansion | Handle growth | Raise revenue per account | Upgrade rate; second-app rate | A hard pause triggers a search for rivals | Soft limits; a suite bundle |
| Renewal | Keep what works | Retain | Customer and revenue retention | Cost review by the owner | A quarterly value summary sent to the owner |

## Part 37 — Retention and churn

The largest controllable cause of churn is failed activation. The largest uncontrollable cause is small stores closing. Swym publishes no churn data, so probability and impact below are my estimates, with reasons.

| # | Potential cause | Type | Probability | Impact | Controllability | Reasoning |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | No message ever goes live, so no revenue is visible by the end of the trial | Failed activation | High | High | High | Drafts by default; Klaviyo gated to Pro; Swym itself says value is hard to see |
| 2 | The store closes or stops trading | Customer churn | High | Medium | Low | Small online stores fail often. Each lost account is small |
| 3 | Quota is reached; the merchant faces a forced upgrade or a paused wishlist and moves to a flat-price rival | Customer churn | Medium | High | High | FACT: reviews from 2024 and 2025 describe exactly this, and one names Swish |
| 4 | The button does not show, or lags, on the merchant's theme or under consent rules | Failed implementation | Medium | High | Medium | FACT: 2026 reviews; the consent article confirms the classic button hides without consent |
| 5 | Support is slow or says nothing is wrong | Customer churn | Medium | High | High | FACT: five of the ten most recent 1-star reviews mention it |
| 6 | Automatic saving used up quota without the merchant knowing | Feature churn, then customer churn | Low to medium | High | High | FACT: three 1-star reviews in 2026 |
| 7 | Shoppers barely use the wishlist because traffic is low or purchases are impulsive | Customer churn | High among small stores | Low | Low | Poor fit, not a product fault |
| 8 | The merchant consolidates apps into a suite | Customer churn | Medium | Medium | Low to medium | Growave and Vitals bundle a wishlist |
| 9 | The price rose or the free plan went away | Customer churn | Medium | Medium | High | Swym's own decision in 2026 |
| 10 | The ESP connection expires and alerts stop quietly | Feature churn | Medium | Medium | High | FACT: a one-click re-authorise banner shipped in 2026, which implies this was happening |
| 11 | The champion leaves and the next marketer does not know the flows | User churn | Low to medium | Medium | Medium | A background tool has few visible owners |
| 12 | The merchant drops the restock app for a free specialist | Account contraction | Medium | Low to medium | Medium | Back in Stock installs fell 9.0% in a year |
| 13 | The merchant leaves Shopify, or goes headless without paying for API access | Customer churn | Low | High | Low | — |
| 14 | Shopify ships a native wishlist | Customer churn | Low in the near term | Very high | Low | No announcement found |

**Ranking by expected loss.** Probability multiplied by impact, then weighted by how much Swym can do about it, gives this order of attack: 1, 3, 5, 4, 6. All five are within the product team's control.

## Part 38 — Customer feedback

The broad evidence is very positive. The recent negative evidence is narrow but consistent, and it clusters on pricing mechanics and support.

### The evidence base

- FACT: 1,481 reviews on the Shopify App Store. 92% are 5-star, 4% are 4-star, and 3% (42 reviews) are 1-star ([App Store listing](https://apps.shopify.com/swym-relay)).
- What I read: Shopify's AI-written summary of all reviews, the newest reviews on the listing, the ten most recent 1-star reviews (October 2025 to September 2026), and four individual review pages from 2024 to 2026.
- My searches surfaced no substantive discussion on Reddit, G2 or Capterra. The App Store is where merchants review this product.
- A caution on balance: App Store reviews are often written right after a helpful support chat, which pushes ratings up.

### Clusters

| Cluster | What merchants say | Breadth of evidence |
| --- | --- | --- |
| Most loved | Fast, expert support, often by name; quick custom design fixes | Broad. It is in Shopify's summary of all reviews |
| Most loved | A simple, reliable wishlist that shoppers actually use | Broad |
| Most loved | Alerts and the Klaviyo integration | Broad |
| Most loved | Reports that guide stock decisions | Broad |
| Most disliked | A quota that shuts the wishlist off, and forced upgrades | Repeated across 2024 to 2026 |
| Most disliked | Automatic saving switched on by default and consuming quota | Three 1-star reviews in 2026 |
| Common complaints | Bugs; the button missing or slow; reports not matching live activity | Four of the ten most recent 1-star reviews |
| Support complaints | Live chat unresponsive; support insists everything works | Five of the ten most recent 1-star reviews |
| Pricing complaints | “The entry level plan costs almost as much as Shopify itself” (restock app); a US$299 Enterprise quote after a US$59.99 plan; a plan changed without warning | Anecdotal, but each from a different year |
| Missing features | Better translation options; more control over how shoppers reach their wishlist; a plan between Premium and Enterprise | Anecdotal |
| UX issues | Setup made harder by new AI steps; “extremely difficult to use”; custom implementation is hard | Anecdotal |
| Reliability issues | An admin page error; stock-sync delays in restock alerts | Anecdotal |
| Competitive complaints | “We have moved to Swish, which is only $49 a month and has unlimited wishlist actions” | One review, but it states the rival's pitch exactly |

Sources: [1-star reviews](https://apps.shopify.com/swym-relay/reviews?ratings%5B%5D=1), individual reviews from [2024](https://apps.shopify.com/reviews/1518056), [2025](https://apps.shopify.com/reviews/1745375), [July 2026](https://apps.shopify.com/reviews/2268711) and [August 2026](https://apps.shopify.com/reviews/2341712), and the [Back in Stock listing](https://apps.shopify.com/watchlist).

### Frequency × severity

Frequency is scored 1 to 5 from how often the theme appears in the negative reviews I read. Severity is scored 1 to 5 from how much damage one occurrence does. The score is the two multiplied.

| Problem | Frequency | Severity | Score | Why this severity |
| --- | --- | --- | --- | --- |
| Support unresponsive or dismissive | 5 | 4 | 20 | It turns a fixable bug into a public review, and it erodes the product's best-known strength |
| Button missing, slow, or reports wrong | 4 | 4 | 16 | Saves are lost silently, and the data the merchant paid for cannot be trusted |
| Quota reached: pause or forced upgrade | 3 | 5 | 15 | The shopper-facing feature disappears, and the merchant often leaves |
| Automatic saving consumes quota by default | 3 | 4 | 12 | A trust problem. The merchant feels billed by a setting they did not choose |
| Setup or customisation is hard | 3 | 3 | 9 | Slows activation |
| Translation gaps | 1 | 3 | 3 | Matters for non-English stores |

### What the pattern says

- **Anecdotal versus broad.** Each complaint is one merchant's account. The praise is the broad signal: nine in ten reviewers give five stars.
- **A possible trend.** FACT: 10 of the 42 one-star reviews are dated in the last 12 months of a ten-year history. INFERENCE: negative reviews are arriving faster than before. I cannot confirm the rate, because I do not have total review counts by month.
- **The timing fits.** The cluster follows three changes Swym made: enforcing quotas, shipping automatic saving as a default, and removing the free plan.
- **Swym responds.** Defaults for automatic saving were tightened by August 2026, and a usage panel shipped in March 2026. The pause at 100% remains.

## Part 39 — Product discovery

The product team's hardest discovery problem is structural: the person who creates the value, the shopper, is not the person who pays, and neither is easy to reach. Everything in this part is INFERENCE from the evidence in earlier parts.

| Area | What the team likely faces |
| --- | --- |
| Unmet needs | Proof that the app pays for itself. A bill the merchant can predict. A use for the merchandiser, not only the marketer |
| Workflow gaps | Draft flows that never go live. Saves from shoppers who cannot be contacted. Three apps that do not feel like one |
| Feature requests | Better translation. A plan with no cap. A route back to a cheaper plan. Multi-country support below Enterprise; the pricing page marks this “coming soon” on Pro |
| Emerging user behaviour | More shopping on phones and in brand apps. Fewer logins. More declined cookie banners. Early use of AI assistants to shop |
| Competitive pressure | Flat pricing from Swish, free apps, bundled suites |
| Technology changes | Shopify's newer customer accounts, Sidekick and agent-facing storefronts. Klaviyo's structured objects. AI coding tools |
| Market changes | Rising ad costs push budget toward retention. Cost-cutting pushes merchants to remove single-purpose apps |

**What makes discovery hard here.**

- The feedback loop is slow. Weeks can pass between a save and a purchase.
- The champion (the marketer) and the buyer (the owner) want different proof.
- Storefronts differ on every merchant, so a bug seen by one may be invisible in testing.
- The loudest feedback comes from reviews, which over-represent support moments.

### Opportunity solution tree

An opportunity solution tree starts from one business outcome, lists the customer problems that block it, then the possible solutions, then the cheapest test of each.

```
BUSINESS OUTCOME
Raise 12-month net revenue retention of newly paying merchants
│
├── OPPORTUNITY 1: 'I cannot tell whether this app pays for itself'
│   ├── Solution: a day-one view of potential revenue
│   │     Experiment: show it to half of new installs; compare trial-to-paid
│   ├── Solution: a report of extra revenue, measured with a no-message group
│   │     Experiment: 10 partner merchants hold back 10% of shoppers for 60 days
│   └── Solution: a trial-end and quarterly value summary
│         Experiment: A/B test on trial conversion and 90-day retention
│
├── OPPORTUNITY 2: 'Nothing was ever sent'
│   ├── Solution: a default reminder through Swym's mailer, clearly disclosed
│   │     Experiment: new Starter installs; measure activation by day 14,
│   │     with unsubscribe rate as the guardrail
│   └── Solution: a 'nothing is sending' warning with one-click publish
│         Experiment: ship the warning alone first and count clicks
│
├── OPPORTUNITY 3: 'My bill and my storefront are unpredictable'
│   ├── Solution: a soft limit (the wishlist keeps working; marketing features wait)
│   │     Experiment: apply to half the merchants who reach 90% of quota
│   ├── Solution: automatic saves do not count, or count less
│   │     Experiment: price test on new signups
│   └── Solution: a published plan above 25,000 actions
│         Experiment: add the pricing card; compare self-serve upgrades with sales calls
│
├── OPPORTUNITY 4: 'Most of my savers are anonymous'
│   ├── Solution: ask for an email on the second save, not the first
│   │     Experiment: A/B test on the share of contactable saves
│   └── Solution: a prompt to sign in through the store's customer account
│         Experiment: prototype with five stores
│
└── OPPORTUNITY 5: 'The button was missing and nobody told me'
    ├── Solution: automated checks that the button renders, with alerts
    │     Experiment: run checks on 1,000 stores; count the failures found
    └── Solution: AI diagnostics with a 'fix it' action
          Experiment: measure support tickets avoided
```

## Part 40 — Roadmap analysis

The three lists below must not be confused. Only the first is Swym's.

### Confirmed roadmap — publicly announced or directly evidenced

| Item | Evidence |
| --- | --- |
| Klaviyo Objects | Early access for Premium and Enterprise, [August 2026 update](https://www.getswym.com/product-updates/august-2026) |
| AI weekly report | Early access, pilot expanding to 20 more stores, [May 2026 update](https://www.getswym.com/product-updates/may-2026) |
| Shopify Markets support on Pro | Marked “coming soon” on the [pricing page](https://www.getswym.com/pricing) |
| Sidekick setup for existing merchants | Available on request, [March 2026 update](https://www.getswym.com/product-updates/march-2026) |
| Stated priorities: make value obvious, become “operationally indispensable”, build vertical solutions, use more AI in the team's work | [Job post](https://jobs.weekday.works/wkdypfybxt) |

### Inferred roadmap — my reading of direction, not announced

- Wider release of Klaviyo Objects and more Shopify Flow triggers.
- An AI assistant that acts on its findings, not only lists them.
- Vertical packages for fashion, beauty, home and jewellery; the landing pages already exist.
- Growth of the paid sales tools for shops.
- Seasonal BFCM tooling, as in 2025.
- HYPOTHESIS: a simpler pricing structure, given review pressure and the 2026 changes to defaults.

### Recommended roadmap — what I believe Swym should prioritise

| Horizon | Recommendation |
| --- | --- |
| Now (0–3 months) | A soft quota limit so the storefront never breaks. No metering of automatic saves during trials. A “nothing is sending” warning with one-click publish. A day-one value view. Automatic button health checks. A published price above 25,000 actions. Corrections to the pricing pages |
| Next (3–6 months) | A measured “extra revenue” report using a no-message group. Tests on email capture. One plan covering wishlist, restock alerts and registries. Multi-country support on Pro. A demand report for merchandisers, and general release of the weekly report |
| Later (6–12 months) | Models trained across merchants for message timing and price sensitivity. Saved-intent data that AI assistants can read, with shopper consent. Vertical packs. A pilot of pricing linked to outcomes |

## Part 41 — Product prioritisation

I use RICE. The score is Reach × Impact × Confidence ÷ Effort.

- **Reach** is the share of paying merchants affected in a quarter, in percentage points. I use shares because Swym's counts are not public. Every reach figure is my assumption.
- **Impact** on retention or revenue per affected merchant: 0.5 low, 1 medium, 2 high, 3 very high.
- **Confidence** is 50%, 80% or 100%.
- **Effort** is person-months.

**Why RICE fits this product.** Swym faces many small, comparable bets with very different reach: a fix for every install competes with a feature for a few hundred enterprise accounts. RICE makes that difference explicit. Its limit is that it undervalues long strategic bets, such as data for AI assistants, so those are judged separately in Part 46.

| Rank | Opportunity | Problem | User | Evidence | Reach | Impact | Confidence | Effort | Score | Expected business outcome |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | “Nothing is sending” warning and one-click default reminders | Flows stay as drafts, so no value appears | New merchants | Drafts by default; job post on hidden value | 40 | 2 | 80% | 2 | 32 | Higher activation and trial conversion |
| 2 | Quota-safe defaults: automatic saves and staff traffic not metered in trial | Quota is spent before the merchant sees value | New merchants | Three 1-star reviews in 2026 | 25 | 1 | 80% | 1 | 20 | Fewer early cancellations and bad reviews |
| 3 | Better email capture at the moment of saving | Anonymous saves cannot trigger messages | Shoppers; marketers | Structure of the product; guest email capture already exists | 60 | 2 | 50% | 4 | 15 | More messages per save across the whole base |
| 4 | Soft quota limit, no storefront pause | Shoppers lose the feature mid-month | Growing merchants | Reviews from 2024 and 2025; help centre confirms the pause | 15 | 3 | 80% | 3 | 12 | Lower churn at the moment of expansion |
| 5 | Day-one potential revenue and a trial-end summary | No proof before the first bill | Owner | Revenue summary hidden until revenue exists | 30 | 1 | 50% | 2 | 7.5 | Higher trial conversion |
| 6 | Automatic button health checks | Saves are lost silently | All merchants | Reviews about missing buttons; consent article | 60 | 1 | 50% | 4 | 7.5 | Fewer tickets; more saves captured |
| 7 | A published self-serve plan above 25,000 actions | A sales call blocks a ready buyer | Fast-growing merchants | 2025 review: a week's wait, then US$299 | 3 | 3 | 80% | 1 | 7.2 | Faster expansion revenue; fewer losses to Swish |
| 8 | Demand report for merchandisers | Wishlist data is not used for stock and price decisions | Merchandiser | Product insights and the weekly report are early steps | 30 | 1 | 50% | 3 | 5 | A second champion in each account |
| 9 | Measured extra revenue with a no-message group | Credited revenue is not proof | Marketer; owner | No rival offers it publicly | 20 | 2 | 50% | 5 | 4 | A defensible value claim; supports price |
| 10 | One plan and one onboarding for all three apps | Cross-sell is hard and the product feels split | All merchants | Three listings, three meters | 30 | 1 | 50% | 6 | 2.5 | Higher revenue per account over time |

**How to read the result.** The top four are cheap and remove self-inflicted problems. Items 8 to 10 score lower on RICE because they take longer, yet 8 and 9 are the ones that change the product's long-term position. I would run the top four at once and start discovery on 8 and 9 in parallel.

## Part 42 — Top product improvements

These are the ten changes I would make as the PM, with the design of each. The order differs slightly from the RICE table in Part 41, because I add weight for reputational damage, which RICE does not score. Everything here is my recommendation.

### 1. Never break the storefront: a soft quota limit

- **Problem:** At 100% of quota the wishlist is paused for shoppers.
- **Evidence:** The help centre states it; reviews from 2024 and 2025 describe it.
- **Target user:** Growing merchants and their shoppers.
- **Proposed solution:** Past the limit, saving keeps working. New saves are held: stored, but not sent to alerts or integrations until the merchant upgrades or the month resets. The merchant sees how many saves are held and what they are worth. An optional automatic upgrade can be chosen in advance.
- **Expected user impact:** Shoppers never meet a broken feature.
- **Expected business impact:** Upgrades are driven by visible value on hold, not by an outage. Fewer cancellations at the moment of growth.
- **Effort:** About 3 person-months.
- **Dependencies:** Quota service, billing through Shopify, alert pipeline.
- **Risks:** Some merchants stay over the limit for free. Limit the hold to 30 days.
- **Success metric:** Churn within 60 days of first reaching 90% of quota; upgrade rate at the limit; reviews that mention quota.
- **Priority:** 1.

### 2. Quota-safe automatic saving

- **Problem:** A default feature spends the merchant's quota without their choice.
- **Evidence:** Three 1-star reviews in 2026, one from a store that had not launched.
- **Target user:** New merchants.
- **Proposed solution:** Ask at onboarding, with a forecast of the quota effect. Do not meter automatic saves during the trial. Exclude staff, developer and preview sessions. Let the merchant cap the share of quota that automatic saves may use.
- **Expected user impact:** No surprise bills.
- **Expected business impact:** Fewer early cancellations and bad reviews; adoption by informed choice, which lasts.
- **Effort:** About 1 person-month.
- **Dependencies:** Onboarding flow, metering.
- **Risks:** Lower short-term upgrade revenue.
- **Success metric:** Share of merchants who keep automatic saving on after 60 days; quota complaints per 1,000 installs.
- **Priority:** 2.

### 3. An activation guard

- **Problem:** Flows sit as drafts; nothing is sent; nothing looks wrong.
- **Evidence:** Drafts are the documented default; Swym says value is hard to see.
- **Target user:** The marketer or owner in the first two weeks.
- **Proposed solution:** A persistent status line: “0 messages sent to 37 shoppers who saved products.” One click publishes a default reminder through Swym's mailer or the connected ESP.
- **Expected user impact:** First value arrives days sooner.
- **Expected business impact:** Higher trial conversion and retention.
- **Effort:** About 2 person-months.
- **Dependencies:** Mailer, ESP status checks.
- **Risks:** Messages sent before the brand has checked the template. Keep a preview step.
- **Success metric:** Share of installs with a live trigger by day 14.
- **Priority:** 3.

### 4. Better identity capture

- **Problem:** A save from an anonymous shopper cannot trigger a message.
- **Evidence:** The structure of the product; the cookie article shows how many saves stay on the device.
- **Target user:** Shoppers; the marketer benefits.
- **Proposed solution:** Test when the email prompt appears (second save, or on leaving the list), what it promises (“tell me if the price drops”), and sign-in through the store's customer account.
- **Expected user impact:** A clear reason to share an email.
- **Expected business impact:** More messages per save, for every merchant.
- **Effort:** About 4 person-months, mostly testing.
- **Dependencies:** Consent rules, customer accounts.
- **Risks:** Prompts that annoy. Guard with dismissal and save-rate metrics.
- **Success metric:** Share of saves from contactable shoppers.
- **Priority:** 4.

### 5. A support-to-product loop for bugs

- **Problem:** Merchants report faults and are told everything works.
- **Evidence:** Five of the ten most recent 1-star reviews.
- **Target user:** Any merchant with a fault.
- **Proposed solution:** Reproduce on the merchant's own store before closing a ticket. Escalate automatically when an AI-drafted reply is rejected. Publish known theme issues.
- **Expected user impact:** Faults get fixed, or at least acknowledged.
- **Expected business impact:** Protects the product's best-known strength.
- **Effort:** Process change plus about 1 person-month of tooling.
- **Dependencies:** Support team, diagnostics.
- **Risks:** Higher support cost per ticket.
- **Success metric:** Reopened tickets; share of new reviews that are 1-star.
- **Priority:** 5.

### 6. Storefront health checks

- **Problem:** A missing or slow button loses saves silently.
- **Evidence:** 2026 reviews; the consent article.
- **Target user:** All merchants.
- **Proposed solution:** Scheduled automated visits to each store's main page types, under each consent state. Alert the merchant when the button fails to render. Offer a fix.
- **Expected user impact:** Problems found before shoppers find them.
- **Expected business impact:** More saves captured; fewer tickets.
- **Effort:** About 4 person-months.
- **Dependencies:** A crawling service; theme knowledge.
- **Risks:** False alarms.
- **Success metric:** Share of stores with a healthy button; tickets about missing buttons.
- **Priority:** 6.

### 7. Proof of value, from day one to a controlled test

- **Problem:** Credited revenue is not proof, and early on there is no number at all.
- **Evidence:** The revenue summary is hidden until revenue exists.
- **Target user:** The owner and the marketer.
- **Proposed solution:** Day one: the value of saved items and a projected recovery. Later: an optional no-message group of 5–10% of shoppers, so the report can show extra revenue with a confidence range.
- **Expected user impact:** A number they can defend to a manager.
- **Expected business impact:** Supports price and renewal; a claim rivals cannot match.
- **Effort:** About 2 person-months for the first part, 5 for the second.
- **Dependencies:** Order data; ESP cooperation for holdouts.
- **Risks:** The measured uplift may be lower than credited revenue. That is still better learned by Swym than by a competitor.
- **Success metric:** Trial-to-paid rate; share of Pro merchants running a holdout.
- **Priority:** 7.

### 8. Published plans above 25,000 actions

- **Problem:** A ready buyer must wait for a sales call.
- **Evidence:** A 2025 review: a week's wait, then a US$299 quote.
- **Target user:** Fast-growing stores.
- **Proposed solution:** Two self-serve tiers, for example 50,000 and 100,000 actions, with prices on the page. Sales begins above that.
- **Expected user impact:** No stall.
- **Expected business impact:** Faster expansion revenue; fewer losses to flat-price rivals.
- **Effort:** About 1 person-month.
- **Dependencies:** Pricing decision; billing.
- **Risks:** Lower negotiated prices at the top.
- **Success metric:** Days from reaching the limit to upgrade.
- **Priority:** 8.

### 9. A demand report for merchandisers

- **Problem:** Wishlist data is not used for stock and price decisions.
- **Evidence:** Insights in Shopify admin and the weekly report pilot are early steps.
- **Target user:** Merchandisers and buyers.
- **Proposed solution:** A weekly list: products wanted but out of stock, products saved often but rarely bought (a price signal), and sizes with unmet demand. Export to the merchant's planning sheet.
- **Expected user impact:** A reason to open Swym every week.
- **Expected business impact:** A second champion in each account, which lowers churn when the marketer leaves.
- **Effort:** About 3 person-months.
- **Dependencies:** Stock and order data.
- **Risks:** Advice that is ignored if not specific.
- **Success metric:** Weekly report opens; actions taken from it.
- **Priority:** 9.

### 10. One Swym: a single plan and onboarding

- **Problem:** Three apps, three meters, three bills.
- **Evidence:** Three listings; the restock app is shrinking.
- **Target user:** Merchants who want more than one app.
- **Proposed solution:** A suite plan with one allowance across wishlist, restock alerts and registries, and one setup.
- **Expected user impact:** Simpler to buy and run.
- **Expected business impact:** Higher revenue per account; a defence against bundles.
- **Effort:** About 6 person-months.
- **Dependencies:** Billing; App Store listing strategy.
- **Risks:** Separate listings each rank for their own search terms. Keep them, and bundle behind them.
- **Success metric:** Share of merchants with two or more Swym products.
- **Priority:** 10.

## Part 43 — What I would build

With limited engineers and designers, a fixed budget and close executive scrutiny, I would group the list above into five bets. Each must show a result within a quarter.

| # | Bet | Why | Target user | Problem | Solution | Expected impact | Metric | Effort | Trade-off |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | Fair usage | Pricing mechanics cause the worst reviews and hand rivals their pitch | Growing merchants | Hard pause; surprise quota use; hidden price above the top plan | Soft limit, quota-safe automatic saving, published higher tiers | Lower churn at expansion; cleaner reviews | Churn within 60 days of reaching 90% of quota | About 5 person-months | Gives up some forced-upgrade revenue now for retention later |
| 2 | Activation path | The funnel leaks between install and first message | New merchants | Nothing is sent, so nothing is proven | Send warning, default reminder, day-one value view, trial-end summary | Higher trial conversion | Live trigger by day 14 | About 4 person-months | Risk of a message going out before a brand has polished it |
| 3 | Capture quality | Every other number depends on saves that can be contacted and buttons that render | Shoppers and all merchants | Anonymous saves; silent button failures | Email-capture tests; health checks | More messages per save | Contactable share of saves | About 8 person-months | The largest effort; slow to show results |
| 4 | Proof of extra revenue | Swym's price rests on a claim nobody has verified | Owner and marketer | Credited revenue is not proof | Optional no-message group and a measured report | Stronger renewals; a unique claim | Share of Pro merchants running a holdout | About 5 person-months | The honest number may be smaller than today's headline |
| 5 | Demand intelligence | Swym needs a second reason to exist inside each account | Merchandiser | Wishlist data is unused for stock and price | Weekly demand report, built on the AI pilot | A weekly habit and a second champion | Weekly report opens and actions | About 3 person-months | Pulls focus from the marketer, the current champion |

### Five things I would explicitly not build

1. **A full email and text platform.** The built-in mailer should stay small. Competing with Klaviyo would turn Swym's best partner into its largest rival.
2. **Loyalty and reviews modules.** Chasing Growave and Vitals means a bundle war against broader suites, and it dilutes the one thing Swym is known for.
3. **A consumer wishlist app across stores.** That is a different business: a consumer network that needs capital Swym does not have. It also conflicts with merchants owning their shopper data.
4. **More storefront widgets and pop-ups.** The widget layer is becoming a commodity, and each addition costs page speed.
5. **Heavy investment in other commerce platforms.** The base is almost entirely Shopify, and the BigCommerce listing has 13 reviews after years. An API-first design is a cheaper hedge than rebuilding for each platform.

## Part 44 — 30/60/90-day PM plan

The plan moves from diagnosis, to tested hypotheses, to two shipped changes and a roadmap. It assumes I have access to product data, which this teardown did not.

### First 30 days — understand

| Activity | What I would do |
| --- | --- |
| Learn | Install all three apps on a test store with three different themes. Go through onboarding as a Starter and as a Pro merchant. Connect a Klaviyo test account. Hit the quota on purpose |
| Read | Twelve months of support tickets, grouped by cause. Every 1-star, 2-star and 3-star review (59 in total). Uninstall survey answers. The history of pricing changes |
| Analyse | The funnel from install to button live, first save, first contactable save, first live trigger, first credited order, paid conversion and retention at 3, 6 and 12 months. Split by plan, vertical, traffic and ESP |
| Measure | A baseline for the North Star and its guardrails. How quota use is distributed. The share of actions that are automatic saves |
| Interview | Fifteen merchants: five retained, five who left within 90 days, five who upgraded at quota. Three agencies. Three support agents. The Klaviyo partner contact |
| Observe | Live support chats. Three enterprise onboarding calls. Recordings of new merchants going through setup, if they exist |

**Output at day 30:** a one-page diagnosis showing where the funnel leaks, with numbers, and a proposed definition of activation.

### Days 31–60 — test

| Hypothesis | How I would test it |
| --- | --- |
| Merchants with a live trigger by day 14 retain at least twice as well as those without | Cohort analysis on existing data. No build needed |
| A default reminder raises activation without raising unsubscribes | A/B test on new Starter installs |
| The hard pause loses more revenue than the forced upgrade earns | Compare 90-day revenue of accounts that hit 100% with similar accounts that did not; then run a soft limit on half |
| Asking for an email on the second save raises the contactable share | A/B test |
| A day-one value view raises trial conversion | A/B test |
| Merchandisers will read a weekly demand report | Hand-built reports for ten merchants; track opens and actions |

I would then re-run the RICE table from Part 41 with real reach numbers and agree the order with engineering, design and support.

### Days 61–90 — ship and recommend

- **Ship:** the activation guard and quota-safe trial defaults. Roll out the soft limit fully if its test supports it.
- **Measure:** activation by day 14, trial-to-paid rate, churn after reaching the limit, and the tone of new reviews.
- **Change:** make the activation rate a team metric reviewed weekly, and set up the support-to-product loop for bugs.
- **Recommend:** a proposal to leadership on the pricing metric, with data; a plan for measured extra revenue; and a two-quarter roadmap.

### Initial roadmap

| Quarter | Theme | Contents |
| --- | --- | --- |
| First | Fair usage and activation | Bets 1 and 2 |
| Second | Capture quality and proof | Bets 3 and 4 |
| Third | Demand intelligence and the suite | Bet 5 and the single plan |
| Ongoing, about 10% of time | Exploration | Saved-intent data that AI assistants can read, with consent |

## Part 45 — The first thing I would improve

The first thing I would improve is what happens in a merchant's first 90 days: getting a first message sent, and making sure a usage limit never switches the wishlist off. This part picks one goal, one user and one problem, and defends the choice. The reasoning comes first, step by step, then a short version.

### The reasoning, step by step

1. **Clarify the objective.** The goal could be more new merchants, better retention, or more revenue per merchant. I chose retention of newly paying merchants in their first 90 days. Swym already wins installs through the App Store, and its own job post says its value is not obvious enough to merchants.
2. **Define the target user.** A retention marketer or owner at a fashion or home brand on Shopify, with 20,000 to 200,000 sessions a month, on the Starter or Pro plan, in their first month.
3. **Identify the problem.** They install the wishlist and shoppers start saving. But no reminder or alert is ever sent, so no sale is ever credited. At the end of the trial they see a charge and no proof.
4. **Analyse the current experience.** Three things cause this. Marketing flows are created as drafts. The Klaviyo link needs the Pro plan. And the dashboard shows revenue only after revenue exists. Separately, a feature that saves products automatically can use up the plan's quota, and at 100% the wishlist is paused on the live store.
5. **Identify opportunities.** Five: a warning that nothing is sending, with one-click default reminders; a day-one view of potential revenue; better email capture when a shopper saves; a soft quota limit that never breaks the storefront; and automatic checks that the button is showing.
6. **Prioritise.** I would score them on reach, impact, confidence and effort. The send warning reaches every new merchant and takes about two months. The soft limit reaches fewer merchants but prevents the most damaging failure. I would do those two first.
7. **Propose the solution.** A status line on the home screen: “You have 37 shoppers with saved products and 0 messages sent.” One click publishes a default reminder, with a preview. For quota: past the limit, shoppers can still save, and those saves are held until the merchant upgrades or the month resets.
8. **Define metrics.** Primary: share of new installs with a live trigger by day 14. Secondary: trial-to-paid rate and 90-day retention. Guardrails: shopper unsubscribe rate, and reviews that mention quota.
9. **Discuss trade-offs.** Default sending risks a message going out before the brand has polished it, so I keep a preview step. The soft limit gives up some forced-upgrade revenue; I would test whether lower churn pays that back within a quarter.

### The short version

Swym's wishlist app is strong at getting installed. Its weak point is what happens next, so I would improve activation and usage limits, with the goal of better retention in a merchant's first 90 days.

Picture a fashion brand's marketer in week one. Shoppers are saving products, but no reminder has gone out, because flows start as drafts and the dashboard shows revenue only once there is some. The trial ends with a charge and no proof. Swym's own job posting says making value obvious is an open problem, so I am confident this is real.

My first change is a line on the home screen: “You have 37 shoppers with saved products and zero messages sent,” with one click to publish a default reminder after a preview. It reaches every new merchant and is about two months of work.

My second change is to usage limits. Today, when a store passes its monthly quota, the wishlist is paused for shoppers. I would let shoppers keep saving and hold those saves until the merchant upgrades. Upgrades would then be driven by visible value, not by an outage. Reviews show merchants leaving for a flat-price rival at exactly this moment.

I would measure the share of installs with a live message by day 14, then trial conversion and 90-day retention. My guardrails are shopper unsubscribes and quota complaints.

The trade-offs are a small brand-voice risk from default messages, and some short-term upgrade revenue. I would test both with half of new installs before rolling out.

## Part 46 — Product strategy

These ten answers are my recommendations, built on the evidence in earlier parts.

1. **Where should this product play?** Shopify and Shopify Plus brands in considered-purchase categories, with roughly US$1 million to US$100 million in online sales and an ESP in place. Its role: the record of shopper intent that sits between the storefront and the tools that sell.
2. **How should it win?** By capturing more intent than anyone else (anonymous, consent-safe, behaviour-based), sending it everywhere it is useful, proving the extra revenue with controlled tests, and pricing in a way that makes growth feel like a win.
3. **What capabilities should it build?** Shopper identity; measurement; models trained across merchants; demand analytics; partner integrations; storefront reliability.
4. **What should it not build?** An ESP, loyalty or reviews modules, a consumer app, more widgets, or versions for other platforms. Part 43 gives the reasons.
5. **Which customers should it prioritise?** Mid-sized merchants on Pro and Premium with an ESP, and Shopify Plus brands. INFERENCE: they produce the most revenue for the least support. Very small stores should be served cheaply and automatically.
6. **Which market should it expand into?** Three, in order. New roles inside existing accounts, starting with the merchandiser. Brands with physical shops, through the sales tools. Europe and Japan, where consent handling and language support are advantages; FACT: the UK and France are already 8.5% and 6.6% of detected stores.
7. **What should it defend?** App Store ranking and reviews; standing with Shopify and Klaviyo; its enterprise accounts; its reputation for support.
8. **What could make the product obsolete?** A native Shopify wishlist combined with Klaviyo capturing saves. Models that infer intent without any save. Shopping that happens through AI assistants instead of storefronts.
9. **What strategic bets should management make?** Redesign pricing. Measure extra revenue honestly. Build demand intelligence. Train models on the combined data. Keep a small, steady bet on intent data that AI assistants can read.
10. **What strategic bets should management avoid?** Competing with either host. Using tighter caps to raise revenue. AI features that are labels more than function. Custom services that grow headcount instead of product. Spreading across platforms.

## Part 47 — Strategic risks

The two risks that matter most are both about dependence: on Shopify, and on the storefront remaining the place where people shop. Probability and impact are my estimates.

| Risk | Probability | Impact | Early warning signal | Mitigation |
| --- | --- | --- | --- | --- |
| Platform dependency: Shopify ships a native wishlist, or changes ranking, rules or fees | Medium | Very high | A “saved items” feature in Shopify's twice-yearly product announcements; sudden ranking shifts | Be the advanced option Shopify points Plus brands to; keep value in data and integrations, which a basic native feature would not cover |
| AI disruption: assistants move discovery and price-watching off the storefront | Medium over 3–5 years | High | Sessions per order falling across the merchant base; orders arriving through assistant channels | Make saved intent readable by assistants, with consent; grow merchant-side value such as demand planning |
| Partner absorption: Klaviyo adds its own capture | Medium | High | New on-site features from Klaviyo; changes to its partner programme | Become Klaviyo's data source through Objects; stay neutral across 20+ ESPs; hold signals Klaviyo cannot get, such as in-store lists |
| Commoditisation and pricing pressure | High | Medium to high | Rivals' review counts growing faster; rivals named in cancellation reasons | Fair-usage pricing; compete on measured outcomes |
| New entrants, including AI-built free apps | High | Low to medium | New free apps climbing the category | Leave the bottom of the market; do not chase it |
| Reputation: support quality slips under an AI-first model | Medium | Medium to high | Share of new reviews that are 1-star; reopened tickets | The support-to-product loop in Part 42 |
| Technology shifts in Shopify's storefront, accounts and checkout | High, continuous | Medium | Deprecation notices | Keep the “Built for Shopify” badge; budget for platform changes every quarter |
| Regulatory change: cookie limits, consent, rules on marketing texts, rules on automated profiling | Medium | Medium | Regulator guidance; browser releases; rising consent declines | Device-stored saves (shipped); identity through customer accounts; clear notice for automatic saving |
| Economic downturn: stores close and survivors cut apps | Medium | Medium | “Cutting costs” as a cancellation reason | Proof of return; yearly plans; a suite price |
| Changing workflows: more sales through social apps, marketplaces and brand apps | Medium | Medium | Share of orders from outside the storefront | The API, Tapcart, and capture inside customer accounts |
| Competitor consolidation: app groups buying and bundling rivals | Medium | Medium | Acquisitions in the category | A suite of its own; openness to partnership |
| Open-source or do-it-yourself alternatives | Low to medium | Low | Agencies shipping their own wishlist code | Win on alerts and integrations, which are hard to maintain alone |
| Customer concentration | Unknown | Unknown | Share of revenue from the largest accounts | Not publicly available. With 48,000 merchants the count is spread, but revenue may not be |

## Part 48 — Product obsolescence

If Swym disappeared tomorrow, most merchants would have a replacement button within a day and would feel the loss for a few weeks. Large brands would feel it for months. This whole part is INFERENCE, except the cited case-study figures.

| Question | Answer |
| --- | --- |
| Alternative products | Swish, Wishlist Hero or Growave for the wishlist. A specialist such as STOQ or Notify Me! for restock alerts |
| Internal tools | Only the largest brands would build their own. An agency could ship a basic version in weeks |
| Manual processes | Restock requests on a spreadsheet; sale announcements sent to the whole list |
| Consultants | Agencies would be hired to migrate flows and rebuild custom designs |
| Migration difficulty | Easy for the button. Days of work to rebuild ESP flows on a new app's events. Weeks for custom or headless builds |
| Data loss | The main loss. Shoppers' saved lists and restock sign-ups vanish unless exported first. Lists held against Swym's anonymous ID probably cannot be moved at all |
| Workflow disruption | Price-drop and restock alerts stop at once. Shop staff lose their lists |
| Revenue impact | Bounded. FACT: Swym's best published cases credit it with nearly 1 in 10 orders (Escentual) and 20% of peak-season revenue (TOV Furniture). HYPOTHESIS: a typical store would lose a low single-digit percentage of revenue until it replaced the alerts |
| Compliance impact | Small. Marketing consents collected through Swym's forms would need to be preserved in the ESP |

### What this reveals about the product's true value

- **The button is replaceable. The accumulated lists and the wiring are not, at least not quickly.** Swym's value sits in stored intent and in the connections that act on it.
- **For most merchants it is a strong “should have”, not a “must have”.** The store keeps trading without it.
- **Value is concentrated.** It is highest where stockouts and markdowns are frequent, which is fashion.
- **The implication for strategy:** invest in what would be missed (data, alerts, measured revenue), not in what would be replaced in a day (widgets).

## Part 49 — Switching costs

Switching costs are low for small stores and high for enterprise accounts, with a steep gradient between.

| Type of cost | Rating | Explanation |
| --- | --- | --- |
| Data | Medium | Saved lists and restock sign-ups must be exported and imported. Anonymous lists are tied to Swym's cookie and are likely lost. Demand history does not transfer |
| Workflow | Medium; high on Pro and above | ESP flows, segments and Shopify Flow automations are built on Swym's event names and must be rebuilt |
| Integration | Low with Klaviyo only; high with enterprise ESPs or custom webhooks | Enterprise connections were set up jointly with Swym's team |
| Training | Low | Marketers need little retraining. Shop staff using the till extension need more |
| Organisational | Low; medium at Enterprise | A new vendor must pass security and legal review again |
| Behavioural | Low for merchants; medium for shoppers | Returning shoppers expect their lists to be there |
| Contractual | Low | Monthly billing through Shopify. Yearly plans commit up to 12 months. Enterprise terms are not public |
| Implementation | Low to high | A theme-based install is quick to replace. Paid custom design work and API builds are not |

**Overall:** low on Starter, medium on Pro and Premium, high on Enterprise. INFERENCE: this is why the product's energy goes into moving merchants up the plans and into integrations.

## Part 50 — Value chain

Swym sits between the storefront and the tools that communicate with shoppers. It converts browsing into addressable, product-level demand.

```
UPSTREAM
Traffic (ads, search, social, email)
↓
Storefront and catalogue (Shopify theme, products, prices, stock)
↓
SWYM
Capture intent  →  identify the shopper  →  store it
→  detect a change (time, price, stock)  →  publish an event
↓
DOWNSTREAM
Messaging (Klaviyo and other ESPs, text, push)
Advertising (Meta)
Automation (Shopify Flow)
In-store selling (the shop till)
↓
Checkout and order
↓
Reporting, and stock and pricing decisions
```

| Element | Detail |
| --- | --- |
| Inputs | Shopper sessions; catalogue data; shopper identity (email, phone, customer account); consent |
| Dependencies | Shopify's theme and data interfaces; the ESP; the browser cookie; the consent banner |
| Outputs | Events, segments, alerts, lists and reports |
| Adjacent products | ESPs; pre-order apps; loyalty and reviews; search and recommendation tools; stock-planning tools; tools for shop staff to manage clients |
| Vertical integration opportunities | Downstream into measurement: proving which messages caused sales. Upstream into on-site personalisation: FACT, the API already has beta endpoints for recently viewed products and saved carts. Going far downstream into messaging would collide with the ESPs |
| Horizontal expansion opportunities | Pre-orders alongside restock alerts, which specialists already bundle. Demand planning. Markdown targeting. Reorder lists for trade buyers |

## Part 51 — Expansion opportunities

The best expansions add a new user inside accounts Swym already has. Market sizes are relative judgements; public data does not support dollar figures.

| Type | Opportunity | Market size | Strategic fit | Competitive intensity | Execution difficulty |
| --- | --- | --- | --- | --- | --- |
| Horizontal | Merchandising and stock teams: a demand report | Medium | High | Low to medium | Medium |
| Horizontal | Shop operations: advanced selling tools for staff | Medium | High | Medium; specialist tools exist | Medium to high |
| Horizontal | Trade buyers: reorder lists and quotes | Small to medium | Medium | Medium | Medium |
| Horizontal | Customer support: agents see a caller's saved items | Small | Medium | Low | Low |
| Vertical | Measured uplift and message optimisation | Medium | High | Low | High |
| Vertical | Pre-orders added to restock alerts | Medium | High | High | Medium |
| Vertical | On-site personalisation driven by saved intent | Large | Medium | High | High |
| Geographic | Europe and Japan | Medium | High. The app already supports German, French, Italian, Spanish, Polish and Japanese | Medium | Low to medium. Support hours are the gap; a reviewer in Ukraine complained of weekday-only support |
| Customer segment | Further up into enterprise | Medium | High | Low among wishlist apps; higher against custom builds | High: sales, security, service |
| Customer segment | Down into very small stores | Large by count, small by revenue | Low. Swym left this segment when it removed the free plan | High | Low |
| Platform | Intent data that other apps and AI assistants can read | Unknown; an option on the future | High | Low today | High |

## Part 52 — Product portfolio strategy

Swym has moved from a point solution toward a suite in name, and toward a platform component in substance. The suite is the weaker half.

| Element | Assessment |
| --- | --- |
| Core product | Wishlist Plus. Detected on 64,525 stores |
| Adjacent products | Back in Stock Alerts (23,167 stores, shrinking). Gift Lists and Registries (38 reviews). Advanced sales tools as a paid add-on. Customisation services |
| Product bundles | None visible. Each app has its own listing, plan and meter |
| Cross-sell | Natural between wishlist and restock alerts. INFERENCE: weak in practice, because the wishlist app already sends restock alerts for saved items |
| Upsell | Strong, through tiers |
| Platform strategy | Shared shopper identity and events across the apps; one developer API |
| Cannibalisation | Wishlist Plus includes restock, price-drop and low-stock alerts for saved products, which removes part of the reason to buy the restock app |
| Suite strategy | “Shopper engagement platform” in the marketing; three separate purchases in practice |

### Point solution → suite → platform

- **2016:** a point solution, the wishlist.
- **2016–2023:** a partial suite of three apps.
- **2025–2026:** platform language, backed by real work on events, Shopify Flow, Klaviyo Objects and the API.

### Is this likely to work?

- **The suite: only partly.** The restock app is losing ground to specialists with pre-orders and free plans. The registry app is small. Nothing ties the three together commercially.
- **The platform component: plausibly, for mid-sized and large merchants.** It works if Swym's data is demonstrably better than what Shopify and Klaviyo can gather themselves. That is the test.
- **My recommendation:** stop presenting three apps as a suite until one plan and one setup make it true, and put the weight on the data layer.

## Part 53 — Business model canvas

The canvas summarises how the business works on one page. Cost structure and key activities are INFERENCE; the rest is drawn from facts in earlier parts.

| Block | Swym |
| --- | --- |
| Customer segments | Small Shopify stores (Starter). Mid-sized and Shopify Plus brands (Pro, Premium). Enterprise brands with several countries and a complex marketing stack. Agencies, as a channel |
| Value propositions | Recover demand that would be lost. Grow the audience the store can contact, using data shoppers give willingly. See which products are wanted. Connect online interest to the shop floor. Do all of it at enterprise scale |
| Channels | The Shopify App Store. Agencies. ESP partner directories and joint content. Demo requests |
| Customer relationships | Self-serve with chat support. A shared success team. A dedicated manager for Enterprise. Webinars and playbooks |
| Revenue streams | Subscriptions to three apps. Enterprise contracts. A paid add-on for sales tools. Customisation work by the hour |
| Key resources | App Store ranking and reviews. More than twenty integrations. Anonymous-identity and consent technology. Accumulated intent data. An engineering and support team based mostly in India |
| Key activities | Keeping the storefront widget working across themes. Maintaining integrations. Support. Partner marketing. Hosting at high volume |
| Key partners | Shopify. Klaviyo and other ESPs. Agencies. Tapcart. A cloud provider |
| Cost structure | People first: engineering and support. Then hosting, Shopify's fees, and partner and event marketing |

## Part 54 — Lean canvas

The lean canvas is a variant aimed at the problem and the edge over rivals.

| Block | Swym |
| --- | --- |
| Problem | Interested shoppers leave without a trace. Stockouts lose ready buyers. Merchants have no signal of demand before a purchase. Existing alternatives: retargeting ads, abandoned-cart emails, spreadsheets |
| Customer segments | Shopify brands in fashion, home, beauty and jewellery. Early adopters: brands with frequent stockouts and an active Klaviyo user |
| Unique value proposition | Know what each shopper wants and bring them back automatically, even if they never logged in |
| Solution | Wishlist, save for later and automatic saving. Price-drop, low-stock and restock alerts. Connections to the store's marketing, automation and till |
| Channels | App Store search, agencies, Klaviyo |
| Revenue streams | US$29.99 to US$99.99 a month in tiers; custom Enterprise pricing |
| Cost structure | Staff, hosting, platform fees |
| Key metrics | Recovered saved-product orders. Activation by day 14. Share of saves from contactable shoppers. Net revenue retention. Churn after reaching quota |
| Unfair advantage | Ten years of App Store position and reviews; the integration set; the installed base |

## Part 55 — Product-market fit

**Rating: Strong for the core wishlist in its target segment. Not exceptional.** The second and third apps, and the “platform” positioning, have weaker fit.

| Signal | Evidence | Reading |
| --- | --- | --- |
| Retention | Not publicly available. Reviews include merchants reporting 5 and 9 years of use | Positive, anecdotal |
| Organic growth | FACT: about 48,000 merchants reached on roughly US$1.3 million of outside funding | Strong. Growth this capital-light means customers pulled the product |
| Recent growth | FACT: detected installs up 23.9% in a year, flat in the latest quarter | Positive, with a recent stall |
| Customer references | Named large brands; case studies with named executives | Strong |
| Expansion | A clear tier path. The rate of upgrades is not public | Unknown |
| Satisfaction | NPS is not public. FACT: 4.7 stars, 92% five-star, across 1,481 reviews | Strong, with the caveat that reviews follow support chats |
| Usage | FACT: 1 billion intent actions; more than 1 million requests a minute at peak | Strong |
| Revenue growth | Not publicly available | Unknown |
| Adoption against rivals | About five times the reviews of its closest wishlist-only rival | Strong |
| Customer concentration | Tens of thousands of accounts | Low risk by count |

### Why “strong” and not “exceptional”

1. **Value takes effort to see.** A product with exceptional fit does not need an AI assistant to point out its own features.
2. **Several churn causes are self-inflicted.** Quota pauses and default settings produce complaints that have nothing to do with whether merchants want the product.
3. **Fit is uneven across the portfolio.** Restock alerts are losing installs. Registries are small.
4. **Fit is uneven across segments.** Strong for mid-sized fashion and home brands; weak for very small stores, which Swym has in effect stopped serving.

| Product or position | Fit rating |
| --- | --- |
| Wishlist Plus, for mid-sized and large Shopify brands | Strong |
| Wishlist Plus, for very small stores | Weak |
| Back in Stock Alerts | Emerging to weakening |
| Gift Lists and Registries | Emerging |
| Swym as an “intent platform” | Emerging |

## Part 56 — Market analysis

No analyst publishes a market size for Shopify wishlist apps, so I build one from the bottom up and show every assumption. My confidence is low: treat each figure as right to within a factor of two.

**Definitions.** TAM (total addressable market) is the revenue if every store that could use the product bought it. SAM (serviceable addressable market) is the part Swym's current product and price can serve. SOM (serviceable obtainable market) is what Swym can realistically hold.

### The calculation

| Step | Figure | Basis |
| --- | --- | --- |
| Active Shopify stores | About 2.5 million | FACT: BuiltWith counts 6.9 million sites with Shopify code, and the same article puts actively trading stores at 2.5 to 3.5 million ([ecomm.design](https://ecomm.design/how-many-shopify-stores-are-there/)). I take the low end |
| Share where a wishlist is useful | 15% to 25% | My assumption. The store needs a real catalogue, considered purchases and some traffic. Most Shopify stores are very small |
| Relevant stores | 375,000 to 625,000 | 2.5 million × 15% and × 25% |
| Average price | US$600 a year | My assumption: US$50 a month, between the entry and top self-serve plans |
| **TAM** | **US$225 million to US$375 million a year** | 375,000 × US$600 and 625,000 × US$600 |
| Share that fits Swym's price and ICP | 5% to 8% of active stores | My assumption: stores with enough traffic to fill a US$30+ plan |
| Fitting stores | 125,000 to 200,000 | 2.5 million × 5% and × 8% |
| Average price for these stores | US$720 a year | My assumption: US$60 a month, since they are larger |
| **SAM** | **US$90 million to US$144 million a year** | 125,000 × US$720 and 200,000 × US$720 |
| **SOM today** | **US$5 million to US$18 million a year** | The revenue range estimated in Part 2 |

**A cross-check.** FACT: Store Leads detects Wishlist Plus on 64,525 stores. Against 375,000 to 625,000 relevant stores, that is 10% to 17%. A leader with that share of its relevant base is consistent with a mature category.

**What is left out.** Other commerce platforms, and adjacent products such as demand planning or in-store tools.

### Market dynamics

| Factor | Assessment | Label |
| --- | --- | --- |
| Market growth | Not publicly available as a number. It follows growth in active Shopify stores and in retention budgets | INFERENCE |
| Adoption drivers | Rising ad costs. Privacy changes that make a store's own data more valuable. Wider use of ESPs that can act on the data | INFERENCE; the first is Swym's own pitch |
| Barriers | Price sensitivity, too many apps, low traffic, consent friction, and the view that a wishlist is nice to have | INFERENCE |
| Regulatory factors | Cookie-consent rules in Europe, consent for marketing texts, and accessibility rules | INFERENCE. Swym's consent modes and accessibility report respond to these |
| Technology trends | AI assistants in shopping; continuing changes to Shopify's storefront and accounts; headless builds | FACT for the Shopify changes, INFERENCE for the effect |
| Competitive intensity | High at the low end, moderate at the top | See Part 31 |

## Part 57 — Category maturity

**The wishlist-app category is mature. The “intent data” category Swym is trying to define is emerging.**

| Indicator | Evidence | Reading |
| --- | --- | --- |
| Feature commoditisation | Save buttons, alerts and a Klaviyo link appear on every serious rival's listing | High |
| Pricing pressure | Free plans from Wishlist Hero and Growave; a fully free app launched in 2025; Swish at a flat price | High |
| Buyer sophistication | Reviewers compare caps and name rival prices | Rising |
| Innovation rate | New work is in integrations, AI setup and data, not in the wishlist itself | Moderate, and moving to the edges |
| Consolidation | Wishlists are being bundled into retention suites. No acquisitions were verified | Underway through bundling |
| New entrants | Still arriving at the low end | Continuous |

## Part 58 — Product life cycle

The products sit at different stages. All four readings are INFERENCE from the evidence shown.

| Product | Stage | Evidence |
| --- | --- | --- |
| Wishlist Plus | Maturity | Ten years old. Installs flat in the latest quarter. The free plan removed and the entry price raised. Effort directed at retention and upsell. These are typical choices for a mature product |
| Back in Stock Alerts | Late maturity, turning to decline | Installs down 9.0% in a year; a paid-only move criticised in reviews |
| Gift Lists and Registries | Introduction | Launched 2023; 38 reviews; English only |
| The data layer (Shopify Flow, Klaviyo Objects, AI reports) | Introduction | Launched or in early access during 2026 |

**What this means.** Swym is trying to start a second growth curve, the data layer, while taking more revenue from the first, the wishlist. The risk is that actions taken to monetise the mature product damage the goodwill the new one needs.

## Part 59 — Customer ROI

An illustrative model shows two things: the return looks very large when measured Swym's way, and it stays healthy but much smaller when measured strictly. Every input below is my assumption, for a mid-sized fashion store on the Pro plan.

### Assumptions

| Input | Value |
| --- | --- |
| Sessions a month | 100,000 |
| Average order value | US$80 |
| Share of sessions that save a product | 4%, so 4,000 wishlist actions a month. This fits the Pro quota of 10,000 |
| Share of saves from shoppers the store can contact | 35% |
| Share of contactable saves that lead to a purchase after a message | 6% |
| Share of those purchases that would not have happened anyway | 40% |
| Gross margin on products | 55% |
| Swym Pro fee | US$59.99 a month |
| Marketer time to maintain flows | 2 hours a month at US$40 an hour, so US$80 |

### The working

```
Contactable saves        = 4,000 × 35%          = 1,400
Credited orders          = 1,400 × 6%           = 84
Credited revenue         = 84 × $80             = $6,720 a month

Extra orders             = 84 × 40%             = about 34
Extra revenue            = 34 × $80             = about $2,690
Extra gross profit       = $2,690 × 55%         = about $1,480

Total monthly cost       = $59.99 + $80         = about $140
```

### Two ways to state the return

| Measure | Calculation | Result |
| --- | --- | --- |
| Credited revenue per dollar of fee | $6,720 ÷ $59.99 | About 112 times |
| Extra gross profit per dollar of total cost | $1,480 ÷ $140 | About 10.6 times |

The first figure sits inside the 16.6 to 239 times range of Swym's case studies. INFERENCE: this suggests the case studies divide credited revenue by the fee. The second figure is the honest one for a finance team, and it is still a strong return.

### Sensitivity

If only 10% of saves are contactable and only 20% of purchases are truly extra, the same store gets 4,000 × 10% × 6% = 24 credited orders, of which about 5 are extra. That is about US$384 of revenue and US$211 of gross profit against US$140 of cost: a return of roughly 1.5 times. The product then barely pays for itself. The two inputs that decide the outcome are the contactable share and true incrementality, which is why Parts 41 to 43 put email capture and measured uplift near the top.

### Value by type

| Type of value | Estimate for this store | Note |
| --- | --- | --- |
| Revenue gained | About US$2,690 a month of extra sales | From the model |
| Time saved | A few hours a month | No manual restock lists |
| Labour saved | Small | Support answers fewer “when is it back?” emails |
| Errors reduced | Not quantified | Batched alerts avoid promising stock to more people than can buy |
| Risk reduced | Not quantified | Less dependence on paid retargeting and third-party tracking |
| Opportunity cost avoided | Not quantified | Demand signals reduce over-buying and missed restocks |

## Part 60 — Buy versus build

For a typical enterprise brand, buying is the rational choice by a wide margin. The build figures are my assumptions for a team based in the United States.

| Factor | Buy Swym | Build internally |
| --- | --- | --- |
| Cost | Custom pricing. The one public data point is US$299 a month. Even at ten times that, about US$36,000 a year | Two engineers for three to four months, then half an engineer to maintain. At an assumed US$150,000 a year per engineer: US$75,000 to US$100,000 to build, about US$75,000 a year to run |
| Time | Days to weeks | Three to six months |
| Customisation | Wide, through the API and paid services, within Swym's data model | Unlimited |
| Maintenance | Swym absorbs changes to Shopify, to themes and to each ESP | The internal team carries it permanently |
| Security | A vendor review is needed; shopper data goes to a third party | Full control, and full responsibility for consent handling |
| Reliability | 99.993% uptime claimed, at more than 1 million requests a minute | Must be engineered and tested for peak days |
| Talent requirements | None | Front end, back end, data and email deliverability |
| Opportunity cost | Low | Engineers are taken off work that differentiates the brand |
| Scalability | Proven across tens of thousands of stores | Unknown until tested |

**Why the customer rationally buys.** A wishlist does not make a brand different from its competitors, so there is no strategic reason to own it. The cost of building is several times the cost of buying, every year. And the integrations, which are the hard part, are maintained by someone else.

**When building makes sense.** A very large retailer with its own platform and data team, or a brand that wants only a basic list and full data ownership. INFERENCE: AI-assisted development is lowering the build cost each year. That pressure is felt first at the top of Swym's market, where its revenue per account is highest.

## Part 61 — Product gaps

Swym's most important gaps are commercial and evidential, not functional. It has more features than its rivals. What it lacks is predictability, proof and a single product experience. The classification is my judgement.

### Table-stakes gaps — what customers already expect

| Rank | Gap | Why it is table stakes |
| --- | --- | --- |
| 1 | Predictable usage: no hard pause, or an uncapped option | Swish offers unlimited saves on paid plans |
| 2 | The Klaviyo link on the entry plan | Wishlist Hero includes it at US$17; Swish on every plan |
| 3 | A free or very cheap way to start | Three direct rivals have one |
| 4 | Multi-country support below Enterprise | Swish lists Shopify Markets on its standard listing |
| 5 | Self-serve reliability: a button that fits the theme without a support chat; sound translations | Named in 2026 reviews |
| 6 | Consistent pricing information and a way to move down a plan | Basic trust |

### Strategic gaps — needed for long-term competitiveness

| Rank | Gap | Why it matters |
| --- | --- | --- |
| 1 | Measured extra revenue, not only credited revenue | Supports the price and cannot be copied by a free button |
| 2 | Demand analytics for merchandisers | A second user and a second reason to stay |
| 3 | One plan and one setup across the three apps | Defence against bundled suites |
| 4 | Intelligence trained across merchants | Turns scale into something a new entrant cannot match |
| 5 | Intent data that AI assistants and other sales channels can read | Protection if shopping moves off the storefront |
| 6 | Pre-orders in the restock app | Specialists already bundle it |
| 7 | Export to data warehouses and reporting tools | Expected by enterprise data teams |

### Delight gaps — could create real differentiation

| Rank | Gap | Who it delights |
| --- | --- | --- |
| 1 | A shopper-set price target: “tell me when this is under US$60” | Shoppers, and merchants planning markdowns |
| 2 | A weekly “money on the table” note with one-click campaigns for the most-saved products | Owners and marketers |
| 3 | A brief for shop staff before an appointment, built from the client's saved items | Associates in premium retail |
| 4 | Shared lists that friends can add to and comment on | Shoppers planning gifts or a home |

### Overall ranking

1. Predictable usage.
2. Measured extra revenue.
3. Klaviyo access on the entry plan, or another way for Starter stores to reach value.
4. Demand analytics.
5. A single suite.

## Part 62 — Final product scorecard

Scores are my judgement on a 10-point scale, where 5 is average for a mature Shopify app and 8 is clearly strong.

| Dimension | Score / 10 | Evidence | Biggest issue | Recommendation |
| --- | --- | --- | --- | --- |
| Product-market fit | 8 | About 48,000 merchants on roughly US$1.3 million of funding; 4.7 stars | Uneven across apps and segments | Concentrate on the core and the data layer |
| Customer value | 7 | Alerts about products shoppers chose; strong case studies | Depends on an ESP and on contactable shoppers; uplift unproven | Measure it |
| UX | 6 | One-click saving, consent modes, Sidekick setup | Limits, defaults and deep settings | Fix the quota experience first |
| Activation | 5 | Draft flows; value hidden at first; heavy 2026 investment | The first message is often never sent | The activation guard |
| Retention | 7 | Embedded in flows; long-tenured reviewers | The quota loop; small-store closures | Soft limit |
| Monetisation | 6 | Clear tiers and built-in expansion | A metric that punishes success; steep steps; hidden top price | Redesign the metric and publish higher tiers |
| Enterprise readiness | 8 | Shopify Plus certified; enterprise ESPs; API; 24×7 support | Roles and audit logs undocumented; multi-country gated | Document controls |
| Integrations | 9 | 20+ partners; Klaviyo Preferred Partner; Flow; till | Some need Swym's staff to set up | Make every connection self-serve |
| AI | 5 | Setup, diagnostics, a pilot report | Not in the core value; some labelling ahead of substance | Build models on Swym's own data |
| Differentiation | 6 | Breadth, automatic saving, in-store tools | The core feature is a commodity | Compete on data and proof |
| Defensibility | 5 | Distribution and integrations | Dependence on two hosts | Hold data the hosts would rather partner for |
| Go-to-market | 7 | App Store lead; partners; 200+ agencies | One marketplace and one main ESP partner | Add merchant referrals; deepen agencies |
| Scalability | 8 | More than 1 million requests a minute; a lean team | Support and custom services do not scale | Fix at the product level |
| Overall product strength | 7 | A strong, mature product | Self-inflicted commercial friction; an unproven second act | Fair usage, activation, proof |

## Part 63 — One-page product strategy

| Field | Summary |
| --- | --- |
| Product | Swym: Wishlist Plus, with Back in Stock Alerts and Gift Registries, for Shopify stores |
| Target customer | Shopify and Shopify Plus brands in fashion, home, beauty and jewellery, with an ESP and steady traffic |
| Core problem | Shoppers who want a product leave without buying, and the store has no record of what they wanted |
| Value proposition | Know what each shopper wants and bring them back automatically |
| Primary use case | A shopper saves a product; a price-drop or restock alert brings them back to buy it |
| Core workflow | Save → identify → detect a change → message → purchase → credited revenue |
| Business model | Tiered subscriptions capped by monthly wishlist actions, billed through Shopify; custom Enterprise contracts |
| Growth engine | App Store ranking, agencies, and the Klaviyo partnership |
| Retention engine | Accumulated shopper lists and marketing flows built on Swym's events |
| Moat | Distribution and integrations. Data is a moat only per merchant today |
| Biggest weakness | Usage caps that pause the storefront, and value that is hard to see early |
| Biggest opportunity | Become the store's record of shopper intent, used by marketing, merchandising and the shop floor |
| Biggest threat | Shopify or Klaviyo doing the capture themselves; later, shopping through AI assistants |
| North Star Metric | Recovered saved-product orders per month |
| Top 3 product priorities | (1) Fair usage: soft limits, quota-safe defaults, published higher tiers. (2) Activation: get a first message sent within 14 days. (3) Proof: measured extra revenue |
| Recommended strategic direction | Stop competing on the button. Win on capture quality, activation and proof, priced so that a merchant's growth feels like a win. Use that base to build demand intelligence and intent data that other systems rely on |

## Part 64 — Understand this product in 10 minutes

1. **Why do customers buy it?** They want a wishlist, usually because shoppers asked or a rival has one. They choose Swym because it is the most reviewed, carries Shopify's quality badge and connects to their email tool.
2. **Why do customers keep using it?** Shoppers' lists pile up, alerts run without effort, and marketing flows come to depend on Swym's events. Leaving means rebuilding.
3. **Why do customers leave?** They never switch on a message and so never see revenue. They hit a quota and face a pause or a jump in price. The button misbehaves on their theme and support does not fix it. Or the store itself closes.
4. **What is its strongest feature?** The integration layer: saved-product events delivered to more than twenty marketing tools, Shopify Flow and the shop till.
5. **What is its weakest feature?** The usage limit. It is the only feature that can switch the product off for shoppers.
6. **What makes it difficult to replace?** For large stores: years of saved lists, flows tied to its events, custom work on its API and a completed security review. For small stores: very little.
7. **What makes it vulnerable?** The basic wishlist is a commodity, its price metric gives rivals an easy pitch, and it lives entirely on two hosts that could do its job.
8. **What is its biggest growth opportunity?** Selling to a second user in the same account, the merchandiser, by turning saves into demand intelligence, and proving the revenue it creates.
9. **What is its biggest strategic threat?** A native Shopify wishlist in the near term. In the longer term, shopping that happens through AI assistants instead of storefronts.
10. **What would you do if you were the PM?** In the first quarter, make sure a billing limit can never break a storefront and that every new merchant sends a first message within two weeks. In the second, prove extra revenue with a controlled test. Then build the demand report.

## Part 65 — Source register

All pages were read on 7 October 2026 unless a different date is shown. “Date” is the page's own date where it has one.

### Primary sources

| Source | Date | What it supports | Reliability |
| --- | --- | --- | --- |
| [Swym homepage](https://www.getswym.com/) | 2026 | Product list, verticals, customer logos, case-study headlines, uptime and volume claims | High for what is offered; medium for performance claims, which are company-reported |
| [Swym pricing page](https://www.getswym.com/pricing) | 2026 | Plans, prices, quotas, pricing questions and answers | High |
| [Help centre: Wishlist Plus pricing and features](https://help.getswym.com/en/articles/11959983-wishlist-plus-pricing-features) | 18 August 2026 | Plan comparison, what counts as an action, the pause at quota, downgrade rules, support levels | High |
| [Help centre: Smart Save](https://help.getswym.com/en/articles/13274798-smart-save) | 31 August 2026 | How automatic saving works, defaults, the 3× and 0.5% figures, the revenue summary | High for mechanics; medium for the figures |
| [Help centre: cookies and consent](https://help.getswym.com/en/articles/16093297-how-wishlist-plus-handles-cookies-and-cookie-consent) | 2026 | Guest identity, cookie list, behaviour without consent | High |
| [About page](https://www.getswym.com/about-us) | 2026 | Founding year, merchant count, team size, Techstars | High, as company statements |
| [Product updates](https://www.getswym.com/product-updates): January to August 2026, and August 2025 | 2025–2026 | The feature timeline; AI features; integrations | High |
| [Developer docs](https://developers.getswym.com/docs/swym-guides-landing) and the [documentation server page](https://developers.getswym.com/docs/mcp) | 2026 | APIs, shopper identity, beta endpoints, tools for AI coding assistants | High |
| [Technology partners](https://www.getswym.com/technology-partners), [Klaviyo integration](https://www.getswym.com/integrations/klaviyo), [Swym for Sales](https://www.getswym.com/platform/swym-for-sales), [customisation services](https://www.getswym.com/customization-services), [agency programme](https://www.getswym.com/agency-program), [careers](https://www.getswym.com/careers) | 2026 | Integrations, plan requirements, sales tools, service pricing, agency count | High. Some integration copy looks older than the release notes |
| Shopify App Store: [Wishlist Plus](https://apps.shopify.com/swym-relay), [Back in Stock Alerts](https://apps.shopify.com/watchlist), [Gift Lists and Registries](https://apps.shopify.com/swym-registry), [developer page](https://apps.shopify.com/partners/developer-ca6a967f09890f68) | 7 October 2026 | Ratings, review counts, launch dates, prices, data access, languages | High |
| [BigCommerce listing](https://www.bigcommerce.com/apps/wishlist-plus/) | Last updated August 2024 | Presence and scale outside Shopify | High |
| [Job post: Product Builder, Founder's Office](https://jobs.weekday.works/wkdypfybxt) | 2026 | Swym's stated strengths, open problems and working style | High for the company-written text; medium for the job board's company panel |
| [Braze partner documentation](https://braze.com/docs/partners/ecommerce/loyalty/swym/) | 2026 | Events sent; Enterprise plan requirement; setup through Swym's support | High |
| Rival listings: [Swish](https://apps.shopify.com/wishlist-king), [Wishlist Hero](https://apps.shopify.com/wishlist-hero), [Growave](https://apps.shopify.com/growave), [Wishlist by Square](https://apps.shopify.com/wishlist-by-square) | 7 October 2026 | Rival ratings, prices and features | High |

### Secondary sources

| Source | Date | What it supports | Reliability |
| --- | --- | --- | --- |
| Store Leads: [Wishlist Plus](https://storeleads.app/reports/shopify/app/swym-relay), [Back in Stock](https://storeleads.app/reports/shopify/app/watchlist) | October 2026 | Detected installs, growth, top stores, category and country mix | Medium. Estimates from site detection |
| [CB Insights](https://www.cbinsights.com/company/swym/financials) | 2026 | Funding total, last round, investors | Medium. Much of the detail is behind a paywall |
| [GeekWire](https://www.geekwire.com/2017/techstars-seattle-demo-day-favorite-pitches-9-coming-startups/) | April 2017 | The original pitch and early traction | High |
| [TIGER 21 speaker biography](https://tiger21.com/presenter/arvind-krishnan-swym-corporation/) | Undated | The CEO's background | Medium. Read from search results, not opened in full |
| [Koala Apps comparison of restock apps](https://koala-apps.io/blog/best-shopify-apps/back-in-stock/) | Updated June 2026 | Ratings and prices of restock specialists | Medium to low. A vendor's blog |
| [ecomm.design on Shopify store counts](https://ecomm.design/how-many-shopify-stores-are-there/) | 2026 | The base for the market-size estimate | Medium to low. Cites BuiltWith |
| [Listify blog](https://listifyregistry.com/blog/migrating-from-swym-registry-to-listify) | September 2026 | The date and size of the 2026 price change | Low to medium. A competitor; read from search results |
| [Craftshift comparison](https://craftshift.com/best-shopify-wishlist-apps-2026/) | July 2026 | Confirms no free plan on the pricing cards by July 2026 | Medium to low. Read from search results |
| [Notify Me blog](https://notify-me.io/post/shopify-wishlist-without-app) | June 2026 | Shopify has no native wishlist; do-it-yourself methods exist | Low to medium. A competitor; read from search results |
| [Vitals blog](https://content.vitals.app/blog/best-shopify-wishlist-apps) | 2026 | Vitals' own figures | Low. Self-promotion |
| [Explainer on Shopify's agent-facing storefronts](https://shugert.com.mx/resources/shopify-agentic-storefronts-product-data) | May 2026 | That Shopify has opened storefronts to AI assistants | Low to medium. Third party; read from search results |

Also used: [Shop Theme Detector's usage page for Swym](https://shopthemedetector.com/shopify-apps/swym-wishlist), 2026, for the ranking of wishlist apps by usage. Reliability: medium to low; its store counts do not match Store Leads.

### Community sources

| Source | Date | What it supports | Reliability |
| --- | --- | --- | --- |
| [Wishlist Plus 1-star reviews](https://apps.shopify.com/swym-relay/reviews?ratings%5B%5D=1), ten most recent | October 2025 to September 2026 | Complaint themes: automatic saving and quota, support, bugs, setup | Medium. First-hand, individual, unverified |
| Individual reviews: [quota enforcement](https://apps.shopify.com/reviews/1518056), [pause and Enterprise quote](https://apps.shopify.com/reviews/1745375), [automatic saving](https://apps.shopify.com/reviews/2268711), [button and reports](https://apps.shopify.com/reviews/2341712) | 2024 to 2026 | Specific incidents and Swym's replies | Medium |
| Shopify's AI summary of all reviews, on the listing | 2026 | What merchants praise | Medium. Machine-written from real reviews |
| Reddit, G2, Capterra | — | Searched. No substantive discussion found | — |

### Limits of this research

- I did not use the product on a live store. Workflow and UX findings come from documentation and reviews.
- Swym's trust centre did not load, so the type of security report is unconfirmed. I did not open the privacy policy or data-processing terms.
- Swym publishes no revenue, retention or funnel figures. Every such number in this document is an estimate with its working shown.
- Shopify's current revenue-share terms for app developers were not verified.

**Coverage check.** Every item on the brief's final checklist is addressed in the part of the same name.
