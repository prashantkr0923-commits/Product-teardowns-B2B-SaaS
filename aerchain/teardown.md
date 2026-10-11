# Aerchain Product Teardown

Oct 10, 2026 · Prashant Kumar

Aerchain sells AI software that runs a large company's buying process, from an employee's request to the supplier's invoice. The product idea is strong and the customer names are impressive for a company this small, but independent proof is thin and every large rival shipped AI agents in 2026. Revenue growth depends on existing customers buying more modules, so the product manager's real job is to turn impressive pilots into measured, repeatable value in each module.

## How to read this document

**Labels.** Important statements carry one of three labels.

- **FACT** means a source in Part 65 directly supports it.
- **INFERENCE** means it is my reasoned conclusion from the facts.
- **HYPOTHESIS** means it is plausible but cannot be confirmed from public information.
- “Aerchain says” or “Aerchain claims” marks a company marketing claim that nobody independent has verified.

**Four limits to keep in mind.**

- **No hands-on use.** Aerchain has no free trial and no public product documentation. The workflow and user-experience parts are built from its product pages, press coverage, job posts and reviews.
- **Estimates, not reported figures.** Aerchain publishes no pricing, retention or funnel numbers. Every such figure here is my estimate, labelled, with the working shown.
- **Public numbers contradict each other.** For example, the value of purchases running through Aerchain appears as $15B, $20B, $45B and $67B in different places. I flag each conflict where it matters.
- **Very few independent reviews.** There are 9 ratings on Gartner Peer Insights and 2 reviews on G2, so customer-feedback conclusions are weak evidence.

**Two websites.** Aerchain runs an older site (aerchain.io, built around “AI agents”) and a newer one (go.aerchain.io, built around “SpendOS”). Where they differ, I treat the newer site as the current positioning and say so.

**Plain terms.** Procurement has a lot of jargon. A glossary sits at the end of Part 1, and each term is explained again where it first matters.

## Part 1 — Executive summary

Aerchain is a small, well-referenced challenger in a market where the product idea has been proven right and the competition has arrived. The twelve answers below are the shortest complete picture of the product.

### The twelve core questions

