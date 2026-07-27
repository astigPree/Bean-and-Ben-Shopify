# Bean & Ben Shopify Website - Project Description

| Item | Decision |
| --- | --- |
| Project | Bean & Ben coffee shop, coworking space, and gaming lounge website |
| Platform | Shopify Online Store 2.0 custom theme |
| Current stage | Approved visual references exist; the project is now in theme implementation |
| Document role | Product, scope, architecture, content, and delivery baseline |
| Version | 1.0 |
| Last updated | 27 July 2026 |

## 1. Executive Summary

Bean & Ben is a rooftop destination in Silang, Cavite that combines three experiences:

- Coffee and food for quick breaks, cravings, and longer stays.
- Coworking for students, freelancers, remote workers, creators, and small teams.
- Social gaming for barkadas and guests who want to unwind and play.

The website's job is not simply to display a menu. It must help a first-time visitor understand the three-in-one venue, choose the experience they need, see verified details, and confidently plan a visit.

The visual direction is already established through the supplied desktop and mobile screens. This project is therefore in the build stage, not an open-ended design exploration. Development should reproduce the approved compositions while making content merchant-editable, responsive, accessible, fast, and maintainable in Shopify.

The original developer handoff specifies WordPress. That platform recommendation is superseded by this repository's confirmed Shopify implementation. The handoff's brand, content, UX, responsive, accessibility, performance, and acceptance requirements remain authoritative.

## 2. Source of Truth

### Reference order

| Priority | Source | Governs |
| --- | --- | --- |
| 1 | `docs/screens/` | Approved composition, section appearance, desktop/mobile behavior, and visual hierarchy for the pictured sections |
| 2 | `Bean_and_Ben_Brand_Website_Developer_Handoff_v1.pdf` | Brand strategy, exact messaging, scope, content rules, UX requirements, accessibility, performance, and launch standards |
| 3 | `docs/brand/` | Logo artwork and available brand lockups |
| 4 | Current menu sheets inside the handoff | Category structure and visual inspiration only; not guaranteed live data |
| 5 | Existing theme code | Starter scaffolding only; it is not the approved design |

### Conflict rules

- For visual layout conflicts, follow the approved screen for that section.
- For wording, factual accuracy, accessibility, content status, or launch requirements, follow the handoff.
- Do not hard-code prices, hours, rates, amenities, station details, reviews, or contact details from a screenshot.
- When two approved sources materially disagree, flag the conflict before implementation instead of guessing.
- The exact hero wording is `FOR YOUR BREAKS & BREAKTHROUGHS.` Visual line breaks may change by viewport, but the wording must not.

## 3. Real Problem

Potential customers may mistake Bean & Ben for only a coffee shop. That hides the venue's strongest competitive advantage: coffee, focused work, food, rooftop atmosphere, and social gaming in one place.

The website must solve five practical questions quickly:

1. What is Bean & Ben?
2. What can I eat or drink?
3. Can I work or study there?
4. Can I play there, and what are the rules or rates?
5. Where is it, and when is it open?

If these answers are unclear, the design may look premium but will fail as a customer-acquisition tool.

## 4. Target Users

| Audience | Primary need | Fast website path |
| --- | --- | --- |
| Coffee and food guests | Check products, prices, atmosphere, and hours | Hero -> Featured menu -> Full menu -> Directions |
| Students and study groups | Confirm focus suitability, Wi-Fi, outlets, rules, rates, and hours | Hero -> Coworking -> Details -> Visit or message |
| Freelancers and remote workers | Find a reliable place to work, meet, or take permitted calls | Hero -> Coworking -> Amenities/rates -> Directions |
| Gamers and barkadas | Confirm stations/platforms, rates, rules, and availability | Hero -> Gaming -> Details -> Visit or message |
| Creators and small teams | Find an informal collaboration and meeting environment | Hero -> Rooftop/space -> Coworking -> Contact |
| Night owls and casual visitors | See the late-night atmosphere, menu, and closing time | Hero -> Gallery/rooftop -> Hours -> Directions |
| Returning guests | Reach menu, hours, location, or current availability immediately | Sticky navigation -> Relevant destination |

