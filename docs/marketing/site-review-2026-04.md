# Site Review — April 2026

Summary of the initial site review and content decisions session.

## Context

MVP stage. First client is a Degmeda dealer (Canada) acting as a reviewer. Sales are direct — the site's purpose is credibility, not self-serve conversion. No funnel needed yet.

## Decisions made

### About section — founder story added

Replaced generic product description with:

> "Achika was built by Artiom Napadiuk, a developer who spent years building operational systems for a small manufacturer. When their dealers asked for something similar, it became a standalone product. The workflows — order tracking, inventory, fulfillment — are grounded in how these businesses actually run."

**Why:** At MVP stage with no customers and no social proof, the founder is the primary trust signal. Removing anonymity matters more than appearing corporate. The `artiom@achika.lt` email was already on the page — the name was already implied.

### Negation copy replaced

"Simple by design" block and one bullet point were rewritten from negative to positive framing:

| Before | After |
|---|---|
| "No ERP-level complexity." | "Ready to use in a day." |
| "No long implementation process." | "Your team sees order status without asking." |
| "Companies not ready for a complex ERP implementation" | "Companies that want to be operational next week, not next quarter" |

One "No complex ERP systems" line retained in the hero as a single objection-handler.

**Why:** Founder preference for calm, positive tone. Repeated negations keep ERP in the reader's head and read as defensive.

### Redundant Demo section removed

The dark full-width CTA section between "Who it's for" and "About" was removed. It duplicated the hero CTAs without adding content. Page flow is now: Features → Pain points → Who it's for → About → Contact.

### Phone number added

`+370 656 26 596` added to the Contact section in both EN and LT pages.

### Footer dead links removed

`Privacy Policy` and `Terms` links with `href="#"` were removed. Dead links undermine credibility more than their absence. To be restored when real documents exist (required before any significant outreach — GDPR applies).

### SEO meta tags added

Open Graph tags (`og:type`, `og:url`, `og:title`, `og:description`) and `hreflang` + `canonical` added to both EN and LT pages.

`og:image` not added — no suitable asset yet. Should be a 1200×630 PNG (product screenshot or branded banner) when created.

## Pending

- **Degmeda as reference:** Ask Degmeda for permission to name them on the About page. A named client reference would be the first concrete trust signal.
- **og:image:** Create a 1200×630 social preview image.
- **Privacy Policy + Terms:** Write minimal versions before scaling outreach.
- **Social proof:** After first paying customers, add a testimonial or logo row.

## What was discussed but not changed

**Language default:** EN at root kept as-is. LT audience comfortable with English in business; EN-first positions for EU expansion.

**Hero mock-UI:** Static HTML widget, not a real product screenshot. Acceptable at current stage — revisit when there is a stable UI to capture.

**Pricing:** No pricing on the page. Deliberate — direct sales model, no need to anchor a price before a conversation.
