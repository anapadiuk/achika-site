# Market & Investment Assessment

> **Product:** Achika — multi-tenant B2B platform for small business order management, inventory, and catalog
> **Live URL:** https://app.achika.lt/
> **Assessment Date:** 2026-03-30
> **Assessor Role:** Technical Investor with Market Analysis
> **Related:** Technical due diligence in `investor-review-backend.md`, `investor-review-frontend.md`, `investor-review-delta.md`

---

## Executive Summary

Achika is a horizontal SMB B2B platform that originated from a charred wood siding manufacturing use case and evolved into a general-purpose order/inventory/catalog system for small businesses. The product is live at `app.achika.lt`, has one pilot customer (a Canadian reseller of Lithuanian charred wood), and targets a €50/month base + €20/seat pricing model.

**Technical foundation is strong** (confirmed by separate technical due diligence — verdict: "Invest"). **Market viability is the open question** — this assessment addresses it.

---

## Product Evolution

| Phase | Description |
|---|---|
| **Origin** | Built for charred wood siding manufacturing (Shou Sugi Ban) — a specific vertical |
| **Current** | Evolved into a general-purpose B2B platform for any products and orders |
| **Architecture** | Multi-tenant: each tenant = one small business. Domain modules: `Catalog`, `Crm` (orders, fulfillment), `Inventory` (warehouses, movements), `Core` (tenants, users) |
| **Demo** | One-click demo onboarding (`POST /auth/start-demo`) — product-led growth pattern |

The domain model retains manufacturing-specific logic (supply types: `FromStock`, `PurchaseToOrder`, `ProduceToOrder`; fulfillment state machine) which is a **differentiator** — most generic order management tools don't model manufacturing workflows.

---

## Target Market

### Primary Segment: Small B2B Businesses (2–15 employees)
- Manufacturers, distributors, wholesalers, resellers
- Currently managing orders and inventory in Excel, paper, or basic tools
- Need: catalog + orders + inventory + customer management in one system
- Don't need (yet): full ERP, accounting integration, advanced analytics

### Geography Strategy

| Phase | Market | Timeline | Rationale |
|---|---|---|---|
| **Phase 1** | Lithuania | Now–12 months | Founder's home market, direct sales, language advantage |
| **Phase 2** | Baltic states (Latvia, Estonia) | 12–24 months | Similar market structure, cultural proximity |
| **Phase 3** | EU expansion | 24–36 months | Multi-language support via Transloco (frontend), multi-tenant architecture supports it |
| **Phase 4** | Global (English-speaking markets) | 36+ months | Canadian pilot validates cross-border use case |

### Market Size Estimates

| Level | Size | Achika-Relevant Subset | Notes |
|---|---|---|---|
| **Lithuania** | ~60,000 SMEs | ~15,000–20,000 (B2B with physical goods) | Government data, Eurostat |
| **Baltic states** | ~150,000 SMEs | ~40,000–50,000 | Latvia + Estonia |
| **EU** | ~23M SMEs | ~2–3M (B2B with inventory) | Highly fragmented, many niches |

**Revenue scenarios (Lithuania only):**

| Penetration | Customers | Avg. Monthly Revenue | ARR |
|---|---|---|---|
| 1% of target | 150–200 | €90–110/customer | ~€200K |
| 3% of target | 450–600 | €90–110/customer | ~€600K |
| 5% of target | 750–1,000 | €90–110/customer | ~€1.1M |

**Revenue scenarios (Baltic states):**

| Penetration | Customers | ARR |
|---|---|---|
| 1% | 400–500 | ~€500K |
| 3% | 1,200–1,500 | ~€1.5M |
| 5% | 2,000–2,500 | ~€2.5M |

---

## Ideal Customer Profile (ICP)

### Buyer Persona

**Owner/Director of a small manufacturing B2B business** (2–15 employees), Lithuania → Baltics.

Not a CTO or IT manager — this is the person who runs the business, makes purchasing decisions, and often does operational work themselves.

### Current Situation

The business already has **multiple disconnected systems** — a patchwork of tools:

| Function | Typical Tool |
|---|---|
| Orders | Excel / Google Sheets / messenger chat |
| Inventory / Warehouse | Separate spreadsheet / notebook / standalone app |
| Customers | Phone contacts / basic CRM / another spreadsheet |
| Catalog / Price list | PDF / website / Word document |

**Manual data transfer between systems** is the daily routine: copy-paste, recalculation, "did you update the spreadsheet?"

### Core Pain (One Sentence)

> **"I don't know what's happening in my business right now without spending 2 hours manually consolidating data from 4 different places."**

### Pain Points in Detail