## 5. Best Strategy

### Product strategy

Build the smallest complete customer journey first:

1. Establish `COFFEE. COWORK. PLAY.` in the first screen.
2. Let users select a mode without reading long paragraphs.
3. Feature a small number of signature menu items.
4. Explain coworking and gaming with verified operational details.
5. Use real venue and product photography as proof.
6. End with clear hours, map, directions, and contact paths.

### Implementation strategy

- Build reusable Shopify sections and blocks from the approved screens.
- Store regularly changing content in Shopify resources, metafields, metaobjects, or theme settings.
- Keep the MVP informational and visit-focused.
- Do not add ordering, payment, booking, loyalty, or live availability until the business rules and operations exist.
- Avoid apps and custom JavaScript unless they create clear customer or merchant value.

## 6. Positioning and Messaging

### Approved positioning

Bean & Ben is a warm industrial rooftop destination that combines a coffee shop, coworking space, and gaming lounge for breaks, focused work, creative progress, shared play, and late-night connection.

### Messaging hierarchy

| Level | Approved line | Primary use |
| --- | --- | --- |
| Hero | `FOR YOUR BREAKS & BREAKTHROUGHS.` | Homepage first screen and major campaigns |
| Core shorthand | `COFFEE. COWORK. PLAY.` | Navigation, labels, summaries, and experience selection |
| Brand essence | `GOOD COFFEE. DEEP FOCUS. BETTER PLAY.` | Supporting sections and campaigns |
| Location | `MEET US AT THE TOP` | Directions and rooftop messaging |
| Coffee/food | `BREAK MODE` | Coffee, food, rest, and recharge |
| Coworking | `WORK MODE` | Study, remote work, and collaboration |
| Gaming | `GAME MODE` | Gaming lounge and social play |
| Hours | `BUILT FOR LATE NIGHTS` | Evening and late-night positioning |
| Wayfinding | `SUNDAN ANG LIWANAG` | Location, arrival, and local personality |

### Voice

The brand is confident, warm, bold, playful, street-smart, and slightly mischievous. Copy should use clear information first, one playful line second, and a direct invitation last.

Use natural English, conversational Filipino, and selective Taglish. Do not use fake luxury language, corporate filler, forced slang, emoji chains, or jokes that hide essential information.

## 7. Business Goals and Success Measures

| Goal | Expected behavior | Suggested measurement |
| --- | --- | --- |
| Explain the venue | A new visitor understands coffee + coworking + gaming in the first screen | Landing-page comprehension testing and hero CTA engagement |
| Drive menu discovery | Users reach the menu without searching through the site | `view_menu` events and menu engagement |
| Drive physical visits | Directions are accessible from hero/navigation and location | `get_directions` clicks |
| Generate qualified inquiries | Coworking and gaming users can reach verified details before messaging | Coworking/gaming detail views and `message_us` clicks |
| Build trust | Real venue, product, founder, and review content replaces generic claims | Gallery engagement and review visibility |
| Reduce update cost | Staff can change products, prices, availability, hours, and details without code | Merchant update test during handoff |

Analytics should only be installed after the owner supplies approved accounts and consent requirements.

## 8. Core Features and Information Architecture

### MVP pages and views

| Page/view | Purpose | Required content |
| --- | --- | --- |
| Homepage | Primary brand story and visit conversion | Navigation, hero, venue facts, featured menu, rooftop experience, coworking, gaming, about/founder, reviews/gallery, directions, footer |
| Full menu | Complete, scannable menu | Categories, products, descriptions, variants, prices, badges, availability, and imagery |
| Coworking page or anchored section | Remove workspace uncertainty | Verified amenities, seating, capacity, rates, session rules, hours, walk-in/reservation process, and real photos |
| Gaming page or anchored section | Remove play and booking uncertainty | Verified platforms/stations, counts, rates, rules, hours, walk-in/reservation process, and real photos |
| Privacy/legal pages | Support compliant forms and analytics | Approved privacy and consent language |

