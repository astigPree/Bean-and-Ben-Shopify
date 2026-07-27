# Bean & Ben Shopify Theme - Design and UI Specification

| Item | Decision |
| --- | --- |
| Theme direction | Warm industrial minimalism / modern industrial luxury |
| Experience shorthand | `COFFEE. COWORK. PLAY.` |
| Hero line | `FOR YOUR BREAKS & BREAKTHROUGHS.` |
| Design status | Approved section screens exist; implement and extend their system |
| Platform | Shopify Online Store 2.0 |
| Version | 1.0 |
| Last updated | 27 July 2026 |

## 1. Visual Objective

The site should feel like entering a rooftop destination at night: dark, architectural, warm, confident, focused, and energetic.

It must balance:

- Coffee and food as sensory reasons to visit.
- Coworking as a useful, focus-friendly service.
- Gaming as social play, not an aggressive esports aesthetic.
- Rooftop atmosphere as the unifying place.

The experience should feel premium because of restraint, spacing, material cues, photography, and typography - not because of gold effects, ornamental decoration, or fake luxury language.

## 2. Approved Visual References

### Desktop and mobile screens

| Area | Desktop | Mobile |
| --- | --- | --- |
| Hero | `docs/screens/hero-section-pc.jpg` | `docs/screens/hero-section-phone.jpg` |
| Mobile navigation | N/A | `docs/screens/hero-section-phone-nav.jpg` |
| Venue information strip | `docs/screens/info-strip-pc.jpg` | `docs/screens/info-strip-phone.jpg` |
| Featured menu | `docs/screens/menu-section-pc.jpg` | `docs/screens/menu-section-phone.jpg` |
| Rooftop atmosphere | `docs/screens/rooftop-section-pc.jpg` | `docs/screens/rooftop-section-phone.jpg` |
| Directions | `docs/screens/direction-section-pc.jpg` | `docs/screens/direction-section-phone.jpg` |
| Footer | `docs/screens/footer-section-pc.jpg` | `docs/screens/footer-section-phone.jpg` |

### Brand artwork

- `docs/brand/brand-logo.svg`
- `docs/brand/brand-with-logo-and-text.svg`
- `docs/brand/vertical-brand-with-logo.svg`

Confirm that these SVG files are final production masters before launch. Never rebuild the wordmark using typed text.

### How to use the references

- Match composition, hierarchy, density, contrast, and responsive intent.
- Rebuild each screen as semantic Shopify components; never use the full screenshot as a webpage image.
- Treat pictured copy, prices, hours, parking, and directions as sample content until verified.
- Extend the same visual system to sections that do not yet have approved screens.
- Do not introduce a second aesthetic for coworking or gaming.

## 3. Visual Formula

| Layer | Target | Meaning |
| --- | ---: | --- |
| Dark industrial minimalism | 70% | Black surfaces, strong type, disciplined grids, steel/chrome, architectural structure |
| Warm hospitality | 20% | Warm ivory, oak, ambient light, food color, and human moments |
| Playful local personality | 10% | Taglish lines, campaign language, and small unexpected details |

The recommended digital color ratio is:

- 65% Obsidian/Carbon Black
- 20% Warm Ivory/Pure White
- 8% Chrome/Steel
- 5% Cement
- 2% Light Oak/Warm Ambient Light

Food, drinks, venue lighting, and people should provide most of the page's natural color.

## 4. Color System

### Core palette

| Token | Value | Primary use |
| --- | --- | --- |
| Obsidian Black | `#050505` | Primary background, navigation, footer, and dark hero surfaces |
| Carbon Black | `#151515` | Cards, panels, and subtle dark-surface separation |
| Warm Ivory | `#F3F0E8` | Primary light surface and warm text on dark |
| Pure White | `#FFFFFF` | Selective maximum-contrast text and logo use |
| Chrome Silver | `#C7CBD0` | Thin rules, icon outlines, borders, and metallic cues |
| Brushed Steel | `#777D82` | Secondary text, muted UI, and disabled states |
| Cement Gray | `#8B8983` | Texture and neutral environmental cues |
| Light Oak | `#C4A174` | Warm hover details and small section accents |
| Warm Ambient Light | `#D3A35A` | Active states, labels, and tiny highlights |

### Suggested global tokens