| Pain | Consequence |
|---|---|
| Manual data transfer between systems | Errors, lost orders, duplication |
| No unified view of "what's happening now" | Decisions made blind or with delay |
| Cannot produce a report without manual work | No control: how many orders, what status, what's in stock |
| Too much manual work on routine operations | Owner spends time on operations instead of business growth |
| Fulfillment tracked in someone's head | "Did we ship this? Did we order the materials?" |

### Trigger Events (What Makes Them Search for a Solution)

- Lost an order / shipped the wrong item / forgot about a client
- Hired another person and the "system in my head" stopped working
- Client asked for order status and they can't answer without calling the warehouse
- Tried to compile a monthly report and spent half a day on it

### Why Achika Solves This

| Problem | Achika Solution |
|---|---|
| 4 disconnected systems | **One platform:** catalog + orders + warehouse + customers |
| Manual data transfer | **Data lives in one place** — create order → warehouse sees it → fulfillment is tracked |
| "What's happening right now?" | **Real-time statuses / dashboard** — no manual consolidation |
| Produce-to-order chaos | **State machine:** Draft → Submitted → Approved → Sourcing → Shipped → Delivered |
| "Too complex to set up Odoo" | **Onboarding in minutes** — one-click demo, simple UI |

### Value Proposition (One Sentence)

> **Achika replaces 4 Excel files and 3 messengers with one system where the owner can see at any moment: which orders, in what status, what's in stock — without manual consolidation.**

### ICP Qualification Criteria

| Criterion | Fit ✅ | No Fit ❌ |
|---|---|---|
| **Company size** | 2–15 employees | 1 person (no collaboration need) or 50+ (needs ERP) |
| **Business type** | Manufacturing, wholesale, distribution with physical goods | Pure services, digital products, retail/B2C |
| **Current tools** | Excel + messenger + separate apps | Already using Odoo/SAP/Katana and satisfied |
| **Decision maker** | Owner/director who feels the pain daily | IT department evaluating tools abstractly |
| **Trigger** | Recent pain event (lost order, scaling team, reporting failure) | "Just exploring options" with no urgency |
| **Geography** | Lithuania (Phase 1), Baltics (Phase 2) | Markets requiring regulatory compliance Achika doesn't support yet |

### Sales Channel Implications

The buyer persona (owner/director of a small business) dictates the sales approach:

- **Primary:** Direct sales + 15-minute live demo ("show me and I'll understand")
- **Secondary:** Referrals from existing customers (small business owners talk to each other)
- **Supporting:** Product-led growth via one-click demo (validates the product, but conversion likely needs human touch)
- **Not effective yet:** Self-serve SaaS funnel (too early, not enough brand recognition)

### Messaging Implications

Based on ICP pain points, the messaging should lead with:
- ❌ Not: "B2B platform for order management"
- ✅ Yes: **"Stop consolidating data manually"** / **"All orders, inventory, and customers — in one place"**
- The demo flow should demonstrate: create order → warehouse updates → status visible → report ready. No copy-paste.

---

## Pricing Analysis

### Current Model: €50/month base + €20/seat (from 4th user)

| Team Size | Monthly Cost | Annual Cost | Cost per User/Month |
|---|---|---|---|
| 1 user | €50 | €600 | €50.00 |
| 3 users | €50 | €600 | €16.67 |
| 5 users | €90 | €1,080 | €18.00 |
| 10 users | €190 | €2,280 | €19.00 |
| 15 users | €290 | €3,480 | €19.33 |

### Competitive Pricing Comparison

| Competitor | Pricing | Target | Differentiation vs Achika |
|---|---|---|---|
| **Odoo** | €24.90/user/month (Online), free self-hosted | SME, all industries | Biggest competitor. Modular, massive ecosystem. But: complex setup, overwhelming for small teams |
| **Katana** | $99–799/month | Manufacturing SMEs | Manufacturing-specific. More expensive. Better brand recognition |
| **inFlow** | $89+/month | Inventory-focused SMEs | Inventory-first. No manufacturing workflows |
| **Zoho Inventory** | €0–249/month | Small e-commerce/wholesale | Part of Zoho suite. Cheap but not manufacturing-aware |
| **Baselinker** | Popular in Baltics | E-commerce order management | B2C-focused, marketplace integrations. Not B2B manufacturing |
| **Excel/Paper** | €0 | Everyone | The real competitor for most prospects |

### Pricing Verdict
€50 base + €20/seat is **well-positioned** for SMB:
- Cheaper than Katana and inFlow for small teams
- Comparable to Odoo Online for 3–5 users
- Low enough to not require enterprise procurement processes
- High enough to sustain a viable business at 500+ customers