### Homepage scroll narrative

1. Navigation
2. Hero
3. Venue information strip
4. Experience selection: Coffee, Cowork, Play
5. Featured menu
6. Rooftop/atmosphere
7. Coworking
8. Gaming lounge
9. About and founder
10. Reviews and gallery
11. Location and directions
12. Footer

The supplied screens currently cover the hero, mobile navigation, information strip, featured menu, rooftop atmosphere, directions, and footer. Coworking, gaming, founder, reviews/gallery, and full-menu layouts still need to be implemented using the approved design system without inventing a new visual language.

## 9. Primary User Flows

### Craving-led visit

`Hero -> Featured menu -> Full menu -> Get directions`

### Work-led visit

`Hero -> Work mode -> Verified amenities/rates/rules -> Visit or message`

### Game-led visit

`Hero -> Game mode -> Verified stations/rates/rules -> Visit or message`

### Atmosphere-led visit

`Hero -> Rooftop gallery -> Reviews -> Location`

### Repeat visit

`Sticky navigation -> Menu or experience -> Hours/location`

Every path must remain usable without animation and without requiring a social-media account.

## 10. Scope

### MVP scope

- Responsive Shopify theme implementation.
- Approved desktop and mobile homepage sections.
- Full menu experience.
- Coworking and gaming information views.
- Merchant-editable products, prices, categories, availability, venue details, and experience details.
- Real gallery, founder, and approved review content when supplied.
- Directions, contact, Facebook, and verified business information.
- Local SEO metadata and verified structured data.
- Accessibility, performance, responsive, and browser QA.

### Explicitly out of scope for MVP

- Online ordering and payment.
- Automated reservations.
- Delivery integrations.
- Loyalty accounts.
- Live desk or gaming-station availability.
- Gaming-session timers.
- Inventory or POS synchronization beyond Shopify's standard product availability.
- Custom customer accounts.
- Automatic social-feed walls.

These features require separate discovery, operating rules, ownership, and budget approval.

## 11. System Design

### Architecture

```text
Merchant
  -> Shopify Admin
      -> Products, collections, metafields, metaobjects, files, theme settings
          -> Online Store 2.0 JSON templates
              -> Reusable Liquid sections, blocks, and snippets
                  -> Shopify CDN storefront
                      -> Customer
                          -> Menu / coworking / gaming / directions / contact
```

The MVP needs no custom backend, separate database, or JavaScript framework.

### Data models

| Content | Recommended Shopify model | Notes |
| --- | --- | --- |
| Menu item | Product | Use title, description, media, variants, price, and availability |
| Hot/iced or size choices | Product variants | Keep variant names and prices explicit |
| Menu category | Collection | Coffee, Matcha, Non-Coffee, Breakfast, Croffles, Pasta, Pizza, and approved future categories |
| Menu badge | Product metafield | `signature`, `bestseller`, `house_favorite`, `new`, or none |
| Dietary/allergen note | Product metafield | Optional; publish only verified information |
| Coworking offer | Page plus structured metafields or an `experience_detail` metaobject | Amenities, capacity, rates, duration, hours, rules, process, and availability |
| Gaming offer | Page plus structured metafields or an `experience_detail` metaobject | Platforms/stations, counts, rates, duration, rules, process, and availability |
| Founder | `founder_profile` metaobject | Name, title, image, story, quote, and approved link |
| Review | `approved_review` metaobject | Quote, name/initial, source, rating if used, and approval status |
| Gallery item | `gallery_item` metaobject or section blocks for a small fixed set | Image, alt text, caption, experience category, and order |
| Venue details | Global theme settings for one location | Address, map URL, hours, last call, contact, Facebook, parking, and wayfinding |
| Announcement | Announcement section settings | Message, active toggle, link, and optional display dates if operationally supported |