```css
:root {
  --color-black: #050505;
  --color-surface: #151515;
  --color-ivory: #f3f0e8;
  --color-white: #ffffff;
  --color-chrome: #c7cbd0;
  --color-steel: #777d82;
  --color-cement: #8b8983;
  --color-oak: #c4a174;
  --color-warm-light: #d3a35a;
  --color-page: var(--color-black);
  --color-text: var(--color-ivory);
  --color-muted: var(--color-steel);
  --color-border: color-mix(in srgb, var(--color-chrome) 42%, transparent);
  --color-action: var(--color-ivory);
  --color-action-text: var(--color-black);
}
```

### Color rules

- Chrome is a material cue, not a gradient effect.
- Use chrome in 1px rules, line icons, small labels, and hardware-like details.
- Use oak and warm light as micro-accents, not full-page brand colors.
- Avoid red/yellow fast-food palettes, heavy gold, neon RGB, large metallic gradients, and low-contrast gray-on-black copy.
- Do not rely on color alone for active, error, sold-out, or selected states.

## 5. Typography

### Font direction

| Role | Typeface | Use |
| --- | --- | --- |
| Logo | Supplied artwork | Never recreate with a font |
| Primary display | Bebas Neue Cyrillic direction | Hero, section titles, campaign statements, menu category titles |
| Supporting sans serif | Manrope | Body copy, navigation, prices, buttons, forms, and product descriptions |
| Fallback display | Bebas Neue, Impact, sans-serif | Use only when the approved display webfont cannot load |
| Fallback body | Manrope, Arial, sans-serif | Standard body fallback |

Do not ship an unlicensed font. If the exact display font file is not supplied and licensed for web use, obtain approval for the fallback before visual sign-off.

### Type scale

| Role | Desktop | Mobile | Notes |
| --- | --- | --- | --- |
| Hero headline | `clamp(72px, 9vw, 128px)` | `clamp(52px, 15vw, 72px)` | Uppercase; line-height `0.85-0.95` |
| Section title | `48-72px` | `38-52px` | Short phrases with strong spacing |
| Subsection title | `30-42px` | `26-34px` | Do not overuse all caps |
| Card title | `20-28px` | `20-24px` | Concise and high contrast |
| Body | `16-18px` | `16-18px` | Line-height `1.5-1.7` |
| Small label | `11-13px` | `11-13px` | Tracking `0.10-0.16em` |
| Button | `13-15px` | `13-15px` | Semibold; uppercase is allowed |

### Type rules

- Display headlines are short, uppercase, tightly spaced, and free of outlines or shadows.
- Body copy should stay within roughly 55-70 characters per line.
- Use modest tracking on navigation and technical labels.
- Do not set whole pages in uppercase.
- Use semantic heading order and exactly one meaningful `h1` per page.
- Hero line breaks are presentational. The underlying text remains the approved phrase.

## 6. Grid, Containers, and Spacing

### Layout grid

| Viewport | Grid | Side margins | Section spacing |
| --- | --- | --- | --- |
| Desktop `>=1280px` | 12 columns; max content width `1440px` | `48-80px` | `120-180px` |
| Tablet `768-1279px` | 8 columns | `32-48px` | `88-120px` |
| Mobile `<768px` | 4 columns | `20-24px` | `64-88px` |

### Spacing tokens

```css
:root {
  --space-1: 0.25rem;
  --space-2: 0.5rem;
  --space-3: 0.75rem;
  --space-4: 1rem;
  --space-6: 1.5rem;
  --space-8: 2rem;
  --space-12: 3rem;
  --space-16: 4rem;
  --space-24: 6rem;
  --space-32: 8rem;
  --container: 90rem;
}
```

### Layout rules

- Use deliberate asymmetry within a disciplined grid.
- Large black fields and negative space are part of the design.
- Alternate image-led and type-led sections to avoid a repetitive card wall.
- Use warm-ivory sections selectively to create breathing room.
- Full-width imagery may break the content grid; text and controls should remain aligned to the grid.
- Absolute positioning is acceptable only for intentional art direction and must collapse safely on smaller screens.

### Shape language

| Element | Radius |
| --- | ---: |
| Buttons | `2-6px` |
| Cards | `0-8px` |
| Images | `0-4px` |
| Large containers | Maximum `12px` |

Do not use large soft pills or rounded SaaS-dashboard cards.

## 7. Responsive Breakpoints