**1. What is the product?** Aerchain SpendOS (“Spend Operating System”) is cloud software that runs source-to-pay, meaning every step from finding a supplier to paying the invoice. The work is done by AI agents. An AI agent is software that takes actions, such as sending a request for quotes, and does not only answer questions. Each agent owns one step: intake, sourcing, bid analysis, evaluation, negotiation, award, vendor onboarding and invoices. A chat assistant called Aiera, a Knowledge Hub and an analytics layer sit across them. (FACT, from [Aerchain's product site](https://go.aerchain.io/).)

**2. Who is it for?** Large companies with many legal entities, plants or offices and a high volume of purchases. Named customers sit in consumer goods, manufacturing, real estate, healthcare, telecom and government, mostly in India, the Middle East and Asia. The buyers are the Chief Procurement Officer (CPO) and the Chief Financial Officer (CFO). The daily users are buyers, requesters, accounts-payable staff and suppliers. (FACT for customers and industries; INFERENCE for the regional weighting.)

**3. What problem does it solve?** Procurement teams receive far more purchase requests than they have people to handle. The work runs on emails, PDFs and spreadsheets. Older procurement suites take over a year to install and employees avoid using them. The result is slow buying, purchases that skip the proper process, and savings that are never captured.

**4. Why do customers pay?** Four reasons appear in customer testimonials: employees and suppliers actually use it, buying gets faster, more spending comes under control, and negotiated prices improve. Aerchain claims 8.4% average savings on spend it sources and a cut of over 50% in cycle time. Both are company claims.

**5. What is the core value proposition?** The routine majority of procurement work is done by agents, inside limits the customer sets, on top of the customer's existing finance system, and live in about 16 weeks instead of about 14 months.

**6. What is the primary workflow?** A request arrives in plain words. The intake agent turns it into a structured request. The sourcing agent sends a request for quotes to suppliers. Bids arrive in any format and are turned into one comparison. Bids are scored and negotiated. The winner is recommended, and the purchase order is written into the customer's finance system. Later the invoice is matched and approved.

**7. What is the core product loop?** Every completed purchase adds prices, specifications and supplier behaviour to the Knowledge Hub. Better history gives better price targets and supplier recommendations. Better recommendations make buyers trust the agents with more categories. More categories mean more spending flows through, which adds more history. (INFERENCE; Aerchain describes the parts but not the loop.)

**8. What makes the product successful?** It was shaped by messy, real conditions: groups with ten legal entities, suppliers who only use email, and requesters who will not fill long forms. Three design choices follow from that. Suppliers can bid without a login. The customer chooses how much each agent may decide. The product sits on top of existing systems instead of replacing them.

**9. What are its biggest weaknesses?** Independent proof is thin, with 9 Gartner ratings and 2 G2 reviews. Its own public numbers contradict each other. Revenue is small: about ₹10 crore (roughly $1.2M) in the year to March 2025, with a net loss of about ₹9.4 crore. Around 100 people cover a scope that rivals staff module by module. Contract and analytics agents are still marked “coming soon” on the main site.

**10. What are its biggest opportunities?** Infosys took a 5.3% stake in August 2026 and runs procurement for large clients through Infosys BPM, which is a ready sales channel. Small, unmanaged purchases (“tail spend”) suit full automation. The Dubai Government deployment shows Aerchain can sell as an AI layer on top of a rival's suite. Price can rise as value is proven.

**11. What are its biggest threats?** The Hackett Group reports that 69% of organisations get their procurement AI from features built into platforms they already own. SAP, Coupa, Zycus, Ivalua, GEP and Zip all shipped agents in 2026. One serious AI mistake in a negotiation or a payment could damage trust in the whole approach.

**12. What makes it difficult to replace?** Once live, Aerchain writes purchase orders into the customer's finance system, holds approval rules for every entity, stores years of price and supplier history, and is the channel suppliers are used to. Replacing it means redoing all four. I rate this lock-in as moderate, not strong, because a product that installs in 16 weeks can also be displaced in a similar time.

### Three levels of explanation

**A. The 30-second version.** Aerchain is AI software that runs a large company's buying process. An employee asks for something in plain words, and AI agents turn that into a proper request, get quotes from suppliers, compare them, negotiate, and raise the purchase order in the company's finance system. The customer decides how much the agents can do alone. It installs in about four months on top of existing systems. It is a Bengaluru company with about $4M in yearly subscription revenue and customers such as AB InBev, WeWork and Reliance Jio.

**B. The 2-minute version.** Large companies buy thousands of things through a small procurement team. Requests arrive as vague emails, buyers copy supplier quotes into spreadsheets by hand, and small purchases skip the process completely. The older software built for this, such as SAP Ariba and Coupa, is powerful but takes more than a year to install, and employees work around it.

Aerchain's answer is to give each step of the process to an AI agent. One agent captures the request, one runs the request for quotes, one reads every bid into a single table, one scores them, one negotiates with suppliers over email and chat, and one raises the order. The key design idea is that the customer sets the level of independence for each agent and each category of spending. Cheap, standard items can run without a person. Strategic purchases keep a buyer in charge.

Commercially it is a subscription sold by a sales team to the procurement head and the finance head together. It has roughly 40 to 50 enterprise customers, raised $13M in March 2026, and Infosys bought a 5.3% stake in August 2026. Its challenge is that Zycus, Zip, Coupa and SAP now all sell procurement agents, and Aerchain's public proof is much thinner than theirs.

**C. The 5-minute version.** Add four more ideas to the 2-minute version.

*How it got here.* The founders first ran a business-to-business marketplace for industrial supplies, then built an online auction tool for procurement teams in 2018 to 2019. A 2020 accelerator programme with the brewer AB InBev pulled them into invoice processing for ten African countries. They called the product “autonomous sourcing” by 2022, rebranded around AI agents in April 2025, and now call it a Spend Operating System. So the AI-first story is true of the current product, but the company is older than the story suggests.

*How it makes money.* There is no price list. Price depends on scope, the amount of spending managed and the modules chosen. Dividing about $4M of yearly subscription revenue by 40 to 50 customers gives roughly $80,000 to $100,000 per customer per year. To reach the company's stated target of $25M, it would need about 280 customers at that size. That is not realistic through new sales alone, so existing customers must buy more modules and release more spending to the platform. That only happens when each module proves its value.

*Where it wins and loses.* It wins where the customer has many entities, suppliers who are not tech-savvy, an existing finance system it will not replace, and impatience with year-long projects. It loses where the buyer wants an analyst-endorsed vendor, deep contract management, or AI from the supplier it already uses.

*What should happen next.* The product needs an auditable record of value per module, a clear evidence-based path for moving a category from human-approved to autonomous, and testing that makes agent behaviour safe to change. These three things turn the current story into something a finance head can verify, and verified value is what unlocks expansion.

### Glossary

| Term | Plain meaning |
| --- | --- |
| Procurement | How a company buys everything it needs, from raw materials to laptops and services. |
| Direct and indirect spend | Direct spend goes into the product a company makes, such as raw materials and packaging. Indirect spend supports the business, such as IT, travel and office supplies. |
| Purchase requisition (PR) | An internal request from an employee to buy something. Collecting these requests is called intake. |
| RFx: RFI, RFQ, RFP | Requests sent to suppliers for information, for a price quote, or for a full proposal. |
| Purchase order (PO) | The official order sent to the chosen supplier. |
| Goods receipt note (GRN) | The record that the ordered goods actually arrived. |
| ERP | Enterprise resource planning software, such as SAP or Oracle. It holds a company's financial and operational records. |
| Three-way match | Checking that the invoice, the purchase order and the goods receipt all agree before paying. |
| Tail spend | The large number of small, irregular purchases. They are most of the transactions but a small share of the money. |
| C-class items | Low-value, low-risk items such as stationery or spare parts. |
| Maverick spend | Buying outside agreed contracts or approved suppliers. |
| Spend under management | The share or amount of company spending that goes through the procurement team's controlled process. |
| BAFO | Best and final offer, the last round of a negotiation. |
| Reverse auction (eAuction) | An online event where suppliers bid prices down against each other. |
| Source-to-pay (S2P) | The full process from finding suppliers to paying them. Procure-to-pay (P2P) covers only ordering through payment. |
| Intake and orchestration | Intake is the front door for requests. Orchestration is routing each request through the right steps and systems. |
| AI agent | Software that uses an AI model to take actions toward a goal, checking results as it goes. |
| Copilot | A chat assistant that answers questions and drafts work, with a person deciding. |
| Category manager | A buyer responsible for one type of spending, such as packaging or IT. |
| Accounts payable (AP) | The finance team that checks and pays supplier invoices. |
| SSO and SCIM | Single sign-on lets staff log in with their company account. SCIM automatically adds and removes user accounts. |
| SOC 2 and ISO 27001 | Independent audits of a software company's security practices. |
| ARR | Annual recurring revenue, the yearly value of active subscriptions. |
| NRR | Net revenue retention: this year's revenue from last year's customers, divided by last year's revenue from them. Above 100% means existing customers are growing. |

## Part 2 — Company and product context

Aerchain is a seven-year-old Bengaluru company that has reinvented its product three times and only became venture-scale funded in 2026. Understanding that history explains both its strengths (it knows messy procurement operations) and its weaknesses (old marketing, small revenue, inconsistent numbers).

### Company facts

| Item | What is publicly known | Label |
| --- | --- | --- |
| Founding | The company says it began in 2019. An older accelerator profile says 2018 with a team of 7. Some press reports say 2021, which looks like an error. | FACT that sources conflict; 2019 is the company's own date ([About page](https://aerchain.io/about-us)) |
| Founders | Harsha Kadimisetty, CEO, a mechanical engineer from BITS Pilani who earlier co-founded SupplyBasics, a business-to-business marketplace for industrial purchases. Himavanth Jasti, CTO, also from BITS Pilani, earlier at SupplyBasics, Belong and Practo. | FACT ([YourStory profile](https://events.yourstory.com/basecamp-cohort-11-jiogennext/aerchain)) |
| Legal entity | Agillos E-Commerce Private Limited. Funding records for it start in March 2017, two years before Aerchain's stated founding. | FACT for the records; INFERENCE that the same entity ran SupplyBasics first |
| Headquarters | Vaishnavi Tech Park, Sarjapur Main Road, Bengaluru. | FACT |
| Team size | “80+” on the About page (2024 milestone). Trackers give 82 to about 117. | FACT that estimates vary; no audited figure |
| Funding | About $3M pre-Series A in September 2021, co-led by IndiaMART and Season Two Ventures. $13M Series A on 18 March 2026, led by Pavestone, with IndiaMART. Infosys Innovation Fund took a 5.3% stake, disclosed in August 2026, amount not disclosed. Earlier small backer: Telama Investments. | FACT ([Inc42](https://inc42.com/buzz/aerchain-bags-13-mn-to-scale-agentic-ai-platform-for-enterprise-procurement/), [Venture Intelligence](https://news.ventureintelligence.com/private-equity/infosys-acquires-5.3%25-stake-in-procurement-s%E2%80%99ware-maker-aerchain)) |
| Total raised | About $17M before the Infosys stake. Inc42 shows $19.5M+ in total. | FACT that trackers differ |
| Valuation | Not publicly available. | See the estimate below |
| Accelerators | Lumis Partners, JioGenNext and AB InBev's Beer Garage programme. | FACT ([YourStory](https://yourstory.com/2021/09/funding-alert-aerchain-raises-3-m-indiamart)) |
| Business model | Enterprise subscription software, sold by a sales team, priced on scope, spend managed and modules. | FACT |
| Major markets | India first, then the Middle East and wider Asia. The company claims customers in 30+ countries. | FACT for the claim; INFERENCE for the weighting |
| Customer count | “40 enterprise accounts” on the product site; “over 50 global enterprise customers” in Series A press. | FACT that the two figures differ |
| Named customers | Logos: Reliance Industries, Reliance Jio, Unilever, NSE, Danone, Tata Communications, WeWork, DS Group, Brigade, HCG Hospitals, Cloudnine, CenturyPly, Infosys, IndiQube, Shahi. Testimonials: AB InBev, Cars24, WeWork, Manjushree. Also named: Dubai Government and Al-Futtaim. | FACT that Aerchain shows them; depth of each deployment is not public |
| Analyst presence | Listed as an autonomous sourcing vendor in Gartner's 2022 Market Guide for E-Sourcing Applications. Rated 4.3 from 9 ratings in Gartner Peer Insights' “AI Agents for Procurement” category. No evidence it appears in the 2026 Gartner Magic Quadrant for source-to-pay suites. | FACT for the first two; INFERENCE for the third |

### Financial picture

Aerchain's filed financials are small next to its marketing, and the gap matters for any view of its growth.

| Period | Figure | Source and label |
| --- | --- | --- |
| September 2021 | About $500K ARR; company said it was EBITDA and cash-flow positive | FACT that the company claimed this ([YourStory](https://yourstory.com/2021/09/funding-alert-aerchain-raises-3-m-indiamart)) |
| FY23 (April 2022 to March 2023) | Revenue about ₹6.4 crore; loss about ₹4.4 crore | FACT from a tracker summary; treat as approximate |
| FY24 | Revenue about ₹5.4 crore | FACT ([Inc42 financials](https://inc42.com/company/aerchain/financials/)) |
| FY25 (April 2024 to March 2025) | Revenue about ₹10.1 crore, up 85.9%. Total expenses about ₹19.5 crore. Net loss about ₹9.4 crore | FACT ([Inc42 financials](https://inc42.com/company/aerchain/financials/); Venture Intelligence gives operating income of ₹9.87 crore) |
| Late 2026 | About $4M ARR, with a stated goal of $25M | FACT that Aerchain's own job postings say this ([Senior Product Manager posting](https://www.foundit.in/job/senior-product-manager-aerchain-bengaluru-bangalore-60049495)); not independently verified |

**The reasoning behind three observations.**

- **FY25 revenue in dollars.** ₹10.1 crore is ₹101 million. At about ₹84.5 to the dollar, the average rate for that year, that is about $1.2M.
- **The jump to $4M ARR.** ARR is a forward-looking run rate, and the $4M figure is from about 18 months after FY25 closed. Going from $1.2M of recognised revenue to $4M of run rate means roughly 3.3 times growth in 18 months. That is fast but possible after a funding round. It could also mean ARR counts signed contracts that are not yet live. (INFERENCE.)
- **“Cash-flow positive since 2021.”** The product site makes this claim. A net loss of ₹9.4 crore on ₹10.1 crore of revenue in FY25, with total assets falling 27%, makes it unlikely that FY25 was cash-flow positive. (INFERENCE.) I do not treat the claim as fact.

**Valuation estimate (HYPOTHESIS).** Series A rounds usually sell 15% to 25% of a company. A $13M round at that range implies a value after the round of $52M to $87M. I cannot confirm where Aerchain's round fell. Infosys's 5.3% stake does not help, because the amount paid was not disclosed.

### Numbers that contradict each other

| Metric | Versions found | Where |
| --- | --- | --- |
| Spend under management | $15B+, $20B+, $45B+, $67B | Old site and About page; job description; Series A press and product site; a second section of the product site |
| Customers | 40; 50+ | Product site; Series A press |
| Countries | 30+; 40+ | Press and product site; old site |
| Founding year | 2018, 2019, 2021 (and 2016 on one tracker) | Accelerator profile; company; press; CB Insights |
| Early funding | “$3.2M pre-seed in 2020”; $3M pre-Series A in September 2021 | About page; press |
| Assistant's name | Aera; Aiera | Old site; new site |

**Why this matters.** A procurement or finance buyer checks vendor claims for a living. Conflicting numbers on the vendor's own pages weaken trust before the first call. It also suggests the metric has no single owner or definition inside the company. (INFERENCE.)

### Product timeline

| Year | Event | Strategic significance |
| --- | --- | --- |
| 2016 to 2017 | SupplyBasics, a marketplace for industrial purchases. The legal entity's first funding dates from March 2017. | The founders learned industrial buying from the supplier and transaction side. |
| 2018 to 2019 | Aerchain starts as an e-procurement and online auction platform for large enterprises. Early customers: WeWork, 91Springboard, PNC Infratech, Colive. | The original product was a sourcing tool. The original customer was a mid-sized Indian company in real estate and infrastructure. The original problem was getting competitive prices through auctions. |
| 2020 | Selected for AB InBev's Beer Garage accelerator. Builds a supplier portal, invoice reading and three-way match for AB InBev in Africa. The contract closed in under a month, and scope grew from 2 countries to 10. | First global enterprise customer. Pulled the product from sourcing into invoices and payments, which is the origin of the full source-to-pay scope. |
| 2021 | $3M pre-Series A from IndiaMART and Season Two Ventures. About $500K ARR. Customers in beverages, real estate and automotive, all in India. | IndiaMART is India's largest business-to-business marketplace, so the investor is also a possible source of supplier data. |
| 2022 | Version 2. Listed in Gartner's Market Guide as an autonomous sourcing vendor. Positioning: “next-generation autonomous sourcing platform”. | First analyst recognition. The message shifts from digitising to automating. |
| 2023 | “Embedded AI for autonomous sourcing”. Blog posts on chatbot intake. | First step toward conversational intake. |
| 2024 | Founder describes an “autonomous PR to PO process” with a virtual assistant working across email, Slack, Teams and WhatsApp. Team reaches 80+. | Generative AI becomes the core of the story. |
| April 2025 | Rebrand. “From a smart sourcing solution into a full-fledged AI-powered procurement platform”, organised as named AI agents. | The product is repackaged as a team of agents. |
| 2025 to 2026 | “SpendOS” positioning and Version 5 with predefined fields, workflows and approvals. 16-week deployment claim. | A move from custom configuration toward a standard product, which is what makes scaling possible. |
| February 2026 | Publishes “State of AI Procurement 2026”, based on interviews with 163 procurement leaders. | Thought-leadership marketing aimed at global buyers. |
| March 2026 | $13M Series A led by Pavestone, for AI capabilities and global expansion. | First institutional growth capital. |
| August 2026 | Infosys Innovation Fund takes a 5.3% stake. Press reports say Infosys BPM could deploy Aerchain to its clients. | A strategic channel partner that is also a customer logo. |

### How the strategy evolved

The product has moved through four identities, and each one widened the scope.

1. **Marketplace to tool (2016 to 2019).** The founders stopped being a middleman for industrial goods and started selling software to the buyer. This traded transaction revenue for subscription revenue.
2. **Sourcing tool to source-to-pay suite (2020 to 2022).** AB InBev's invoice problem pulled the product downstream. This gave breadth early, but breadth built for one customer's needs risks being shallow elsewhere. (INFERENCE.)
3. **Suite to “autonomous” (2022 to 2024).** The message moved from digitising steps to removing human effort from them.
4. **Autonomous to agents and operating system (2025 onward).** The same capabilities are now presented as agents on one data model, with the customer choosing each agent's independence.

**The trade-off behind this path.** Aerchain optimised for covering the whole process on one data model. It sacrificed depth in any single step, and it took on the cost of serving demanding enterprises with a small team. That was rational for one reason: AI agents are more useful when one agent can see what the others learned, and a small company cannot win a feature-by-feature fight against a specialist in every step. (INFERENCE.)

## Part 3 — Product positioning

Aerchain positions itself as the AI-native operating system for all enterprise spending, but what customers visibly value is narrower and more practical: people use it, it goes live fast, and suppliers respond. The positioning is stronger on its practical claims than on its grand ones.

### Positioning elements

| Element | Aerchain's position |
| --- | --- |
| Product category | Procurement software. Gartner Peer Insights files it under “AI Agents for Procurement”. G2 files it under procure-to-pay and strategic sourcing. |
| Subcategory | AI-native source-to-pay, with its deepest roots in autonomous sourcing and negotiation. |
| Primary job to be done | Get a purchase from request to order quickly, at a good price, inside company rules, without a buyer doing the manual steps. |
| Secondary jobs | Bring unmanaged spending under control. Give finance a live view of committed spending. Match and clear invoices. Onboard and check suppliers. |
| Core value proposition | Agents do the routine procurement work inside limits you set. |
| Differentiated value proposition | Full request-to-pay scope on one data model, live in about 16 weeks, on top of the systems you already own, with suppliers who do not need a login. |
| Brand promise | Procurement that runs itself where it safely can, and advises you where it cannot. |
| Strategic positioning | A challenger to legacy suites on speed and cost, and to single-step AI tools on breadth. |
| Category narrative | Old suites are workflow software with AI added later. Intake and orchestration tools only route work between other tools. Agents on shared company data make orchestration built-in. |

### Positioning statement

For procurement and finance leaders at large, multi-entity companies, who cannot keep up with purchase volume using emails, spreadsheets and software their employees avoid, Aerchain SpendOS is an AI-native source-to-pay platform that completes routine buying work from request to payment with AI agents. Unlike legacy suites such as SAP Ariba and Coupa, which take over a year to install, or single-step AI tools such as Pactum and Fairmarkit, Aerchain covers the whole process on one data model, lets the customer set each agent's independence, and goes live in about 16 weeks on top of the existing ERP.

### Is the positioning credible?

**What the company claims.** AI-native. 300+ agents in production. $45B+ (or $67B) of spend managed. 8.4% average savings. 16 weeks to go live. “1 in 5 of Asia's largest enterprises run on SpendOS.” Eight wins that replaced SAP Ariba and one that replaced GEP.

**What customers appear to value.** The four named testimonials each stress a different practical result. Cars24 cites 99% adoption. WeWork cites 100% of operational spend under management. AB InBev cites a 97% cut in cycle time. Manjushree cites 4.5% cash savings and 87% supplier participation in an auction. The one visible Gartner review praises the purchase order workflow, supplier communication in one place, and an interface that is “relatively intuitive compared to older procurement tools”. None of them leads with autonomy or agents. (FACT for the quotes; INFERENCE for the pattern.)

**Where the positioning is strong.**

- **Speed and overlay.** The Dubai Government runs Aerchain on top of an existing Jaggaer installation. That is concrete evidence for “no rip and replace”.
- **Supplier ease.** No-login bid links and replies by email match how suppliers in its home markets actually work.
- **Graduated autonomy.** Letting the customer set independence per agent and per category is a credible answer to the trust question every buyer asks.
- **Enterprise security proof.** Passing a 119-row security questionnaire and a 142-row architecture review at Al-Futtaim, and a review at the National Stock Exchange of India, is specific and checkable.

**Where it is weak.**

- **“AI-native.”** The company started as an auction tool in 2018 to 2019 and says it embedded AI in 2023. “Rebuilt around AI” is more accurate than “born AI-native”. A rival can point this out. (INFERENCE.)
- **“300+ agents.”** The sites name six to eight agents. The larger number probably counts small task-level agents or per-customer instances. Without a definition it reads as inflation. (INFERENCE.)
- **“Operating system for spend.”** The main site still marks the Contract Agent and Analytics Agent as “coming soon”. An operating system with two missing parts is a stretch.
- **Unverifiable scale claims.** The spend figure has four versions, and the “1 in 5 of Asia's largest enterprises” claim has no stated basis.
- **Proof depth.** Case studies on the main site link to a “soon” page. Statistics on agent pages are labelled “For 100 RFQs” with no baseline or method.

**Verdict.** The product is over-positioned on breadth and autonomy, and under-positioned on the things it has actually proven: adoption by ordinary users, supplier participation, multi-entity complexity, and fast deployment over existing systems. A sharper position would be “the procurement system people and suppliers actually use, live in a quarter”, with autonomy as the growth path and not the headline. (INFERENCE.)

## Part 4 — Ideal customer profile

The best-fit customer is a large, multi-entity group in a physical-goods or multi-site industry, running a major ERP, with a small procurement team and suppliers who live in email. The profile below is inferred from named customers, case material and the product's design.

### Firmographic characteristics

| Attribute | Best fit | Evidence and label |
| --- | --- | --- |
| Company size | Large enterprise or large mid-market. Thousands of employees, hundreds to thousands of requesters. | FACT: an FMCG deployment had 1,000+ users and 7,500+ suppliers. |
| Revenue | Roughly $200M and above, with third-party spending of $100M or more. | HYPOTHESIS: below this, savings may not justify an enterprise contract. Aerchain's own return model uses $500M of managed spend. |
| Industry | Consumer goods, food and beverage, manufacturing, real estate and co-working, healthcare, telecom, government. | FACT from logos and the industries listed on the site. |
| Geography | India first, then the Gulf and wider Asia. Selective global reach through multinational customers. | INFERENCE from customer names and the Dubai and Al-Futtaim references. |
| Structure | Many legal entities, plants or sites, several currencies. | FACT: the product is described as built for multi-entity, multi-currency, multi-geography buying. |
| Growth stage | Established and operationally complex, or fast-growing with procurement falling behind. | INFERENCE: Cars24 and WeWork fit the second type. |

### Organisational characteristics

| Role | Who it is here | Part in the deal |
| --- | --- | --- |
| Economic buyer | CPO or Head of Procurement, with the CFO as co-signer | Owns the budget. Aerchain's demo explicitly invites both. |
| Decision maker | CPO for scope; CFO for money; CIO for technical approval | Any one of the three can stop the deal. |
| Champion | Head of procurement operations or a digital-transformation lead | Feels the daily pain and runs the evaluation. |
| End users | Buyers and category managers; requesters across the business; accounts-payable staff | Decide whether the product is actually used. |
| Administrator | Procurement operations or a systems analyst | Configures workflows, approval rules and templates. |
| Finance | Controller and accounts payable | Care about budget checks, invoice matching and audit trail. |
| IT and security | CIO office, ERP team, information security | Review integration, single sign-on and data protection. |
| Legal | Contracts team | Lighter role today because contract management is not a mature module. |
| The customer's own procurement team | The same people who use the product | Unusual feature of this market: the buyer of procurement software is a professional buyer. Expect hard negotiation. |

### Behavioural characteristics

- **Existing tools.** A major ERP (SAP, Oracle, NetSuite or Microsoft Dynamics) with procurement done partly in the ERP and mostly in email and spreadsheets, or an older suite that employees avoid.
- **Workflow maturity.** Approval rules exist but differ by plant or entity. There is no single view of where a request is.
- **Pain intensity and frequency.** High and daily. Thousands of requests a year, each needing triage, quotes and comparison.
- **Technical sophistication.** Moderate. Procurement teams are process experts, not technologists. Suppliers are often small and email-first.
- **Integration needs.** Two-way sync with the ERP for requisitions, purchase orders, goods receipts and invoices is essential.
- **Compliance needs.** Audit trails, approval evidence and, for regulated customers, security certifications and data-protection compliance.

### Trigger events

| Trigger | Why it starts an evaluation |
| --- | --- |
| A cost-reduction mandate from the CFO or board | Procurement savings are the fastest visible lever. |
| Workload outgrowing headcount | The Hackett Group projects procurement workload up 8% in 2026 while headcount falls 0.9%. |
| A new CPO or CFO | New leaders review tools in their first year. |
| A failed or stalled suite rollout | Low adoption of an expensive suite creates appetite for something lighter on top. |
| ERP migration, for example to SAP S/4HANA | Process redesign is already funded, so adding a procurement layer is easier. |
| An audit finding or fraud incident | Maverick spend, duplicate payments or weak approval evidence force action. |
| Mergers, new entities or new countries | Each new entity multiplies approval paths and supplier lists. |
| A leadership instruction to “use AI” | Hackett reports 43% of organisations are actively pursuing AI deployment in procurement, nearly double the year before. |
| A supply shock | Price spikes or supplier failures expose a narrow supplier base. |

**Who is a poor fit.** Small companies with few purchases. Companies whose spending is mostly a few very large strategic contracts. Companies fully committed to a single vendor's suite and happy with it. Buyers who need a vendor from the top of an analyst ranking to get internal approval. (INFERENCE.)

## Part 5 — User personas

Aerchain has to satisfy nine different kinds of people, and the person who signs the contract almost never uses the product daily. One of the nine, the supplier, is not even the customer's employee. The roles are inferred from Aerchain's own material and from how enterprise procurement works; job titles vary by company.

| Persona | Role | Goals | Pain points | Jobs to be done | Frequency of use | Important features | Success metric | Buying influence |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Chief Procurement Officer | Economic buyer and decision maker | Visible savings; more spend under control; a team doing strategy, not admin | Cannot see where cycle time goes; cannot hire enough buyers; has paid for software nobody used | Prove procurement's value to the CFO | Weekly, through dashboards | Analytics, savings against baseline, autonomy settings | Savings, spend under management, cycle time | Very high |
| CFO or Finance Controller | Co-buyer | Spending within budget; clean audits; committed spend visible before month-end | Duplicate or wrong payments; spend that skips approval; waiting for spreadsheet reports | Trust the numbers and control cash | Weekly to monthly | Budget checks, invoice matching, one ledger view | Budget compliance, invoice exceptions, payback | Very high; can veto |
| Head of procurement operations | Champion and administrator | A process that runs without daily firefighting | Different approval paths per plant; manual triage each morning | Standardise and monitor the process | Daily | Workflow builder, approval rules, buyer allocation, templates | Requests closed on time; rework rate | High; runs the evaluation |
| Category manager or buyer | Power user | Spend the week negotiating, not copying quotes | Chasing suppliers; rebuilding the same request for quotes; manual bid comparison | Run more sourcing events with better results | Daily, hours per day | Sourcing, bid analysis, evaluation, negotiation agents; Aiera | Events per buyer; savings per event; supplier participation | Medium; adoption depends on them |
| Requester | Occasional user: plant manager, office admin, any employee | Get what is needed fast | Long forms; no status; repeated clarification questions | Ask once and track it | A few times a month | Conversational intake, status tracking | Time from request to delivery | Low in the deal; decisive for adoption |
| Approver | Budget owner or line manager | Approve quickly with enough context | Approvals arriving with no detail; chasing emails | Say yes or no in one step | Weekly | One-click approvals, pending list in Aiera | Approval turnaround time | Low |
| Accounts-payable clerk or manager | Regular user | Invoices matched automatically; only real exceptions left | Manual matching; supplier calls about payment status | Clear invoices correctly and fast | Daily | Invoice agent, exception routing, duplicate checks | Touchless rate; time to clear; exception rate | Medium |
| CIO, ERP team and information security | Gatekeeper | Clean integration; single sign-on; audit logs; protected data | Another vendor to review, connect and support | Approve safely with little effort | During the deal and at upgrades | Connectors, SSO and SCIM, certifications, audit trail | Integration incidents; review time | High; can block |
| Supplier | External user | Easy bidding; clear requirements; predictable payment | Every customer has a different portal and login | Respond and get paid with little effort | Per event | Magic Links, email replies, portal, mobile app, invoice status | Response rate; time to respond; supplier satisfaction | None in the deal; decisive for value |

**An emerging tenth persona (HYPOTHESIS).** If Infosys BPM runs Aerchain for its outsourcing clients, the daily user becomes an outsourced operator handling many customers at once. That person needs queues, service-level timers and views across several customers, which a product built for one customer's own team does not naturally have.

### Conflicts between personas and how the product handles them

| Conflict | How it shows up | How Aerchain resolves it | What stays unresolved |
| --- | --- | --- | --- |
| Requester wants speed; procurement wants control | People email a buyer or buy directly because the proper route is slow | Conversational intake that asks only for what is missing and checks policy at the start | If buyers still accept emails, the old habit survives |
| Buyer fears replacement; CPO wants headcount leverage | Buyers quietly resist agents that do “their” work | The autonomy ladder keeps buyers in charge of strategic spend, and messaging says the assistant “doesn't replace your team” | The value pitch to the CPO is still partly about doing more with fewer people |
| Finance wants proof; procurement reports optimistic savings | Savings claimed in procurement do not appear in the accounts | Analytics tracks savings “against a baseline, not a rate card” and shows committed, projected and realised spend together | Who defines the baseline is not stated publicly |
| IT wants few systems; procurement wants a specialist tool | Long security and architecture reviews | Sits on the existing ERP, certifications in hand, single sign-on | Still one more vendor with access to financial data |
| Supplier wants little effort; buyer wants structured data | Suppliers ignore portals, so few bids arrive | Suppliers reply by email in any format and the agent structures it | Data read from free-form replies can contain errors that a form would have prevented |
| Admin wants configurability; the company wants a standard product | Each customer asks for its own workflow | Version 5 ships predefined fields and workflows, with a no-code builder for changes | Every exception still tempts the team into custom work |

## Part 6 — Jobs to be done

The primary job is to turn a purchase need into a compliant order at a good price with almost no manual effort. Everything else supports or follows from that.

### Functional jobs

| Rank | Job | Situation (“When…”) | Motivation (“I want to…”) | Expected outcome (“So that…”) |
| --- | --- | --- | --- | --- |
| 1, primary | Convert a need into an order | When a request reaches procurement, usually incomplete | I want it clarified, quoted, compared, negotiated and ordered without doing each step by hand | So that the business gets what it needs in days, at a competitive price, inside policy |
| 2, secondary | Bring unmanaged spend under control | When small purchases skip sourcing because nobody has time | I want them handled automatically within rules | So that savings and compliance cover all spending, not only the big contracts |
| 3, secondary | Compare bids fairly | When ten quotes arrive as PDFs, spreadsheets and emails | I want one like-for-like comparison | So that I pick the right supplier in an hour, not a day |
| 4, secondary | Clear invoices | When an invoice arrives | I want it matched to the order and receipt automatically | So that suppliers are paid correctly and only real exceptions need me |
| 5, supporting | See the truth about spending | When finance or leadership asks what we spent or saved | I want a sourced answer immediately | So that decisions do not wait for a month-end spreadsheet |
| 6, supporting | Onboard and check suppliers | When a new supplier is needed | I want documents and checks handled digitally | So that the supplier can be used quickly and safely |
| 7, supporting | Request something as an employee | When I need an item or service | I want to describe it once in plain words and see its status | So that I do not chase anyone or learn procurement rules |

### Emotional jobs

- **Feel in control.** A CPO wants to stop being surprised by spending they never saw.
- **Feel safe using AI.** Nobody wants to be the person whose AI tool overpaid a supplier. Adjustable autonomy and logged negotiation rounds exist to answer this fear.
- **Feel like a professional, not a clerk.** Buyers want to spend time on judgement and relationships.
- **Not feel blamed.** Requesters and approvers want a visible status so delays are not pinned on them.

### Social jobs

- **Be seen as a strategic function.** Procurement leaders want the board to see them as value creators, not cost police.
- **Be seen as modern.** A leadership team under pressure to “use AI” wants a credible success story.
- **Be a good customer to suppliers.** Fast, clear dealings improve a company's standing with its supply base. AB InBev measured this as supplier satisfaction.

## Part 7 — Customer problem analysis

Before Aerchain, the typical customer runs procurement through an ERP for record-keeping and through email, phone and spreadsheets for the actual work. Six problems follow, and each one feeds the next.

### Summary table

| Customer problem | Existing workaround | Product solution | Value created |
| --- | --- | --- | --- |
| Requests arrive vague and incomplete | Buyers email back and forth to clarify | Conversational intake that asks only for missing details and checks policy | Fewer clarification loops; clean data for every later step |
| Too many requests for too few buyers | Morning triage by hand; requests queue in inboxes | Automatic classification and allocation to buyers; agents run routine events | Shorter cycle time; capacity without hiring |
| Quotes arrive in every format | Copy into a spreadsheet by hand | Bid analysis agent reads PDFs, sheets and emails into one table | A day of work becomes minutes; fewer copying errors |
| The same few suppliers get every request | Send to known suppliers and hope they reply | Supplier recommendation, no-login bidding, automated reminders | More bids per event, which lowers prices |
| Small purchases skip sourcing | Accept the leakage or use purchase cards | Agents run tail-spend purchases autonomously within limits | Savings and compliance on spend nobody managed |
| Invoices need manual matching | AP staff compare documents line by line | Invoice agent reads, matches three ways and routes exceptions | Faster payment; fewer duplicate or wrong payments |

### Problem by problem

**Problem 1: bad intake.**

- **Current process.** An employee emails a buyer or fills a static form: “need 100 laptops for new hires”.
- **Workaround and its cost.** The buyer asks follow-up questions. Aerchain's blog cites Gartner that staff spend up to 27% of their time fixing data quality.
- **Frequency and severity.** Every request; moderate each time, large in total.
- **Users affected.** Requesters, buyers and, later, anyone using the data.
- **Business impact.** Wrong specifications, duplicate purchases and poor data for any AI tool. Gartner found 74% of procurement leaders say their data is not ready for AI.
- **Why existing solutions fail.** A form must show every field for every case, so people skip it.
- **Chain.** Vague request → conversational intake with validation → requester answers two or three targeted questions → complete request on first submission → faster sourcing and trustworthy data.

**Problem 2: volume beyond capacity.**

- **Current process.** Buyers sort and assign requests each morning, then work them one at a time.
- **Cost.** In Aerchain's FMCG example, a group handled 10,000+ requisitions a year across 10 entities, and triage took hours daily.
- **Severity.** High. The Hackett Group projects workload up 8% in 2026 with headcount down 0.9%.
- **Business impact.** Slow buying, production risk, and people going around procurement.
- **Why existing solutions fail.** Workflow software moves a request between people; it does not do the work.
- **Chain.** Queue of requests → automatic allocation plus agents that draft and send RFQs → buyers review instead of create → more events per buyer → shorter request-to-order time.

**Problem 3: manual bid comparison.**

- **Current process.** Quotes arrive as PDFs, spreadsheets and email text with different units, taxes and terms.
- **Cost.** “A full buyer day” per event in the FMCG example. Aerchain's survey of 163 leaders reports evaluation falling from 3 to 4 weeks to 3 to 5 days with AI.
- **Business impact.** Slow awards and comparison errors that pick the wrong supplier.
- **Why existing solutions fail.** Suites require suppliers to type bids into a portal template, and many suppliers will not.
- **Chain.** Mixed-format quotes → extraction into one table → buyer checks exceptions only → decision in an hour → faster awards and auditable comparisons.

**Problem 4: narrow supplier reach.**

- **Current process.** Requests go to three to five familiar suppliers. Some never reply, and the buyer cannot see who opened the request.
- **Business impact.** Less competition and higher prices. Aerchain claims up to 3% extra savings from wider participation.
- **Why existing solutions fail.** Supplier portals need registration and login, which lowers response rates.
- **Chain.** Low participation → recommended suppliers plus no-login links → more suppliers respond → more bids per event → lower prices and less dependence on one supplier.

**Problem 5: unmanaged tail spend.**

- **Current process.** Thousands of small purchases are bought without quotes because sourcing them costs more than it saves.
- **Cost.** An early Aerchain-related case study put leakage at about 5% of tail spend.
- **Users affected.** Requesters, buyers and finance.
- **Why existing solutions fail.** Human effort per purchase is too high relative to its value.
- **Chain.** Small request → agent runs quotes and negotiation inside limits → no buyer time used → competitive price on every purchase → savings and compliance on previously invisible spend.

**Problem 6: invoice matching.**

- **Current process.** Accounts-payable staff compare invoice, order and receipt by hand and chase mismatches.
- **Cost.** AB InBev's African operations handled roughly 100,000 invoices a year when Aerchain began working with them.
- **Business impact.** Late payments, duplicate payments, supplier disputes and weak supplier relationships.
- **Why existing solutions fail.** Template-based invoice reading breaks on varied formats.
- **Chain.** Invoice in any format → reading, duplicate check and three-way match → staff handle exceptions only → faster, correct payment → lower processing cost and better supplier satisfaction.

## Part 8 — Product architecture

The product has three layers: agents that do the work, a platform that connects and governs them, and an intelligence layer that remembers and explains. The tree below combines both of Aerchain's websites, because neither one lists everything.

```text
Aerchain SpendOS
├── Agents (the work)
│   ├── Intake Agent
│   │   ├── Chat or upload to create a request
│   │   ├── Automatic classification and routing
│   │   ├── Policy and budget checks at the start
│   │   └── Approver suggestion and status tracking
│   ├── Sourcing Agent
│   │   ├── Scope and RFQ generation
│   │   ├── Evaluation criteria generation
│   │   ├── Supplier recommendation and discovery
│   │   └── Reverse auctions (named in press, not on the agent page)
│   ├── Bid Analysis Agent
│   │   └── Reads PDF, spreadsheet and email quotes into one table
│   ├── Evaluation Agent
│   │   ├── Scorecards on price, compliance and past performance
│   │   └── Stakeholder review and manual adjustment
│   ├── Negotiation Agent
│   │   ├── Playbooks by category and supplier type
│   │   ├── Target price benchmarking
│   │   └── Parallel multi-round negotiation over email and chat
│   ├── Award Agent
│   │   └── Award recommendation and purchase order pushed to the ERP
│   ├── Vendor Onboarding Agent
│   │   ├── Registration and document collection
│   │   ├── Credibility and compliance checks
│   │   └── Ongoing supplier ratings
│   ├── Invoice Agent
│   │   ├── Invoice reading from PDF, image and email
│   │   ├── Duplicate, fraud and date checks
│   │   ├── Three-way match
│   │   └── Exception and dispute routing
│   ├── Compliance Policy Agent (runs policy checks alongside the others)
│   ├── Contract Agent (marked “coming soon” on the main site)
│   └── Analytics Agent (marked “coming soon” on the main site)
├── Intelligence (memory and answers)
│   ├── Aiera copilot (chat across all agents and data, with sources)
│   ├── Knowledge Hub (specifications, price benchmarks, contract clauses)
│   └── Analytics (committed, projected and realised spend; savings; risk)
└── Platform (connection and control)
    ├── Integrations Hub
    │   ├── Connectors: SAP, Oracle, NetSuite, Dynamics, Coupa, Ariba, Workday
    │   └── Two-way sync of requisitions, orders, receipts and invoices
    ├── Omnichannel Hub (takes in email, chat, portal, PDF, Excel, screenshots)
    ├── Supplier experience (Magic Links, email replies, portal, mobile app)
    ├── Administration
    │   ├── DIY Framework (no-code templates, workflows, reports)
    │   ├── Approval matrices by category, value or risk
    │   └── Autonomy settings per agent and per category
    ├── Security (SSO, SCIM, role-based access, audit logs, encryption)
    └── Multi-Agent Framework (how agents share context and hand off work)
```

**A caution on the tree.** The product site says “eight modules on one data model” but does not name the eight. It also says “300+ agents in production” while naming fewer than ten. The tree shows named capabilities only. (FACT for each named item; INFERENCE for how they group.)

### How the pieces classify

| Type | Items |
| --- | --- |
| Core product | Sourcing, bid analysis, evaluation, negotiation and award. This is the original sourcing product and still the centre of gravity. |
| Core modules added later | Intake at the front; invoices at the back. |
| Supporting modules | Vendor onboarding, compliance policy checks, reverse auctions. |
| Platform capabilities | Integrations Hub, Omnichannel Hub, Multi-Agent Framework, Knowledge Hub. |
| Administrative capabilities | DIY Framework, approval matrices, autonomy settings, role-based access. |
| Analytics | Spend views, savings tracking, supplier risk scoring, off-contract spend flags. |
| Automation | Agent-run events, automatic buyer allocation, one-click approvals. |
| AI capabilities | Document reading, classification, supplier matching, negotiation over text, question answering with sources. |

### The strategic role of each module

| Module | Strategic role | Why it matters to the business |
| --- | --- | --- |
| Intake Agent | The front door and the data source | Whoever owns the request owns the user habit and the cleanest data. Aerchain's own rollout advice is to fix intake first because it creates the measurement baseline. Zip built a $2.2B company on this step alone. |
| Sourcing, bid analysis and evaluation | The proven core | This is where savings are created and where Aerchain has the longest history. It is the land module for most deals. (INFERENCE.) |
| Negotiation Agent | The headline differentiator | “65% of RFQs auto-negotiated at AB InBev” is the most quoted proof point. It is also the highest-risk agent, because it commits money. |
| Award Agent and ERP write-back | The lock-in | Once orders are written into the ERP by Aerchain, removing it means rebuilding an integration that finance depends on. |
| Vendor Onboarding Agent | Supply-side growth | Every new supplier profile makes the next event faster. It also feeds the claimed base of 150,000 suppliers. |
| Invoice Agent | Finance sponsorship | Invoices bring the CFO's team into the product, which widens the buyer group and the contract. It began as custom work for AB InBev. |
| Aiera copilot | Adoption and reach | A chat front end lowers training needs and gives executives a reason to open the product. |
| Knowledge Hub | The memory that could become a moat | Stores each customer's prices, specifications and clauses so agents improve with use. |
| Analytics | Proof of value | The CFO renews on evidence. This layer is the weakest publicly evidenced part, which is a strategic problem. |
| Integrations and Omnichannel hubs | Deployment speed | They make the 16-week promise possible and let Aerchain sit on top of a rival suite. |
| DIY Framework and autonomy settings | Scalability and trust | No-code changes keep customer requests out of engineering. Autonomy settings let cautious customers start small and expand. |
| Contract Agent | The largest gap | Suites and Zip all have contract capabilities. Its absence limits the “operating system” claim. |

## Part 9 — Complete feature breakdown

Sixteen features carry the product, and only three of them are clearly differentiated: format-free bid analysis, negotiation that shares context with the other steps, and the supplier experience. The rest are needed to compete but do not win deals alone. Each feature below is analysed on the same fifteen points.

**How to read the evidence.** Workflows are reconstructed from Aerchain's product pages, which describe capabilities but rarely give numbered steps. Performance figures on those pages are labelled “For 100 RFQs” with no baseline or method, so I quote them as claims only. Maturity ratings are my judgement. (INFERENCE unless marked.)

### 1. Intake Agent

| Point | Analysis |
| --- | --- |
| Purpose | A single entry point that turns a plain-language need or an uploaded file into a structured, policy-checked purchase request. |
| Target user | Requesters across the business. Buyers benefit from cleaner requests. |
| Customer problem | Vague requests, long forms nobody completes, and no visible status. |
| User workflow | 1. The requester types the need or uploads a specification or past order. 2. The agent extracts item, quantity, specifications, budget and cost centre. 3. It asks only for what is missing and suggests catalogue items or approved suppliers. 4. It checks policy and budget. 5. It suggests approvers and routes the request. 6. The request is classified and assigned to a buyer or to an agent. 7. The requester tracks status. |
| Inputs | Free text, files, past orders. |
| Actions | Create, refine, search, submit, track. |
| Outputs | A complete request with category, approval path and owner, synced to the ERP. |
| Dependencies | Master data such as items and cost centres, approval rules, policy rules, ERP sync, Knowledge Hub. |
| Frequency | Daily for the company; a few times a month for each requester. |
| User value | Ask once, in normal words, and see where the request stands. |
| Business value | Complete data at the start, fewer purchases outside the process, and a measurable baseline for everything after. |
| Differentiation | Table stakes in 2026. Zip, Coupa (through Tonkean), SAP and Zycus all offer conversational intake. Aerchain's edge is that the request flows straight into its own sourcing agents on the same data. |
| UX considerations | Chat is slower than one click for repeat purchases, so catalogue shortcuts matter. The pages describe chat and upload only; a 2024 founder post promised email, Slack, Teams and WhatsApp, and it is unclear which are live. |
| Technical complexity | Classifying into thousands of categories, policies that differ by entity, asking useful questions without annoying people, and working in 30+ languages. |
| Potential metrics | Share of requests complete on first submission; share of all requests raised through intake instead of email; time from request to sourcing start; clarification loops per request; reclassification rate. |
| Feature maturity | Mature. |

Company claims: “10X efficiency boost” in request creation and “3x faster approval cycles”.

### 2. Sourcing Agent (RFQ creation and supplier recommendation)

| Point | Analysis |
| --- | --- |
| Purpose | Turns an approved request into a live sourcing event: scope, request for quotes, evaluation criteria, supplier list and invitations. |
| Target user | Buyers and category managers. |
| Customer problem | Rebuilding the same request for quotes every time, and sending it to the same few suppliers. |
| User workflow | 1. The buyer opens one or more approved requests. 2. The agent drafts the scope and RFQ from templates and past events. 3. It generates evaluation criteria. 4. It recommends suppliers on performance, price and compliance, including alternatives. 5. The buyer reviews and edits. 6. The agent sends the RFQ by email with a no-login link and syncs the event to the ERP. 7. It tracks responses and reminds suppliers. |
| Inputs | Approved request, category template, supplier master data, history from the Knowledge Hub. |
| Actions | Generate, edit, select suppliers, send, monitor. |
| Outputs | A floated RFQ, an invited supplier list, a cost breakdown structure and a response tracker. |
| Dependencies | Intake data quality, supplier master data, Knowledge Hub, supplier communication channels. |
| Frequency | Daily for buyers. |
| User value | An RFQ in minutes instead of hours, with suppliers the buyer might not have thought of. |
| Business value | More events run per buyer and more suppliers per event, which is the main driver of price savings. |
| Differentiation | Differentiated on speed to a floated RFQ and on email-first supplier handling. RFQ automation itself is becoming common: Coupa, Fairmarkit, Keelvar and Zip (September 2026) all offer it. |
| UX considerations | Buyers must be able to see why a supplier was recommended. Over-inviting irrelevant suppliers damages supplier goodwill. |
| Technical complexity | Supplier matching needs clean supplier records. Finding genuinely new suppliers needs outside data; IndiaMART, an investor, is a possible source (HYPOTHESIS). |
| Potential metrics | Time from approved request to RFQ sent; suppliers invited and responding per event; share of events sent without buyer edits; share of awards going to newly recommended suppliers. |
| Feature maturity | Advanced. |

Company claims: “5x faster sourcing kickoff” and “40% more accurate supplier matches”. Aerchain's survey of 163 procurement leaders reports RFx drafting falling from two days to ten minutes.

### 3. Bid Analysis Agent

| Point | Analysis |
| --- | --- |
| Purpose | Reads every supplier quote, in whatever format it arrives, into one like-for-like comparison. |
| Target user | Buyers. |
| Customer problem | A full day spent copying quotes from PDFs, spreadsheets and emails into a comparison sheet. |
| User workflow | 1. Suppliers reply by email with an attachment, or through the link. 2. The agent extracts line items, prices, taxes, lead times and terms. 3. It maps them to the RFQ lines. 4. It flags missing fields, inconsistencies and unusual prices. 5. The buyer reviews the flagged items and confirms the comparison. |
| Inputs | Quotes as Word, PDF, PowerPoint, Excel, plain email text or screenshots. |
| Actions | Review, correct, ask a supplier to clarify, accept. |
| Outputs | A single comparison table per event, with exceptions marked. |
| Dependencies | The RFQ structure from the sourcing agent, the Omnichannel Hub, document-reading models. |
| Frequency | Every sourcing event. |
| User value | The most tedious step disappears. |
| Business value | Faster awards, fewer comparison errors, and an auditable record of how bids were compared. |
| Differentiation | Differentiated. Accepting bids in any format removes the main reason suppliers ignore RFQs. |
| UX considerations | The buyer needs to see the source document next to each extracted value, or trust breaks at the first error. |
| Technical complexity | Units, currencies, taxes, partial bids, alternative offers, bundled prices, scanned documents and many languages. |
| Potential metrics | Extraction accuracy against a checked sample; buyer edits per comparison; hours from last bid to finished comparison; share of bids accepted without resubmission. |
| Feature maturity | Advanced. |

### 4. Evaluation Agent

| Point | Analysis |
| --- | --- |
| Purpose | Scores bids on price, technical fit, commercial terms and past supplier performance, and proposes a shortlist. |
| Target user | Buyers, plus technical reviewers from the requesting team. |
| Customer problem | Slow, inconsistent evaluation that depends on who is doing it. |
| User workflow | 1. Criteria and weights come from the sourcing step. 2. The agent builds a scorecard for each supplier. 3. It checks prices against history and benchmarks and flags non-compliant bids. 4. It assigns technical sections to stakeholders. 5. Reviewers adjust scores where needed. 6. The agent recommends the top suppliers. |
| Inputs | The bid comparison, criteria and weights, supplier performance history. |
| Actions | Review, adjust, assign, approve. |
| Outputs | Supplier scorecards, a ranked shortlist, risk and price alerts. |
| Dependencies | Bid analysis output, Knowledge Hub benchmarks, supplier ratings from onboarding. |
| Frequency | Every sourcing event. |
| User value | A defensible recommendation with the reasoning attached. |
| Business value | Consistent decisions, faster awards and an audit trail for why a supplier won. |
| Differentiation | Between table stakes and differentiated. Scoring is common. Tying it to live supplier performance is useful but not unique. |
| UX considerations | Scores must be explainable. The page's claim of “unbiased” selection overstates what a model can guarantee. |
| Technical complexity | Technical evaluation needs domain judgement. Weightings differ by category and customer. |
| Potential metrics | Time from last bid to shortlist; share of recommendations accepted unchanged; reviewer override rate; later performance of recommended suppliers. |
| Feature maturity | Mature. |

Company claim: evaluation time cut by 80% to 90%.

### 5. Negotiation Agent

| Point | Analysis |
| --- | --- |
| Purpose | Negotiates price and terms with several suppliers at once, in writing, inside limits the buyer sets. |
| Target user | The buyer sets the strategy. The supplier is on the other side of the conversation. |
| Customer problem | Buyers have no time to negotiate small and medium purchases, so first quotes are accepted. |
| User workflow | 1. The buyer chooses a playbook and sets priorities, such as price, payment terms or delivery, and the walk-away limits. 2. The agent sets a target from past prices, internal benchmarks and market data. 3. It sends counter-offers by email or chat to several suppliers in parallel. 4. It reads free-text replies and adjusts across rounds. 5. It reaches a best and final offer or stops at the limit. 6. It updates the quotes and sends the result for approval where rules require. |
| Inputs | Bids, playbook, limits, price history and benchmarks. |
| Actions | Configure, monitor, intervene, approve. |
| Outputs | Revised quotes, a log of every round, and a recommended outcome. |
| Dependencies | Bid analysis and evaluation, Knowledge Hub benchmarks, autonomy settings, supplier email and chat channels. |
| Frequency | Per event; continuous for tail spend once released to the agent. |
| User value | Negotiation happens on purchases that never got it before. |
| Business value | Direct price savings, and savings on the long tail where human negotiation is uneconomic. |
| Differentiation | Differentiated but not unique. Pactum serves Walmart and Maersk. Zycus says about half of Tata Play's purchase orders run through its negotiation agent. Zip added tail-spend negotiation in 2026. Aerchain's edge is that negotiation sees what intake and evaluation already learned. |
| UX considerations | Buyers need a clear view of what the agent may concede. Suppliers may react badly to an undisclosed bot. |
| Technical complexity | Not revealing the walk-away price, resisting instructions hidden in supplier emails, knowing when to stop, and handling many languages. |
| Potential metrics | Savings against first quote and against last purchase price; share of events negotiated end to end; walk-away breaches, with a target of zero; human override rate; rounds to close; supplier satisfaction. |
| Feature maturity | Advanced. |

Company claims: 65% of RFQs negotiated automatically from start to finish at AB InBev, and “3x faster deal closures”.

### 6. Reverse auctions

| Point | Analysis |
| --- | --- |
| Purpose | Runs online events where suppliers bid prices down against each other. |
| Target user | Buyers running competitive, well-specified purchases. |
| Customer problem | One-round quotes leave money on the table when several suppliers can supply the same item. |
| User workflow | 1. The buyer chooses the auction format and rules. 2. Suppliers are invited. 3. Suppliers bid live and see their rank or the leading price. 4. The event closes and results feed the award step. |
| Inputs | Item specification, starting price, rules, qualified suppliers. |
| Actions | Configure, invite, monitor, extend, close. |
| Outputs | Final ranked bids and savings against the starting price. |
| Dependencies | Supplier onboarding, clear specifications, supplier communication. |
| Frequency | Weekly to monthly, depending on category. |
| User value | The best price in an hour, with proof. |
| Business value | Hard, measurable savings. Manjushree's head of purchase cites 4.5% cash savings and 87% supplier participation in an auction. |
| Differentiation | Table stakes. Every suite has auctions. This was Aerchain's original product in 2018 to 2019. |
| UX considerations | Supplier participation decides the result, so joining must be effortless. |
| Technical complexity | Real-time bidding, fairness rules and reliability during a live event. |
| Potential metrics | Suppliers participating per auction; savings against starting price; share of eligible events run as auctions. |
| Feature maturity | Mature. |

### 7. Award Agent and purchase order write-back

| Point | Analysis |
| --- | --- |
| Purpose | Recommends who should win, collects approval, and writes the purchase order into the customer's ERP. |
| Target user | Buyers and approvers. Finance relies on the result. |
| Customer problem | After the decision, someone still has to re-enter everything into the finance system. |
| User workflow | 1. The agent recommends an award, to one supplier or split across several. 2. The approval path is set by category, value or risk. 3. Approvers approve, often in one click. 4. The purchase order and audit trail are pushed to the ERP. |
| Inputs | Evaluation and negotiation results, approval rules, ERP master data. |
| Actions | Review, approve, reject, split, release. |
| Outputs | An approved award, a purchase order in the ERP, and a full audit record. |
| Dependencies | Integrations Hub, approval matrices, correct ERP codes for supplier, item, tax and entity. |
| Frequency | Every completed event. |
| User value | No double entry. |
| Business value | Faster orders, fewer keying errors, and proof for auditors of who approved what. |
| Differentiation | Table stakes as a function. Strategically it is the feature that makes Aerchain hard to remove. |
| UX considerations | Failed ERP syncs must be visible and fixable by a non-technical user. |
| Technical complexity | Every customer's ERP is configured differently. Multi-entity tax and coding rules multiply the cases. |
| Potential metrics | Share of orders pushed automatically; ERP sync failure rate; time from request to order; share of awards changed at approval. |
| Feature maturity | Mature. |

### 8. Vendor Onboarding Agent

| Point | Analysis |
| --- | --- |
| Purpose | Registers a new supplier, collects and checks documents, and keeps supplier ratings current. |
| Target user | Procurement operations and suppliers. Finance and compliance review. |
| Customer problem | New suppliers wait weeks for paperwork before they can be used or paid. |
| User workflow | 1. The supplier is invited and enters details or uploads documents. 2. The agent extracts details and maps them to fields. 3. It checks legitimacy, compliance records and financial credibility, and flags fraud or blacklisting risk. 4. Approvals are routed. 5. The supplier is activated and synced to the ERP. 6. Ratings update from later performance. |
| Inputs | Supplier forms and documents, public and third-party information. |
| Actions | Invite, review, approve, reject, monitor. |
| Outputs | An approved supplier record and a risk and performance rating. |
| Dependencies | ERP supplier master data, verification data sources, approval rules. |
| Frequency | Weekly, and whenever a new supplier wins. |
| User value | Suppliers become usable quickly; staff stop chasing documents. |
| Business value | Lower supplier risk and no delay between award and first order. |
| Differentiation | Table stakes. The depth of risk data feeds is not disclosed, which reviewers note as a gap. |
| UX considerations | The supplier's effort must be minimal, and requirements differ by country. |
| Technical complexity | Tax and registration checks vary by country. Duplicate supplier records are hard to detect. |
| Potential metrics | Days from invitation to active supplier; share of registrations complete first time; duplicates caught; share of suppliers with expired documents. |
| Feature maturity | Mature. |

Company claim: “5x faster vendor activation”. Aerchain's survey reports onboarding 50% to 70% faster with AI.

### 9. Invoice Agent

| Point | Analysis |
| --- | --- |
| Purpose | Reads invoices, checks them, matches them to the order and the goods receipt, and routes exceptions. |
| Target user | Accounts-payable staff. Suppliers see status. |
| Customer problem | Manual matching, duplicate payments and constant supplier calls about payment status. |
| User workflow | 1. The invoice arrives by supplier portal, email or upload. 2. The agent reads it, including scans and handwriting. 3. It checks for duplicates, fraud signals and future dates. 4. It maps the invoice to its purchase order and runs the three-way match. 5. Mismatches go to an exception queue with a suggested fix. 6. The invoice is approved through configurable steps. 7. Status is visible to finance and the supplier. |
| Inputs | Invoices in any format, purchase orders, goods receipts. |
| Actions | Review exceptions, resolve disputes, approve. |
| Outputs | An approved, matched invoice ready for payment in the ERP, plus status and dispute records. |
| Dependencies | Purchase orders and receipts from the ERP, approval rules, supplier records. |
| Frequency | Daily and high-volume. |
| User value | Staff only handle real exceptions. |
| Business value | Lower processing cost, fewer wrong payments, faster payment and happier suppliers. AB InBev reported supplier satisfaction up 52%. |
| Differentiation | Table stakes against invoice specialists such as Stampli and Coupa (which bought Rossum). The value here is one data model shared with the purchase order. |
| UX considerations | The exception queue is where staff live, so it must be fast. The page does not describe making the payment itself, only approval. |
| Technical complexity | Invoice formats, tax rules by country, partial deliveries, price and quantity tolerances, and legally compliant e-invoices. |
| Potential metrics | Touchless rate, meaning invoices with no human step; first-pass match rate; exception rate by type; time to clear; duplicates prevented. |
| Feature maturity | Mature. It dates from the AB InBev work in 2020. |

Company claims: “5x faster processing”, “80% faster issue resolution”, and invoices cleared in 30 minutes.

### 10. Aiera copilot

| Point | Analysis |
| --- | --- |
| Purpose | A chat assistant across all agents and data. It answers questions with sources and starts or completes tasks. |
| Target user | Everyone, especially executives, approvers and buyers. |
| Customer problem | Finding information means opening several screens or asking an analyst. |
| User workflow | 1. The user asks a question or gives an instruction, such as “what did we pay for laptops last quarter?”. 2. Aiera retrieves the relevant records. 3. It answers and shows the purchase orders it used. 4. For tasks, it creates the request, fills gaps, or lists pending approvals for one-click action. |
| Inputs | Natural-language questions and instructions. |
| Actions | Ask, create, approve, track. |
| Outputs | Sourced answers, drafted requests, approval actions. |
| Dependencies | All agents, Knowledge Hub, analytics data, user permissions. |
| Frequency | Daily for buyers; weekly for executives. |
| User value | One place to ask, with no training needed. |
| Business value | Higher adoption among occasional users and faster decisions. |
| Differentiation | Table stakes. SAP has Joule, Coupa has Navi, Zycus has Merlin Assist inside Microsoft Teams, and Zip exposes its data to assistants such as Claude and ChatGPT. |
| UX considerations | It is most useful where people already work. An assistant that lives only inside Aerchain's own screen competes with email and Teams. |
| Technical complexity | Answers must respect each user's access rights and each entity's data separation, and must never invent a figure. |
| Potential metrics | Weekly active users by role; share of answers with a correct source record; tasks completed through chat; time to answer a spend question. |
| Feature maturity | Mature. The name appears as both “Aera” and “Aiera”. |

### 11. Knowledge Hub

| Point | Analysis |
| --- | --- |
| Purpose | The company's procurement memory: specifications, price benchmarks and contract clauses drawn from contracts, emails and ERP data. |
| Target user | Used directly by buyers and indirectly by every agent. |
| Customer problem | Each sourcing event starts from scratch because past knowledge sits in inboxes and old files. |
| User workflow | 1. Past contracts, quotes and transactions are ingested and organised. 2. The customer sets what to learn by category, supplier, terms or metric. 3. Agents draw on it for RFQ drafts, price targets and supplier choices. 4. It raises signals such as price anomalies or supplier performance dips. |
| Inputs | Contracts, emails, ERP extracts, quotes, transaction history. |
| Actions | Browse, search, set learning parameters, review signals. |
| Outputs | Reusable specifications, benchmarks, clause libraries and alerts. |
| Dependencies | Data ingestion from the Integrations and Omnichannel hubs. |
| Frequency | Continuous in the background. |
| User value | Every event starts from what the company already knows. |
| Business value | Better targets and faster drafting. It is also the main reason the product should get better the longer a customer uses it. |
| Differentiation | Differentiated in concept. AI-native rivals have similar layers, such as Levelpath's reasoning engine. |
| UX considerations | Users need to see where a benchmark came from and how old it is. |
| Technical complexity | Recognising that differently described items are the same thing, keeping benchmarks current, and keeping entities' data separate. |
| Potential metrics | Share of events that use a benchmark; benchmark coverage by category; gap between target price and final price. |
| Feature maturity | Advanced in concept; depth not verifiable publicly. |

### 12. Analytics

| Point | Analysis |
| --- | --- |
| Purpose | Shows spending, savings, supplier risk and off-contract buying in one place, as it happens. |
| Target user | CPO, CFO, finance controllers and category managers. |
| Customer problem | Finance waits for a month-end extract, and procurement cannot prove its savings. |
| User workflow | 1. Data flows in from every agent and the ERP. 2. The user opens a dashboard or builds one. 3. They see committed, projected and realised spend together. 4. They drill into savings against a baseline, supplier risk scores and flagged off-contract purchases. 5. Reports can be scheduled or triggered. |
| Inputs | Transaction data from all modules and the ERP; baselines. |
| Actions | View, filter, build dashboards, schedule reports. |
| Outputs | Dashboards, scheduled reports, alerts. |
| Dependencies | Clean, classified spend data; baseline definitions; ERP sync. |
| Frequency | Weekly for leaders; monthly for finance close. |
| User value | An answer without an analyst ticket. |
| Business value | Proof of value for renewal, and earlier warning on overspend and supplier risk. |
| Differentiation | Table stakes, and probably behind. The main site marks the Analytics Agent “coming soon”, and the one visible Gartner review says there is “room to grow on the analytics side”. Specialists such as Sievo guarantee classification accuracy in contracts. |
| UX considerations | Executives want three numbers, not thirty charts. |
| Technical complexity | Classifying messy spend data correctly, and agreeing what counts as a saving. |
| Potential metrics | Weekly active finance and procurement leaders; share of spend classified; share of reported savings accepted by finance; time to produce a board report. |
| Feature maturity | Basic to Mature. |

### 13. Autonomy settings and policy guardrails

| Point | Analysis |
| --- | --- |
| Purpose | Lets the customer decide how much each agent may do alone, for each category of spending, and enforces policy on every step. |
| Target user | CPO and procurement operations as owners; buyers as supervisors. |
| Customer problem | Fear that an AI will commit company money wrongly, with nobody accountable. |
| User workflow | 1. The customer sets a level per agent and category: agents advise, agents assist, or agents execute. 2. Rollout runs in waves: a person approves everything, then chosen categories are released, then the full suite. 3. Negotiations run inside walk-away terms. 4. A compliance policy agent checks each step. 5. Every action and round is logged. |
| Inputs | Category list, risk appetite, approval rules, walk-away terms, policies. |
| Actions | Set levels, release categories, review logs, pull a category back. |
| Outputs | An autonomy map, an audit trail, policy exceptions. |
| Dependencies | Approval matrices, role-based access, logging, every agent. |
| Frequency | Set at rollout and adjusted quarterly. |
| User value | Control and a clear record if something goes wrong. |
| Business value | Makes adoption possible for cautious enterprises, and creates a built-in expansion path as more categories are released. |
| Differentiation | Differentiated in how explicitly it is packaged. Rivals also keep people in the loop, but Aerchain makes the ladder the centre of its pitch. |
| UX considerations | There is no public description of what evidence tells a customer a category is ready to move up. Without that, promotion is a judgement call and may never happen. |
| Technical complexity | Consistent enforcement across agents, and logs detailed enough to reconstruct any decision. |
| Potential metrics | Share of categories and of spend at each level; agreement rate between agent recommendations and buyer decisions; time for a category to move up; policy breaches. |
| Feature maturity | Advanced as a concept; the promotion mechanism is unproven publicly. |

### 14. Supplier experience (Magic Links, email replies, portal, mobile app)

| Point | Analysis |
| --- | --- |
| Purpose | Lets suppliers respond with almost no effort, through whichever channel they already use. |
| Target user | Suppliers, many of them small businesses. |
| Customer problem | Suppliers ignore RFQs that require registering on yet another portal. |
| User workflow | 1. The supplier receives an email. 2. A Magic Link opens the bid page directly, with no login. 3. Or the supplier simply replies with a spreadsheet or document, and the agent reads it. 4. Complex multi-stage evaluations use a portal. 5. A mobile app covers bidding and invoice status on a phone. |
| Inputs | The supplier's quote in any format. |
| Actions | View, bid, revise, upload invoice, check payment status. |
| Outputs | A structured bid inside the buyer's event. |
| Dependencies | Bid analysis, Omnichannel Hub, social login through Google or Microsoft for supplier accounts. |
| Frequency | Per event for each supplier. |
| User value | Minutes to respond, no new password. Aerchain says “most never log in”. |
| Business value | More bids per event. AB InBev reached 87.5% supplier participation with the mobile app. |
| Differentiation | Differentiated, and well suited to email-first supplier bases in India, Africa and the Gulf. |
| UX considerations | A link that opens a bid page without login must still prove who is bidding. |
| Technical complexity | Security of no-login access, and accurate reading of free-form replies. |
| Potential metrics | Supplier response rate; time to first response; share of bids by channel; supplier satisfaction. |
| Feature maturity | Advanced. |

### 15. Integrations Hub

| Point | Analysis |
| --- | --- |
| Purpose | Connects Aerchain to the customer's ERP and finance systems in both directions. |
| Target user | The customer's IT and ERP team, and Aerchain's implementation team. |
| Customer problem | A procurement tool that does not sync with the ERP creates double entry and mistrust. |
| User workflow | 1. Choose a pre-built connector. 2. Map fields using a predefined dictionary, or design the data payload field by field without code. 3. Simulate and test. 4. Go live with two-way sync of requisitions, orders, goods receipts and invoices. 5. Monitor through audit logs. |
| Inputs | ERP credentials, field mappings, master data. |
| Actions | Configure, map, test, monitor. |
| Outputs | Live two-way data flows and an integration audit trail. |
| Dependencies | The customer's ERP configuration and IT cooperation. |
| Frequency | Set up once; monitored continuously. |
| User value | No re-keying; finance sees the truth in the system it trusts. |
| Business value | Makes the 16-week go-live possible and lets Aerchain sit on top of a rival suite, as with Jaggaer at the Dubai Government. |
| Differentiation | Table stakes in function. Zycus advertises 1,121 interfaces, and SAP's agents work on live SAP records with no integration at all. |
| UX considerations | Field mapping is where projects stall, so defaults and error messages matter. |
| Technical complexity | Every ERP is customised. Sync failures must be handled without losing or duplicating a transaction. |
| Potential metrics | Days to first successful sync; sync failure rate; share of deployments using standard connectors without custom work. |
| Feature maturity | Mature. Named connectors: SAP, Oracle, NetSuite, Dynamics, Coupa, Ariba and Workday. |

### 16. DIY Framework (no-code configuration)

| Point | Analysis |
| --- | --- |
| Purpose | Lets the customer's own team build sourcing templates, change workflows and approval chains, and create reports without engineers. |
| Target user | Procurement operations and system administrators. |
| Customer problem | Every process change in a legacy suite needs an IT ticket or a consultant. |
| User workflow | 1. Build a template with drag-and-drop fields, tables and questionnaires. 2. Define routing, approval chains and negotiation triggers as rules. 3. Configure dashboards. 4. Reuse the template across categories, regions or teams. |
| Inputs | Process rules and form fields. |
| Actions | Build, edit, publish, reuse. |
| Outputs | Live templates, workflows and reports. |
| Dependencies | Role-based access, approval matrices, analytics. |
| Frequency | Heavy at rollout; monthly afterwards. |
| User value | Changes in hours, by the people who own the process. |
| Business value | Lower running cost for the customer. For Aerchain, it keeps customer-specific requests out of engineering, which protects margin and the 16-week promise. |
| Differentiation | Table stakes. Zip, Levelpath and Coupa all have no-code builders. |
| UX considerations | Powerful builders are easy to misconfigure, so changes need testing and version history. |
| Technical complexity | Flexibility without breaking the standard data model that the agents depend on. |
| Potential metrics | Share of customer changes made without Aerchain's help; support tickets per configuration change; implementation hours per customer. |
| Feature maturity | Mature. |

### What the sixteen features add up to

| Class | Features |
| --- | --- |
| Differentiated | Bid analysis in any format; negotiation that shares context; supplier experience; the autonomy ladder as a packaged idea |
| Table stakes done well | Intake, sourcing, evaluation, auctions, award and write-back, vendor onboarding, invoices, integrations, no-code configuration, copilot |
| Behind or unproven | Analytics; contract management, which is not yet available; the mechanism for promoting a category to autonomy |

**The second-order effect to notice.** The differentiated features all increase how much activity flows through the product. The weak features are the ones that prove value afterwards. A product that creates value it cannot prove will struggle at renewal and expansion, which is exactly where Aerchain's growth has to come from. (INFERENCE.)

## Part 10 — End-to-end user journeys

Aerchain's customer journey is slow and heavy at the front, where a committee buys and a project team installs, and its long-term success is decided in the middle, where ordinary employees and suppliers either change their habits or do not. There is no self-serve route at any stage. (INFERENCE from the sales model and product pages.)

| Journey | User goal | User actions | System or company response | Friction | Stakeholders | Likely drop-off | Product opportunity | Metric |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 1. Discovery | Find a credible way to apply AI to procurement | Hears of Aerchain from a peer, an event, LinkedIn, press or Infosys | Website, research report, outreach by sales | Low brand awareness outside India; absent from the main analyst ranking | CPO, procurement operations lead | Buyer shortlists only analyst-ranked vendors | Publishable benchmarks and research that earn inbound interest | Demo requests; share of pipeline from referrals and partners |
| 2. Evaluation | Decide whether Aerchain deserves a serious look | Reads the site, compares with SAP Ariba, Coupa, Zycus and Zip, asks peers | Sales calls, references | Conflicting public numbers; case studies page still says “soon”; no pricing | CPO, CFO, IT | Buyer cannot verify claims and moves on | Case studies with stated baselines and methods; a working return calculator | Evaluation-to-demo conversion |
| 3. Demo | See it work on a real category | Attends a 30-minute live simulation with CPO and CFO together | Live walkthrough of agents on the customer's category | Getting both executives in one room; gap between demo and the customer's messy data | CPO, CFO, buyers | Demo impresses but feels too good to be true | A sandbox loaded with the customer's own past RFQs | Demo-to-proposal conversion |
| 4. Purchase | Get a contract signed safely | Negotiates price, runs security and architecture reviews, legal review | Certifications, questionnaire answers, scoped proposal | Professional buyers negotiate hard; reviews of 100+ questions; many approvers | Procurement, finance, IT, security, legal | Security or IT blocks; budget freeze | A ready security pack and standard contract terms | Sales cycle length; win rate; review turnaround |
| 5. Implementation | Go live without disrupting finance | Supplies master data, dimensions, routing rules, users and integration access | Four phases over 16 weeks: design, build, test, go-live with close support | Dirty master data; ERP mapping; limited IT time | Procurement operations, IT, Aerchain's team | Project stalls on data or integration | Guided setup with data-quality checks before kickoff | Weeks to go-live against 16; implementation hours |
| 6. Onboarding | Get people and suppliers using it | Training sessions; supplier invitations | Guided flows, Aiera, supplier Magic Links | Habit of email; buyers' fear of being replaced | Buyers, requesters, AP, suppliers | Users log in once and return to email | In-product guidance by role; a first-week checklist | Share of invited users active within 30 days |
| 7. First value | See one real result | A buyer runs the first live event | RFQ drafted and sent in minutes; bids compared automatically | First event exposes data gaps | Buyer, a few suppliers | First event goes badly and trust drops | Start with a category chosen for clean data and willing suppliers | Days from go-live to first completed event |
| 8. Activation | Make it the normal way to buy | Events run across several categories; orders land in the ERP | End-to-end flow with write-back | Uneven adoption between plants or entities | Procurement team, finance | Stays a pilot in one team | Adoption dashboard by entity and category | Events per buyer per week; share of requests through intake |
| 9. Habit formation | Stop thinking about the tool | Requesters default to intake; buyers start the day in the workbench; AP lives in the exception queue | Status updates, pending approvals, alerts | Old channels still work | All users | Parallel email process survives | Email forwarding into intake; notifications where people already work | Weekly active users by role; requests by channel |
| 10. Expansion | Get more value | Adds modules, entities and categories; releases categories to autonomy | Wave 2 and Wave 3 rollout | Needs proof to justify more budget | CPO, CFO | No evidence, so no expansion | A value record per module that finance accepts | Modules per customer; net revenue retention; share of spend run by agents |
| 11. Renewal | Confirm it was worth it | Finance asks for the return; procurement may run a competitive review | Business review, savings report | Savings claimed but not reconciled to the accounts | CFO, CPO | Incumbent suite offers “free” AI | Savings reconciled with finance during the year, not at renewal | Gross revenue retention |
| 12. Churn | Leave with little pain | Stops events; exports data; turns off sync | Offboarding | Loss of history and supplier habits | Procurement, IT | Not applicable | Early-warning signals and executive check-ins | Falling events; falling supplier response; unused modules |

### The aha moment, the activation event and retention predictors

**Aha moment.** A buyer watches a vague request become a sent RFQ within minutes, and then sees supplier replies from PDFs and emails appear as one clean comparison without touching a spreadsheet. That is the moment the product feels different from workflow software. (INFERENCE.)

**Activation event.** The first purchase that goes all the way from a real request to a purchase order written into the customer's ERP, in production, on a real category. Before that point the customer has seen a demo. After it, the product is part of how the company buys. (INFERENCE.)

**Activation threshold (HYPOTHESIS).** A reasonable definition to test with data: within 60 days of go-live, at least 25 events completed end to end, across at least two categories, with at least half of invited requesters having raised a request through intake.

**Behaviours that likely predict long-term retention (INFERENCE).**

- Two-way ERP sync is live for orders and invoices, not only one of them.
- Most requests arrive through intake instead of email.
- At least one category has been released from human approval to agent execution.
- Supplier response rates hold or rise after the first quarter.
- Finance users, not only procurement users, open analytics.
- More than one entity or plant is live.

## Part 11 — User flow analysis

Four flows carry almost all of the product's value. The request-to-order flow is both the most frequent and the most valuable, and the setup flow is the one most likely to fail.

### Flow A: request to purchase order (assisted mode)

```text
Requester describes a need in chat or uploads a file
↓
Intake Agent structures it, asks for missing details, checks policy and budget
↓
Approver approves the request
↓
Request is classified and assigned to a buyer
↓
Sourcing Agent drafts the RFQ and recommends suppliers; buyer reviews and sends
↓
Suppliers reply by email, Magic Link, portal or app
↓
Bid Analysis Agent builds one comparison; buyer checks flagged items
↓
Evaluation Agent scores bids; reviewers adjust
↓
Negotiation Agent runs rounds inside the buyer's limits
↓
Award Agent recommends; approvers approve
↓
Purchase order is written to the ERP; requester is notified
```

| Step | User intent | User action | System response | Friction and mental effort | Failure modes | Opportunity |
| --- | --- | --- | --- | --- | --- | --- |
| Describe the need | Get something without learning the rules | Types or uploads | Extracts details, asks what is missing | Low, if questions are few | Wrong category; too many questions | One-click reorder for repeat items |
| Approve the request | Decide quickly | One click | Routes by rule | Low, if context is shown | Approver ignores it; wrong approver | Reminders and delegation |
| Draft and send RFQ | Start sourcing fast | Reviews draft, edits supplier list | Generates RFQ and criteria, sends | Medium: buyer must trust the draft | Irrelevant suppliers; wrong specification | Show why each supplier was chosen |
| Collect bids | Get enough competition | Waits; nudges | Tracks opens and replies, reminds | Low | Few suppliers reply | Response-rate insight by supplier |
| Compare bids | Understand offers | Checks flagged items | Builds comparison table | Medium: checking extraction | Misread price or unit | Source document beside each value |
| Evaluate | Choose well | Reviews scores, assigns technical review | Scores and flags | Medium to high | Technical reviewer delays | Deadline and escalation for reviewers |
| Negotiate | Improve the deal | Sets limits and priorities | Runs rounds, logs them | High the first few times | Limit set wrongly; supplier disengages | Suggested limits from history |
| Award and approve | Close with accountability | Approves | Recommends, routes | Low | Approval above the wrong threshold | Clear summary of savings and risk |
| Create the order | Avoid re-keying | None | Writes to ERP | None when it works | Sync fails on a code or tax field | Plain-language sync errors with a fix |

### Flow B: autonomous tail-spend purchase (agents execute)

```text
Requester asks for a low-value, standard item
↓
Intake Agent matches a catalogue item or creates a small RFQ
↓
Policy check confirms the category is released to agents and under the value cap
↓
Agent collects quotes, negotiates within limits and selects the supplier
↓
Purchase order is written to the ERP with no buyer involved
↓
A sample of these purchases is reviewed weekly by a buyer
```

This flow is where the product's economics are strongest, because the buyer's time per purchase drops to almost zero. It is also where a mistake repeats quietly at volume, so the sample review and value cap matter. The weekly sample review is my recommendation, not a documented feature. (INFERENCE.)

### Flow C: invoice to approval

```text
Invoice arrives by email, portal or upload
↓
Invoice Agent reads it and checks for duplicates, fraud signals and wrong dates
↓
Three-way match against purchase order and goods receipt
↓
Match within tolerance → routed for approval or approved automatically
Mismatch → exception queue with a suggested fix
↓
Approved invoice is posted to the ERP; supplier sees status
```

### Flow D: deployment (signature to first value)

```text
Contract signed
↓
Discovery and design: categories, entities, approval rules, target metrics
↓
Build and configure: master data, dimensions, routing, users, ERP connector
↓
Test and validate: end-to-end runs with real data
↓
Go-live with close support (Wave 1: a person approves everything)
↓
First live event → first purchase order in the ERP
↓
Wave 2: chosen categories released to agents
```

### The six flows to know

| Question | Answer | Why |
| --- | --- | --- |
| Shortest path from signature to first value | One category, one entity, sourcing agents only, with ERP write-back for orders | Avoids invoice and multi-entity complexity until trust exists |
| Shortest path from first value to recurring value | Turn on intake for that category so every request flows in automatically | Removes dependence on buyers choosing to use the tool |
| Most important recurring workflow | Flow A, request to purchase order | It runs daily and touches every persona |
| Most valuable workflow | Flow A for savings; Flow B for labour saved per purchase | Savings come from competition and negotiation; Flow B scales without people |
| Most complex workflow | Multi-entity sourcing with split awards and ERP write-back to several company codes | Rules, taxes and approvals differ by entity |
| Most failure-prone workflow | Flow D, deployment, followed by ERP sync inside Flow A | Depends on the customer's data quality and IT time, which Aerchain does not control |

## Part 12 — UX and UI analysis

Aerchain's user experience is strongest where it removes screens altogether, for requesters and suppliers, and weakest in the places that explain and prove what the agents did. I have not used the product, so this part is built from product pages, testimonials and the one visible review. Treat every judgement as INFERENCE unless a source is named.

### Information architecture

- **Navigation and hierarchy.** The product is organised by agent, one per step of the process, with Aiera as a single entry point across them. This mirrors how procurement people think about their work, which helps learning.
- **Search and discoverability.** Intake includes “AI-powered contextual search”, and Aiera answers questions across records. Asking is the main way to find things.
- **Organisation.** Each request has an owner, a stage and an audit trail, according to Aerchain's FMCG write-up. Invoices use “smart workbench filters” so staff see only relevant items.
- **Information density.** Not publicly visible. Bid comparison and evaluation screens are dense by nature, so this is where design quality matters most.
- **A warning sign.** Names differ between the two websites: Aera and Aiera; a “Purchase Agent” and “Onboarding Agent” in one place, an “Award Agent” and “Vendor Onboarding Agent” in another. If the same drift exists inside the product, users will struggle to build a clear mental model. (HYPOTHESIS.)

### Interaction design

- **Clicks and forms.** Chat or upload replaces long forms at intake. Approvals are described as one click.
- **Defaults.** Version 5 ships with predefined fields, workflows and approvals. Good defaults are the main reason a 16-week rollout is possible.
- **Bulk actions and automation.** Negotiation runs with several suppliers at once. Buyer allocation is automatic. Bulk approval and bulk editing are not described.
- **Error handling and recovery.** The agents flag missing fields, inconsistencies and unusual prices. How a user corrects a wrong extraction, undoes an agent action, or recovers from a failed ERP sync is not publicly documented.
- **Confirmations.** Evaluation and negotiation both route to manual approval “when needed”, so confirmation points are configurable.

### Usability

- **Learning curve.** The visible Gartner reviewer wrote that “onboarding took some adjustment, but day-to-day usage has been straightforward for most of the team”. Gartner's page notes its displayed text may be placeholder wording, so weigh this lightly.
- **Adoption evidence.** Cars24's supply chain director cites 99% adoption. That is a company-selected testimonial, but adoption is the theme customers chose to highlight.
- **Consistency.** Not verifiable. The marketing sites contain placeholder tabs, a misspelt statistic label and a statistic labelled for RFQs on the invoice page, which suggests attention to detail is stretched.
- **Accessibility.** Information not publicly available. There is no public statement on accessibility standards such as WCAG. Government and large global buyers increasingly ask for one.
- **Languages.** Works in 30+ languages, which matters for plants and suppliers outside head office.

### Enterprise UX

| Capability | What is known | Label |
| --- | --- | --- |
| Permissions and roles | Role-based access; field-level permissions on integration payloads | FACT |
| Approval workflows | Multi-level approval matrices by category, value or risk; no-code editing | FACT |
| Audit logs | “Full audit logs”; every negotiation round logged; integration actions logged | FACT that it is claimed; export depth not documented |
| Admin controls | DIY Framework for templates, routing and reports | FACT |
| Configuration | Predefined in Version 5; five inputs at deployment | FACT |
| Governance | Autonomy level per agent and category; wave-based release | FACT |
| Data separation | An FMCG deployment ran “10 regulated entities with strict data separation” | FACT |

### Top 10 UX strengths

1. **Plain-language intake.** Requesters do not need to know categories or policies.
2. **No-login supplier response.** The largest source of friction in sourcing is removed for the people least motivated to learn a tool.
3. **Format-free bids.** Suppliers send what they already have; buyers receive one table.
4. **One place to ask.** Aiera answers with the records it used, which builds trust in the answer.
5. **Visible status.** Every request has an owner and a stage, which stops chasing by email.
6. **One-click approvals with a pending list.** Approvers are occasional users and need exactly this.
7. **Adjustable human control.** Reviewers can override scores, and negotiation can route for approval.
8. **Role-filtered workbenches.** Staff see their own queue, not the whole system.
9. **No-code changes.** Process owners can adapt templates and routes themselves.
10. **Multilingual operation.** Useful for multi-country groups and local suppliers.

### Top 10 UX weaknesses

| # | Weakness | Evidence | Likely user and business impact |
| --- | --- | --- | --- |
| 1 | Onboarding takes adjustment | Visible Gartner review | Slower first value; early users form a poor first impression |
| 2 | Analytics is thin | Review; “coming soon” label | Executives cannot see proof, which weakens renewal and expansion |
| 3 | No documented path for promoting a category to autonomy | Nothing public on evidence or thresholds | Customers stay in human-approval mode, so labour savings never arrive |
| 4 | Explainability of agent output is unclear | Not described | Buyers recheck everything by hand, which removes the time saving |
| 5 | Inconsistent names for agents and the assistant | Two websites disagree | Confusion in training and support |
| 6 | Chat-first intake for repeat buys | Product design | Frequent requesters find it slower than a saved order |
| 7 | Unclear presence in email, Teams, Slack or WhatsApp | Promised in 2024; not on current pages | Users must go to a separate tool, so email habits persist |
| 8 | Recovery from errors is undocumented | No public help centre | Support tickets and loss of trust after the first failed sync or wrong extraction |
| 9 | No public accessibility statement | Not found | Risk in government and global enterprise deals |
| 10 | Governance is configured by the buyer, not ready-made | Independent reviewer summary on RFP.wiki | More setup effort and more ways to misconfigure |

## Part 13 — Onboarding and activation

Onboarding is a project run by people, not a product flow, and the calendar from signature to a first real purchase is roughly four to five months. The biggest risks sit in the customer's own data and habits, which is why the best improvements start before kickoff. (INFERENCE.)

### How onboarding works today

| Stage | What happens | Label |
| --- | --- | --- |
| Signup | None. There is no self-serve signup. | FACT |
| Trial | None. The demo is the trial. | FACT |
| Demo | A 30-minute live simulation on the customer's category, with CPO and CFO invited together. | FACT |
| Setup | Five inputs: masters, dimensions, orchestrator, users and integrations. My reading: master data such as supplier and item lists; the ways spend is split, such as entity, cost centre and category; approval routing rules; user accounts; system connections. | FACT for the list; INFERENCE for the meanings |
| Data import | Supplier, item and history data loaded from the ERP and files. | INFERENCE |
| Integrations | Pre-built ERP connector with a predefined field dictionary; two-way sync. | FACT |
| Invitations | Internal users through single sign-on; suppliers by email with Magic Links. | FACT for the mechanisms |
| Configuration and templates | Version 5 ships predefined fields, workflows and approvals. | FACT |
| Guided setup and education | No public help centre, academy or documentation found. | FACT that none is public |
| Training | Delivered by Aerchain's team during go-live and “hypercare”, a period of close support after launch. | FACT for hypercare; INFERENCE for training |
| Rollout | Wave 1: a person approves everything. Wave 2: chosen categories released. Wave 3: full suite. | FACT |

### Time-to-value

- **Time to go-live.** 16 weeks, which Aerchain says is “measured from live deployments”. It compares this with 14 months for source-to-pay suites and 9 months for intake platforms. These comparison figures are Aerchain's own.
- **Time to first value.** Go-live plus the first completed event. If the first event runs in the first two weeks, that is about 18 weeks from kickoff. (INFERENCE.)
- **Time to proven value.** A finance-accepted savings number needs a quarter or two of events. So proof arrives roughly 9 to 12 months after signature, which is close to the first renewal conversation. (INFERENCE.) This timing is the core tension in the business.
- **A faster precedent.** For AB InBev in 2020, a supplier platform was built within two months of selection.

### Activation and where customers drop off

- **Activation event.** First purchase from real request to purchase order in the ERP, in production.
- **Activation threshold (HYPOTHESIS).** 25 completed events across two categories within 60 days of go-live, with half of invited requesters using intake.

| Drop-off point | Why it happens | Signal to watch |
| --- | --- | --- |
| Before kickoff | Master data is too messy to load | Data-readiness score |
| During build | ERP team has no time; mapping disputes | Days waiting on customer IT |
| At go-live | Only the project team logs in | Share of invited users active |
| First month | Suppliers do not respond to the new channel | Supplier response rate against the old baseline |
| Months two to three | Requesters keep emailing buyers | Share of requests through intake |
| Months three to six | Stuck in Wave 1 with a person approving everything | Categories released to agents |

### Recommended improvements, ranked

Ranking uses three judgements: impact on time-to-value and adoption, effort to build, and my confidence that it would work. All are my estimates.

| Rank | Improvement | Impact | Effort | Confidence | Reasoning |
| --- | --- | --- | --- | --- | --- |
| 1 | Data-readiness check before kickoff: an automated report on duplicates, missing fields and inactive suppliers | High | Low to medium | High | Bad master data is a common cause of stalled enterprise rollouts, and it is detectable in advance |
| 2 | Adoption dashboard for the customer's champion, by entity, category and channel | High | Low to medium | High | The champion cannot fix what they cannot see, and the same data serves Aerchain's own account reviews |
| 3 | Single-category fast start: one entity, one category, sourcing only, live in 6 to 8 weeks | High | Medium | Medium | Brings first value forward by two months and builds trust before complexity |
| 4 | Requests by forwarded email, plus presence in Teams or WhatsApp | High | Medium | Medium | Lets the old habit feed the new system instead of competing with it |
| 5 | Autonomy readiness report at day 60, showing how often buyers accepted the agent's recommendation by category | High | Medium | Medium | Gives the evidence needed to start Wave 2 |
| 6 | Role-based first-week checklists and in-product guidance | Medium | Low | High | Cheap, and addresses the “onboarding took some adjustment” feedback |
| 7 | Proof-of-value sandbox using the customer's own past RFQs, before signing | High | Medium | Medium | Shortens the sale and sets a baseline for later savings claims |
| 8 | Public help centre with short walkthrough videos | Medium | Low | High | Reduces support load and helps evaluation-stage buyers |
| 9 | Supplier launch kit: announcement emails and a short guide in local languages | Medium | Low | Medium | Supplier response in month one decides whether buyers keep using it |
| 10 | Integration test harness with plain-language error messages | Medium | Medium | Medium | Reduces days lost during build and after go-live |

## Part 14 — Retention

Customers stay because Aerchain becomes the place where purchase orders are created and where suppliers respond, not because of any single feature. Retention strength therefore depends on how deeply a customer has deployed it. Aerchain publishes no retention figures, so everything here is INFERENCE from how the product works.

### What holds customers

| Retention force | How it works for Aerchain | Strength |
| --- | --- | --- |
| Workflow dependency | Orders, approvals and audit records are created inside it and written to the ERP | Strong once write-back is live |
| Integrations | Two-way ERP sync took weeks to build and finance relies on it | Strong |
| Data accumulation | Price history, specifications, clauses and supplier performance build up in the Knowledge Hub | Moderate, growing with time |
| Habit formation | Buyers start their day in it; requesters ask through it | Moderate; weak if email still works |
| Supplier habits | Suppliers learn that this customer's requests arrive in a certain way and get paid through it | Moderate |
| Institutional knowledge | Approval matrices, templates and playbooks for every entity are encoded in it | Moderate to strong |
| Compliance | Auditors are shown its trail as evidence of control | Moderate |
| Automation | Categories running without people would need staff again if it were removed | Strong where autonomy is real; absent where it is not |
| Reporting | Leadership reports come from it | Weak today, because analytics is thin |
| Collaboration | Requesters, buyers, approvers, finance and suppliers all meet in it | Moderate |
| Contractual | Annual or multi-year subscriptions | Moderate |
| Network or ecosystem effects | Little evidence | Weak |

### Retention loops

**Loop 1: knowledge.**

```text
More completed purchases
↓
More price, specification and supplier history in the Knowledge Hub
↓
Better price targets and supplier recommendations
↓
Better outcomes per event
↓
Buyers run more purchases through the platform
```

**Loop 2: trust and autonomy.**

```text
Agent recommendations match what buyers would have decided
↓
Buyers accept them without edits
↓
The customer releases the category to agent execution
↓
Buyer time is freed and cycle time falls
↓
The customer releases more categories
```

This is the loop that makes the product cheaper to run the longer it is used. It is also the one most likely to stall, because nothing public shows how a customer knows a category is ready.

**Loop 3: supplier participation.**

```text
Responding is easy for suppliers
↓
More suppliers bid on each event
↓
Prices improve and buyers see the benefit
↓
Buyers run more events through the platform
↓
Suppliers see more opportunities and keep responding
```

**Loop 4: system of record.**

```text
Orders are written to the ERP from Aerchain
↓
Finance treats Aerchain as the source of committed spend
↓
More entities and categories are required to use it
↓
More orders are written from Aerchain
```

**Loop 5: requester habit.**

```text
A request gets a fast answer and visible status
↓
The requester uses intake again instead of email
↓
Request data is cleaner and more complete
↓
Requests are handled faster
```

**Loop 6: proof and budget (the weak loop).**

```text
Savings and time saved are recorded in a form finance accepts
↓
The CFO trusts the return
↓
Budget is approved for more modules and entities
↓
More savings are recorded
```

Loops 1 to 5 create value. Loop 6 converts value into revenue for Aerchain. Because analytics is the least mature area, the loop that matters most commercially is the least supported by the product.

## Part 15 — Virality and network effects

Aerchain grows through a sales team and, increasingly, partners. It has almost no viral growth and only weak network effects today, though it holds two assets that could become network effects with deliberate product work.

| Mechanism | Present? | Assessment |
| --- | --- | --- |
| Invitations | Yes, but one-sided | Buyers invite suppliers to every event. Aerchain claims 150,000 active suppliers. Those suppliers are users, not prospects, so this spreads usage, not sales. |
| Collaboration | Inside one customer | Requesters, approvers, buyers and finance work together, which spreads the product across departments and entities after the sale. |
| Sharing | No | Nothing is designed to be shared outside the customer. |
| External users | Yes | Suppliers. A supplier who likes the experience may mention it to another customer, but there is no evidence this drives sales. |
| Referrals | Informal | Procurement heads talk to peers and move between companies. For a company with few public reviews, this is probably the main source of trust. (INFERENCE.) |
| Direct network effects | No | One customer does not get more value because another customer joins. |
| Cross-side network effects | Latent | A supplier already verified for one customer could be instantly usable by another. Nothing public shows supplier profiles are shared across customers. (HYPOTHESIS.) |
| Data network effects | Weak | Press coverage describes agents “trained on each customer's data”. That means learning stays inside each customer. Coupa, by contrast, markets a community data set of over $10 trillion in spend. |
| Marketplace effects | No | Aerchain is not a marketplace. IndiaMART, an investor, is one, which is a possible partnership for supplier discovery. (HYPOTHESIS.) |
| Partner effects | Emerging | Infosys BPM could deploy Aerchain across outsourcing clients. Each deployment through a partner costs Aerchain less sales effort. |
| Ecosystem effects | Small | ERP connectors exist, but there is no developer community or app marketplace. |

### Which growth model is it?

**Sales-led, becoming sales-led plus partner-led.** The reasons:

- **The buyer is a committee.** CPO, CFO and IT must all agree, and security reviews run to hundreds of questions. A product cannot sell itself through that.
- **There is no self-serve entry.** No free tier, trial or public price.
- **Value needs integration.** Nothing useful happens until the ERP is connected, which needs a project.
- **Deals are few and large.** Roughly 40 to 50 customers produce all revenue, so each one justifies human attention.
- **Partners fit the motion.** Outsourcers and system integrators already run procurement operations for large companies and are trusted by the same buyers.

It is not product-led, community-led or marketplace-led. Marketing plays a supporting role through research reports and events. (INFERENCE from the sales process described on Aerchain's site.)

## Part 16 — Business model

Aerchain sells annual enterprise subscriptions priced on three things: the scope of the deployment, the amount of spending managed, and the modules chosen. The model rewards breadth of deployment, but nothing in it is tied to the value a customer actually realises.

### Which pricing mechanisms apply

| Mechanism | Does Aerchain use it? | Evidence and label |
| --- | --- | --- |
| Subscription | Yes | Annual business-to-business subscriptions. FACT. |
| Module-based | Yes | Price depends on “which modules you deploy”. FACT. |
| Scaled by spend | Yes | Price depends on “spend under management”. FACT. |
| Seat-based | Possibly, historically | A 2018 to 2019 profile said price depended on client size, number of users and modules. Current pages do not mention users. INFERENCE that seats matter less now. |
| Tiered plans | Not publicly | No named tiers exist. FACT. |
| Transaction pricing | No evidence | Information not publicly available. |
| Implementation fees | Likely | Enterprise deployments with ERP integration normally carry a one-time fee. HYPOTHESIS. |
| Hybrid | Yes | Modules multiplied by scope and spend. INFERENCE. |

### The seven business-model questions

1. **Who pays?** The procurement function's budget, with the CFO approving. In some groups the central digital or IT budget pays.
2. **What exactly are they paying for?** The right to run a set of modules across an agreed scope of entities and spending. In the buyer's mind they are paying for savings, speed and control.
3. **What makes the bill go up?** More modules, more entities or countries, and more spending routed through the platform.
4. **What causes expansion?** Adding invoices or vendor onboarding to a sourcing deployment, rolling out to more plants, and moving more categories onto the platform.
5. **What causes contraction?** Dropping an unused module at renewal, selling or closing an entity, or a tough renegotiation. The customer's own negotiators are professionals.
6. **What causes churn?** Low adoption, an ERP or suite vendor offering similar AI inside an existing contract, loss of the executive sponsor, or a damaging AI error. Part 37 ranks these.
7. **Does the pricing metric match customer value?** Partly. Spend under management tracks potential value, and modules track scope. Neither tracks realised value, such as savings achieved or purchases completed without a buyer. A customer can pay for scope it has not activated, which creates resentment at renewal. (INFERENCE.)

## Part 17 — Pricing

There is no public price list, plan table, free plan or trial. The best available estimate is an average of about $80,000 to $100,000 per customer per year, which puts Aerchain close to the typical Coupa or Zip contract and well below a full legacy-suite deal.

### What is known

| Item | Detail | Label |
| --- | --- | --- |
| Published prices | None. “Quoted after understanding scope, spend under management and modules.” | FACT |
| Pricing calculator | A “Pricing Calculator” appears in the old site's menu but links to a placeholder page. | FACT |
| Free plan or trial | None. | FACT |
| Stated price position | Total cost “materially below the $500K to $2M+ annual range” of legacy suites. | FACT that Aerchain says this |
| Average contract size | About $80K to $100K a year. | My estimate; working below |
| Add-ons, usage limits, overage | Information not publicly available. |  |
| Feature gating | By module. | INFERENCE |

**How the average is derived.** Aerchain's job postings state about $4M ARR. The product site says 40 enterprise accounts and Series A press says 50+. $4M ÷ 50 = $80,000. $4M ÷ 40 = $100,000. The real spread is probably wide, with a few large accounts well above this and many small ones below. (INFERENCE.)

### Reference prices from competitors

| Vendor | Typical yearly price | Source and label |
| --- | --- | --- |
| Aerchain | About $80K to $100K average | Derived above |
| Coupa | Median $94,519 across 126 purchases; range about $20,700 to $331,800; $800K to $2M+ for a full suite at a 5,000+ employee company | [Vendr](https://www.vendr.com/marketplace/coupa) buyer data. FACT that Vendr reports this |
| Zip | Median $88,000 across 75 purchases; range about $26,600 to $214,750 | [Vendr](https://www.vendr.com/marketplace/zip-hq) buyer data |
| SAP Ariba | Not published; its Joule agent runtime is free until 31 December 2026 | Third-party round-up; treat as reported |
| Pactum | Platform fee plus a share of value created (reported) | Third-party round-up |
| Fairmarkit | Scaled to spend under management (reported) | Third-party round-up |

**What this comparison shows.** Aerchain's “far cheaper than legacy suites” claim is true against the largest full-suite deals. Against the median Coupa or Zip contract, Aerchain is at roughly the same price. So price is an advantage only when the customer is comparing a broad scope. For a single-module purchase, Aerchain must win on results, not on cost. (INFERENCE.)

### How deals are probably packaged

No plan names are public. The table below is my reconstruction of likely deal shapes, to make the upgrade logic concrete. (HYPOTHESIS throughout.)

| Likely package | Target customer | Price | Features | Limits | Upgrade trigger |
| --- | --- | --- | --- | --- | --- |
| Land: sourcing | One business unit with a sourcing backlog | Not public; probably below the average | Sourcing, bid analysis, evaluation, auctions, supplier links | One entity, a few categories | Proven savings; requests still arriving by email |
| Expand: request to order | A procurement function standardising its process | Not public; around the average | Adds intake, negotiation, award with ERP write-back, vendor onboarding | Agreed entities and spend | More entities; finance asks for invoice control |
| Full SpendOS | A multi-entity group | Not public; several times the average | Adds invoices, analytics, Aiera, autonomy rollout across categories | Group-wide | New countries; overlay on an older suite |

### Is the product priced according to the value it creates?

**No, not yet.** The reasoning uses Aerchain's own figures.

- **Revenue per dollar managed.** $4M of ARR on a claimed $45B of spend is 0.009%, or about $89 for every $1M of spend. Using the $20B figure from the job description, it is 0.02%, or $200 per $1M.
- **Claimed value per dollar managed.** Aerchain's return model claims $45.2M of value over three years on $500M of spend. That is about $15M a year, or 3% of spend.
- **Share of value captured.** 0.009% ÷ 3% is 0.3%. Even using the higher 0.02% figure, Aerchain captures under 1% of the value it claims to create.

Two explanations are possible, and both are probably true. First, the product is priced to win deals and land, not to capture value. Second, the “spend under management” figure counts spending that could flow through the platform, not spending that actively does. If only a tenth of it is active, the gap shrinks by a factor of ten. (INFERENCE.)

**The opportunity.** Rivals are moving toward outcome-linked pricing: Pactum reportedly takes a share of savings, Coupa has introduced an outcome-based option, and Zip bundles AI usage credits with engineers. A price element tied to verified savings or to purchases completed without a buyer would align Aerchain's revenue with its strongest promise. It requires the value record described in Part 42. Without trusted measurement, outcome pricing causes disputes.

## Part 18 — Unit economics

Almost none of Aerchain's unit economics are public. What can be inferred points to a company that is early, people-heavy for its revenue, and well funded relative to its recent losses.

| Metric | Status | What can be inferred | Label |
| --- | --- | --- | --- |
| Customer acquisition cost (CAC) | Not publicly available | Enterprise sales with security reviews and tailored demos is expensive per deal. The AB InBev contract closed in under a month through an accelerator, which is an exception. | INFERENCE |
| Average revenue per customer | Not published | About $80K to $100K a year, derived in Part 17. | Estimate |
| Lifetime value (LTV) | Not publicly available | Illustration only: $90K a year × 70% gross margin × 5 years = about $315K. The margin and the lifetime are assumptions. | HYPOTHESIS |
| Gross margin | Not publicly available | Pressure comes from AI model costs per transaction and from implementation labour. | INFERENCE |
| Net revenue retention (NRR) | Not publicly available | The $25M target cannot be reached without NRR well above 100%, as Part 1 explains. | INFERENCE |
| Gross revenue retention | Not publicly available | Revenue reportedly fell from about ₹6.4 crore in FY23 to ₹5.4 crore in FY24 before rising 86% in FY25. A fall suggests a lost or shrunken account, or one-time fees in FY23. The FY23 figure comes from a tracker summary, so treat this lightly. | INFERENCE |
| Churn | Not publicly available |  |  |
| Payback period | Not publicly available |  |  |
| Revenue per employee | Derivable | About $40K: $4M ARR ÷ roughly 100 people. | Estimate |
| Burn | Partly visible | FY25 net loss about ₹9.4 crore, roughly $1.1M. | FACT |

**Three observations with the reasoning.**

- **Revenue per employee is low.** Levelpath, a US AI-native rival, reported $15M of revenue with 80 employees in June 2025. That is about $187,500 per employee. Aerchain's roughly $40,000 is about one fifth of that. Lower Indian salaries explain part of the gap. The rest suggests more people per customer for implementation and support. (INFERENCE.)
- **Expenses were nearly double revenue.** In FY25, about ₹19.5 crore of expenses against ₹10.1 crore of revenue. The company spent about ₹1.93 for every ₹1 it earned.
- **Runway is long.** A $13M round against a loss of about $1.1M a year is more than ten years at the FY25 rate. Spending will rise with hiring and global expansion, so the real figure is shorter, but cash is not the near-term constraint. Proof and distribution are. (INFERENCE.)

**What data would settle the picture.** Revenue by customer cohort, to calculate retention. Sales and marketing spend per new customer, to calculate CAC and payback. Implementation hours per deployment, to see services weight. AI model cost per event and per invoice, to see gross margin at volume.

## Part 19 — Go-to-market strategy

Aerchain goes to market through enterprise sales led by relationships and references, and it is adding a partner channel through Infosys. Its marketing is light for a company chasing global buyers, which is one reason its public proof looks thin.

**Model: sales-led, with partner-led emerging.** Product-led, community-led and marketplace-led growth are not materially applicable to this product, because nothing can be bought or tried without a sales conversation and an ERP integration.

| Channel | Evidence | Assessment |
| --- | --- | --- |
| Enterprise sales | Demo pitched to CPO and CFO together; a reply from “a procurement specialist” within one business day; an open role for a sales development representative supporting the “Enterprise Sales team” | The primary engine. FACT for each piece of evidence. |
| Outbound | The sales development role is about generating and qualifying leads | In use. INFERENCE on scale. |
| Inbound and content | Eight blog posts visible from 2022 to 2026; one research report based on 163 interviews; an ebooks page | Thin. Two to three posts a year will not build search visibility against Zycus, Coupa and Zip, which publish constantly. |
| SEO | Process and industry pages on the old site link to “soon” placeholders | Weak. Pages that should capture searches such as “tail spend management” do not exist yet. |
| Paid acquisition | No evidence | Information not publicly available. |
| Partnerships | Infosys Innovation Fund took a 5.3% stake; press reports describe Infosys BPM deploying Aerchain to clients and an “Autonomous Sourcing as a Service” offering | The largest growth opportunity. The stake is FACT. The deployment plan is press-reported and unconfirmed by Aerchain. |
| Investor network | IndiaMART is an investor and India's largest business-to-business marketplace | Possible data and distribution partner. HYPOTHESIS. |
| Corporate accelerators | AB InBev's Beer Garage, JioGenNext, Lumis Partners | Historically the way in to marquee logos. AB InBev and Reliance Jio both appear as customers. INFERENCE that the accelerators opened those doors. |
| Events | No specific events found | Information not publicly available. |
| Analyst relations | Gartner Market Guide listing in 2022; 9 Gartner Peer Insights ratings; 2 G2 reviews; not found in the 2026 Magic Quadrant coverage | Under-invested for global enterprise selling. |
| Referrals | Customer movement between companies and peer networks among procurement heads | Probably important and unmeasured. INFERENCE. |
| Product-led acquisition | Suppliers use the product without being customers | Not converted into leads today. |

### Why this model fits the product

- **High contract value and few buyers.** A few thousand large companies are realistic targets. Named-account selling is efficient at that scale.
- **A committee decision.** Three executives and a security team must agree. Only people can run that process.
- **Trust is the product.** Buyers are asked to let software commit company money. They need references and conversations, not a landing page.
- **Integration before value.** There is nothing to try until the ERP is connected.

### Where the model is strained

- **Proof.** A sales-led motion aimed at global buyers needs analyst coverage and reviews. Aerchain has little of either.
- **Reach.** A Bengaluru team cannot cover the Gulf, South-East Asia and the United States in person. Partners or regional hires are needed.
- **Dependence on a partner.** If Infosys becomes the main channel, Infosys controls the customer relationship and pricing power shifts toward it. (INFERENCE.)
- **Marketing basics.** Conflicting numbers, placeholder pages and two parallel websites undercut the sales team's work.

## Part 20 — Sales motion

Every Aerchain sale is an enterprise sale, but the weight of the process changes a great deal with customer size. There is no self-serve or small-business motion.

| Element | Assessment | Label |
| --- | --- | --- |
| Small business | Not served | FACT |
| Self-serve | None | FACT |
| Mid-market | Served. Likely the “Tier B” and “Tier C” accounts in the job description, which product managers are expected to own directly | INFERENCE; the tier definitions are not public |
| Enterprise | The focus. A Senior Product Manager posting says that role owns “Tier A customer engagements end-to-end”, so the largest accounts sit with senior staff | FACT for the posting; INFERENCE for the rest |
| Sales development representatives | Being hired | FACT |
| Account executives and field sales | An “Enterprise Sales team” exists; size not public | FACT that it exists |
| Founder-led selling | Likely still significant at this revenue | HYPOTHESIS |
| Customer success | Implementation and “hypercare” teams; product managers also own customer relationships | FACT for hypercare; job description for the PM role |

### Estimates where evidence exists

- **Sales cycle.** Not published. My estimate is three to nine months for a new enterprise customer. The one data point is unusual: AB InBev signed in under a month through its accelerator. A low-reliability third-party profile says earlier cycles ran 9 to 12 months. (HYPOTHESIS.)
- **Buying committee.** CPO, CFO or controller, CIO or ERP owner, information security, legal, and the procurement operations lead as champion. Five to eight people. (INFERENCE.)
- **Procurement complexity.** High, and with a twist: the customer's negotiators are the users. Expect benchmarking against Coupa, Zycus and Zip prices.
- **Security review.** Heavy. Aerchain cites a 119-row security questionnaire and a 142-row architecture review at Al-Futtaim, and a regulated-environment review at the National Stock Exchange of India.
- **Implementation complexity.** Medium to high. 16 weeks, four phases, an ERP integration and master-data loading.

### How the motion changes with customer size

|  | Mid-market (likely Tier C) | Large enterprise (likely Tier B) | Global group or government (likely Tier A) |
| --- | --- | --- | --- |
| Entry point | One module, usually sourcing | Request-to-order across a business unit | Group-wide programme or overlay on an existing suite |
| Buyer | Head of procurement and CFO | CPO, CFO, CIO | Group CPO, CFO, CIO, plus regional heads |
| Proof needed | Demo and one reference | References, security pack, pilot | Formal tender, architecture review, analyst standing |
| Sales cycle (HYPOTHESIS) | 2 to 4 months | 4 to 9 months | 9 to 18 months |
| Who leads | Account executive, with a product manager | Senior sales and a founder | Founders, possibly with a partner such as Infosys |
| Main risk | Low willingness to pay | IT or security blocks | Incumbent suite vendor defends the account |

## Part 21 — Customer success

Aerchain runs a high-touch model, and it has to: value depends on integration, configuration and behaviour change that customers cannot do alone. The strategic question is whether the touch can become lighter fast enough for the business to scale.

| Area | What is known | Label |
| --- | --- | --- |
| Implementation | Four phases over 16 weeks, run with Aerchain's team | FACT |
| Onboarding | Go-live followed by hypercare, a period of close support | FACT |
| Training | Delivered during rollout; no public academy or help centre | INFERENCE for the first; FACT for the second |
| Customer support | Support channels, hours and service-level commitments are not public. An independent reviewer notes no public uptime figure or status page. | FACT that none is public |
| Customer success and account management | The job description makes product managers accountable for customer outcomes and for adoption after launch | FACT from Aerchain's job description for the Product Manager role |
| Renewal and expansion | Driven by proof of value, wave-based release of categories, and adding modules | INFERENCE |
| Enablement | Open roles for a Product Operations Manager and a Technical Writer with 6 to 9 years' experience | FACT that the roles are listed; INFERENCE that documentation and process are being built now |

**Model: high-touch.** Not low-touch or tech-touch.

**Why it is high-touch.**

- Each deployment touches the customer's ERP, approval rules and supplier base.
- With 40 to 50 customers producing all revenue, losing one costs about 2% of revenue, so each deserves close attention.
- Autonomy is released in waves, and each wave is a conversation with the customer about risk.

**The trade-off.** High touch protects retention and produces deep customer knowledge. It costs margin and limits how many customers the team can run at once. Version 5's predefined configuration, the no-code framework, the open documentation roles and a delivery partner such as Infosys are all ways to reduce touch without reducing outcomes. Whether they are working is not visible publicly. (INFERENCE.)

**An unusual feature worth noting.** Making product managers own customer relationships puts the people who decide what gets built in direct contact with the people who use it. That shortens feedback loops. It also risks pulling product managers into account management and custom requests, which is why the job description stresses deciding what gets “built, deferred and killed”.

## Part 22 — Integration ecosystem

Aerchain's integrations are few but well chosen: the major ERPs, the main rival procurement suites, and enterprise login systems. They exist to make one promise true, that a customer can go live without replacing anything. There is no broad app ecosystem.

### Integration map

| Category | What exists | Label |
| --- | --- | --- |
| Identity | Single sign-on using the SAML and OIDC standards, built on a vendor called Scalekit. Supported identity providers include WSO2, Microsoft Entra ID, OneLogin and Ping Identity. Suppliers log in with Google or Microsoft accounts. SCIM user provisioning is listed on the product site. | FACT ([Scalekit case study](https://www.scalekit.com/customers/aerchain), product site) |
| Productivity and communication | Email is both an input and an output channel. Chat is supported. Slack, Microsoft Teams and WhatsApp were promised in a 2024 founder post and are not confirmed on current pages. | FACT for email and chat; unconfirmed for the rest |
| CRM | Not materially applicable. Procurement software does not depend on sales systems. |  |
| Finance and ERP | Native connectors for SAP, Oracle, NetSuite, Microsoft Dynamics and Workday, each with a predefined field dictionary. Two-way sync of requisitions, purchase orders, goods receipts and invoices. | FACT |
| Other procurement suites | Connectors for Coupa and SAP Ariba. Runs as a layer over Jaggaer at the Dubai Government. | FACT |
| Payments | The old site mentions “payment platforms” without naming any. Press mentions payment tracking. | Unspecific |
| HR | Information not publicly available. User accounts come through single sign-on and SCIM. |  |
| Data and business intelligence | Information not publicly available. Dashboards are built inside the product. |  |
| Developer | No public API documentation. One press article mentions a REST and GraphQL interface, which is unverified. Webhook validation is mentioned on the Integrations Hub page. | FACT that no public docs exist |
| Marketplace | None. | FACT |
| Third-party data | Supplier credibility checks “scan the web”. Named risk-data providers are not disclosed. | FACT that it is undisclosed |

### Why each major integration matters

| Integration | Why customers need it | Workflow enabled | Strategic importance | Effect on switching cost | Competitive significance |
| --- | --- | --- | --- | --- | --- |
| ERP (SAP, Oracle, NetSuite, Dynamics) | The ERP is the legal record of orders and payments | Requests and orders flow in and out without re-keying; invoices match against real receipts | Essential. Nothing counts as live without it. | High. Rebuilding mappings for every entity is slow and risky. | Table stakes. SAP's own agents need no integration, which is an advantage for SAP inside SAP customers. |
| Rival suites (Ariba, Coupa, Jaggaer) | Many large companies already own a suite they cannot remove | Aerchain's agents work on top; the suite remains the record | High. It opens accounts that would never replace their suite. | Low to medium. An overlay is easier to remove than a core system. | Differentiating as a sales approach. It depends on rivals continuing to allow access. |
| Single sign-on and SCIM | Security teams require central login and automatic removal of leavers | Staff log in with company accounts; accounts close when people leave | Required to pass security review | Low | Table stakes. Support for WSO2 edge cases helped onboard Reliance Jio. |
| Email | Suppliers and requesters already live there | Bids and requests arrive without anyone adopting a new tool | High. It drives supplier participation. | Medium. Supplier habits form around it. | Differentiating in email-first markets. |
| Supplier social login | Small suppliers have no corporate identity system | A supplier signs in with Google or Microsoft | Medium | Low | Minor |

### What is missing

- **Collaboration tools confirmed.** Zycus puts its assistant inside Microsoft Teams. Aerchain's presence there is unclear.
- **Contract and e-signature systems.** No named integration, consistent with contract management not being a live module.
- **Supplier risk data.** No named providers for sanctions, financial health or sustainability checks.
- **Tax and e-invoicing networks.** Important for invoices in many countries; not described.
- **Analytics export.** No stated connection to data warehouses or business-intelligence tools, which finance teams often require.

## Part 23 — API and platform strategy

Aerchain calls itself an operating system, but today it is an application with strong configuration, not a platform others build on. Rivals are opening up faster, and that gap is strategic.

| Platform element | Aerchain | What rivals offer | Label |
| --- | --- | --- | --- |
| Public APIs | No public documentation | Zycus advertises 1,121 interfaces | FACT |
| Webhooks | Mentioned | Standard elsewhere | FACT |
| Software development kits | None found | Varies | FACT |
| Developer platform | None | Coupa's Agent Studio reports 400+ customer-built agents since May 2026; Ivalua has IVA Studio; Zycus has AppXtend | FACT for rivals |
| Open agent access | None found | Zip launched a server using the Model Context Protocol, a standard that lets assistants such as Claude or ChatGPT use Zip's data and actions | FACT for Zip |
| Automation and custom logic | No-code templates, workflows, approval rules and integration payloads | No-code builders at Zip, Levelpath and Coupa | FACT |
| Custom integrations | No-code payload designer with simulation | Similar | FACT |
| Data import and export | Information not publicly available |  |  |
| Marketplace | None | Zip launched a marketplace in September 2026 with 100+ app integrations | FACT for Zip |

### Direction of travel

**Application moving toward platform, slowly.** The named pieces, a multi-agent framework, a knowledge hub, an integrations hub and a no-code framework, are the internal parts of a platform. None of them is yet open to customers or partners to build new agents. (INFERENCE.)

### Strategic implications

1. **The “operating system” claim needs extensibility to be true.** An operating system lets others build on it. A customer-facing agent builder or open APIs would close the gap between the name and the product.
2. **A partner channel needs platform features.** If Infosys runs Aerchain for many clients, Infosys will want APIs, management across clients and its own configurations. Building these is a precondition for the channel working, not a later nicety. (INFERENCE.)
3. **The overlay strategy carries dependency risk.** Running on top of Ariba, Coupa or Jaggaer depends on those vendors' interfaces. A rival can restrict access or simply ship the same agents inside its own suite.
4. **Open agent standards could bypass the interface.** If buyers increasingly ask questions through general assistants, a vendor that exposes its data and actions safely, as Zip has, becomes the easy choice. Aerchain has not announced anything similar.
5. **Data portability cuts both ways.** Easy export reassures enterprise buyers and security reviewers. It also lowers switching costs. On balance, enterprise buyers demand it, so resisting it loses deals.

**The trade-off Aerchain appears to have made.** It optimised for a controlled, standard product that deploys quickly, and gave up the ecosystem leverage that comes from letting others extend it. With about 100 people, that was reasonable. With an outsourcing partner and competitors opening up, it needs revisiting. (INFERENCE.)

## Part 24 — AI strategy

AI is the core of Aerchain's value in three places: reading messy documents, holding a negotiation in writing, and turning plain-language requests into structured ones. Around that core sits a layer of marketing language that goes further than the evidence. The durable advantage will not be the AI models, which everyone can buy, but the context, controls and track record built around them.

### AI capabilities by type

| Type | Where it appears | Label |
| --- | --- | --- |
| Generative AI | Drafting scopes, RFQs and evaluation criteria; writing negotiation messages; conversational intake | FACT |
| Document understanding | Reading bids and invoices from PDF, Excel, Word, images, handwriting and email | FACT |
| Predictive AI | Target prices from history and benchmarks; demand forecasting is claimed for the Knowledge Hub and the coming Analytics Agent | FACT that it is claimed |
| Recommendations | Suppliers to invite; approvers; award decisions; exception fixes | FACT |
| AI search and question answering | Contextual search in intake; Aiera's sourced answers | FACT |
| Summarisation | Not described explicitly |  |
| Agents | Each process step has an agent that can act within limits | FACT |
| Workflow automation | Buyer allocation, routing, approvals, ERP write-back | FACT |
| Assisted decisions | Scorecards, risk flags, price anomaly alerts | FACT |
| Underlying models | Information not publicly available. Aerchain does not say which AI models or providers it uses. | FACT that it is undisclosed |

### The eight main AI features

| AI feature | User problem | Input | AI processing | Output | User action | Value | Accuracy needed | Human oversight | Main risk | Competitive differentiation |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Conversational intake | Forms are long and requests arrive vague | Text, files | Extracts fields, classifies category, spots gaps | Structured, policy-checked request | Answers a few questions, submits | Complete requests first time | High on category and cost centre; errors are cheap to fix | Requester and approver see it before it moves | Wrong classification routes spend badly | Low. Widely available. |
| Bid reading and comparison | Quotes come in every format | Supplier documents and emails | Extracts and normalises line items, prices, terms | One comparison table with flags | Checks flagged items | A day's work in minutes | Very high. A misread price changes the award. | Buyer reviews; source shown beside value would help | Silent extraction error | Medium to high. Format freedom is a real advantage. |
| Supplier recommendation | The same few suppliers get every request | Request, supplier history, ratings | Matches suppliers on performance, price and compliance | Ranked supplier list | Edits and sends | More bids per event | Medium. A weak suggestion costs little. | Buyer approves the list | Irrelevant invitations annoy suppliers | Medium |
| Evaluation scoring | Inconsistent, slow evaluation | Bids, criteria, performance data | Scores and ranks; flags non-compliance and outliers | Scorecard and shortlist | Adjusts, approves | Consistent, auditable decisions | High | Stakeholders validate | False sense of objectivity | Low to medium |
| Autonomous negotiation | No time to negotiate small and mid-size buys | Bids, playbook, limits, benchmarks | Plans concessions, writes and reads messages over several rounds | Improved offers and a full log | Sets limits; approves result where required | Savings on spend that got none | Very high. It commits money and relationships. | Limits, logging, approval routing; level set per category | Overpaying, leaking the limit, manipulation by supplier text | High, but shared with Pactum, Zycus and Zip |
| Sourced question answering (Aiera) | Finding facts needs an analyst | Question in plain words | Retrieves records and composes an answer | Answer with the records used | Reads, acts | Faster decisions; wider usage | High. A wrong spend figure in a board pack is serious. | Sources shown for checking | Confident wrong answers; showing data the user should not see | Low. Standard in 2026. |
| Invoice matching and exception advice | Manual matching and disputes | Invoice, order, receipt | Reads, matches, detects duplicates, suggests a fix | Matched invoice or a queued exception | Handles exceptions | Lower cost, fewer wrong payments | Very high. Errors become payments. | Exceptions go to staff; tolerances set by finance | Paying a fraudulent or duplicate invoice | Low. Specialists are strong here. |
| Risk and anomaly signals | Problems are found late | Transactions, supplier data | Detects price anomalies, performance dips, off-contract buying | Alerts inside workflows | Investigates | Earlier action | Medium. Too many false alarms get ignored. | Human decides | Alert fatigue | Low to medium |

### What role does AI play?

| Role | Verdict | Reasoning |
| --- | --- | --- |
| Core product value | Yes, for intake, bid reading and negotiation | Without AI these features would not exist in a useful form |
| Feature enhancement | Yes, for evaluation, onboarding, invoices and analytics | These existed as workflow features before; AI speeds them up |
| Marketing layer | Partly | “300+ agents”, “self-learning” and “unbiased” are stronger than anything shown |
| Strategic platform shift | Yes, for the company | The April 2025 rebrand and the SpendOS name reorganise the whole product around agents |

### What could AI commoditise?

- **Document reading.** General AI models read invoices and quotes well and keep improving. This was once hard and is becoming ordinary.
- **Drafting.** Any assistant can draft an RFQ or a supplier email.
- **Chat intake and question answering.** Incumbent suites and ERPs include these. The Hackett Group reports 69% of organisations get procurement AI through platforms they already own.
- **Basic negotiation scripts.** A capable model with a simple playbook can run a price negotiation.
- **The agent idea itself.** Coupa lists over 50 agents, Ivalua over 30 and SAP eleven. “We have agents” no longer differentiates.

### What could AI make more valuable?

- **Customer-specific context.** Years of prices, specifications and supplier behaviour make a general model useful for one company's buying. This is the Knowledge Hub's job.
- **Controls.** Limits, approval rules, logs and autonomy levels are what let an enterprise use AI for money decisions at all.
- **Write access to the system of record.** An agent that can create a valid purchase order in a customised ERP is worth more than one that only advises.
- **Proof of reliability.** Test sets and track records by category become the reason a customer releases more spending to agents.
- **Supplier reach.** An agent is only as good as the suppliers who answer it.

### AI risks specific to this product

| Risk | Why it matters here | Sensible control |
| --- | --- | --- |
| Instructions hidden in supplier content | Agents read supplier emails and attachments. A supplier could write text that tries to steer the agent. | Treat supplier content as data only; restrict agent actions; approvals for high-value steps |
| Leaking the walk-away price | A negotiation agent knows the buyer's limit | Keep limits out of generated text; test for leakage before each release |
| Silent extraction errors | A wrong unit or tax treatment changes who wins | Show the source beside each value; sample audits |
| Quality drift after a model change | Model providers update models; behaviour shifts | A fixed test set and a release gate for every agent |
| Agents negotiating with agents | Suppliers will adopt their own AI | Design for it early; log everything; keep policy limits firm |
| Accountability | When an agent errs, who answers? | Clear ownership by the customer for limits and by Aerchain for behaviour inside them |

Whether Aerchain has these controls is not public, except for limits, logging and approvals, which it does describe.

## Part 25 — Data strategy

Aerchain gathers valuable data inside each customer, and that makes each customer stickier. It does not appear to combine learning across customers, so it has a per-customer flywheel but no market-wide data moat.

| Aspect | Assessment | Label |
| --- | --- | --- |
| Data generated | Requests, RFQs, bids, negotiation rounds, awards, orders, invoices, supplier responses and ratings, approval times | FACT |
| Data collected from the customer | ERP master data and history, contracts, emails, quotes | FACT |
| Data stored | The Knowledge Hub holds specifications, price benchmarks and contract clauses | FACT |
| Data processed | Unstructured documents turned into structured records | FACT |
| Data analysed | Spend by category, region, project and supplier; savings; supplier risk | FACT |
| Data exported | Written back to the ERP; other export options not public | FACT for write-back |
| Portability | Information not publicly available |  |
| Ownership | The customer's data. Press describes agents “trained on each customer's data”. Whether any data improves shared models is not stated. | FACT for the quote; the rest is undisclosed |

### Is there a data flywheel?

**Inside one customer: yes.**

```text
More purchases through the platform
↓
More price, supplier and specification history
↓
Better targets and recommendations
↓
Better outcomes and more trust
↓
More purchases through the platform
```

**Across customers: not visibly.** Nothing public shows shared benchmarks or pooled supplier performance. Coupa, by contrast, markets insights drawn from over $10 trillion of community spend. (INFERENCE.)

### Is there a data moat?

**Weak to moderate.** The per-customer history raises switching costs, which is a retention advantage. It does not stop a rival from winning the next new customer. A true moat would need something rivals cannot easily copy, such as opt-in, anonymised price benchmarks for categories and regions where global vendors have little data. Aerchain's base in Indian and Gulf enterprises, its claimed 150,000 suppliers and its IndiaMART relationship are raw material for exactly that. Building it needs customer consent, careful anonymisation and legal review, because shared price data raises confidentiality and competition-law questions. (INFERENCE and HYPOTHESIS.)

## Part 26 — Security, privacy and compliance

Aerchain has the certifications needed to pass enterprise security review, and it has specific proof of passing hard ones. Its gap is transparency: nothing is published about uptime, data location or how AI providers handle customer data.

| Area | Status | Label |
| --- | --- | --- |
| Authentication | Single sign-on through SAML and OIDC; supplier login through Google or Microsoft | FACT |
| Authorisation | Role-based access; field-level permissions on integration data | FACT |
| User provisioning | SCIM listed | FACT that it is claimed |
| Audit logs | Full audit logs; every negotiation round logged; integration actions logged | FACT that it is claimed |
| Encryption | In transit and at rest | FACT that it is claimed |
| SOC 2 Type II | Listed | FACT that it is claimed; report not public |
| ISO 27001 | Listed | FACT that it is claimed |
| GDPR and India's DPDP Act | Listed | FACT that it is claimed |
| Penetration testing | Regular testing listed | FACT that it is claimed |
| Modern Slavery Act | Listed as a compliance item | FACT that it is claimed |
| Data residency | Information not publicly available |  |
| HIPAA | Not materially applicable. Hospital customers use it for purchasing, not patient data. | INFERENCE |
| US government certification (FedRAMP) | Not listed. SAP and Ivalua have it. | FACT |
| Uptime commitment and status page | None public | FACT |
| AI data handling | Not stated: which model providers process customer data, and whether data is used to train shared models | FACT that it is undisclosed |
| Regulated-environment proof | Cleared reviews at the National Stock Exchange of India; a 119-row security questionnaire and a 142-row architecture review at Al-Futtaim | FACT that Aerchain states this |

### How security affects the business

- **Enterprise sales.** Certifications are the entry ticket. Without them, the deal ends at the security team. Publishing the review counts is clever: it tells the next buyer's security team that a peer already did the work.
- **Procurement by the customer.** A ready security pack shortens the purchase. Aerchain outsourced login to a specialist vendor after building it in-house, which shows a preference for buying non-core security components.
- **Customer trust.** For AI that negotiates and approves, the audit trail matters more than the certificate. The ability to replay exactly what an agent did, and why, is the real trust feature.
- **Switching costs.** Passing a customer's security and architecture review is an investment the customer does not want to repeat with another vendor.
- **Product adoption.** Strict separation between entities and role-based access let a group roll out across regulated subsidiaries.

### Gaps a buyer's security team would raise

1. Where is data stored, and can it stay in-country for India or the Gulf?
2. Which AI model providers see our data, and under what terms?
3. Is our data used to improve anything shared with other customers?
4. What uptime is committed, and what happened in past incidents?
5. How is a no-login supplier link protected from being forwarded or guessed?
6. Can audit logs be exported in full for our regulators?

## Part 27 — Competitive landscape

Aerchain is squeezed from three sides: suites with far more proof that now ship agents, a well-funded intake leader moving into sourcing, and specialists that go deeper on single steps. Its most dangerous rival is Zycus, which tells the same story from the same home market with a Gartner Leader badge. Its most common rival is still email and spreadsheets.

### Direct competitors

| Competitor | Ideal customer | Core strength | Weakness | Pricing | Differentiator | Strategic threat |
| --- | --- | --- | --- | --- | --- | --- |
| Zycus (Merlin Agentic AI) | Large global enterprises | Full suite plus agents for intake, negotiation, analytics and accounts payable; says it is a Leader in the 2026 Gartner Magic Quadrant; says about half of Tata Play's purchase orders run through its negotiation agent | A long-established suite underneath, so the “built for AI” claim is contestable; implementation likely heavier | Not public | Calls its category “intake to outcomes”; 1,121 interfaces; assistant inside Microsoft Teams | Very high. Same story, same home market, more proof |
| SAP Ariba | Companies running SAP | Largest supplier network, in 190+ countries; about 27% of the procurement software market by one estimate; agents that act on live SAP records | Long projects; rated 4.1 on G2 across 799 reviews, the lowest of the big names shown there | Not public; agent runtime free to the end of 2026 | A rebuilt “AI-native” platform arriving in 2026 | High inside SAP accounts, where the AI arrives at no extra cost |
| Coupa | Mid-size to large enterprises worldwide | Over 50 agents; 450+ customers using agents in production; community data on over $10 trillion of spend; bought Rossum (invoice reading) and Tonkean (intake) | Suite price and complexity at full scope | Median about $94,500 a year; $800K to $2M+ at full suite | An agent builder with 400+ customer-made agents | High globally |
| GEP | Large enterprises wanting procurement and supply chain together | Gartner Leader; software plus a large services arm | Enterprise-only; heavy | Not public | Software and outsourced services from one firm | Medium. Aerchain says one of its wins replaced GEP |
| Ivalua | Large, complex enterprises and public sector | Gartner Leader; 500+ organisations; 30+ agents; very configurable | Enterprise-only; long configuration | Not public | Flexibility; US government-grade hosting | Medium |
| Jaggaer | Manufacturing, education, public sector | Gartner Leader; deep direct-materials sourcing | Older user experience | Not public | Sector depth | Medium, and also a host: Aerchain runs on top of it in Dubai |
| Zip | US technology and mid-to-large enterprises | Owns the “front door” for requests; valued at $2.2B with about $371M raised; Gartner Visionary; 50+ agents live | Sits on top of other systems; sourcing and invoice agents are new | Median about $88,000 a year | Agents for procurement, legal, accounts payable, intake and configuration; open access for AI assistants; an app marketplace | High. It is moving from intake into Aerchain's core |
| Levelpath | US mid-size to large enterprises replacing a suite | AI-native, about $100M raised, $15M revenue in mid-2025; founders sold a sourcing company to Workday | Newer; smaller partner network | Not public | Mobile-first design; its own reasoning engine | Medium to high in the United States |

### Indirect competitors

| Competitor | What part of the problem it solves | Threat |
| --- | --- | --- |
| Pactum | Autonomous negotiation; customers include Walmart and Maersk; over $100M raised; connects to Ariba and Coupa | High for the negotiation module |
| Fairmarkit | Tail-spend sourcing with five agents; reports 11% average identified savings | High for tail spend |
| Keelvar, Arkestro, Globality | Sourcing optimisation, predictive pricing, services sourcing | Medium |
| Omnea, ORO Labs | Intake and orchestration | Medium |
| Invoice specialists such as Stampli | Invoice processing | Medium for the invoice module |
| Sievo | Spend analytics with contractual accuracy guarantees | Medium for analytics |
| Procol, 1Buy.AI | Indian procurement startups | Medium in the Indian mid-market |
| SAP Procure AI, IBM watsonx Procurement Agents, Oracle | AI from the ERP or infrastructure vendor | High where the customer wants one vendor |

### Substitutes

| Substitute | Why customers choose it | Its weakness |
| --- | --- | --- |
| Email, spreadsheets and the ERP | Free, familiar, no project | Does not scale; no control or data |
| Outsourced procurement teams | No software to run; cost is variable | Labour-based; quality varies. Infosys BPM is now also a partner. |
| Building in-house with general AI tools | Control; no new vendor; uses existing AI licences | Needs engineers, controls, ERP integration and upkeep |
| Consultants running sourcing projects | Expertise for big categories | Expensive; leaves no system behind |
| Purchase cards and online marketplaces for small buys | Fast for the requester | No negotiation; weak control |

### Emerging competitors

- **General agent platforms** from large software companies, which let customers build their own procurement agents.
- **New AI-native startups** listed beside Aerchain on comparison sites, such as Lio, Opstream and Procure Ai.
- **Supplier-side AI.** Once suppliers use agents to respond and negotiate, the value of a buyer-side negotiation agent changes.
- **The next-generation SAP Ariba**, which SAP describes as AI-native from 2026.

## Part 28 — Competitive feature matrix

Aerchain matches the suites on breadth except for contracts and analytics, and it is ahead of most on supplier-side ease. It is behind on openness and independent proof.

Key: ✓ strong, \~ partial, × absent, ? unclear from public evidence. I use ? wherever I could not find evidence either way.

| Capability | Aerchain | Zycus | Coupa | SAP Ariba | Zip | Pactum |
| --- | --- | --- | --- | --- | --- | --- |
| Conversational intake | ✓ | ✓ | ✓ | ✓ | ✓ | \~ |
| Automated RFQ and sourcing event creation | ✓ | ✓ | ✓ | ? | \~ | \~ |
| Reading bids in any format | ✓ | ? | ? | ? | ? | ? |
| Bid scoring and evaluation | ✓ | ✓ | \~ | ? | \~ | ? |
| Autonomous negotiation | ✓ | ✓ | \~ | ? | \~ | ✓ |
| Reverse auctions | ✓ | ✓ | ✓ | ✓ | ? | ? |
| Supplier onboarding and checks | ✓ | ✓ | ✓ | ✓ | \~ | × |
| Contract management | × | ✓ | ✓ | ✓ | ✓ | × |
| Invoice matching | ✓ | ✓ | ✓ | ✓ | \~ | × |
| Making payments | ? | ? | ✓ | ? | ? | × |
| Spend analytics | \~ | ✓ | ✓ | ✓ | \~ | × |
| Chat assistant | ✓ | ✓ | ✓ | ✓ | ✓ | ? |
| Autonomy adjustable by category | ✓ | ? | \~ | ? | \~ | \~ |
| Works as a layer over other suites | ✓ | ? | ? | × | ✓ | ✓ |
| Supplier response without login | ✓ | ? | ? | ? | ? | ? |
| Customer-built agents or open platform | × | ✓ | ✓ | \~ | ✓ | × |
| Cross-customer data or supplier network | \~ | ? | ✓ | ✓ | \~ | \~ |
| Place in the 2026 Gartner suite ranking | × | ✓ | ✓ | ✓ | \~ | × |
| Independent reviews at volume | × | ? | ✓ | ✓ | \~ | × |

**Notes on the matrix.** Auctions for the three suites are marked from their long-standing sourcing products. Zip's sourcing, negotiation and invoice agents were announced in June and September 2026, some in beta, so they are marked partial. Coupa's negotiation support is market data, not an agent that negotiates. Aerchain's contract cell is × because the main site marks it “coming soon”, although Series A press lists contract management among its capabilities.

## Part 29 — Competitive positioning

Against every rival, Aerchain's honest pitch is the same: faster to live, easier for suppliers and ordinary users, and willing to sit on top of what the customer already has. Its honest weakness is also the same: less proof.

| Competitor | Why a customer would choose them | Why a customer would choose Aerchain instead |
| --- | --- | --- |
| Zycus | Analyst-endorsed, full suite including contracts and analytics, global references | Faster deployment, lighter project, supplier-friendly bidding, sits on top instead of replacing |
| SAP Ariba | Already an SAP customer; one vendor; largest supplier network; agents included in the contract | Works across several ERPs in a multi-entity group; live in months; employees actually use it |
| Coupa | Proven at scale; huge data set; agent builder; strong invoices and payments | Lower total cost at broad scope; attention from a vendor for whom the customer is a top account |
| GEP or Ivalua | Depth, configurability, services, public-sector credentials | Speed and simplicity for teams without a large programme budget |
| Jaggaer | Sector depth and installed base | Aerchain as an AI layer on top, with no migration |
| Zip | Best-known intake product; strong in technology companies; open to AI assistants | Does the sourcing, negotiation and invoice work itself, not only routing; fits direct-materials and multi-plant companies |
| Levelpath | US presence and investor backing | Experience with Indian, Gulf and Asian operating realities; multi-entity depth |
| Pactum | Deepest negotiation track record with very large enterprises | One system from request to invoice, so negotiation uses context from the earlier steps |
| Fairmarkit | Focused tail-spend results | Covers strategic and tail spend plus invoices |
| Build in-house | Control and no vendor | Controls, integrations and procurement know-how already built |

### Summary of the competitive position

- **Table stakes.** Conversational intake, a chat assistant, RFQ automation, three-way match, ERP connectors, single sign-on, security certifications, “agents”.
- **Differentiators.** Bids in any format; no-login supplier response; autonomy set per category; overlay on rival suites; multi-entity depth; 16-week deployment.
- **Weaknesses.** No contract module; thin analytics; closed platform; few reviews; inconsistent public numbers; small team; limited presence outside its home regions.
- **Moats.** Per-customer data and integration lock-in. Nothing yet that blocks a rival at the point of a new sale.
- **White spaces.** Regional price benchmarks for India and the Gulf. Rescue layers for stalled suite rollouts. Tools for outsourcing operators. Published agent track records by category, which no vendor offers. Services for small suppliers, such as faster payment, built on the supplier base.
- **Vulnerabilities.** A rival copying format-free bidding. SAP or Coupa bundling agents at no extra cost. Zycus winning the Indian enterprise narrative. Dependence on rivals' interfaces for the overlay approach.

## Part 30 — SWOT

Aerchain's strengths are operational and its weaknesses are about proof and reach. The opportunities depend on one partner and one capability, measured value. The threats come mostly from larger companies doing the same thing with more distribution.

### Strengths

- **A full request-to-invoice scope on one data model.** The negotiation agent can use what intake and evaluation learned. Single-step tools cannot.
- **Supplier-side design.** No-login links, replies by email in any format and a mobile app. AB InBev reached 87.5% supplier participation.
- **Deployment speed and overlay.** 16 weeks claimed, with the Dubai Government running it on top of Jaggaer.
- **Graduated autonomy.** A packaged answer to “how much do we trust the AI?” that lets cautious customers start.
- **Enterprise credentials unusual for its size.** Reliance, Unilever, Danone, AB InBev, NSE and a government deployment; security reviews passed at Al-Futtaim.
- **Strategic investors with distribution.** Infosys holds 5.3% and runs procurement for large clients. IndiaMART holds supplier data.
- **Cost base.** A Bengaluru team keeps spending low: about ₹19.5 crore of total expenses in FY25.

### Weaknesses

- **Thin independent proof.** 9 Gartner ratings, 2 G2 reviews, no public case studies with methods, and no place in the 2026 Gartner suite ranking.
- **Inconsistent public numbers.** Four versions of spend under management and two customer counts.
- **Small revenue and losses.** About ₹10.1 crore of revenue and a ₹9.4 crore loss in FY25.
- **Missing and immature modules.** Contracts not yet available; analytics flagged as weak.
- **Closed platform.** No public interfaces, agent builder or marketplace while rivals open up.
- **Breadth with a small team.** Around 100 people covering eight or more modules against specialists.
- **Marketing hygiene.** Two websites, placeholder pages and copy errors.

### Opportunities

- **Infosys BPM as a channel.** Outsourced procurement teams could run Aerchain for many clients at once.
- **Tail spend.** Most companies do not manage it at all, and it suits full automation.
- **Overlay on stalled suites.** Companies unhappy with adoption of an expensive suite can add Aerchain without replacing it.
- **Gulf and public sector.** In May 2026 Dubai launched a two-year programme to move its private sector toward agentic AI, and Aerchain already has a government reference there.
- **Value-linked pricing.** Aerchain captures under 1% of the value it claims to create.
- **Regional benchmarks.** Opt-in price and supplier benchmarks for Indian and Gulf categories would be hard for global vendors to match.
- **A rising tide.** The Hackett Group projects workloads up 8% with headcount down 0.9%, and technology spending up 6.1% in 2026.

### Threats

- **AI bundled by incumbents.** 69% of organisations get procurement AI through platforms they already own, per the Hackett Group. SAP's agent runtime is free to the end of 2026.
- **Zycus.** An established rival with a Leader badge, an Indian customer base and a live autonomous negotiation reference.
- **Zip moving into sourcing.** $371M raised, new sourcing and purchase-order agents in September 2026.
- **A visible AI failure.** One overpayment or mishandled negotiation at a marquee customer would travel fast.
- **Commoditisation of the AI layer.** Document reading and drafting are becoming ordinary.
- **Services gravity.** Enterprise customers pull a small vendor into custom work, which erodes margin and the 16-week promise.
- **Partner dependence.** If Infosys becomes the main route to market, it gains leverage over price and customer access.
- **Access risk in overlay deals.** Rival suites control the interfaces Aerchain needs.

## Part 31 — Porter's five forces

The industry is attractive in size but hard on small vendors: rivalry is intense, buyers are powerful and professional, and substitutes are free. Only supplier power and new entry at the enterprise level are moderate.

| Force | Strength | Why, for Aerchain specifically | Implication |
| --- | --- | --- | --- |
| Competitive rivalry | Very high | Five or six Gartner Leaders, a $2.2B intake company and well-funded AI specialists all sell “procurement agents”. Features converge within quarters. | Compete on a segment and on proof, not on a feature list |
| Supplier power | Moderate | The key suppliers are AI model providers and cloud hosts. Models are interchangeable to a degree, but price and behaviour changes hit margin and quality. ERP vendors are also suppliers of access. | Stay model-independent; test every model change; treat ERP interfaces as a risk |
| Buyer power | High | Buyers are procurement professionals, deals are large, there are few customers, and each has alternatives. Roughly 40 to 50 customers produce all revenue. | Expect discounting pressure; reduce it with measured value and multi-year terms |
| Threat of substitutes | High | The status quo of email, spreadsheets and the ERP is free. Outsourcers and in-house builds are credible. | The main competitor is inaction, so time-to-value is the weapon |
| Threat of new entrants | Moderate | Building an AI demo is easy. Passing enterprise security review, integrating with ERPs and earning trust takes years. | The barrier is trust and integration, so invest there |

**Overall.** Profit in this market goes to vendors with distribution (SAP, Coupa) or with a defensible niche. Aerchain has neither at scale yet. Its realistic route is a defensible niche: complex multi-entity groups in its home regions, plus overlay deals and a partner channel. (INFERENCE.)

## Part 32 — Moats and defensibility

Aerchain's defences are real inside each customer and weak in the open market. It keeps customers better than it blocks competitors.

| Potential moat | Rating | Reasoning |
| --- | --- | --- |
| Network effects | Weak | No evidence that one customer or supplier joining makes the product better for others |
| Data | Weak to moderate | Deep history inside each customer; no visible cross-customer data asset |
| Switching costs | Moderate | ERP write-back, approval rules for every entity and supplier habits take effort to rebuild. A 16-week install is also a 16-week replacement. |
| Brand | Weak | Little recognition outside India; few reviews; conflicting numbers |
| Distribution | Weak, possibly improving | Small direct team; the Infosys relationship could change this |
| Ecosystem | Weak | No marketplace, developer community or agent builder |
| Integrations | Moderate | Connectors to the main ERPs and rival suites are valuable and laborious, but rivals have them too |
| Scale | Weak | Around 100 people and about $4M ARR against rivals with hundreds of millions |
| Workflow lock-in | Moderate to strong after full rollout | Once orders and invoices run through it, removal disrupts finance |
| Proprietary technology | Weak to moderate | Agents sit on commercially available AI models. The procurement-specific logic, playbooks and controls are know-how, not hard barriers. |
| Regulatory barriers | Weak | Certifications are necessary and obtainable by any serious rival |
| Domain know-how in complex emerging-market groups | Moderate | Seven years of multi-entity, email-first, India and Gulf operating detail is slow to copy |

### Could a well-funded startup recreate this product today?

**Yes, most of it, in 12 to 18 months.** A strong team could rebuild the intake, document reading, RFQ drafting, scoring and chat features quickly with current AI models. Levelpath and Zip show that well-funded teams do exactly this.

**What would still be hard to copy.**

1. **Reference customers and passed security reviews.** Unilever, Reliance, AB InBev, NSE and a government deployment cannot be bought.
2. **ERP integrations proven in customised, multi-entity environments.** Each one is learned on a real customer.
3. **Operating knowledge of its home markets.** How approvals, taxes and suppliers actually behave across Indian and Gulf groups.
4. **Accumulated per-customer history.** A new entrant starts every customer from zero.
5. **The Infosys relationship.** A strategic investor who is also a customer and a potential channel.

**What this means.** Aerchain's lead is measured in relationships and operating detail, not in technology. Its strategy should convert those into things that compound: a cross-customer data asset, a partner ecosystem, and published reliability records. (INFERENCE.)

## Part 33 — Product-led growth

Aerchain does not have a product-led growth engine, and it should not try to build a classic one. What it can borrow is the discipline: treat activation, engagement and expansion inside each account as a funnel the product is responsible for. The likely bottleneck is the step from first value to wider rollout.

### The six stages, adapted to an enterprise product

| Stage | How it works at Aerchain | Strength |
| --- | --- | --- |
| Acquisition: how users enter | Companies enter through sales and partners. Individual users enter by being invited after the sale. Suppliers enter by being invited to an event. | Weak as a product engine; normal for the category |
| Activation: what predicts value | The first purchase completed from request to purchase order in the ERP, then repeated across categories | Depends on a 16-week project |
| Engagement: what users repeat | Requesters raise requests; buyers run events; approvers approve; accounts payable clears exceptions; suppliers bid | Strong for buyers; fragile for requesters |
| Retention: why they return | Orders and invoices are created there; history accumulates; suppliers expect it | Moderate to strong after full rollout |
| Revenue: how usage becomes money | Not automatically. Price is set by modules and scope in a contract. More usage only becomes revenue when a new scope is negotiated. | Weak link between usage and revenue |
| Referral: how users bring others | Procurement leaders recommend to peers and take it to new employers. Suppliers see it but are not converted into leads. | Informal |

### The funnel

```text
Awareness: target accounts that know Aerchain
↓
Acquisition: accounts that take a demo and sign
↓
Activation: accounts with a first end-to-end purchase in production
↓
Engagement: accounts where most requests and events run on the platform
↓
Retention: accounts that renew
↓
Revenue: accounts that add modules, entities or autonomous categories
↓
Referral: accounts that act as references or lead to sister companies
```

### Where is the bottleneck?

**Most likely between activation and expansion.** The reasoning:

- The company's own growth target requires existing customers to grow, as Part 17 shows.
- Expansion needs proof of value, and analytics is the weakest area.
- Expansion also needs categories to move from human approval to agent execution, and no public mechanism shows how that happens.
- The job description makes product managers accountable for adoption after launch, which suggests the company sees this gap too.

A second bottleneck sits at the top: awareness and trust among buyers outside India. That one belongs mostly to marketing and partners. (INFERENCE.)

### Product-led elements worth adding

- **A sandbox on the customer's own past RFQs.** Lets a prospect feel the aha moment before signing.
- **A working return calculator.** The menu item exists and leads nowhere.
- **Supplier-side prompts.** A supplier who also buys could be invited to learn more. Used carelessly this would annoy customers, so it needs their consent.
- **An executive view in Aiera.** A weekly summary a CFO actually reads keeps the sponsor engaged.

## Part 34 — North Star Metric

The North Star Metric should be the **value of purchases completed end to end through Aerchain each month**, summed across customers. “Completed end to end” means the purchase went from a request or RFQ to an award and a purchase order written to the ERP, on the platform.

### Why this metric

- **It measures value delivered.** Savings, shorter cycle times and compliance can only happen on spending that actually flows through the platform.
- **It rises only when real things improve.** More customers live, more entities and categories on board, more requests coming through intake, and more events finishing instead of stalling.
- **It is hard to fake.** Logins and “spend under management” can grow without any work being done. A purchase order in the ERP cannot.
- **It predicts revenue.** Price scales with scope and spend, and expansion follows usage.
- **It gives the company one honest definition.** That would end the confusion of four different public spend figures.

### Metrics I considered and rejected as the North Star

| Candidate | Why it is not the North Star | Where it belongs |
| --- | --- | --- |
| Revenue or ARR | It is the result of value, not the value | Lagging business metric |
| Active users | A requester who logs in once a month can be perfectly served | Input metric, by role |
| Savings delivered | The baseline is disputed and it arrives late | Paired guardrail: value must accompany volume |
| Spend under management | Counts what could flow, not what does | Capacity measure for sales |
| Purchases completed without a person | Excludes strategic spend where agents rightly only advise | Input metric for autonomy |

### Supporting metrics

| Type | Metrics |
| --- | --- |
| Input metrics | Customers and entities live; categories live per customer; share of requests raised through intake; events per buyer per week; supplier response rate; share of agent recommendations accepted unchanged; share of spend at each autonomy level; modules live per customer |
| Leading indicators | Days from go-live to first completed event; requester adoption in week four; supplier response in the first month; number of categories released to agents by day 90 |
| Lagging indicators | Net and gross revenue retention; savings accepted by the customer's finance team; request-to-order cycle time; renewals |
| Guardrail metrics | Savings rate against baseline; walk-away limit breaches; human override rate; extraction error rate on a checked sample; supplier satisfaction; ERP sync failures; support tickets per 100 events; AI cost per event; weeks to go-live |

**Why guardrails matter here.** A team chasing volume could push low-quality purchases through quickly. The guardrails make sure volume comes with savings, accuracy and supplier goodwill.

## Part 35 — Product metrics

The framework below adapts standard software metrics to a product where the customer is a company, the users have five different roles, and half the value depends on outsiders. Daily active users is deliberately absent as a headline, because most users are not meant to be daily.

| Area | Metric | Definition | Why it matters here |
| --- | --- | --- | --- |
| Acquisition | Qualified pipeline | Value of deals past first demo | Traffic matters little; named accounts matter |
| Acquisition | Demo-to-proposal and win rate | Share of demos that become proposals, and proposals that close | Shows whether proof is strong enough |
| Acquisition | Sales cycle and cost to acquire a customer | Days from first meeting to signature; sales and marketing cost per new customer | Decides how fast the company can grow on its cash |
| Activation | Setup completion | Share of the five deployment inputs complete by week | Early warning of a stalled rollout |
| Activation | Time to go-live | Weeks from kickoff to production | The 16-week promise |
| Activation | Time to first value | Days from go-live to first completed purchase | The moment trust begins |
| Activation | Activated accounts | Accounts passing the activation threshold in Part 10 | Separates live from merely installed |
| Engagement | Weekly active users by role | Buyers, approvers, accounts payable weekly; requesters monthly | Each role has its own healthy rhythm |
| Engagement | Feature adoption by module | Share of licensed modules with real weekly use | Finds paid-for modules nobody uses |
| Engagement | Workflow completion | Share of requests that reach a purchase order on the platform | Finds where work leaks back to email |
| Engagement | Channel mix | Share of requests through intake against email | The habit-change measure |
| Retention | Logo retention | Share of customers renewing | Basic health |
| Retention | Gross and net revenue retention | Revenue kept, and revenue kept plus expansion, from last year's customers | The route to $25M |
| Retention | Entity-level retention | Share of live entities still active after 6 and 12 months | Catches quiet shrinkage inside an account |
| Monetisation | ARR per customer and modules per customer | Contract value and breadth | Land-and-expand progress |
| Monetisation | Expansion ARR and discount rate | New revenue from existing customers; average discount given | Pricing power |
| Product quality | Extraction accuracy | Correct fields on a checked sample of bids and invoices | A misread number changes money |
| Product quality | Guardrail breaches | Negotiations ending outside limits; payments outside tolerance | Target is zero |
| Product quality | ERP sync failures and failed workflows | Share of orders or invoices that fail to post; events that error | Finance loses trust quickly |
| Product quality | Response time and support tickets | Time for an agent task to finish; tickets per 100 events | Speed is the promise |
| Satisfaction | Recommendation score by persona | For buyers, requesters and suppliers separately | One blended score hides the unhappy group |
| Satisfaction | Satisfaction after a request | One question when a request closes | Tracks the requester experience |
| Satisfaction | Effort score | “How easy was it?” for requesters and suppliers | Effort drives whether they come back |

### Metrics by module

| Module | Is procurement better? | Are people using it? | Is the AI behaving? |
| --- | --- | --- | --- |
| Intake | Time from request to sourcing start; share complete on first submission | Share of requests raised in Aerchain instead of email | Clarification loops per request; reclassification rate |
| Sourcing | Suppliers invited and responding per event; new suppliers awarded | Share of events created by the agent | Irrelevant suppliers invited |
| Bid analysis and evaluation | Hours from last bid to scored comparison | Share of comparisons used without edits | Extraction accuracy; buyer edits per comparison |
| Negotiation | Savings against first quote and last purchase price | Share of events negotiated end to end by the agent | Limit breaches; override rate; supplier satisfaction |
| Award and order | Request-to-order cycle time | Share of orders pushed to the ERP automatically | Sync failures |
| Vendor onboarding | Days from invitation to active supplier | Share of new suppliers onboarded through the agent | Duplicates and risky suppliers caught or missed |
| Invoices | Time to clear; wrong or duplicate payments prevented | Touchless rate | First-pass match accuracy; exception rate by type |
| Analytics and Aiera | Time to answer a spend question; off-contract spend caught | Weekly active finance and procurement leaders | Share of answers with a correct source |

## Part 36 — Product funnel

The funnel has nine stages, and the product team can directly influence six of them. The largest improvement opportunities sit at evaluation, where proof is thin, and at expansion, where proof is needed again.

| Stage | User goal | Company goal | Key metric | Drop-off risk | Improvement opportunity |
| --- | --- | --- | --- | --- | --- |
| Awareness | Learn what is possible with AI in procurement | Be on the shortlist | Share of target accounts aware | Unknown outside India | Research, analyst coverage, partner introductions |
| Website visit | Check credibility | Convert interest to a demo | Demo requests per visit | Conflicting numbers; placeholder pages | One site, one set of numbers, real case studies |
| Demo | See it on a real category | Win CPO and CFO together | Demo-to-proposal rate | Looks too good; data is cleaner than reality | Sandbox on the customer's own history |
| Activation | Go live safely | First completed purchase | Weeks to go-live; days to first event | Data and integration stalls | Data-readiness check; single-category fast start |
| First value | See a real result | Create an internal success story | Savings and time on first ten events | A poor first event | Choose the first category for clean data and willing suppliers |
| Regular usage | Make it the default | Most requests and events on the platform | Channel mix; events per buyer | Email survives | Email forwarding; status updates; adoption dashboard |
| Paid conversion | Not applicable as a separate stage; payment begins at signature |  |  |  |  |
| Expansion | Get more value | More modules, entities and autonomy | Modules per customer; net revenue retention | No accepted proof | Value record per module; autonomy readiness report |
| Renewal | Confirm the choice | Renew at or above current value | Gross revenue retention | Bundled AI from an incumbent | Savings reconciled with finance through the year |

## Part 37 — Retention and churn

The most likely reasons a customer leaves or shrinks are within Aerchain's control: people not using it, autonomy never being switched on, and savings never being proven. The causes it cannot control, such as an incumbent bundling AI or a sponsor leaving, hurt most when those first three have already weakened the account. No churn data is public, so this is a reasoned ranking. (INFERENCE.)

| # | Cause | Type | Probability | Impact | Controllability | Reasoning |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | Savings and time saved are not proven in a form finance accepts | Customer churn or contraction | High | High | High | Analytics is the weakest area, and proof is needed at the first renewal |
| 2 | Requesters keep using email | User churn | High | High | High | The old channel still works unless the product and the customer's leaders close it |
| 3 | The customer stays in human-approval mode | Contraction; unmet expectations | High | High | Medium to high | Labour savings depend on releasing categories, and no public mechanism supports that decision |
| 4 | A paid-for module goes unused and is dropped | Feature churn; contraction | High | Medium | High | Broad contracts with uneven rollout create shelfware |
| 5 | Hard renegotiation at renewal | Contraction | High | Medium | Medium | The customer's negotiators are professionals with competitor quotes |
| 6 | The incumbent suite or ERP offers similar AI in the existing contract | Customer churn | Medium to high | High | Low | 69% of organisations get procurement AI from existing platforms; SAP's agent runtime is free to the end of 2026 |
| 7 | Rollout stalls on master data or ERP integration | Failed implementation | Medium | High | Medium | Depends on the customer's data and IT time |
| 8 | The executive sponsor leaves | Customer churn | Medium | High | Low | New leaders review tools, and a thin user base offers no defence |
| 9 | Supplier response falls after the launch period | User churn on the supplier side | Medium | High | Medium | Fewer bids means weaker results, which buyers notice |
| 10 | Buyers resist agents they see as a threat | User churn | Medium | Medium | Medium | Passive resistance shows up as heavy overriding and parallel spreadsheets |
| 11 | Custom requests are refused or delayed | Customer churn | Medium | Medium | Medium | The tension between a standard product and enterprise demands |
| 12 | A serious AI error: overpayment, a bad award, a wrong invoice paid | Customer churn; feature switched off | Low to medium | Very high | High | Rare if limits and tests are sound, but one case can end a deployment and travel through the market |
| 13 | The customer is acquired, sells an entity or standardises on a group-wide suite | Customer churn or contraction | Low to medium | High | Low | Outside the product's control |
| 14 | A security or compliance incident | Customer churn | Low | Very high | High | Certifications reduce but do not remove the risk |

### Failed activation in particular

A deployment that goes live but never activates looks like this: the project team is the only group logging in, the first event exposed bad data, suppliers did not respond, and the champion moved on to another project. The account stays on the books for a year and then leaves. The fixes are in Part 13: check data before kickoff, start with one well-chosen category, and give the champion an adoption dashboard.

## Part 38 — Customer feedback

There is almost no independent customer feedback on Aerchain, and that absence is itself the main finding. What exists is positive but far too thin to prove anything.

### What exists

| Source | Volume | What it shows | Reliability |
| --- | --- | --- | --- |
| [Gartner Peer Insights](https://www.gartner.com/reviews/product/aerchain-164583452) | 4.3 out of 5 from 9 ratings; one third 5-star and two thirds 4-star; no ratings below 4 | One review text visible, from a cybersecurity specialist at an IT services firm, April 2026. Gartner's page notes the displayed text may be placeholder wording. | Medium for the rating; low for the text |
| [G2](https://www.g2.com/products/aerchain-aerchain/reviews) | 4.5 from 2 reviews | No review text visible | Low |
| RFP.wiki | A composite score of 3.6 with a stated confidence of 42% | A reviewer-site summary: praises adoption, speed and savings; criticises low review volume, price opacity and missing uptime data | Low to medium; it summarises, with no first-hand reviews |
| Aerchain's own testimonials | Four named executives | Adoption, spend under management, cycle time, savings, supplier participation | Low as evidence; they are selected by the company |
| Reddit, forums, community sites | None found |  |  |

### Clusters

| Cluster | What was said | Source |
| --- | --- | --- |
| Most loved | A purchase order workflow where requests “move through approval stages cleanly”; supplier communication in one place; an interface that is “relatively intuitive compared to older procurement tools”; high user adoption; faster cycles | Gartner excerpts; testimonials |
| Most disliked | Nothing recorded. Gartner shows no critical reviews. |  |
| Common complaints | “Onboarding took some adjustment”; “room to grow on the analytics side” | The one visible Gartner review |
| Missing features | Deeper analytics | Same review |
| UX issues | Initial learning curve | Same review |
| Reliability issues | None reported. No public uptime figure exists either. | RFP.wiki notes the gap |
| Pricing complaints | None from customers. Price opacity is noted by a reviewer site. | RFP.wiki |
| Support complaints | None found |  |
| Competitive complaints | None found |  |

### Frequency and severity

With so little data, frequency means “mentioned at all”. Severity is my judgement of business impact.

| Issue | Frequency | Severity | Priority | Evidence strength |
| --- | --- | --- | --- | --- |
| Analytics depth | Mentioned once; supported by the “coming soon” label | High, because it affects proof at renewal | High | Anecdotal plus product evidence |
| Onboarding adjustment | Mentioned once | Medium | Medium | Anecdotal |
| Lack of public reliability data | Raised by one reviewer site | Medium for enterprise buyers | Medium | Observable fact |
| Price opacity | Raised by one reviewer site | Low to medium; normal for the category | Low | Observable fact |

### How to read the absence of feedback

- **It is partly structural.** Forty to fifty enterprise customers, mostly in India and the Gulf, produce few public reviews. Enterprise users review less than small-business users.
- **It still costs deals.** Global buyers and their advisers look for peer reviews. Zip has 18 Gartner ratings in the same category, SAP's product has 47, and Coupa has 570 reviews on G2.
- **It is fixable cheaply.** A structured review request after each successful go-live would multiply the count within a year. This is a marketing action, but a product manager can support it by building the request into the moment a customer hits a milestone.
- **Do not over-read the scores.** Nine ratings with none below four says customers who chose to review were satisfied. It says nothing about those who did not.

**Anecdote versus evidence.** Everything in this part is anecdotal. The only broad evidence about what customers value is indirect: named enterprises keep their logos on the site, and a strategic investor that is also a customer bought a stake. (INFERENCE.)

## Part 39 — Product discovery

Discovery at Aerchain is hard for structural reasons: few customers, each one large and loud, five kinds of users, and a product whose core behaviour is produced by AI and cannot be understood by interviews alone. The team's central discovery question is what evidence makes a customer trust an agent with more. (INFERENCE.)

### Discovery challenges the team likely faces

| Challenge | Why it is hard here |
| --- | --- |
| Buyer, user and supplier are different people | The CPO's wish list, the buyer's daily friction and the supplier's patience point in different directions |
| A small customer base | With 40 to 50 customers, one large account's request can look like a market signal. The job description warns against prioritising by “stakeholder volume”. |
| Telling product gaps from configuration gaps | Many requests can be met by configuring what exists. Finding out takes time with the customer. |
| Understanding AI behaviour | Whether an agent is good enough is answered by test sets and logs, not by opinions |
| Reaching occasional users | Requesters and suppliers rarely join calls, yet they decide adoption |
| Seeing usage across deployments | Enterprise data separation can limit what product teams may analyse |
| Feature-parity pressure | Rivals announce agents every quarter, which tempts the team to copy instead of deepen |

### Signals worth tracking

- **Unmet needs.** Finance-grade proof of savings. A safe way to increase autonomy. Contract awareness during sourcing.
- **Workflow gaps.** Contracts between award and order. Payment after invoice approval. Supplier performance after delivery.
- **Likely feature requests.** Customer-specific approval paths, more ERP fields, more languages, mobile approvals, reports in the customer's own format. (INFERENCE.)
- **Emerging user behaviour.** Employees paste contracts and quotes into personal AI tools, which Zip's 2026 launch explicitly targets. Suppliers begin to answer with AI. Executives expect to ask questions in a general assistant.
- **Competitive pressure.** Zip into sourcing; Coupa and SAP with bundled agents; Zycus with a live negotiation reference in India.
- **Technology changes.** Open standards for connecting assistants to business systems. Cheaper and better models. Agents on both sides of a negotiation.
- **Market changes.** Workloads rising while headcount falls. Government-led pushes for agentic AI in the Gulf. E-invoicing mandates in more countries.

### Opportunity solution tree

```text
Business outcome: existing customers expand
(more modules, more entities, more spending run by agents)
│
├── Opportunity 1: “Finance does not believe our savings numbers”
│   ├── Solution: a value record per module with an agreed baseline
│   ├── Solution: a baseline sign-off step with finance at kickoff
│   └── Experiment: rebuild last quarter's savings for two customers and
│       compare with their finance team's own figure
│
├── Opportunity 2: “We do not know when it is safe to let the agent decide”
│   ├── Solution: a readiness scorecard per category
│   ├── Solution: shadow mode, where the agent decides silently beside the buyer
│   └── Experiment: 60 days of shadow mode on three categories; measure
│       agreement with buyers and whether the CPO then releases them
│
├── Opportunity 3: “People still email the buyer”
│   ├── Solution: forward any email to intake
│   ├── Solution: status updates in the channels people already use
│   └── Experiment: switch on for two departments; compare channel mix
│       with two similar departments
│
├── Opportunity 4: “Buyers recheck everything the agent produces”
│   ├── Solution: show the source document beside each extracted value
│   ├── Solution: flag low-confidence fields only
│   └── Experiment: measure minutes and edits per comparison before and after
│
└── Opportunity 5: “Supplier responses fade after launch”
    ├── Solution: response insights and smarter reminders
    ├── Solution: give suppliers something back, such as payment status
    └── Experiment: track response rate by supplier cohort for two quarters
```

## Part 40 — Roadmap analysis

Aerchain publishes no roadmap. A few items are confirmed by its own pages and funding announcements, more can be inferred, and my recommendations differ from both in emphasis: proof and trust before breadth.

### Confirmed: publicly announced or directly evidenced

| Item | Evidence |
| --- | --- |
| Contract Agent | Marked “coming soon” on the main site |
| Analytics Agent, with dashboards, spend analysis and demand forecasting | Marked “coming soon” on the main site; an analytics section exists on the newer site |
| Stronger AI capabilities and global expansion | Stated use of the Series A funds |
| A spend intelligence layer using outside factors such as commodity prices and contract expiry dates | Described in Series A press |
| Solution pages by process and industry: tail spend, strategic sourcing, logistics, services and technology buying; manufacturing, FMCG, healthcare, food and beverage | Listed on the site as “soon” |
| More standardisation | Version 5 ships predefined fields, workflows and approvals |
| Documentation and product operations | Open roles for a Technical Writer and a Product Operations Manager |

### Inferred: reasonable conclusions, not announcements

- **Work with Infosys.** Press reports describe Aerchain inside Infosys's AI services and an “Autonomous Sourcing as a Service” offering. That would require features for operators serving many clients.
- **More autonomy.** Aerchain's own research says leaders expect near-autonomous operation in several areas within 12 to 18 months.
- **Gulf readiness.** Local data hosting and Arabic depth, given the Dubai and Al-Futtaim references.
- **Category-specific agents.** The planned process pages suggest packaged solutions for logistics and services buying.
- **Supplier risk data.** A known gap that reviewers note.

### Recommended: what I believe the company should prioritise

| Horizon | Recommendation | Why |
| --- | --- | --- |
| Now (0 to 6 months) | A value record per module that finance accepts | Unlocks renewal and expansion |
| Now | An autonomy readiness scorecard with shadow mode | Turns the autonomy ladder from a slogan into a process |
| Now | A test harness and release gate for every agent, plus replay of any negotiation | Makes agents safe to improve and safe to trust |
| Now | Requests by forwarded email and status updates in existing channels | Fixes the most common adoption leak |
| Now | A data-readiness check before kickoff | Protects the 16-week promise |
| Next (6 to 12 months) | Analytics made generally available, with savings reconciled to finance | Closes the most visible product gap |
| Next | A light contract capability: extract key terms, flag renewals, check awards against contracts, and connect to the customer's existing contract system | Fills the gap without building a full contract product |
| Next | Interfaces and an operator console for partners | A precondition for the Infosys channel |
| Next | An invoice exception workbench focused on the top exception types | Raises the touchless rate where finance feels it |
| Later (12 to 24 months) | Opt-in regional price and supplier benchmarks | A data asset rivals cannot easily match |
| Later | A price element linked to verified outcomes | Aligns revenue with value |
| Later | Open access for AI assistants and a customer-facing agent builder | Makes “operating system” true |
| Later | Services for suppliers, such as early payment | Monetises the supplier base |

## Part 41 — Product prioritisation

Ranked with a scoring framework, the top opportunity is the value record, followed by agent testing, intake through existing channels, the data-readiness check and the autonomy scorecard. Partner tooling scores low but may still be necessary for strategic reasons.

### Why RICE fits, and how I adapted it

RICE scores each idea as Reach × Impact × Confidence ÷ Effort. It fits Aerchain because the company has more ideas than engineers and needs a defensible way to say no. I made two adaptations.

- **Reach is counted in customers, not users.** With about 45 customers, the question is how many accounts benefit in a year.
- **Confidence is taken seriously.** Evidence is thin, so ideas resting on one anecdote are marked down.

**Scales.** Reach: number of customers affected within a year, out of about 45. Impact: 3 is very large, 2 is large, 1 is moderate. Confidence: 100% is strong evidence, 80% is good, 50% is a reasoned guess. Effort: person-months for a small team. All four inputs are my estimates.

| Rank | Opportunity | Problem | User | Evidence | Reach | Impact | Confidence | Effort | Score | Expected business outcome |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | Value record per module | Savings are claimed but not proven to finance | CFO, CPO | Analytics is weak; public numbers conflict; growth depends on expansion | 45 | 3 | 80% | 6 | 18.0 | Higher renewal and expansion |
| 2 | Agent test harness and negotiation replay | Agent changes are risky; trust is fragile | Buyers, CPO, Aerchain's own team | Agents commit money; models change | 45 | 2 | 80% | 6 | 12.0 | Fewer incidents; faster agent improvement |
| 3 | Requests through email and existing chat tools, with status updates | Requesters keep emailing buyers | Requesters, buyers | Promised in 2024; unclear today; common adoption leak | 40 | 2 | 70% | 5 | 11.2 | More spend flowing through the platform |
| 4 | Data-readiness check and guided setup | Rollouts stall on bad master data | Implementation team, champion | 16-week promise; review notes onboarding friction | 20 | 2 | 80% | 3 | 10.7 | Faster go-live; lower services cost |
| 5 | Autonomy readiness scorecard | Customers stay in human-approval mode | CPO, procurement operations | No public promotion mechanism | 30 | 2 | 70% | 4 | 10.5 | More spend run by agents; labour savings realised |
| 6 | Invoice exception workbench | Staff time goes into a few exception types | Accounts payable | Typical of invoice automation; no usage data | 20 | 2 | 70% | 5 | 5.6 | Higher touchless rate |
| 7 | Executive analytics with sourced answers | Leaders cannot self-serve answers | CFO, CPO | Review: analytics has room to grow | 35 | 1 | 70% | 6 | 4.1 | Stronger sponsor engagement |
| 8 | Shared supplier profile across customers | Suppliers re-register for each customer | Suppliers, onboarding teams | 150,000 suppliers claimed; no shared profile visible | 45 | 1 | 50% | 9 | 2.5 | Faster onboarding; start of a network effect |
| 9 | Light contract capability | No contract awareness in the flow | Buyers, legal | “Coming soon”; rivals all have it | 25 | 2 | 50% | 12 | 2.1 | Fewer lost deals on scope |
| 10 | Partner operator console and interfaces | Outsourcers cannot run many clients efficiently | Partner operators | Infosys stake; press-reported plans | 10 | 3 | 40% | 10 | 1.2 | Opens a new channel |

**How the scores are worked out.** Example for rank 1: 45 × 3 × 0.8 ÷ 6 = 18.0. Example for rank 10: 10 × 3 × 0.4 ÷ 10 = 1.2.

**What the framework misses.** RICE rewards near-term breadth. The partner console scores lowest, yet if the Infosys channel is a company-level bet, it must be funded as a strategic investment outside the scoring.

## Part 42 — Top product improvements

If I were the product manager, the ten improvements below are what I would pursue, in this order. The first five strengthen proof, trust and adoption. The last five add breadth. Part 41 gave the scores; this part gives the design of each one. All proposals are mine, built on the evidence cited. (INFERENCE.)

### 1. A value record for every module

| Point | Detail |
| --- | --- |
| Problem | Savings and time saved are claimed by procurement but not accepted by finance. |
| Evidence | Analytics is the weakest area. Aerchain's own public numbers conflict. The company's growth depends on existing customers expanding. |
| Target user | CFO and controller, CPO, and Aerchain's own product managers. |
| Proposed solution | At kickoff, agree a baseline rule per category with finance, such as last purchase price or the average of the last three. Every completed purchase records baseline, final price, volume and the type of saving. Negotiated savings are separated from realised savings, which are confirmed when the invoice is paid. Cycle time and human touches are recorded automatically. Finance signs off each quarter, and the result exports as an evidence pack. |
| Expected user impact | The CPO can defend the numbers. The CFO stops discounting them. |
| Expected business impact | Stronger renewals, easier expansion, a basis for outcome-linked pricing, and one honest public metric. |
| Effort | Medium, about six person-months. The data already exists in the modules. |
| Dependencies | Invoice data for realised savings; analytics; time from the customer's finance team. |
| Risks | Baseline disputes. Some categories will show small or no savings. Real numbers may be lower than marketing numbers. |
| Success metric | Share of reported savings signed off by the customer's finance team; share of customers receiving a quarterly value report; net revenue retention. |
| Priority | 1 |

### 2. A test harness, release gate and replay for agents

| Point | Detail |
| --- | --- |
| Problem | Agents commit money, and their behaviour can change whenever a prompt or underlying model changes. |
| Evidence | Negotiation and invoice agents act on real transactions. Nothing public describes how agent quality is tested. |
| Target user | Aerchain's product and engineering teams first; customer administrators and auditors second. |
| Proposed solution | A fixed set of test cases for each agent, built from past anonymised events: bids with known correct readings, negotiation scenarios with expected bounds, and hostile cases such as instructions hidden in a supplier email. Every change is scored against the set and blocked if the score falls. A replay screen shows each round of a negotiation, the inputs and the rule applied. |
| Expected user impact | Fewer surprises. Any incident can be explained in minutes. |
| Expected business impact | Lower risk of a damaging failure, faster safe improvement of agents, and a trust story sales can show. |
| Effort | Medium, about six person-months, then continuing upkeep. |
| Dependencies | Access to historical events; engineering release process. |
| Risks | Test sets go stale. It competes with feature work for engineering time. |
| Success metric | Incidents per 1,000 agent actions; share of releases that passed the gate; time to diagnose an incident. |
| Priority | 2 |

### 3. Requests where people already are

| Point | Detail |
| --- | --- |
| Problem | Requesters keep emailing buyers, so work bypasses the platform. |
| Evidence | A 2024 founder post promised email, Slack, Teams and WhatsApp intake. Current pages describe chat and upload only. Channel habit is the usual adoption leak. |
| Target user | Requesters and buyers. |
| Proposed solution | A customer-specific address that turns any forwarded or copied email into a request. The agent replies in the same thread for missing details. Status updates arrive in email or the customer's chat tool. Buyers get a one-click “convert to request”. After an agreed date, direct emails get an automatic redirect. |
| Expected user impact | No new habit to learn. Status without chasing. |
| Expected business impact | More spending flows through the platform, which raises every other metric. |
| Effort | Medium, about five person-months. |
| Dependencies | The Omnichannel Hub; matching a sender to an employee record; protection against spoofed emails. |
| Risks | Noise from ambiguous emails. Security of email as an entry point. |
| Success metric | Share of requests arriving through managed channels; share complete on first submission. |
| Priority | 3 |

### 4. A data-readiness check and guided setup

| Point | Detail |
| --- | --- |
| Problem | Rollouts stall on messy master data and unclear approval rules. |
| Evidence | The 16-week promise depends on five customer inputs. The visible review mentions onboarding friction. |
| Target user | The customer's champion and Aerchain's implementation team. |
| Proposed solution | Before kickoff, scan the customer's supplier, item and approval data. Report duplicate suppliers, missing tax details, inactive items, inconsistent units and gaps in approval rules. Give a readiness score and a fix list. Track the five inputs in a setup wizard with visible progress. |
| Expected user impact | No surprises in week eight. |
| Expected business impact | Faster go-live, fewer implementation hours, and a stronger sales promise. |
| Effort | Low to medium, about three person-months. |
| Dependencies | ERP connectors; implementation playbooks. |
| Risks | A poor score could delay signature. Position it as a plan, not a verdict. |
| Success metric | Weeks to go-live; variance from 16 weeks; implementation hours per customer. |
| Priority | 4 |

### 5. An autonomy readiness scorecard with shadow mode

| Point | Detail |
| --- | --- |
| Problem | Customers do not know when it is safe to let an agent decide, so they never do. |
| Evidence | Autonomy levels and waves are described, but no mechanism for promotion is. |
| Target user | CPO and procurement operations. |
| Proposed solution | While an agent assists, record its recommendation beside the buyer's final decision. Show, per category, how often they agreed and the price difference when they did not. Offer shadow mode, where the agent decides silently. When the customer's own thresholds are met over a set number of events, recommend release with a value cap. Sample released purchases weekly, and pull a category back automatically after a breach. |
| Expected user impact | A decision based on evidence instead of nerve. |
| Expected business impact | More spending run by agents, real labour savings, and a natural expansion path. |
| Effort | Medium, about four person-months. |
| Dependencies | Logging of recommendations and decisions; autonomy settings. |
| Risks | Buyers may override to protect their role, which lowers agreement rates. Thresholds will be argued over. |
| Success metric | Share of spend at the “agents execute” level; time for a category to move up; breaches after release. |
| Priority | 5 |

### 6. An invoice exception workbench

| Point | Detail |
| --- | --- |
| Problem | Accounts-payable time goes into a handful of repeating exception types. |
| Evidence | Typical of invoice automation. The page describes routing exceptions but not working them in bulk. No usage data is public. |
| Target user | Accounts-payable staff. |
| Proposed solution | Group exceptions by type: price difference, quantity difference, missing receipt, missing order, duplicate, tax mismatch. Allow bulk resolution with a suggested fix. Suggest tolerance changes from patterns. Let suppliers correct their own errors. |
| Expected user impact | Hours saved each day on the largest queues. |
| Expected business impact | A higher touchless rate, which is the number finance watches. |
| Effort | Medium, about five person-months. |
| Dependencies | Invoice agent; supplier portal. |
| Risks | Bulk actions can spread a mistake. |
| Success metric | Touchless rate; exceptions per 100 invoices; time to clear. |
| Priority | 6 |

### 7. Executive analytics with sourced answers

| Point | Detail |
| --- | --- |
| Problem | Leaders cannot get simple answers without an analyst. |
| Evidence | The one visible review says analytics has room to grow. |
| Target user | CFO and CPO. |
| Proposed solution | A home view with three numbers: spend completed through the platform, savings accepted by finance, and request-to-order time. A weekly summary sent to executives. Answers in Aiera that always show their source records. |
| Expected user impact | Confidence and a reason to stay engaged. |
| Expected business impact | Sponsors who see value defend the product at renewal. |
| Effort | Medium, about six person-months. |
| Dependencies | The value record in improvement 1. |
| Risks | Wrong numbers in front of an executive are worse than none. |
| Success metric | Weekly active finance and procurement leaders; time to answer a spend question. |
| Priority | 7 |

### 8. A shared supplier profile, with consent

| Point | Detail |
| --- | --- |
| Problem | A supplier already verified for one customer starts from zero with the next. |
| Evidence | 150,000 suppliers claimed; no shared profile is visible. |
| Target user | Suppliers and onboarding teams. |
| Proposed solution | A profile the supplier owns, holding documents and verification status, reusable across customers with the supplier's consent. Customer-specific terms stay private. |
| Expected user impact | Onboarding in minutes for returning suppliers. |
| Expected business impact | The first real network effect: each new customer makes onboarding faster for the next. |
| Effort | High, about nine person-months. |
| Dependencies | Legal review; data-protection design; customer agreement. |
| Risks | Customers may see their supplier list as confidential. Liability for verification. |
| Success metric | Onboarding time for returning suppliers; share of suppliers with a reusable profile. |
| Priority | 8 |

### 9. A light contract capability

| Point | Detail |
| --- | --- |
| Problem | The process has no awareness of contracts between award and order. |
| Evidence | The Contract Agent is “coming soon”. Suites and Zip all cover contracts. |
| Target user | Buyers and legal teams. |
| Proposed solution | Read existing contracts and extract price, validity, volume commitments and renewal dates. Alert before renewals. Check awards, orders and invoices against contract prices. Connect to the customer's existing contract and e-signature tools. |
| Expected user impact | Fewer purchases above contract price; no missed renewals. |
| Expected business impact | Removes a common objection in competitive deals. |
| Effort | High, about twelve person-months. |
| Dependencies | Knowledge Hub; document reading. |
| Risks | Scope creep into a full contract product. |
| Success metric | Share of spend linked to a contract; price differences against contract caught. |
| Priority | 9 |

### 10. A partner operator console and interfaces

| Point | Detail |
| --- | --- |
| Problem | An outsourcing partner cannot efficiently run Aerchain for many clients. |
| Evidence | Infosys holds 5.3%. Press reports describe plans to deploy through Infosys BPM. |
| Target user | Partner operators and their managers. |
| Proposed solution | A queue across clients with service-level timers, strict separation between clients, partner-level reporting and documented interfaces. |
| Expected user impact | One operator can serve several clients. |
| Expected business impact | A scalable channel that does not depend on Aerchain's own headcount. |
| Effort | High, about ten person-months. |
| Dependencies | A firm partner commitment; security review of cross-client access. |
| Risks | Building for one partner. Giving the partner control of the customer relationship. |
| Success metric | Clients per operator; revenue through partners. |
| Priority | 10, unless leadership makes the channel a company bet |

## Part 43 — What I would build

With limited engineers and designers, a fixed budget and close executive scrutiny, I would build five things in the first year and explicitly refuse five others. The five I would build all make existing customers more valuable before adding anything new to sell.

### The five highest-impact things to build

| Priority | What | Why this, now | Target user | Problem | Solution in one line | Expected impact | Metric | Effort | Trade-off accepted |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | Value record per module | Expansion and renewal both wait on proof | CFO, CPO | Savings are not believed | Baseline agreed with finance; every purchase recorded against it; quarterly sign-off | Higher renewal and expansion; one honest metric | Share of savings signed off by finance | About 6 person-months | Real numbers may be less flattering than marketing numbers |
| 2 | Autonomy readiness scorecard | It converts the product's central idea into behaviour | CPO, procurement operations | Categories stay under human approval | Agent-versus-buyer agreement by category, shadow mode, recommended release with caps | More spend run by agents; real labour savings | Share of spend at “agents execute” | About 4 person-months | Exposes categories where the agent is not yet good enough |
| 3 | Agent test harness and replay | One failure can undo years of trust | Internal teams, auditors | Agent changes are risky and incidents are hard to explain | Fixed test sets, a release gate, a round-by-round replay | Fewer incidents; faster safe iteration | Incidents per 1,000 agent actions | About 6 person-months, then upkeep | Slower feature releases at first |
| 4 | Requests through existing channels | Volume through the platform drives everything else | Requesters, buyers | Email bypasses the system | Forward any email to create a request; status updates where people work | Higher share of spend on the platform | Share of requests through managed channels | About 5 person-months | More unstructured input to handle |
| 5 | Data-readiness check and guided setup | Protects the 16-week promise and services margin | Champion, implementation team | Rollouts stall on data | Pre-kickoff scan, readiness score, setup wizard | Faster go-live | Weeks to go-live | About 3 person-months | May surface problems before signature |

**Total.** About 24 person-months, which is roughly one small team for a year or two small teams for six months. The order matters: the value record and the scorecard both rely on logging that the test harness also needs, so the three share a foundation.

### Five things I would explicitly not build

| What I would not build | Why not |
| --- | --- |
| A full contract lifecycle product | It is a deep, crowded category. A light capability that reads contracts and checks prices against them, plus connections to the customer's existing contract system, delivers most of the value at a fraction of the cost. |
| Payments and supplier financing | Moving money brings licensing, capital and fraud risks that a company of this size cannot carry while its core is still being proven. Approve invoices and let the ERP and banks pay. |
| A self-serve edition for small businesses | The product's value needs ERP integration, multi-entity rules and negotiation volume. Small firms have none of these, pay little and need support. |
| A customer-facing agent builder, yet | Rivals have one, so it is tempting. Opening agent creation before testing, replay and controls are mature multiplies risk. Build the trust foundation first. |
| One-off custom workflows coded for single customers | Each one slows deployment for everyone and turns a product company into a services company. Meet the underlying need through configuration, or decline with a reason. |

**A sixth, for completeness.** I would not build a supplier discovery marketplace. An investor, IndiaMART, already runs India's largest one. Partnering is faster and cheaper than competing.

## Part 44 — 30/60/90-day PM plan

In the first 90 days as the product manager for one module, I would spend a month learning from customers and data, a month testing hypotheses with prototypes, and a month shipping one measured improvement. The plan assumes ownership of one module, such as intake or negotiation, plus direct responsibility for a few mid-sized customers, which is how Aerchain's job postings describe its product manager roles.

### First 30 days: learn and baseline

| Activity | What I would do |
| --- | --- |
| Learn | Run a full purchase myself in a test environment, from request to purchase order, as each persona. Learn the procurement terms well enough to follow a buyer's day. |
| Read | The module's requirement documents, release notes and open bugs. Six months of support tickets and implementation notes. The contracts and success criteria of my assigned customers. The security questionnaire answers. |
| Analyse | For each customer: where events enter and where they stall in my module, how often people override the agent, and time spent per step. |
| Measure | Set a baseline for five numbers: share of work flowing through the module, completion rate, time per step, override rate and one value measure such as savings or first-time-complete requests. |
| Interview | Five buyers, five requesters, three accounts-payable staff, five suppliers and two customer champions. Inside Aerchain: implementation leads, sales on recent wins and losses, support, and the engineers who built the module. |
| Observe | Sit in on two go-live support sessions. Watch a buyer run a live event on a shared screen. Watch a supplier respond to a request. |
| Deliverable | A one-page diagnosis: the three biggest problems with evidence and size, and written definitions for each metric. |

### Days 31 to 60: hypotheses and experiments

| Step | What I would do |
| --- | --- |
| Develop hypotheses | Examples: requesters email buyers because they cannot see status. Buyers recheck the agent's work because they cannot see the source. Categories stay under approval because nobody has evidence of agent accuracy. |
| Test and validate | Build a working prototype for the top hypothesis myself with AI coding tools, and put it in front of two customers. Run shadow mode on three categories at one customer. Pilot email forwarding in one department. |
| Build the test set | Collect 50 to 100 real cases for my module with known correct outcomes, so every later change can be checked. |
| Prioritise | Score the candidate improvements with RICE, agree the top one with my lead and with engineering, and write the specification with scenarios, edge cases and acceptance criteria. |
| Deliverable | A validated problem, a tested prototype, a test set and an agreed specification. |

### Days 61 to 90: ship, measure, recommend

| Step | What I would do |
| --- | --- |
| Ship | Release the improvement to one customer first, then to the rest once the numbers hold. |
| Measure | Compare against the day-30 baseline. Report what moved and what did not. |
| Change | Start a weekly module review covering adoption, quality and value, shared with engineering and customer-facing teams. |
| Recommend | Present a two-quarter roadmap for the module, with what will be built, deferred and killed, and why. |

### Initial roadmap for the module

| When | Item | Outcome it targets |
| --- | --- | --- |
| Quarter 1 | Metric definitions and baseline; the first shipped improvement; a test set for the module | A measurable starting point and one proven gain |
| Quarter 1 | Value record for this module | Savings or time saved that finance accepts |
| Quarter 2 | Readiness scorecard for this module's categories | First categories released to agents on evidence |
| Quarter 2 | Top two adoption fixes found in discovery | Higher share of work flowing through the module |
| Later | Items that need other modules or partners | Sequenced with other product managers |

**The principle behind the plan.** Do not propose a roadmap in week two. Earn the right to prioritise by first showing the team a baseline they did not have, then one improvement measured against it.

## Part 45 — The first thing I would improve

The first thing I would improve is evidence. I would build a category scorecard that shows, for each category of spending, how much flowed through Aerchain, what it saved against an agreed baseline, and how often buyers accepted the agent's recommendation. It combines improvements 1 and 5 from Part 42 into one thing a customer can see. The reasoning comes first, step by step, then a short version.

### The reasoning, step by step

**1. Clarify the objective.** Aerchain is growing from about $4M toward $25M in yearly subscription revenue. With 40 to 50 enterprise customers, most of that has to come from existing customers doing more on the platform. So the objective I chose is expansion inside current accounts.

**2. Define the target user.** Two people decide whether an account expands. The CPO or procurement operations lead decides how much the agents may do. The CFO decides whether to pay for more. Buyers supply the evidence through their daily use. I will design for the CPO and CFO, using data the buyers generate.

**3. Identify the problem.** After go-live, a customer starts with a person approving everything. To get the full benefit, they must release categories to the agents and add modules. Both decisions need evidence, and today the evidence is weak. The CPO does not know whether the agent is accurate enough for a category. The CFO does not trust the savings figure.

**4. Analyse the current experience.** The product lets the customer set autonomy per agent and per category, logs every negotiation round, and reports savings against a baseline. What is missing publicly is a view that says “in packaging, the agent's choice matched your buyer's 94 times out of 100, and here is what it saved”. Without it, promotion to autonomy is a leap of faith, and the one visible review says analytics has room to grow.

**5. Identify opportunities.**

- A value record so finance accepts the savings.
- A readiness scorecard so the CPO can release categories on evidence.
- Requests through email, so more spending flows through the platform.
- Showing the source beside each extracted value, so buyers stop rechecking.

**6. Prioritise.** The first two address the decision that drives expansion, for every customer, using data the product already holds. The other two increase volume and speed, which matter but do not unlock the next contract. So I would build the first two as one scorecard.

**7. Propose the solution.** A scorecard per category with three parts.

- **Volume.** Purchases and value completed through Aerchain this quarter.
- **Value.** Savings against a baseline rule agreed with finance at kickoff, split into negotiated and realised, plus request-to-order time.
- **Trust.** How often the buyer accepted the agent's recommendation unchanged, and the price difference when they did not.

When a category passes thresholds the customer sets, the product recommends releasing it to the agent with a value cap, and samples those purchases for review each week.

**8. Define metrics.**

- Primary: share of each customer's spend running at the “agents execute” level.
- Secondary: share of reported savings signed off by finance; modules per customer; net revenue retention.
- Guardrails: limit breaches after release; override rate; supplier satisfaction.

**9. Discuss trade-offs.**

- Honest numbers may be lower than marketing numbers. I would accept that, because unproven numbers do not renew.
- Buyers may override more to protect their role. I would show the scorecard to buyers first and position autonomy as removing their low-value work.
- It delays new features such as contracts. I would accept that for two quarters, because breadth without proof does not expand accounts.

### The short version

I would start from the business goal. Aerchain has around 40 to 50 enterprise customers, so growth has to come largely from those customers doing more: more modules, and more spending handled by the agents. Both of those are decisions a customer makes on evidence.

Today the product lets a customer choose how independent each agent is, per category, and it starts with a person approving everything. The gap I see is that nothing tells the customer when a category is ready to move up, and finance does not always trust the savings number. So customers can sit in approval mode, and the labour saving never arrives.

I would build a category scorecard. For each category it shows three things: how much spending went through Aerchain, what it saved against a baseline agreed with finance, and how often the buyer accepted the agent's recommendation without changing it. When a category crosses thresholds the customer has set, the product recommends releasing it to the agent with a value cap, and samples those purchases weekly.

I would measure success by the share of customer spend that runs without a buyer, the share of savings that finance signs off, and net revenue retention. My guardrails would be limit breaches and supplier satisfaction.

The trade-off is that real numbers might look smaller than the marketing ones, and that this comes ahead of new modules like contracts. I think that is right, because proven value is what renews and expands an enterprise account.

## Part 46 — Product strategy

Aerchain should play where its operating knowledge is rare, win on speed to proven value, and turn its relationships into assets that compound. It should avoid a head-on fight with well-funded rivals in the United States.

**1. Where should this product play?** Large, multi-entity groups in India, the Gulf and South-East Asia, in industries that buy physical goods across many sites. Add companies anywhere that own an older suite with poor adoption and want an AI layer on top. Reach global enterprises through Infosys instead of a direct sales force.

**2. How should it win?** By being the fastest route to value a finance head will sign off. That means quick deployment, high supplier and employee adoption, and autonomy that grows on evidence.

**3. What capabilities should it build?** Value measurement that finance trusts. Agent testing and replay. A readiness mechanism for autonomy. Interfaces and tooling for partners. A regional benchmark data asset. A light contract capability.

**4. What should it not build?** A full contract product, payments and financing, a small-business edition, its own supplier marketplace, and customer-specific custom workflows.

**5. Which customers should it prioritise?** Existing customers first, because expansion is the cheapest growth. Then companies that resemble its best-performing accounts. Keep a few marquee accounts as references, but do not let them dictate the roadmap.

**6. Which market should it expand into?** The Gulf first. It already has a government reference in Dubai and a passed review at Al-Futtaim. South-East Asia second. The United States only through partners for now.

**7. What should it defend?** The supplier experience, multi-entity depth, deployment speed, and its reference customers. These are the reasons it wins today.

**8. What could make the product obsolete?** Agents from the ERP or suite vendor that are good enough and included in the contract. A general enterprise AI assistant with safe write access to the ERP. A standard for buyer and supplier agents to transact directly that Aerchain is not part of.

**9. What strategic bets should management make?**

- The Infosys channel, with clear rules on who owns the customer relationship.
- Outcome-linked pricing, once measurement is trusted.
- Opt-in regional benchmarks built from its own customer and supplier base.
- A reputation as the most auditable procurement AI, with published reliability by category.

**10. What strategic bets should management avoid?**

- A direct sales push in the United States against Zip, Levelpath and Coupa.
- A race on the number of agents.
- Custom builds to win logos.
- Dependence on a single partner for most new revenue.

## Part 47 — Strategic risks

The risks that matter most are the ones that are both likely and partly outside Aerchain's control: bundled AI from incumbents and commoditisation of the AI layer. The most damaging single event would be a visible agent failure. Ratings are my judgement. (INFERENCE.)

| Risk | Probability | Impact | Early warning signal | Mitigation |
| --- | --- | --- | --- | --- |
| Incumbents bundle agents at no extra cost | High | High | Deals lost with “our ERP vendor includes this”; SAP's free agent runtime extended past 2026 | Sell as a layer that works across systems; prove value the incumbent cannot measure |
| The AI layer becomes ordinary | High | Medium to high | Rivals match format-free bid reading; customers build basic agents in-house | Invest in context, controls, testing and write-back, which are harder to copy |
| A visible agent failure | Low to medium | Very high | Rising override rates; near-misses in logs; a customer pausing an agent | Test harness, release gates, value caps, replay, weekly sampling |
| Zycus or Zip wins the home-market narrative | Medium to high | High | Indian and Gulf tenders citing analyst rankings; Zip hiring in the region | Analyst relations, published case studies, reference programme |
| Pricing pressure | High | Medium | Rising discounts; customers quoting Coupa and Zip medians | Value record; multi-year terms; outcome-linked element |
| Customer concentration | Medium | High | A few accounts making up a large share of revenue. The actual split is not public. | Broaden the base; multi-year contracts with the largest accounts |
| Platform dependency on ERP and suite interfaces | Medium | High | Interface changes or new fees; a suite blocking overlay access | Certified connectors; partnerships; value independent of any single host |
| Dependency on AI model providers | Medium | Medium | Price rises; behaviour changes after model updates | Work with several models; test every change |
| Partner dependence on Infosys | Medium | Medium to high | Most new pipeline coming through one partner | Keep direct relationships with end customers; add a second partner |
| Services gravity | High | Medium | Go-live times creeping past 16 weeks; rising implementation hours | Predefined configuration; no-code changes; firm rules on custom work |
| Consolidation among rivals | Medium | Medium | Suites buying AI specialists, as Coupa did with Rossum and Tonkean | Stay partner-friendly; be clear on independent value |
| Regulatory change | Medium | Medium | New rules on AI decisions, data localisation or e-invoicing in key markets | Audit trails; in-country hosting options; compliance updates as a feature |
| New entrants | Medium | Medium | Well-funded AI-native startups targeting India or the Gulf | Depth in multi-entity operations; references |
| Economic downturn | Medium | Mixed | Budget freezes lengthen sales cycles, while cost pressure raises interest in savings | Lead with payback period and a small first scope |
| Changing workflows: agents on both sides | Medium | Medium to high | Suppliers answering with AI; standards emerging for agent-to-agent trade | Take part early; keep limits and logs firm |
| Credibility of public claims | Medium | Medium | Buyers or analysts questioning the conflicting figures | One definition, one number, one website |
| Talent and execution | Medium | Medium | Attrition; slow hiring | Clear ownership and realistic workloads |
| Open-source alternatives | Low | Low | Not materially applicable today; no credible open-source procurement suite targets this buyer | Monitor only |

## Part 48 — Product obsolescence

If Aerchain disappeared tomorrow, how much it hurt would depend entirely on how deeply each customer had deployed it. For some it would be an inconvenience; for others, purchase orders and invoice approvals would stop. That spread reveals where the product's true value sits. (INFERENCE throughout.)

| Customer situation | What they would do | Disruption |
| --- | --- | --- |
| Sourcing only, with buyers still approving everything | Go back to email, spreadsheets and the ERP within days | Low to medium. Slower events and weaker prices, but nothing stops. |
| Request-to-order with ERP write-back | Create orders by hand in the ERP; rebuild approval routing by email | High. Requests pile up, approvals lose their trail, buyers are swamped. |
| Full scope including invoices | Match and approve invoices by hand; suppliers chase payment | Very high. Payment delays and audit gaps appear within weeks. |
| Categories running autonomously | Staff must take back purchases nobody has handled for months | Very high where autonomy is real, because the capacity no longer exists. |
| Overlay on another suite, as at the Dubai Government | Fall back to the suite underneath | Low to medium. The suite still works; the speed and automation are lost. |

### The elements of the loss

- **Alternative products.** Zycus, Coupa, SAP Ariba or Zip could replace the functions, after a project of several months to over a year.
- **Internal tools.** The ERP's own purchasing screens would carry the load in the meantime.
- **Manual processes.** Email and spreadsheets return for requests, quotes and comparisons.
- **Consultants and outsourcers.** Some companies would add temporary staff or use an outsourced team.
- **Migration difficulty.** Approval rules, templates and playbooks would have to be rebuilt elsewhere.
- **Data loss.** Orders and invoices survive in the ERP. Price benchmarks, negotiation history, supplier response records and specifications in the Knowledge Hub would be lost unless exported.
- **Workflow disruption.** Requesters lose status tracking. Suppliers lose their familiar channel.
- **Revenue impact for the customer.** Indirect: slower buying can delay production or projects, and savings shrink.
- **Compliance impact.** A gap in approval evidence and audit trail from the day it stops.

### What this reveals about the product's true value

The product's lasting value is operating capacity and control, not intelligence. Where Aerchain is the system through which orders and invoices actually flow, and where agents do work no person does any more, it is very hard to live without. Where it is an accelerator beside an old process, it is easy to drop. The strategy that follows is to deepen every deployment toward write-back, invoices and real autonomy, because that is where the product becomes essential.

## Part 49 — Switching costs

Switching away from Aerchain costs a customer a moderate amount overall, with integration and workflow the heaviest parts. The cost is lopsided: moving to a legacy suite is expensive, while moving to another light AI layer is not.

| Switching cost | Rating | Reasoning |
| --- | --- | --- |
| Data | Medium | Legal records stay in the ERP. Benchmarks, specifications and negotiation history are valuable and may not transfer cleanly. Export options are not public. |
| Workflow | Medium to high | Approval matrices, templates and negotiation playbooks for every entity are encoded in the product. |
| Integration | High | Two-way ERP sync for requisitions, orders, receipts and invoices must be rebuilt and retested. |
| Training | Low to medium | The interface is described as intuitive, and chat intake needs little training. That cuts both ways. |
| Organisational | Medium | Another change programme for buyers, requesters and finance. |
| Behavioural | Medium | Suppliers and requesters have formed habits around its channels. |
| Contractual | Medium | Annual or multi-year subscriptions. Terms are not public. |
| Implementation | Medium against a light rival; high against a suite | By Aerchain's own comparison, suites take about 14 months and intake platforms about 9. |

**Second-order effect.** Aerchain's fast, light deployment lowers the barrier to adopting it and also the barrier to replacing it. The way to raise switching costs without hurting customers is to add value that accumulates: history, proven autonomy by category, and supplier relationships.

## Part 50 — Value chain

Aerchain sits between the moment a business need appears and the moment finance pays for it. It depends on the ERP at both ends and leaves contracts and payment to other systems.

```text
Upstream
  Demand planning and budgets (ERP, production planning)
  Category strategy and approved supplier lists
  An employee's need
↓
Aerchain
  Intake → sourcing → bid analysis → evaluation → negotiation → award
  → purchase order written to the ERP
  Vendor onboarding alongside
  Invoice reading, matching and approval
↓
Downstream
  Goods receipt and inventory (warehouse, ERP)
  Contract storage and signature (other systems)
  Payment (ERP, treasury, banks)
  Supplier performance management
  Accounting, audit and reporting
```

| Element | Detail |
| --- | --- |
| Inputs | Requests, budgets, master data, supplier lists, past prices, contracts, goods receipts |
| Dependencies | The ERP for master data and for recording orders and receipts; suppliers' willingness to respond; AI model providers |
| Outputs | Approved requests, awarded suppliers, purchase orders, onboarded suppliers, approved invoices, audit trails, spend data |
| Adjacent products | ERP purchasing modules, contract management, invoice and payment automation, supplier risk data, travel and expense tools, inventory planning, working-capital finance |
| Vertical integration opportunities | Contract awareness between award and order. Payment execution and early-payment finance after approval. Demand signals that trigger sourcing before a request is raised. |
| Horizontal expansion opportunities | Services buying, freight and logistics buying, software and IT buying, capital projects, public tenders |

## Part 51 — Expansion opportunities

The best expansion moves are the ones that reuse what Aerchain already has: deeper automation of tail spend, the Gulf, and partner-led reach to larger enterprises. Market sizes are given as relative judgements because reliable figures for each slice are not publicly available; where a sourced regional figure exists, I cite it.

| Opportunity | Type | Market size | Strategic fit | Competitive intensity | Execution difficulty |
| --- | --- | --- | --- | --- | --- |
| Tail-spend autopilot as a packaged offer | Vertical: deeper functionality | Large. Most transactions in most companies are tail spend. | Very high. Uses the negotiation agent and autonomy levels. | High: Fairmarkit, Pactum, Zip | Medium |
| Analytics and spend intelligence | Vertical | Medium to large. One estimate puts spend analysis at about a third of procurement software revenue. | High. Needed for proof. | High: suites, Sievo | Medium |
| Contract awareness | Vertical | Large as a category | Medium. Fills a gap. | Very high | High if built fully; medium if light |
| Supplier risk monitoring | Vertical | Medium | Medium | High | Medium; needs data partners |
| Services procurement | Horizontal: new use case | Large | Medium. Bids are harder to compare. | Medium: Globality | High |
| Freight and logistics buying | Horizontal | Medium to large | Medium to high for manufacturing and consumer-goods customers | Medium | Medium |
| Software and IT buying | Horizontal | Medium | Low to medium | Very high: Zip and others | Medium |
| The Gulf | Geographic | Middle East and Africa procurement software was about $0.48B in 2025 by one estimate | High. References exist. | Medium | Medium; needs local presence and hosting |
| South-East Asia | Geographic | Part of Asia Pacific, about $2.0B in 2025 and the fastest-growing region by the same estimate | High. Similar multi-entity, email-first conditions. | Medium | Medium |
| United States and Europe, directly | Geographic | Largest. North America is about a third of the market. | Low today. Little brand or proof. | Very high | High |
| Global enterprises through Infosys | Segment: upward | Large | High if the partner commits | Medium | Medium to high; needs partner tooling |
| Upper mid-market with a standard package | Segment: downward | Large by count; small per deal | Medium. Version 5's predefined setup helps. | Medium | Medium; support cost is the risk |
| Partner interfaces and an agent builder | Platform | Hard to size | High long-term | High | High |
| Regional benchmarks as a data product | Platform | Unproven | High. Hard for others to copy. | Low | High; needs consent and legal care |

**Recommended order.** Tail-spend autopilot and analytics first, because they make current customers more valuable. The Gulf and the Infosys channel next, because they add customers with existing proof. Everything else later.

## Part 52 — Product portfolio strategy

Aerchain is one product sold as modules, not a set of separate products. It has already moved from a point solution to a suite, and it is now claiming to be a platform. The suite step is credible in its niche. The platform step is not yet real.

| Portfolio element | Assessment |
| --- | --- |
| Core product | Sourcing: RFQ creation, bid analysis, evaluation, negotiation, auctions and award. The oldest and best-proven part. |
| Adjacent products | Intake upstream; invoices and vendor onboarding downstream; analytics and Aiera across. |
| Bundles | SpendOS is the bundle of everything. No named smaller bundles are public. |
| Cross-sell | Sourcing customers add intake to capture more requests, then invoices to bring in finance. Invoice customers, as AB InBev began, add sourcing. |
| Upsell | More entities, more categories, and higher autonomy levels. |
| Platform strategy | Internal platform pieces exist. Nothing is open to customers or partners yet. |
| Cannibalisation | Low. One watch-point: if any pricing is per user, autonomy reduces the number of users needed. Pricing on spend and modules avoids this. |
| Suite strategy | “Eight modules on one data model” is the suite claim. |

**Direction: point solution to suite, done; suite to platform, claimed.**

**Will it work?**

- **The suite step is likely to work in the niche.** Mid-sized and large groups in its home regions want fewer vendors and one view of spending, and they cannot afford a year-long suite project. Shared data across modules also makes the agents better.
- **The suite step is risky in the open market.** Calling itself a full suite invites comparison with Gartner Leaders on contracts, analytics and payments, where it is behind.
- **The platform step needs work that has not been announced.** Open interfaces, partner tooling and an agent builder would have to exist.
- **The practical answer is two motions.** Sell the suite to companies with no suite. Sell the AI layer to companies that already have one. The same product can serve both if packaging and messaging are kept distinct. (INFERENCE.)

## Part 53 — Business model canvas

The canvas shows a classic enterprise software business with one unusual feature: its most valuable partner is also an investor and a customer.

| Block | Aerchain |
| --- | --- |
| Customer segments | Large, multi-entity enterprises in consumer goods, manufacturing, real estate, healthcare, telecom and government, mainly in India, the Gulf and Asia. Within each: procurement, finance and IT as buyers; buyers, requesters, accounts payable and suppliers as users. |
| Value propositions | Routine procurement work done by agents inside limits the customer sets. Live in about 16 weeks on the existing ERP. Suppliers respond without a login. Savings, speed and control with an audit trail. |
| Channels | Direct enterprise sales; founder relationships; corporate accelerators historically; Infosys as an emerging partner channel; research reports and a small content programme. |
| Customer relationships | High-touch: a joint implementation project, close support after go-live, and product managers who own customer outcomes. |
| Revenue streams | Annual subscriptions priced on modules, scope and spend managed. Probably implementation fees (HYPOTHESIS). |
| Key resources | The product and its agents; ERP connectors; reference customers and passed security reviews; procurement domain knowledge; a Bengaluru engineering team; Series A cash. |
| Key activities | Product and AI development; implementation and integration; enterprise selling; security and compliance upkeep; customer success. |
| Key partners | Infosys (investor, customer logo, channel); IndiaMART (investor, possible supplier data); ERP vendors as integration hosts; AI model and cloud providers; Scalekit for login. |
| Cost structure | Mostly people: engineering, implementation and sales. Then AI model usage and hosting. Total expenses were about ₹19.5 crore in FY25. |

## Part 54 — Lean canvas

The lean canvas exposes the weakest box clearly: the unfair advantage is real but thin.

| Block | Aerchain |
| --- | --- |
| Problem | 1. More purchase requests than buyers can handle. 2. Manual work in email, PDFs and spreadsheets. 3. Legacy suites that take over a year to install and that employees avoid. Existing alternatives: the ERP plus email, legacy suites, outsourcers. |
| Customer segments | Multi-entity enterprises with a small procurement team and email-first suppliers. Early adopters: fast-growing or operationally stretched companies with a sponsor under cost pressure, as WeWork and AB InBev's African operations were. |
| Unique value proposition | Procurement that runs itself where it safely can, live in a quarter, on what you already have. |
| Solution | An agent for each step from request to invoice, on one data model; autonomy set per category; no-login supplier response; ERP write-back. |
| Channels | Enterprise sales, partners, references, research content. |
| Revenue streams | Subscriptions by module, scope and spend. About $4M ARR per the job description. |
| Cost structure | Engineering, implementation, sales, AI and hosting. |
| Key metrics | Value of purchases completed through the platform; share of spend run by agents; savings accepted by finance; weeks to go-live; net revenue retention. |
| Unfair advantage | Operating knowledge of complex groups in its home markets; marquee references and passed security reviews; a strategic investor with distribution. None of these is permanent, and none is a technology barrier. |

## Part 55 — Product-market fit

Aerchain has emerging product-market fit: strong within a narrow segment, unproven beyond it. The evidence for fit is real customers who stay and grow. The evidence against calling it strong is the small scale after seven years and the lack of published retention data.

| Signal | Evidence | Reading |
| --- | --- | --- |
| Retention | No figures published. WeWork appears as a customer in a 2018 to 2019 profile and still gives a testimonial. AB InBev has been a customer since 2020. | Positive but anecdotal |
| Organic growth | Revenue rose about 86% in FY25. It had dipped the year before, from about ₹6.4 crore to ₹5.4 crore. | Mixed |
| Long-run revenue growth | About $0.5M ARR in 2021 to about $4M in 2026. That is eight times in five years, or roughly 52% a year compounded. | Solid, not explosive |
| Customer references | Four named senior executives give testimonials. Well-known logos are displayed. | Positive |
| Expansion | AB InBev's scope grew from two countries to ten, and later results cite negotiation as well as invoices. | Positive for one account |
| Recommendation scores | Not published. | Unknown |
| Usage | Cars24 cites 99% adoption. No product-wide data. | Anecdotal |
| Customer adoption | 40 to 50 enterprise customers after about seven years. | Slow accumulation |
| Customer concentration | Not published. With this few customers and logos this large, concentration is likely. | Risk (HYPOTHESIS) |
| Competitive wins | Aerchain says eight wins replaced SAP Ariba and one replaced GEP. | Positive if accurate; unverified |
| Strategic validation | Infosys, a customer logo, bought 5.3%. Pavestone led a $13M round. | Positive |
| Independent reviews | 9 Gartner ratings, 2 on G2, none below four stars. | Too few to count |

### How the rating was worked out

- **The growth arithmetic.** $4M ÷ $0.5M = 8. The fifth root of 8 is about 1.52, which means about 52% growth a year for five years.
- **Why not “strong”.** Strong fit usually shows as customers pulling the product faster than the company can sell it. Forty to fifty customers in seven years, revenue of about $1.2M in FY25, and a year of decline do not show that.
- **Why not “weak”.** Demanding enterprises have stayed for years, expanded and lent their names. A strategic investor that uses the product bought in.

**Rating: Emerging.** Fit is clearest for multi-entity groups in India and the Gulf that need speed and supplier-friendly sourcing. It is unproven for global enterprises choosing between analyst-ranked suites, and for the autonomous end of the product, where only one customer result is public. (INFERENCE.)

## Part 56 — Market analysis

The global procurement software market is about $9B to $11B in 2026 and growing 8% to 10% a year. Aerchain's realistic home market is about $1.6B, and its stated $25M revenue goal would be about 1.5% of that. Market size is not the constraint; proof and distribution are.

### Sizing, with the working

| Layer | Estimate | How it is derived | Confidence |
| --- | --- | --- | --- |
| TAM: total market | $8.8B to $10.9B in 2026 | [GM Insights](https://www.gminsights.com/industry-analysis/procurement-software-market) gives $8.77B for 2026. [Grand View Research](https://www.grandviewresearch.com/industry-analysis/procurement-software-market-report) gives $10.9B. The two firms define the market slightly differently. | Medium. FACT that these are the published estimates. |
| SAM: the part Aerchain can serve now | About $1.6B | GM Insights puts Asia Pacific at $2.01B and Middle East and Africa at $0.48B in 2025, together $2.49B. Large enterprises are 65% of the global market. $2.49B × 65% = $1.62B. | Low to medium. It assumes the large-enterprise share is the same in these regions. It includes countries where Aerchain has no presence and excludes partner-led deals elsewhere. |
| SOM: what it can realistically win | $25M as the company's own stated target | $25M ÷ $1.62B = 1.5% of SAM, and about 0.25% of the global market. Today's $4M is about 0.25% of SAM. | The target is FACT from the job description; whether it is reachable is judgement. |

**A bottom-up cross-check.** $25M at today's average of about $90K per customer needs about 280 customers. At $200K per customer it needs 125. Reliable counts of large multi-entity enterprises across India, the Gulf and South-East Asia are not in the sources I opened. If there are a few thousand such companies, the target needs a few percent of them. (HYPOTHESIS; low confidence.)

**A second way to see the market.** Agents replace labour as well as software. Budgets for procurement staff and outsourced procurement are larger than software budgets, which is why an outsourcer such as Infosys is interested. I have not sized this pool.

### Market dynamics

| Factor | Assessment |
| --- | --- |
| Growth | 8.3% a year to 2035 by GM Insights; 10.0% a year to 2033 by Grand View Research. Asia Pacific is the fastest-growing region. |
| Adoption drivers | Workload up 8% with headcount down 0.9% and budgets down 0.4% in 2026, per the Hackett Group. Technology spending up 6.1%. 80% of procurement executives call AI the most transformational trend. |
| Barriers | Only 12% of organisations report large-scale AI implementation. Gartner found 74% of procurement leaders say their data is not AI-ready. Change management and trust slow everything. |
| Regulatory factors | Public procurement rules, e-invoicing mandates, supply-chain reporting laws and data-protection laws such as GDPR and India's DPDP Act. These raise demand for audit trails and compliant invoicing. |
| Technology trends | AI agents, open standards connecting assistants to business systems, falling model costs, and agents on the supplier side. |
| Competitive intensity | Very high. By one estimate the top five vendors hold about 61% of the market, with SAP alone at 27%. |

## Part 57 — Category maturity

Procurement software as a whole is a mature category. The agent-led slice Aerchain sells in is emerging and growing quickly. Aerchain therefore faces mature-market competitors in an early-market race.

| Dimension | Procurement suites overall | AI agents for procurement |
| --- | --- | --- |
| Stage | Mature | Emerging to growing |
| Feature commoditisation | High. Core workflow features are standard. | Fast. Within about a year, every major vendor announced agents. |
| Pricing pressure | Moderate; large discounts are normal | Rising, as incumbents bundle agents into existing contracts |
| Buyer sophistication | High. Buyers are procurement professionals. | Low in AI specifically. Most are still piloting. |
| Innovation rate | Slow historically | Very high. Launches every quarter. |
| Consolidation | Ongoing. The top five hold about 61%. | Beginning. Coupa bought Rossum and Tonkean in 2026. |
| New entrants | Few | Many. Gartner's “AI Agents for Procurement” category lists 17 products, six of them with no reviews yet. |

**Implication.** In an emerging slice of a mature market, incumbents can absorb the innovation if they move fast enough, and in 2026 they are moving. A challenger wins only by being meaningfully better for a specific kind of customer, or by being bought. (INFERENCE.)

## Part 58 — Product life cycle

Aerchain's current product is in early growth, after an unusually long introduction. The company is seven years old, but the agent-based product it sells today is about two.

| Evidence for early growth | Evidence it is not yet in full growth |
| --- | --- |
| Revenue up about 86% in FY25 | Revenue of about $1.2M that year is small |
| First institutional round in March 2026; strategic stake in August 2026 | Two agents still “coming soon” |
| Rebrand and new positioning in 2025 to 2026 | Very few independent reviews |
| Hiring in product operations, documentation, sales development and marketing | Marketing sites still carry placeholders |
| Named replacements of older suites | No evidence of demand outrunning sales capacity |

The original auction and sourcing tool went through its own introduction and modest growth from 2019 to 2023. The April 2025 rebrand effectively restarted the cycle with a new product story. (INFERENCE.)

## Part 59 — Customer ROI

On conservative assumptions, a company with $500M of yearly purchases would gain about $11.9M over three years for a cost of under $1M. That is roughly a quarter of the value Aerchain's own model claims, and still more than ten times the cost. Every figure below is illustrative.

### Aerchain's claim

Aerchain's model says that on $500M of managed spend, the three-year value is $45.2M with payback in eight months. $45.2M ÷ 3 is about $15M a year, which is 3% of the full $500M. That assumes nearly all spending is influenced from the first year.

### An illustrative model with conservative assumptions

| # | Assumption | Value | Basis |
| --- | --- | --- | --- |
| A1 | Spending actually run through the platform | 20%, 40% and 60% of $500M in years 1, 2 and 3 | My assumption. Rollout happens category by category. |
| A2 | Extra savings on that spending | 3% | Aerchain's FMCG write-up cites up to 3% from wider supplier participation. Its 8.4% average claim is higher; I use the lower figure. |
| A3 | Share of negotiated savings that reach the accounts | 60% | My assumption. Some savings are lost to volume changes and off-contract buying. |
| A4 | Buyer time saved | 3 hours on each of 10,000 requests a year | Request volume from Aerchain's FMCG example. Hours are my assumption. |
| A5 | Invoice time saved | 10 minutes on each of 90,000 invoices a year, from year 2 | Invoice count is my estimate for $500M of spend. Minutes are my assumption. |
| A6 | Cost of a full-time employee | $20,000 a year, fully loaded | My assumption for India. It would be several times higher elsewhere. |
| A7 | Subscription | $250,000 a year | HYPOTHESIS: a multi-module deployment at about three times the estimated average contract. |
| A8 | One-time implementation and internal effort | $200,000 | HYPOTHESIS. |

**The invoice count in A5.** Assume 70% of spending is direct materials with invoices averaging $25,000: $350M ÷ $25,000 = 14,000 invoices. Assume 30% is indirect with invoices averaging $2,000: $150M ÷ $2,000 = 75,000 invoices. Total about 90,000.

| Line | Year 1 | Year 2 | Year 3 | Three years |
| --- | --- | --- | --- | --- |
| Spending through the platform | $100M | $200M | $300M |  |
| Savings: spend × 3% × 60% | $1.80M | $3.60M | $5.40M | $10.80M |
| Buyer time: 30,000 hours is 15 staff; at $20,000 each is $300,000; half in year 1 | $0.15M | $0.30M | $0.30M | $0.75M |
| Invoice time: 15,000 hours is 7.5 staff; at $20,000 each is $150,000 | $0 | $0.15M | $0.15M | $0.30M |
| Total benefit | $1.95M | $4.05M | $5.85M | $11.85M |
| Subscription | $0.25M | $0.25M | $0.25M | $0.75M |
| Implementation and internal effort | $0.20M |  |  | $0.20M |
| Total cost | $0.45M | $0.25M | $0.25M | $0.95M |
| Net benefit | $1.50M | $3.80M | $5.60M | $10.90M |

**Results.**

- **Return.** $10.9M net on $0.95M of cost is about 11 times.
- **Payback.** Year-1 benefit of $1.95M is about $162,000 a month. First-year cost of $450,000 is recovered in about three months of live operation. Adding the four-month deployment gives about seven months from kickoff, close to Aerchain's eight-month claim.
- **Against the claim.** $11.85M is about 26% of Aerchain's $45.2M.
- **Stress test.** Halve the coverage and halve the savings rate: $50M × 1.5% × 60% = $450,000 in year 1. That alone covers the first-year cost.

**Not counted.** Duplicate or wrong payments prevented, lower risk from better supplier checks, faster production because materials arrive sooner, and the value of buyers' time moving to strategic work.

**What the model shows.** Price is not the barrier to buying Aerchain. Even pessimistic assumptions pay back within a year. The real barriers are trust, change and proof, which is why the product priorities in Part 42 focus on those. It also shows the largest driver by far is savings on spending that actually flows through, so adoption and coverage matter more than any other lever. (INFERENCE.)

## Part 60 — Buy versus build

For a typical enterprise, buying is the rational choice, because the hard parts are not the AI demo but the controls, integrations and upkeep around it. Building makes sense only for a few very large companies with unusual processes and strong engineering teams.

| Dimension | Buy Aerchain | Build internally |
| --- | --- | --- |
| Cost | About $250,000 a year plus a one-time $200,000, on the assumptions in Part 59 | A team of about eight for 15 months, then about four people permanently. At $100,000 per person a year that is about $1M to build and $400,000 a year to run. All figures are HYPOTHESIS. |
| Time | About 4 months to go live | 12 to 18 months to reach intake, RFQs and bid reading for one ERP |
| Customisation | Configurable within a standard model | Unlimited, which is both the attraction and the trap |
| Maintenance | Vendor handles model changes, ERP upgrades and new formats | The company owns every change forever |
| Security | Certifications and passed reviews exist | Internal tools need the same controls, plus a supplier-facing surface the company must secure |
| Reliability | Shared across customers and tested at volume | Depends on one internal team |
| Talent | None needed beyond administrators | AI engineers and procurement specialists, both scarce |
| Opportunity cost | Engineers stay on the company's own products | Engineers work on procurement instead |
| Scalability | Multi-entity, multi-currency and 30+ languages already built | Each added entity or language is new work |
| Learning | Benefits from what the vendor learns across customers | Learns only from its own data |

**Why a customer would rationally buy.** The value comes from savings and time, which start months earlier with a bought product. Procurement software is not what makes a consumer-goods or real-estate company win, so engineering time is better spent elsewhere. The risky parts, such as write-back to the ERP, negotiation limits and audit trails, are exactly the parts a vendor has already hardened.

**When building is rational.** A very large, technically strong company with processes no vendor supports. Even there, the common pattern is to buy the platform and build thin custom agents on top. That is another argument for Aerchain opening its platform. (INFERENCE.)

## Part 61 — Product gaps

Aerchain's most important gaps are not missing modules. They are the missing means of proving value and earning trust. Contracts and analytics are the gaps a competitor will point to; value measurement and an autonomy mechanism are the gaps that actually limit growth.

### Table-stakes gaps: capabilities customers expect

| Gap | Evidence |
| --- | --- |
| Contract awareness | Contract Agent marked “coming soon”; every suite and Zip have it |
| Finance-grade analytics | Analytics Agent marked “coming soon”; the visible review asks for more |
| Public reliability information | No uptime figure, status page or service-level commitment published |
| Help centre and documentation | None public; a technical writer is being hired |
| Requests and approvals inside email and chat tools | Promised in 2024; unconfirmed today |
| Named supplier risk data sources | Not disclosed |
| Stated data-location options | Not disclosed |

### Strategic gaps: needed for long-term competitiveness

| Gap | Why it is strategic |
| --- | --- |
| A value record finance accepts | Renewal, expansion and outcome-linked pricing all depend on it |
| A mechanism for promoting categories to autonomy | Without it, the central product idea does not turn into results |
| Agent testing, release gates and replay | Protects against the one failure that could undo trust |
| An open platform: interfaces, assistant access, agent builder | Rivals are opening up; “operating system” requires it |
| Partner tooling | A precondition for the Infosys channel |
| A cross-customer data asset | The only route to a moat that blocks competitors at the point of sale |

### Delight gaps: could create real differentiation

| Gap | What it would feel like |
| --- | --- |
| Category scorecards | “Here is what flowed, what it saved and how often the agent was right” |
| Regional price benchmarks | “You paid 6% above what similar companies pay for this packaging grade” |
| Value for suppliers | Payment status, a reusable verified profile, perhaps early payment |
| Proactive sourcing | The agent proposes an event before the request arrives, from demand and contract-expiry signals |
| An executive weekly brief | Three numbers and one decision, delivered to the CFO |
| Published reliability by category | A public record of how agents perform, which no vendor offers |

### Overall ranking by importance

1. Value record
2. Autonomy promotion mechanism
3. Agent testing and replay
4. Finance-grade analytics
5. Requests through existing channels
6. Partner tooling and open interfaces
7. Contract awareness
8. Public reliability and documentation
9. Cross-customer benchmarks
10. Supplier-side value

## Part 62 — Final product scorecard

Aerchain scores 6.5 out of 10 overall: a good product for a specific customer, held back by proof, monetisation and defensibility. Scores are my judgement from public evidence.

| Dimension | Score / 10 | Evidence | Biggest issue | Recommendation |
| --- | --- | --- | --- | --- |
| Product-market fit | 6.5 | Long-standing marquee customers; 86% growth in FY25; strategic investor | Small scale after seven years; no retention data | Deepen the niche before widening |
| Customer value | 7.5 | Testimonials on adoption, cycle time, savings; return model holds on conservative assumptions | Value is asserted more than measured | Build the value record |
| UX | 6.5 | “Relatively intuitive”; no-login suppliers; chat intake | Onboarding adjustment; explainability unknown | Show sources; add role-based guidance |
| Activation | 5.5 | 16-week go-live; wave-based rollout | Long path to proven value; depends on customer data | Data-readiness check; single-category fast start |
| Retention | 7.0 | ERP write-back, history and supplier habits create dependence | Shallow deployments are easy to drop | Push every account to write-back and autonomy |
| Monetisation | 5.0 | About $80K to $100K per customer; under 1% of claimed value captured | Price not linked to realised value | Add an outcome-linked element once measurement is trusted |
| Enterprise readiness | 7.5 | SOC 2 Type II, ISO 27001, SSO, audit logs; hard reviews passed | No public uptime, data-location or AI data-handling statement | Publish a trust page |
| Integrations | 7.0 | Connectors for major ERPs and rival suites; overlay proven in Dubai | Few integrations beyond ERP; no public interfaces | Add chat tools, contract systems and risk data |
| AI | 7.5 | Bid reading, negotiation and intake are real uses; 65% of RFQs auto-negotiated at one customer | Testing and controls not visible; marketing overreach | Test harness; publish reliability |
| Differentiation | 6.5 | Supplier experience, autonomy ladder, overlay, speed | Rivals converging quickly | Lead on proof and trust, not agent count |
| Defensibility | 5.0 | Per-customer lock-in only | No cross-customer moat | Benchmarks and partner ecosystem |
| Go-to-market | 5.5 | Strong logos; Infosys stake | Thin marketing and reviews; conflicting numbers | One site, one set of numbers, a review programme |
| Scalability | 5.5 | Version 5 standardisation; no-code framework | High-touch delivery; about $40K revenue per employee | Reduce implementation hours; enable partners |
| Overall product strength | 6.5 | Real capability and real customers | Proof, monetisation, moat | Make value measurable, then scale through partners |

## Part 63 — One-page product strategy

| Element | Summary |
| --- | --- |
| Product | Aerchain SpendOS: AI agents that run procurement from request to invoice, with autonomy set by the customer |
| Target customer | Large, multi-entity groups in India, the Gulf and Asia, in physical-goods and multi-site industries; plus companies wanting an AI layer on an existing suite |
| Core problem | More purchase requests than buyers can handle, manual work in email and spreadsheets, and suites that are slow to install and avoided by users |
| Value proposition | Routine procurement done by agents inside your limits, live in about 16 weeks on your existing ERP |
| Primary use case | Turning a purchase request into a competitive, compliant purchase order with minimal buyer effort |
| Core workflow | Request → RFQ → bids compared → scored → negotiated → awarded → order written to the ERP → invoice matched |
| Business model | Annual enterprise subscription priced on modules, scope and spend; about $4M ARR across 40 to 50 customers |
| Growth engine | Enterprise sales and references today; expansion within accounts and the Infosys channel next |
| Retention engine | ERP write-back, accumulated price and supplier history, supplier habits, categories running without people |
| Moat | Moderate lock-in per customer; operating knowledge of its home markets; no market-wide moat yet |
| Biggest weakness | Value and reliability are asserted, not proven |
| Biggest opportunity | Evidence-based autonomy on tail spend, sold through partners |
| Biggest threat | Incumbent suites and ERPs bundling good-enough agents |
| North Star Metric | Value of purchases completed end to end through Aerchain each month |
| Top 3 product priorities | 1. Value record per module. 2. Autonomy readiness scorecard. 3. Agent test harness and replay. |
| Recommended strategic direction | Become the most provable and auditable procurement AI for complex groups in its home regions, then scale through partners and overlay deals instead of a direct fight in the United States |

## Part 64 — Understand this product in 10 minutes

These ten answers are the whole teardown in short form.

**1. Why do customers buy it?** To get more purchasing done with the same team, faster and at better prices, without a year-long suite project. The demo shows a vague request becoming a sent RFQ and a clean bid comparison in minutes.

**2. Why do customers keep using it?** Because orders and invoices come to be created through it, years of price and supplier history build up in it, and suppliers get used to responding through it.

**3. Why do customers leave?** Most likely because employees kept using email, the agents never moved beyond human approval, or finance never accepted the savings. Then an incumbent's bundled AI or a change of sponsor finishes it. No churn data is public.

**4. What is its strongest feature?** Reading supplier bids in any format into one comparison, combined with suppliers answering by email without a login. Together they remove the two biggest sources of friction in sourcing.

**5. What is its weakest feature?** Analytics. It is the feature that proves value, it is marked “coming soon” on the main site, and the one visible review asks for more.

**6. What makes it difficult to replace?** Two-way ERP integration, approval rules for every entity, and accumulated history. The difficulty is moderate and depends on how deeply it is deployed.

**7. What makes it vulnerable?** Thin independent proof, a small team covering a wide scope, a closed platform, and AI capabilities that large rivals now ship inside products customers already own.

**8. What is its biggest growth opportunity?** Existing customers releasing more spending to the agents and adding modules, and new customers arriving through Infosys. Both depend on proof.

**9. What is its biggest strategic threat?** SAP, Coupa and Zycus making agents a standard, bundled part of suites, so that a separate vendor has to justify itself on measurable results alone.

**10. What would I do as the PM?** Build the evidence layer first: a value record finance signs off, a scorecard that tells a customer when a category is ready for autonomy, and testing that makes agents safe to change. Then use that evidence to expand accounts and to give partners something provable to sell.

## Part 65 — Source register

All pages were read on 9 and 10 October 2026. “Date” is the page's own date where it has one. Reliability reflects how far a claim from that source can be trusted without a second source.

### Primary sources

| Source | Date | What it supports | Reliability |
| --- | --- | --- | --- |
| [Aerchain product site](https://go.aerchain.io/) | 2026 | SpendOS, the named agents, autonomy levels and waves, connectors, security list, 16-week rollout, pricing statement, return model, customer logos and results | High for what is offered; medium for performance claims; contains conflicting spend figures |
| [Aerchain main site](https://aerchain.io/) | 2025 to 2026 | Agent list, “coming soon” items, platform components, testimonials, older statistics | High for what is listed; low for statistics; contains placeholders |
| [About page](https://aerchain.io/about-us) | 2024 to 2025 | Founders, company timeline, team size, older statistics | Medium; some entries conflict with press |
| [Why Aerchain](https://aerchain.io/why-aerchain) | 2025 | Differentiation claims | Low to medium |
| Agent pages: [Intake](https://aerchain.io/products/intake-agent), [Sourcing](https://aerchain.io/products/sourcing-agent), [Evaluation](https://aerchain.io/products/evaluation-agent), [Negotiation](https://aerchain.io/products/negotiation-agent), [Invoice](https://aerchain.io/products/invoice-agent), [Vendor Onboarding](https://aerchain.io/products/vendor-onboarding-agent), [Aera](https://aerchain.io/aera-ai) | 2025 | Capabilities of each agent; the “For 100 RFQs” statistics | High for capabilities; low for statistics, which have no method |
| Platform pages: [Integrations Hub](https://aerchain.io/integrations-hub), [Multi-Agent Framework](https://aerchain.io/multi-agent-framework), [Knowledge Hub](https://aerchain.io/knowledge-hub), [Omnichannel Hub](https://aerchain.io/omnichannel-hub), [DIY Framework](https://aerchain.io/diy-framework) | 2025 | ERP sync, input formats, no-code configuration, knowledge layer | High for capabilities described |
| [Blog: The State of AI Procurement in 2026](https://aerchain.io/blogs/the-state-of-ai-procurement-2026) | 3 February 2026 | Survey of 163 procurement leaders; time savings by task | Medium; company research with no published method |
| [Blog: Reinventing procurement for the FMCG supply chain](https://aerchain.io/blogs/reinventing-procurement-fmcg-supply-chain) | 5 August 2026 | Scale of an FMCG deployment; rollout order; claimed results | Medium; company case material |
| [Blog: The Hidden Cost of Bad Procurement Intake Data](https://aerchain.io/blogs/hidden-cost-of-bad-procurement-intake-data) and [Intake Management is the Key](https://aerchain.io/blogs/intake-management-is-the-key-to-ai-ready-procurement) | August and July 2025 | Intake problem; Gartner figures quoted second-hand | Medium for the argument; low for unsourced statistics |
| [Blog: Automating your Sourcing through Generative AI](https://aerchain.io/blogs/automating-your-sourcing-through-generative-ai) | 8 March 2024 | Founder's description of intake across email and chat tools | Medium; a statement of intent |
| [Blog: Gartner Recognises Aerchain](https://aerchain.io/blogs/gartner-recognises-aerchain-for-autonomous-sourcing) and [A New Look for a New Era](https://aerchain.io/blogs/a-new-look-for-a-new-era-at-aerchain) | June 2022; April 2025 | 2022 Market Guide listing; the rebrand | High as company statements |
| [Careers page](https://aerchain.io/careers) and [Uplers listing](https://www.uplers.com/company/aerchain-6393) | 2026 | Open roles, working arrangement | High |
| Aerchain job postings for product managers: the [Senior Product Manager posting](https://www.foundit.in/job/senior-product-manager-aerchain-bengaluru-bangalore-60049495) and the Product Manager posting | August and September 2026 | About $4M ARR, the $25M goal, $20B+ spend figure, role expectations | High as a company statement; not independently verified |
| [Scalekit customer story](https://www.scalekit.com/customers/aerchain) | 9 June 2025 | Login architecture, identity providers, named customers, quotes from the CTO | High |
| [SAP News](https://news.sap.com/2026/01/sap-leader-gartner-magic-quadrant-source-to-pay-suites/) | 26 January 2026 | SAP's Leader position; next-generation Ariba; date of the Gartner report | High for SAP's own statements |
| [Coupa newsroom](https://www.coupa.com/newsroom/coupas-september-release-accelerates-agentic-spend-capabilities/) | 20 August 2026 | Coupa's agents, customer counts, data claims, acquisitions | High for Coupa's own statements |
| [Zycus Merlin page](https://zycus.com/solution/merlin-agentic-ai-platform) and [Zycus comparison page](https://www.zycus.com/compare/best-ai-procurement-software) | 2026 | Zycus agents, Leader claim, Tata Play claim | Medium; competitor marketing |
| [Zip announcements](https://zip.com/blog/zip-forward-2026-announcements) | 16 September 2026 | Zip's sourcing and purchase-order agents, marketplace | High for Zip's own statements |
| [Dubai Media Office](https://www.mediaoffice.ae/en/news/2026/may/04-05/hamdan-bin-mohammed-launches-dubai-private-sector-shift-to-agentic-ai-within-two-years) | 4 May 2026 | Dubai's two-year agentic AI programme for the private sector | High |

### Secondary sources

| Source | Date | What it supports | Reliability |
| --- | --- | --- | --- |
| [Inc42: Series A](https://inc42.com/buzz/aerchain-bags-13-mn-to-scale-agentic-ai-platform-for-enterprise-procurement/) | 18 March 2026 | Round size, investors, founding year, product layers, customer and spend claims | High for deal facts; medium for company claims |
| [Entrackr](https://entrackr.com/news/enterprise-procurement-platform-aerchain-secures-13-mn-in-series-a-round-11225084) and [Entrepreneur India](https://india.entrepreneur.com/news-and-trends/aerchain-raises-usd-13-mn-in-series-a-funding-round/503533) | 18 March 2026 | Round details; 50+ customers; $45B spend | Medium; both give a founding year of 2021 that conflicts with other sources |
| [Venture Intelligence: Series A](https://news.ventureintelligence.com/private-equity/enterprise-procurement-solutions-firm-aerchain-raises-%2413-m) and [Infosys stake](https://news.ventureintelligence.com/private-equity/infosys-acquires-5.3%25-stake-in-procurement-s%E2%80%99ware-maker-aerchain) | 18 March and 28 August 2026 | Earlier funding from 2017; Infosys's 5.3% stake, citing an Infosys filing; FY25 income and loss | High |
| [Inc42 financials page](https://inc42.com/company/aerchain/financials/) | FY25 data | Revenue, expenses, loss, growth rate, total funding | Medium to high; year labels on the page are inconsistent |
| [StartupWire: Infosys investment](https://www.startupwire.in/post/infosys-bets-on-ai-startup-aerchain-enterprise-procurement-autonomous-spend-os) | 28 August 2026 | How Infosys might use Aerchain | Low to medium; unnamed quotes and unverified metrics |
| [YourStory: pre-Series A](https://yourstory.com/2021/09/funding-alert-aerchain-raises-3-m-indiamart) | September 2021 | $3M round, $500K ARR claim, accelerators, early customers | High for deal facts |
| [YourStory: AB InBev programme](https://yourstory.com/2021/04/aerchain-ab-inbevs-global-accelerator-program-2020-expanded-globally-within-6-months) | 22 April 2021 | How the AB InBev work began and grew | Medium to high; sponsored-style feature |
| [YourStory accelerator profile](https://events.yourstory.com/basecamp-cohort-11-jiogennext/aerchain) | About 2019 | Founders' backgrounds, early product, early customers, early pricing basis | Medium |
| [CXOToday interview](https://cxotoday.com/corner-office/aerchain-indias-leading-ai-backed-sourcing-platform/) | 22 July 2022 | 2022 positioning as autonomous sourcing | Medium; founder's own statements |
| [The Hackett Group](https://www.thehackettgroup.com/the-hackett-group-reports-rapid-progress-in-procurements-ai-agenda/) and [Supply Chain 24/7](https://supplychain247.com/article/procurement-workloads-rise-8-percent-2026-ai) | March 2026 | Workload, headcount, budget and AI adoption figures | High |
| [Grand View Research](https://www.grandviewresearch.com/industry-analysis/procurement-software-market-report) and [GM Insights](https://www.gminsights.com/industry-analysis/procurement-software-market) | 2026 | Market size, growth, regional and segment shares, vendor shares | Medium; research firms differ |
| [Procurement Magazine](https://procurementmag.com/news/cpos-choose-coupa-ivalua-for-source-to-pay-suites) | 10 February 2026 | Leaders and Visionaries in the 2026 Gartner ranking | Medium to high |
| [VentureBeat on Zip](https://venturebeat.com/technology/zips-new-ai-agents-want-to-stop-your-finance-team-from-uploading-contracts-into-personal-chatgpt-accounts) | 2 June 2026 | Zip's valuation, funding, agents and customers | High |
| Vendr pricing pages for [Coupa](https://www.vendr.com/marketplace/coupa) and [Zip](https://www.vendr.com/marketplace/zip-hq) | 2026 | Median contract values and ranges | Medium; based on Vendr's own buyers |
| [CPOstrategy on Zycus](https://cpostrategy.media/blog/2026/05/22/zycus-concludes-agentic-ai-procurement-summit-2026-with-a-mandate-for-cpo-led-ai-ownership/) | 22 May 2026 | Zycus agents and positioning | Medium |
| [TechIntelPro on Levelpath](https://techintelpro.com/news/ai/agentic-ai/levelpath-secures-55m-series-b-to-revolutionize-enterprise-procurement-with-ai-agents) | 1 July 2025 | Levelpath funding, revenue and headcount | Medium |
| [Asymmetrix on Pactum](https://asymmetrixintelligence.substack.com/p/insight-partners-54m-investment-in) | 17 June 2025 | Pactum funding and customers | Medium |
| [Rework round-up of procurement agents](https://resources.rework.com/tools/ai-agents/best-ai-agents-for-procurement-2026) | 2026 | Reported pricing models and agent counts for rivals | Low to medium; a third-party summary |
| [RFP.wiki profile](https://www.rfp.wiki/vendors/aerchain) | 31 August 2026 | A reviewer-site summary of strengths, weaknesses and pricing basis | Low to medium; states it may contain inaccuracies |
| [CB Insights profile](https://www.cbinsights.com/company/aerchain) | 2026 | Investor list, total raised, news dates | Medium |
| Latka, StartupIntros and one investor-style profile | 2026 | Revenue and headcount estimates | Low; estimates conflict with filings, and one names the wrong founder. Not relied on. |
| [Medium case study](https://medium.com/@nehamuralidhar03/aerchain-case-study-5bf2fa5542e9) | September 2021 | Tail spend at about 10% of spend and 5% leakage | Low; an individual's case study |

### Community sources

| Source | Date | What it supports | Reliability |
| --- | --- | --- | --- |
| [Gartner Peer Insights: Aerchain](https://www.gartner.com/reviews/product/aerchain-164583452) and the [category page](https://www.gartner.com/reviews/market/ai-agents-for-procurement) | Review dated 9 April 2026 | Rating of 4.3 from 9; one review; ratings of other products in the category | Medium for ratings; low for review text, which Gartner marks as possibly placeholder |
| [G2: Aerchain](https://www.g2.com/products/aerchain-aerchain/reviews) | Page modified 28 September 2026 | 4.5 from 2 reviews; review counts for SAP Ariba and Coupa | Low for Aerchain; high for the counts |
| Reddit and other forums |  | Nothing found about Aerchain |  |

### Sources I could not open

- Tracxn's company profile and Aerchain's LinkedIn page blocked automated reading.
- The 2026 Gartner Magic Quadrant report itself is behind a paywall. Positions are taken from vendor announcements and trade press.
- Aerchain's security reports and any trust centre are not public.