Products and collections are preferred for menu data because they preserve a clean path to future Shopify ordering. Purchase controls must remain hidden until online ordering is explicitly approved and operational.

### Shopify theme structure

- Sections own merchant-editable page modules.
- Blocks own repeatable facts, products, reviews, gallery items, or experience pillars.
- Snippets own reusable rendering logic such as buttons, icons, images, and menu cards.
- JSON templates define section order without hard-coding the whole page.
- Component CSS and JavaScript stay with their section, block, or snippet where supported.
- User-facing fixed strings use locale keys.

### API and integration flow

- Shopify Liquid reads native storefront resources; no custom API is required for ordinary page rendering.
- Map buttons link to a verified maps URL. A map embed should lazy-load or use a static preview.
- Facebook links use the approved profile after final verification.
- A contact form may use Shopify's native contact form.
- A newsletter form should only be included when it writes to an approved Shopify customer/email-marketing flow and displays compliant consent text.
- No API keys or secrets belong in theme files.

### Deployment notes

1. Develop against an unpublished Shopify theme.
2. Run `shopify theme check` before review.
3. Validate Liquid schemas and theme structure.
4. Push an unpublished staging version.
5. Test content editing with the merchant.
6. Test the required viewport and browser matrix.
7. Back up the current live theme before publishing.
8. Publish only after factual and visual approval.

### Security considerations

- Use Shopify-native resources and forms wherever possible.
- Do not place private credentials in Liquid, JavaScript, theme settings, or committed files.
- Escape rendered content and use supported Shopify objects and filters.
- Keep external scripts to the minimum approved set.
- Confirm privacy and consent language before analytics or email capture.
- Do not claim bookings, inventory, availability, rates, or amenities that are not operationally verified.

## 12. Content Governance

### Currently supplied business details - verify before launch

- Location: Rooftop of 888 Martinez Building, Brgy. Anahaw I, Silang, Cavite.
- Hours: Daily, 6:00 PM-2:00 AM.
- Last call: 1:30 AM.
- Facebook: `https://www.facebook.com/profile.php?id=61573491156329`

These are working references, not permission to publish without final confirmation.

### Required client inputs

- Confirmation that the SVG files in `docs/brand/` are final production masters.
- Licensed webfont files or approval to use the documented fallbacks.
- Final founder name, title, portrait, story, and quote.
- Verified menu names, descriptions, variants, prices, add-ons, badges, and availability.
- Verified coworking amenities, capacity, rates, duration, rules, hours, and reservation/walk-in process.
- Verified gaming platforms/stations, counts, rates, duration, rules, hours, and reservation/walk-in process.
- High-resolution product, venue, coworking, gaming, rooftop, founder, team, and customer photography with usage permission.
- Verified map listing, address, parking details, hours, last call, phone, email, and social links.
- Genuine approved reviews with source/permission.
- Privacy, consent, and other required legal text.

### Content rules

- Screenshots and menu sheets are not databases.
- Never store the only copy of a price or availability state inside an image.
- Never invent founder information, customer reviews, equipment claims, rates, or amenities.
- Hide incomplete modules until approved data exists.
- Use descriptive alt text for informative images and empty alt text for decorative imagery.

## 13. Execution Steps

### Phase 1 - Foundation

- Replace generic skeleton settings with Bean & Ben design tokens.
- Add approved logo variants and confirm font licensing.
- Build reusable buttons, icons, images, labels, and menu cards.
- Establish container, spacing, typography, focus, and responsive systems.

### Phase 2 - Approved homepage screens

- Header and mobile navigation.
- Hero.
- Venue information strip.
- Featured menu.
- Rooftop atmosphere.
- Location/directions.
- Footer.

### Phase 3 - Required experience content

- Coffee/Cowork/Play selection.
- Coworking details.
- Gaming lounge details.
- About and founder.
- Reviews/gallery.
- Full menu view.

### Phase 4 - Content integration