| Token | Range | Use |
| --- | --- | --- |
| `xs` | `320-479px` | Small phones; stress-test labels and CTA widths |
| `sm` | `480-767px` | Large phones |
| `md` | `768-1023px` | Tablets and small landscape devices |
| `lg` | `1024-1279px` | Laptops |
| `xl` | `1280-1599px` | Desktop |
| `2xl` | `1600px+` | Large desktop with preserved max-width and negative space |

### Mobile rules

- Maintain at least `20px` side padding.
- All primary interactive targets must be at least `44x44px`.
- Recompose image/text layouts instead of shrinking desktop overlaps.
- Keep `View Menu` and `Get Directions` within easy reach.
- Use horizontal category scrolling or an accessible select for long menu lists.
- Avoid autoplay video, heavy parallax, and interaction that depends on hover.
- The layout must support 320px without horizontal scrolling.

## 8. Core Components

### Header and navigation

Desktop:

- Transparent over the hero.
- Becomes solid Obsidian Black after the hero threshold.
- Horizontal wordmark approximately `140-180px` wide.
- Links: Menu, Coworking, Gaming, About, Reviews/Gallery, Location.
- Primary utility CTA at the far right: Explore the Space or Get Directions.
- Sticky transition: `150-250ms`.

Mobile:

- Fixed black or translucent top bar.
- Compact wordmark or monogram approximately `110-140px` wide.
- Accessible menu button with a visible label or accessible name.
- Full-screen Obsidian Black drawer based on `hero-section-phone-nav.jpg`.
- Large vertically stacked links, current hours microcopy, action CTA, and approved social links.
- Trap focus while open, close on Escape, restore focus to the trigger, and lock background scrolling.

### Buttons

Primary:

- Warm Ivory background.
- Obsidian Black text.
- Minimum touch height `44px`.
- Dark or oak hover/active treatment with clear text contrast.

Secondary:

- Transparent background.
- Chrome or warm-ivory 1px border.
- Warm-ivory text.
- Visible hover and focus treatment.

Rules:

- Use direct labels such as `VIEW MENU`, `EXPLORE THE SPACE`, and `GET DIRECTIONS`.
- Do not use vague labels such as `Learn More` where a specific action exists.
- Never make hover the only indication that an element is clickable.

### Labels and badges

- Use one small technical-label style.
- Allowed menu badges: Signature, Bestseller, House Favorite, New, and Sold Out.
- Warm Light or Light Oak may highlight an active or featured state.
- Do not use sticker bursts, emoji, floral badges, or multiple competing badge designs.

### Cards

Product cards:

- Carbon Black surface.
- Thin Chrome/Steel border.
- Strong editorial image.
- Product name, concise description, explicit variant prices, and no more than one badge.
- Minimal or no drop shadow.

Content cards:

- Warm Ivory or Carbon Black.
- Use only when grouping improves scanning.
- Do not place every paragraph inside a card.

### Icons and dividers

- Use simple line icons with consistent stroke weight.
- Use white, Chrome, or small Warm Light accents.
- Dividers are 1px Chrome, Steel, or Warm Ivory.
- Avoid cute permanent coffee illustrations and gamer-interface icon clutter.

### Forms

- Use visible labels, not placeholder-only fields.
- Use large input targets, clear help text, and specific error messages.
- Newsletter capture is optional and should not appear until the destination, consent copy, and owner workflow are confirmed.

### States

| State | Treatment |
| --- | --- |
| Hover | Subtle color or `translate` change |
| Focus | Visible 2px high-contrast outline |
| Active | Warm Light/Oak accent plus text or shape change |
| Disabled | Brushed Steel with reduced emphasis while readable |
| Error | Clear message plus visual indicator; never red alone |
| Loading | Restrained spinner or skeleton that preserves layout |
| Sold out | Explicit label and unavailable control state |

## 9. Section Blueprints

### 9.1 Hero

References:

- `docs/screens/hero-section-pc.jpg`
- `docs/screens/hero-section-phone.jpg`

Purpose:

- Establish the rooftop coffee + coworking + gaming concept in one screen.
- Create the strongest visual impact on the page.
- Drive View Menu and Explore the Space actions.

Content hierarchy:

1. Logo/navigation.
2. Eyebrow: `COFFEE • COWORK • PLAY`.
3. `h1`: `FOR YOUR BREAKS & BREAKTHROUGHS.`
4. Supporting line: `Coffee, focus-friendly space, and social gaming under one rooftop in Silang.`
5. Primary CTA: `EXPLORE THE SPACE`.
6. Secondary CTA: `VIEW THE MENU`.
7. Optional verified hours or scroll cue.

Desktop composition:

- Minimum height `88-100vh`.
- Cinematic dark venue image with warm practical lighting.
- Strong left-aligned headline.
- Hero product/venue visual may overlap the center-right grid.
- Thin rules, compact technical labels, and logo devices support the composition.

Mobile composition:

- Minimum height approximately `85svh`.
- Headline remains dominant.
- Copy and CTAs stack without covering the hero product.
- Primary and secondary actions stay visible without horizontal overflow.
- Preserve the lower product image and restrained `Scroll to discover` cue from the approved screen.

Merchant-editable settings:

- Eyebrow, headline, body, primary/secondary labels and links.
- Desktop and mobile images with focal-point control.
- Optional verified microcopy.
- Overlay strength and content alignment within approved choices.

Do not use:

- Sliders.
- Multiple competing products.
- Long paragraphs.
- Mobile background video.
- Floating ingredient effects.
- Fake coding screens.
- RGB gaming effects.

### 9.2 Mobile Navigation Drawer

Reference:

- `docs/screens/hero-section-phone-nav.jpg`

Required behavior:

- Full viewport, dark surface, large scannable links.
- Clear close control.
- Links for Home, About, Coffee/Menu, Food, Coworking, Gaming, Rooftop, Gallery, Visit Us, and Contact as relevant to the launched information architecture.
- Verified open-hours microcopy and one high-value CTA.
- Approved social links only.
- Keyboard focus management and reduced-motion-safe open/close transitions.

### 9.3 Venue Information Strip

References:

- `docs/screens/info-strip-pc.jpg`
- `docs/screens/info-strip-phone.jpg`

Purpose:

- Answer high-frequency visit questions immediately after the hero.

Recommended facts:

- Rooftop Cafe / Silang, Cavite.
- Verified open hours.
- Dine-in and takeaway status.
- Coworking.
- Gaming.
- Parking, only if confirmed.

Desktop:

- Warm Ivory horizontal band.
- Six evenly distributed icon-and-label facts separated by small rules or spacing.

Mobile:

- Stack facts in a clear vertical timeline or compact grid.
- Keep every label readable and every factual value editable.

### 9.4 Experience Selection

This section is required by the handoff even though no dedicated approved screenshot was supplied.

Use three clear choices:

- Break Mode / Coffee and Food.
- Work Mode / Coworking.
- Game Mode / Gaming Lounge.

Extend the existing dark surfaces, condensed headings, thin metallic rules, real photography, and small oak highlights. Do not use three generic rounded marketing cards.

### 9.5 Featured Menu

References:

- `docs/screens/menu-section-pc.jpg`
- `docs/screens/menu-section-phone.jpg`

Purpose:

- Sell cravings and demonstrate menu breadth without placing the full menu on the homepage.

Content:

- Heading: `PICK YOUR CRAVING` or the approved screen heading.
- Three to six signature/bestselling products.
- One visually dominant product and supporting items.
- Product image, title, short description, explicit price/variant price, one badge.
- CTA: `EXPLORE FULL MENU`.

Desktop:

- Obsidian/Carbon section with editorial asymmetry.
- One large featured card and smaller supporting cards.
- Warm product photography supplies the color.

Mobile:

- Large featured product first.
- Supporting cards flow in a stable one- or two-column layout depending on available width.
- Do not reduce text or price below readable sizes.

Data rules:

- Render Shopify product and variant data.
- Never hard-code the screenshot's product prices.
- Use product availability for sold-out treatment.
- Use collections for category navigation.

### 9.6 Rooftop Atmosphere

References:

- `docs/screens/rooftop-section-pc.jpg`
- `docs/screens/rooftop-section-phone.jpg`

Purpose:

- Sell the destination, not only the menu.
- Connect coffee, work, dining, social activity, and rooftop views.

Design:

- Warm Ivory section creates contrast after dark menu content.
- Condensed black display heading and short supporting copy.
- Small Warm Light CTA.
- Filmstrip-like gallery with dark frame/rules and small experience labels.

Desktop:

- Wide horizontal image sequence with selected venue moments.

Mobile:

- Intro content stacks above the gallery.
- Horizontal swipe is allowed when controls, scroll affordance, keyboard access, and a non-JavaScript fallback exist.

Avoid automatic social feeds and uncontrolled carousels.

### 9.7 Coworking / Work Mode

No approved section screenshot exists yet. Extend the rooftop and featured-menu system.

Required content:

- Who the space is for.
- Verified seating types, capacity, Wi-Fi, outlets, rates, duration, hours, noise expectations, rules, and walk-in/reservation process.
- Real guests working or studying.
- CTA: `VIEW COWORKING DETAILS`, or `MESSAGE TO RESERVE` only when the process is confirmed.

Recommended composition:

- Image-led split section.
- Dark Carbon panel with condensed `WORK MODE` title.
- Structured fact list using thin rules, not a dense card dashboard.

### 9.8 Gaming Lounge / Game Mode

No approved section screenshot exists yet. Use the same design language as coworking.

Required content:

- Verified platforms/stations, counts, rates, duration, game-library policy, capacity, age/equipment rules, hours, and walk-in/reservation process.
- Real players, controllers/screens, group energy, and clean stations.
- CTA: `VIEW GAMING DETAILS`, or `MESSAGE TO BOOK` only when booking is confirmed.

Avoid neon RGB backgrounds, fake esports claims, aggressive glitch effects, and a separate gamer-site aesthetic.

### 9.9 About and Founder

Purpose:

- Explain why coffee, coworking, gaming, and rooftop atmosphere belong together.
- Add a real human story.

Design:

- Use an environmental founder portrait or venue image.
- Limit homepage about copy to approximately `60-120` words.
- Founder story must be editable and omitted until approved.
- One short founder quote may use display type; do not use generic motivational filler.

### 9.10 Reviews and Gallery

Recommended:

- Two or three genuine approved reviews.
- Six to eight strong images covering coffee, focus, play, food, people, and rooftop atmosphere.

If a carousel is used:

- Provide visible controls.
- Support keyboard navigation and pause behavior.
- Do not autoplay rapidly.
- Preserve a useful non-JavaScript layout.

Never generate testimonials or import social quotes without approval and source confirmation.

### 9.11 Directions

References:

- `docs/screens/direction-section-pc.jpg`
- `docs/screens/direction-section-phone.jpg`

Content:

- Heading: `SUNDAN ANG LIWANAG`.
- Verified address.
- Verified hours and last call.
- Parking and landmark guidance only when confirmed.
- `GET DIRECTIONS` CTA.
- `MESSAGE US` or Facebook action.
- Map or static map preview.

Desktop:

- Dark two-column layout.
- Details and actions on the left.
- Map treatment on the right.

Mobile:

- Stack heading, facts, actions, then map.
- Directions action remains prominent.

Performance:

- Prefer a static preview linked to the verified maps listing.
- Lazy-load any third-party map embed.

### 9.12 Footer

References:

- `docs/screens/footer-section-pc.jpg`
- `docs/screens/footer-section-phone.jpg`

Required:

- Wordmark or monogram.
- Approved social links.
- Menu, Coworking, Gaming, About, Founder, Gallery/Reviews, and Location links as applicable.
- Verified address, hours, last call, and contact details.
- Final Menu or Directions action.
- Copyright and legal links.

Responsive:

- Desktop uses a structured multi-column grid.
- Mobile centers the brand, then uses readable grouped links and information.
- Newsletter form is conditional on an approved marketing workflow and consent copy.

## 10. Photography and Art Direction

### Show

- Condensation, steam, foam, espresso flow, sauce texture, and crisp food edges.
- Branded cups and real serving sizes.
- Warm lights against the night.
- Rooftop views, exterior landmarks, and industrial material details.
- Candid guests working, studying, collaborating, eating, and gaming.
- Students, freelancers, professionals, creators, gamers, barkadas, couples, and families.
- Black stone, smoked glass, steel, cement, black fabric, and light oak.

### Avoid

- Generic stock coffee-bean backgrounds.
- Fake office and productivity poses.
- Cluttered gamer setups and RGB cliches.
- Rustic kraft paper, farmhouse styling, pastels, or floral props.
- Low-resolution cutouts and heavy drop shadows.
- Floating ingredients across multiple sections.
- Misleading portions or staged claims.
- Empty spaces that feel sterile.

### Image implementation