**Planned module-based pricing** is architecturally supported (domain modules: Catalog, CRM, Inventory map to feature tiers).

---

## Competitive Positioning

### The Critical Question: "Why Not Odoo?"

This is the question every investor, customer, and competitor will ask. The answer must be clear:

| Dimension | Odoo | Achika |
|---|---|---|
| **Setup complexity** | High — requires configuration, potentially a consultant | Low — one-click demo, pre-configured for B2B orders/inventory |
| **Time to value** | Days–weeks | Minutes (demo onboarding proves this) |
| **Manufacturing awareness** | Generic or through expensive modules | Built-in: supply types, fulfillment state machine, warehouse allocation |
| **Target company size** | 10–500+ employees | 2–15 employees |
| **Pricing for 5 users** | ~€125/month | €90/month |
| **UX for non-technical users** | Complex, ERP-like interface | Modern Angular UI designed for small teams |

**Achika's moat is not features — it's simplicity + manufacturing domain knowledge + speed to value.** This is the "Basecamp vs Jira" positioning for B2B order management.

### Defensibility Assessment

| Factor | Strength | Notes |
|---|---|---|
| **Domain model** | 🟢 Strong | Manufacturing workflows (supply types, fulfillment states, warehouse allocation) are hard to replicate generically |
| **Multi-tenancy** | 🟢 Strong | Architecturally correct from day one. Competitors retrofitting multi-tenancy struggle |
| **Switching costs** | 🟡 Medium | Once customer data (orders, inventory, customers) is in the system, switching is painful |
| **Network effects** | 🟡 Weak-Medium | `ProductShare` (cross-tenant catalog) could enable marketplace dynamics, but not yet activated |
| **Brand/distribution** | 🔴 Weak | One pilot, no brand recognition, no distribution channel |
| **Technology** | 🟡 Medium | Strong codebase but not patentable. Advantage is execution speed, not IP |

---

## Pilot Customer Analysis

### Current Pilot: Canadian Charred Wood Reseller

| Attribute | Detail |
|---|---|
| **Business** | Resells Lithuanian-manufactured charred wood siding in Canada |
| **Use case** | Cross-border B2B supply chain: orders from Canadian clients → fulfillment from Lithuanian manufacturer |
| **Value** | Validates: multi-tenant isolation, cross-border workflow, order lifecycle, inventory tracking |
| **Risk** | Single pilot = no statistical significance. Cannot extrapolate churn, NPS, or feature demands |

### What the Pilot Proves
- ✅ Product works for a real B2B use case
- ✅ Cross-border supply chain is functional
- ✅ Multi-tenancy works in practice (not just in architecture)

### What the Pilot Does NOT Prove
- ❌ Product-market fit (need 10–20 paying customers from different segments)
- ❌ Self-service onboarding works (pilot likely had founder support)
- ❌ Pricing is acceptable to the market
- ❌ Churn rate
- ❌ Feature completeness for non-charred-wood use cases

---

## Key Market Risks

### Risk 1: SMB Is a Notoriously Difficult Segment
- **Description:** Small businesses have high churn (20–30% annual typical for SMB SaaS), low willingness to pay, high support expectations relative to revenue, and are price-sensitive.
- **Mitigation:** Low base price (€50), product-led growth (demo onboarding reduces CAC), modular pricing allows upsell.
- **Risk level:** 🟡 **Medium** — inherent to segment, not specific to Achika

### Risk 2: Lithuania Is a Small Starting Market
- **Description:** ~15,000–20,000 target companies. At 5% penetration (very optimistic for year 1–2), ceiling is ~€1M ARR. Need to expand to Baltics/EU within 2 years.
- **Mitigation:** Product is English-first with i18n support. Architecture supports multi-region. Canadian pilot proves cross-border works.
- **Risk level:** 🟡 **Medium**

### Risk 3: No Clear Distribution Channel
- **Description:** No partnerships, no integrations marketplace, no content marketing, no referral program. Current go-to-market appears to be founder-driven direct sales.
- **Mitigation:** Demo onboarding enables product-led growth. Manufacturing trade shows, industry associations (Lithuanian Manufacturers Association), and Google Ads for "order management for small business" are low-cost channels.
- **Risk level:** 🔴 **High** — this is the #1 market risk

### Risk 4: "Good Enough" Competition
- **Description:** Odoo (free tier), Google Sheets + manual processes, and industry-specific tools may be "good enough" for many SMBs. Convincing a small business owner to switch from "what works" is the hardest sale in SaaS.
- **Mitigation:** One-click demo reduces friction. Manufacturing-specific features (supply types, fulfillment states) offer concrete value that spreadsheets can't replicate.
- **Risk level:** 🟡 **Medium**