- Configure products, variants, collections, metafields, and metaobjects.
- Replace screenshot text and prices with verified Shopify data.
- Add real imagery, alt text, location, hours, and contact details.

### Phase 5 - QA and launch

- Visual comparison against every desktop/mobile reference.
- Accessibility and keyboard testing.
- Responsive, browser, and content-stress testing.
- Performance, local SEO, structured data, and link verification.
- Merchant editing test, backup, handoff guide, and publish approval.

## 14. Monetization

The MVP's revenue job is to increase qualified physical visits and on-site purchases:

`Discovery -> Menu/experience interest -> Directions or message -> Venue visit -> Coffee, food, coworking, or gaming revenue`

The most valuable conversion events are:

- View full menu.
- Get directions.
- View coworking details.
- View gaming details.
- Message the venue.

Future monetization can include Shopify pickup ordering, gift cards, prepaid coworking passes, gaming packages, events, or merchandise. These should be added only after the venue has reliable fulfillment, scheduling, refund, capacity, and support processes.

## 15. Scaling Plan

### Validate first

- Measure which experience drives visits.
- Track menu, directions, coworking, gaming, and message interactions.
- Collect recurring customer questions.
- Confirm staff can keep content accurate.

### Scale second

- Add dedicated coworking and gaming landing pages if anchored sections become too dense.
- Add structured events or campaigns.
- Add another location only after replacing single-location theme settings with a location metaobject.
- Add ordering or passes only after operational discovery.
- Keep one component system across all additions.

## 16. Major Risks and Decisions

| Risk | Impact | Decision |
| --- | --- | --- |
| WordPress handoff vs Shopify repository | Conflicting technical instructions | Shopify is the implementation platform; translate the intent rather than copying WordPress architecture |
| Screens show sample prices/details | Incorrect public information | Render verified Shopify data only |
| Missing coworking/gaming facts | Misleading claims or unusable sections | Do not invent; hide incomplete facts or modules |
| Missing founder/reviews | Loss of trust or fake content | Publish only approved real content |
| Screenshot-only development | Brittle, inaccessible page | Rebuild as semantic responsive components, not a single image |
| Too much decorative motion | Slower access and lower usability | Use restrained motion and respect reduced-motion preferences |
| Newsletter without a real workflow | Lost leads and consent risk | Omit until the destination and consent language are approved |
| Trying to launch every future feature | Delay and operational complexity | Launch the visit-focused MVP first |

## 17. Acceptance Criteria

The build is ready for launch only when:

- The first screen clearly communicates coffee, coworking, gaming, rooftop location, and the approved hero line.
- Pictured sections match the supplied desktop and mobile references in composition and hierarchy.
- Menu, coworking, gaming, hours, and directions are quickly reachable.
- All live prices, variants, availability, rates, amenities, rules, and business details are verified and editable.
- Founder and review content is genuine and approved.
- There are no broken links, duplicated IDs, missing required alt text, console errors, horizontal scrolling, clipped text, overlaps, or layout shifts.
- Keyboard navigation, focus states, mobile navigation, filters, dialogs, and carousels work correctly.
- Pages work at 320px, 375px, 768px, 1024px, 1440px, and large desktop widths.
- Current Chrome, Firefox, Safari, and Edge are tested.
- Images are responsive and optimized; below-the-fold media and maps are lazy-loaded.
- Local SEO, social sharing, backups, ownership, and merchant handoff are complete.

## 18. Brutal Feedback

The strongest part of the project is the distinctive visual identity. The biggest failure risk is treating that identity as the product.

The site will not succeed if it becomes a beautiful coffee-only landing page while coworking and gaming remain vague. The approved screens cover the visual foundation well, but several business-critical sections and facts are still missing. Development must not solve those gaps with invented copy, rates, equipment, or reviews.

The correct MVP is not more animation or more sections. It is a fast, accurate, highly editable site that makes the three experiences and the route to the rooftop immediately obvious.