- Provide desktop and mobile crops where art direction requires them.
- Use Shopify responsive image filters and declared dimensions.
- Preserve focal points.
- Use AVIF/WebP delivery where Shopify supports it.
- Preload only the actual hero LCP image.
- Lazy-load below-the-fold media.

## 11. Motion and Interaction

| Interaction | Timing | Treatment |
| --- | ---: | --- |
| Hover/focus | `150-250ms` | Small color, border, or translation change |
| Section entrance | `500-800ms` | Restrained fade, small slide, or image reveal |
| Product emphasis | `300-500ms` | Scale `1.00-1.02` or subtle translation |
| Mobile drawer | `250-400ms` | Opacity plus controlled panel movement |

Rules:

- Respect `prefers-reduced-motion`.
- Do not delay access to information.
- Do not animate layout dimensions in ways that cause shift.
- Avoid cursor trails, constant floating objects, bounce effects, heavy parallax, and decorative canvas animation.
- Motion supports hierarchy; it is never the product.

## 12. Accessibility Requirements

- Use semantic landmarks and logical heading order.
- Maintain WCAG 2.1 AA contrast for text and controls.
- All interactive elements are keyboard reachable.
- Focus indicators are always visible.
- Icon-only controls have accessible names.
- Form inputs use real labels and clear error messages.
- Informative images use meaningful alt text; decorative images use empty alt text.
- Dialogs, navigation drawers, filters, and carousels manage focus correctly.
- Touch targets are at least `44x44px`.
- Reduced-motion preferences are respected.
- Menus and content remain usable without JavaScript.
- Text must remain usable at browser zoom and user font scaling.

## 13. Shopify Theme Implementation Map

### Global foundation

| Path | Responsibility |
| --- | --- |
| `layout/theme.liquid` | Document shell, content regions, critical assets, and global semantics |
| `config/settings_schema.json` | Brand colors, typography, layout, venue details, social links, and optional global actions |
| `snippets/css-variables.liquid` | Render approved design tokens from global settings |
| `assets/critical.css` | Reset and truly global above-the-fold foundations only |
| `locales/en.default.json` | Fixed user-facing UI strings |

### Sections

| Proposed path | Responsibility |
| --- | --- |
| `sections/header.liquid` | Desktop header and mobile drawer |
| `sections/hero-banner.liquid` | Approved hero composition |
| `sections/venue-info-strip.liquid` | Editable venue facts |
| `sections/experience-pillars.liquid` | Break, Work, and Game mode selection |
| `sections/featured-menu.liquid` | Selected Shopify products and menu CTA |
| `sections/rooftop-experience.liquid` | Intro and atmosphere gallery |
| `sections/experience-details.liquid` | Reusable coworking or gaming detail section |
| `sections/about-founder.liquid` | About story and founder profile |
| `sections/reviews-gallery.liquid` | Approved social proof and gallery |
| `sections/location-directions.liquid` | Venue details, actions, and map treatment |
| `sections/footer.liquid` | Footer navigation, venue details, socials, and optional signup |

### Blocks

| Proposed path | Responsibility |
| --- | --- |
| `blocks/venue-fact.liquid` | Icon, label, and verified value |
| `blocks/experience-pillar.liquid` | Break, Work, or Game mode card |
| `blocks/gallery-item.liquid` | Image, label, caption, and alt text |
| `blocks/review-card.liquid` | Approved quote and source |

### Snippets

| Proposed path | Responsibility |
| --- | --- |
| `snippets/button.liquid` | Shared primary/secondary action rendering |
| `snippets/icon.liquid` | Approved icon set |
| `snippets/image.liquid` | Responsive image rendering |
| `snippets/menu-product-card.liquid` | Shopify product/variant menu card |
| `snippets/price-variants.liquid` | Explicit hot/iced/size price output |

Every new snippet must begin with LiquidDoc. Blocks that are statically rendered must also include LiquidDoc.

### Templates

| Proposed path | Responsibility |
| --- | --- |
| `templates/index.json` | Homepage section order |
| `templates/page.menu.json` | Full menu view |
| `templates/page.coworking.json` | Coworking detail view if launched |
| `templates/page.gaming.json` | Gaming detail view if launched |

### Styling and scripts

