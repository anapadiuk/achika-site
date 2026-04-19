# Achika — Product Snapshot

**Purpose:** Give a reasoning agent enough grounded context to discuss pricing, positioning, or strategy without hallucinating. This is a factual snapshot of what exists as of **2026-04-19**, not a plan or a pitch. Gaps are marked **[Unknown]** — do not fill them in.

---

## 1. Product at a glance

- **Name:** Achika
- **Legal entity:** Achika, MB (Lithuania)
- **Domain:** achika.lt (marketing), app.achika.lt (product)
- **Category:** B2B SaaS — order and inventory management for small manufacturers and distributors
- **Stage:** MVP. No paying customers. One prospective customer lined up (not yet onboarded).
- **Team:** Solo — Artiom Napadiuk (founder, developer, operator).

## 2. Origin story (relevant context)

- Built as an internal system for **Degmeda** (degmeda.eu — Lithuanian premium charred wood siding manufacturer).
- Degmeda's dealers asked for "something similar" to manage their own orders. Artiom decided to generalize it into a standalone product.
- A Degmeda dealer in **Canada** is the first prospective client. **They have not started using Achika yet.** Framing as "dealers use it" in any copy or positioning is inaccurate.

**Why this matters for pricing:** the product was born from real operational use, not a blank-page startup. Manufacturing-specific logic is already present. But there is zero external pricing data — no pilot pricing, no LOIs with numbers, no benchmark from existing customers.

## 3. Target audience (ICP)

- **Role:** Owner or director of a small manufacturing or distribution business.
- **Size:** 2–15 employees managing physical goods.
- **Current stack:** Excel, email, WhatsApp/Slack/Viber group chats.
- **Trigger to buy:** Lost an order, hired a new person who can't load state into their head, couldn't answer a client's status question without manual digging.
- **Buyer profile:** The person who feels the operational pain daily — **not** a tech evaluator or IT buyer.
- **Geography priority:** Lithuania first → Baltics → EU long-term. Canadian dealer is an opportunistic beachhead, not a geographic strategy.

## 4. Product capabilities (what the app actually does)

*Derived from existing domain logic, not the marketing copy.*

- **Orders:** Track order lifecycle through a fulfillment state machine (sourcing → producing → picking → ready → delivered).
- **Inventory:** Stock levels, low-stock flags, expected incoming supply.
- **Supply types baked in** (manufacturing-aware, not generic):
  - `FromStock` — ship from on-hand inventory
  - `PurchaseToOrder` — purchase from supplier for a specific order
  - `ProduceToOrder` — manufacture for a specific order
- **Fulfillment:** Status visibility across the team — who is doing what, what is blocked, what is waiting on supply.
- **Multi-tenant:** Product is built as a multi-tenant SaaS (each client = a tenant). Tenant isolation is functional.
- **Live demo:** Public demo at `app.achika.lt/auth/demo` with no signup, seeded with sample data.

**[Unknown]:** Exact feature depth (e.g. does inventory support multi-warehouse? Are there user roles/permissions? Is there reporting/export? Mobile?). Agent should ask if specifics matter for the pricing question.

## 5. Planned differentiator — Inter Tenant Network

- **Concept:** Networked multi-tenant — tenants (small businesses) can connect to each other so that supplier/dealer relationships flow inside Achika instead of over email.
- **Example:** Degmeda (manufacturer tenant) + a dealer (dealer tenant) → dealer's purchase order becomes the manufacturer's production order automatically; status updates flow back.
- **Status:** **Not built, not shipped.** Strategic direction, not a current feature.
- **Implication for pricing:** this is the intended long-term moat and the reason to charge above commodity inventory-tool rates. But it cannot justify a premium price *today* — today's product stands on core orders+inventory+fulfillment + domain logic + founder proximity.
- **Public positioning rule:** not mentioned on the site, not referenced in sales copy until closer to shipping.

## 6. What the marketing site communicates (as of today)

The site is at achika.lt — a single-page bilingual marketing page (EN at `/`, LT at `/lt/`).

