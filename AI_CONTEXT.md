# AI Context — achika-site

Read this before making any content, copy, or structural changes to the site.

## Product

Achika is a B2B order and inventory management platform for small manufacturers and distributors (2–15 employees).

**Origin:** Built as an internal system for Degmeda (degmeda.eu — Lithuanian premium charred wood manufacturer). When Degmeda's dealers asked for something similar to manage their own orders, it became a standalone product. The first client is a Degmeda dealer selling their products in Canada.

**Differentiator:** Manufacturing-specific domain logic (supply types, fulfillment state machine) built in from the start — not adapted from generic tools.

## Ideal Customer Profile (ICP)

- Owner or director of a small manufacturing or distribution business
- 2–15 employees managing physical goods
- Currently running operations through Excel, email, or group chats
- Trigger events: lost an order, hired a new person, couldn't answer a client's status question without manual work
- Geography: Lithuania first, Baltics next, EU long-term
- **Not** a tech evaluator — the buyer is the person who feels the operational pain daily

## Tone and voice

- Calm, direct, understated. Not aggressive or pushy.
- Short sentences. Plain language. No jargon.
- No exclamation marks.
- Positive framing: describe what the user gains, not what they avoid.
- "No ERP complexity" type lines: one is useful as an objection-handler. More than one is noise.

## Positioning decisions

| Decision | Choice | Reason |
|---|---|---|
| Negation copy | Avoid; one line maximum | Founder preference: calm, not fear-based |
| "Not ERP" messaging | One instance retained in hero | Audience knows ERP, fears it — acknowledge once |
| About section | Personal, founder-led | Artiom Napadiuk, Degmeda origin story builds trust at MVP stage |
| Social proof | None yet | MVP; Degmeda reference pending their approval |
| CTA density | Hero + Contact only | Redundant dark Demo section removed |
| Language default | EN at root, LT at /lt/ | EN default with EU expansion in mind; LT audience comfortable with English in business context |

## Technical constraints

- **Stack:** Plain HTML + Tailwind CSS v4. No framework, no bundler, no TypeScript.
- **Two files:** `index.html` (EN) and `lt/index.html` (LT). Every content change must be applied to both manually.
- **CSS:** `public/tailwind.css` is committed. Run `npm run build` after adding new Tailwind classes.
- **No templating:** Header, footer, and shared sections are duplicated. Accept this for now.