- Keep component CSS and JavaScript in the relevant section, block, or snippet using `{% stylesheet %}` and `{% javascript %}` where supported.
- Use CSS variables for settings that control one property.
- Use approved CSS classes for settings that switch a multi-property layout.
- Keep JavaScript dependency-free and progressively enhanced.
- Validate every section/block schema.
- Use `{{ block.shopify_attributes }}` on merchant-editable block wrappers.
- Use locale keys for fixed UI copy.

## 14. Merchant Editing Boundaries

### Global settings

- Logo variants.
- Approved brand colors and font choices.
- Address, hours, last call, parking, map URL, contact details, and social links.
- Default CTA destinations.
- Optional announcement.

### Section settings

- Section headings and short copy.
- Desktop/mobile images and focal points.
- Layout choice from a small approved set.
- Section spacing within bounded values.
- Selected products, collections, metaobjects, or pages.
- CTA label and destination.

### Do not expose

- Arbitrary colors on every section.
- Unbounded typography sizes.
- Unlimited corner radii.
- Free-form layout controls that can break the composition.
- Multiple animation styles.
- Settings that duplicate live product prices or availability.

The merchant should be able to update content without being able to accidentally dismantle the brand system.

## 15. Content and Data Rules

- Use Shopify products and variants for menu names, prices, hot/iced/size choices, media, and availability.
- Use collections for menu categories.
- Use metafields for badges, dietary/allergen notes, and menu-specific labels.
- Use structured experience content for coworking and gaming.
- Keep address, hours, map URL, and social links globally editable.
- Do not publish placeholder founders, testimonials, rates, amenities, or equipment.
- Do not bake text into images when it needs to remain readable, translatable, searchable, or editable.
- Do not use screenshot prices as defaults.

## 16. Performance and SEO

- Compress hero imagery and preload only the actual LCP image.
- Declare image width and height.
- Lazy-load below-the-fold images, gallery media, and maps.
- Avoid third-party libraries for simple interactions.
- Prevent layout shifts during image, font, and content loading.
- Use a clear page title and meta description for Bean & Ben in Silang.
- Use verified `LocalBusiness` or `CafeOrCoffeeShop` structured data only.
- Create a branded `1200x630` social-sharing image showing venue atmosphere and coffee/work/play cues.
- Keep URLs clear, such as `/pages/menu`, `/pages/coworking`, or `/pages/gaming-lounge`, based on the launched structure.

## 17. Visual QA Checklist

- Hero uses the exact approved phrase and communicates all three experiences.
- Desktop and mobile compositions match their supplied references.
- Black surfaces remain warm and readable rather than cold or muddy.
- Warm Ivory sections create controlled contrast.
- Chrome/Oak accents remain restrained.
- Display and body typography match the documented hierarchy.
- Product imagery is sharp and prices come from Shopify.
- Header, mobile drawer, CTAs, filters, and carousels are accessible.
- No section becomes a generic card grid.
- No text is clipped at 320px or at large display sizes.
- No horizontal page scrolling exists.
- The layout is tested at 320px, 375px, 768px, 1024px, 1440px, and 1600px+.
- Reduced-motion mode remains complete and usable.
- Long product names, missing optional images, sold-out products, and empty optional content are tested.
- Current Chrome, Firefox, Safari, and Edge are visually checked.

## 18. Do Not Build

- A generic coffee template with stock beans and script fonts.
- A corporate coworking dashboard.
- A neon gaming landing page.
- A fast-food promotional layout.
- A gold-heavy fake luxury theme.
- A homepage containing the entire menu.
- A hero carousel or autoplay mobile video.
- A screenshot sliced into webpage images.
- Fake reviews, founder content, prices, amenities, rates, or equipment.
- An email form that goes nowhere.

## 19. Developer Quick Reference

```text
Brand: Bold, warm, versatile
Concept: Coffee + Cowork + Gaming under one rooftop
Hero: FOR YOUR BREAKS & BREAKTHROUGHS.
Style: Warm industrial minimalism
Primary surfaces: #050505 / #151515
Primary light: #F3F0E8
Metal cue: #C7CBD0
Warm accents: #C4A174 / #D3A35A
Display: Bebas Neue Cyrillic direction
Body: Manrope
Container: 1440px
Mobile gutter: 20-24px
Touch target: 44px minimum
Primary actions: Explore the Space, View Menu, Get Directions
Build model: Shopify sections, blocks, snippets, JSON templates
Content rule: Verified, structured, editable, never invented
```