### Page sections in order
1. **Hero** — Headline: *"Run orders and inventory without spreadsheets."* Subhead: positioning as a simple system for small manufacturers and distributors outgrowing Excel/email. Product dashboard mockup (KPIs, needs-attention cards, recent orders). Single primary CTA: **View live demo** (no signup). Secondary walkthrough request is demoted to an inline text link.
2. **Product** — Three feature cards (Orders / Inventory / Fulfillment). Abstract, no screenshots, no specifics.
3. **"When it becomes useful"** — Four pain points (orders get lost, stock unclear, knowledge concentrated on one person, status questions never stop). Framed as triggers, not as a feature checklist.
4. **Who it is for** — 2–10 employees, Excel/email/chat-based, growing volume, wants to be operational next week not next quarter.
5. **About** — Founder-led: Artiom built ops systems for a small manufacturer for years; dealers asked for something similar.
6. **Contact** — Email (`artiom@achika.lt`), phone (`+370 656 26 596`), CTAs to demo and walkthrough request.
7. **Footer** — Three columns (Achika / Contact / Product). Legal entity line: *© 2026 Achika, MB*.

### What is deliberately NOT on the site
- **No pricing.** Not "starts at €X", not "free during beta", not "contact us for pricing". Silent.
- **No customer logos.** Degmeda reference is pending their approval. Canadian dealer isn't live.
- **No testimonials.** No case studies. No uptime/status page. No self-service signup (only demo + email).
- **No ROI / savings calculator.** No competitor comparison table.

## 7. Tone and positioning anchors

- Calm, direct, understated. Not aggressive, not pushy, no exclamation marks.
- **Anti-ERP** positioning used sparingly ("No complex ERP systems. No heavy setup." — one line). The audience fears ERP complexity; one acknowledgment is signal, more is noise.
- **Not** positioned as "AI-powered" / "revolutionary" / "all-in-one". Plain language is a deliberate choice.
- "Beyond spreadsheets" is the consistent framing — the villain is Excel, not competitors.

## 8. Business context relevant to pricing

- **Cost structure:** Solo founder. No team payroll. Infrastructure costs are small (standard web app hosting). Main cost is founder time.
- **Sales motion:** Founder-led, high-touch. Demos, walkthroughs, phone number on every page. Not a PLG funnel.
- **Market price anchors** (general, not Achika-specific — verify before citing):
  - Excel = free (anchor low)
  - Zoho Inventory, inFlow, Odoo Community = €30–100/month tier (anchor mid)
  - NetSuite / SAP Business One / Dynamics = €€€€ (anchor high, feared)
  - Industry-specific MRP (Katana, MRPeasy) = €100–300/month per tenant
- **Willingness-to-pay signal:** Unknown. No pilot pricing has been tested. Lithuanian SMBs are price-sensitive; Canadian/EU dealers may absorb more.
- **Pricing decision:** **Not made yet.** Do not propose specific numbers as if they are set. Frame any numeric suggestions as hypotheses to test.

## 9. Open questions an agent should ask before recommending pricing

1. Is pricing **per tenant**, **per user**, **per order volume**, or **flat**? Not decided.
2. Is there a **free tier / beta period** plan? Not decided.
3. What is the **target ARPU or monthly revenue** at 10 customers? 50? Unknown.
4. Is Achika being positioned as **cheapest credible alternative to ERP** or as **best-in-class SMB manufacturing tool**? The copy is ambiguous.
5. Does the Inter Tenant Network charge asymmetrically (e.g. manufacturer pays, dealer free)? Not decided.
6. Runway / timeline pressure? **[Unknown]** — affects whether pricing prioritizes growth (low) or revenue (higher).
7. Does Artiom want to self-fund or raise? **[Unknown]** — affects pricing risk tolerance.

## 10. Rules for the reasoning agent

- Treat this document as a snapshot. If you need live state (site copy, product features), read the source files in the repo — `index.html`, `lt/index.html`, and `AI_CONTEXT.md`.
- Do not fabricate customer counts, pricing tests, or traction data. None exist.
- Do not assume Inter Tenant Network exists today when proposing pricing.
- When uncertain, ask — do not extrapolate from other SaaS pricing without checking whether the analogy holds.