### Risk 5: Founder Capacity
- **Description:** Single founder handling: product development, sales, support, infrastructure. This doesn't scale beyond 5–10 customers without help.
- **Mitigation:** Strong documentation culture and AI-assisted development contracts reduce bus factor for engineering. But sales and support remain bottlenecked.
- **Risk level:** 🔴 **High**

---

## Investment Thesis

### Bull Case: €2–5M ARR in 3–5 Years
- Achika captures 3–5% of Baltic SMB B2B market
- Module-based pricing increases ARPU to €150–200/month
- `ProductShare` evolves into a marketplace connecting manufacturers and resellers
- Lithuanian/Baltic manufacturing sector growth (EU industrial policy tailwinds)
- Low-cost operation (solo founder + AI-assisted development) means early profitability

### Base Case: €500K–1M ARR in 3–5 Years
- Achika captures 1–2% of Lithuanian market, starts Baltic expansion
- Moderate churn (25%) limits net growth
- ARPU stays at €90–110/month
- Sustainable but not venture-scale — lifestyle business or small PE exit

### Bear Case: <€200K ARR, Pivot or Shutdown
- Product-market fit not achieved beyond charred wood niche
- Odoo free tier captures same customers
- Founder burns out trying to do everything alone
- Churn exceeds 30%, making growth impossible

---

## Conditions for Investment

### Pre-Investment Requirements (Before Writing a Check)

| # | Condition | Why | Status |
|---|---|---|---|
| 1 | **5–10 paying customers** from at least 2 different industries | Proves PMF beyond charred wood | ❌ Not met (1 pilot) |
| 2 | **Clear "Why not Odoo" answer** validated by customers | Competitive positioning is existential | ❌ Not formalized |
| 3 | **3-month retention data** (>80% retention) | SMB churn is the killer | ❌ No data yet |
| 4 | **Go-to-market plan** with at least one scalable channel | Founder-driven sales has a ceiling | ❌ Not documented |

### Post-Investment Milestones (First 12 Months)

| Quarter | Milestone | Success Metric |
|---|---|---|
| **Q1** | Acquire 10 paying customers in Lithuania | ≥10 customers, ≥€900/month MRR |
| **Q2** | Achieve <25% monthly churn, validate module pricing | Churn data, at least 2 customers on higher tier |
| **Q3** | First Baltic expansion (Latvia or Estonia) | ≥3 customers outside Lithuania |
| **Q4** | €3K+ MRR, hire first employee (sales or support) | Revenue supports partial salary |

---

## Final Market Verdict

### Would I invest from a market standpoint?

**Not yet — but the setup is promising.**

The product has **the right technical foundation** for a horizontal SMB B2B platform. The domain model is genuinely differentiated (manufacturing workflows that competitors don't offer natively). The pricing is sensible. The demo onboarding is a product-led growth signal that most early-stage products lack.

**However, the market case is pre-validation:**
- One pilot customer ≠ product-market fit
- No distribution channel beyond founder effort
- Lithuania is a small market with a low ceiling
- SMB SaaS is a high-churn, high-effort segment

### Combined Verdict (Technical + Market)

| Dimension | Verdict | Confidence |
|---|---|---|
| **Technical foundation** | ✅ Invest | High — confirmed by code review |
| **Product-market fit** | ❓ Unproven | Low — 1 pilot, no churn data |
| **Market size** | 🟡 Adequate if expands beyond Lithuania | Medium |
| **Competitive positioning** | 🟡 Defensible niche possible | Medium — "Why not Odoo" needs sharpening |
| **Go-to-market** | 🔴 Not developed | Low |
| **Founder capability** | 🟡 Technically strong, capacity constrained | Medium |

### Recommendation

> **Invest at a small angel/pre-seed check (€20–50K)** contingent on:
> 1. Founder commits to acquiring 10 paying customers within 6 months (with investment capital for marketing/sales, not engineering)
> 2. Investment capital goes primarily to **go-to-market** (marketing, sales tooling, first hire), not engineering (technical foundation is already strong)
> 3. Clear 6-month review gate: if <5 paying customers by month 6, reassess before follow-on
>
> **Do NOT invest at a larger check (>€100K) until PMF is demonstrated** (10+ customers, <25% monthly churn, validated pricing).
>
> **The founder should be spending 80% of time on sales and customer acquisition, not engineering.** The product is ahead of the market validation — this is the right problem to have, but only if the founder shifts focus.

---

*Assessment based on technical due diligence of `anapadiuk/degmeda.b2b` and `anapadiuk/degmeda.b2b.web`, founder-provided business context, and public market data as of 2026-03-30.*