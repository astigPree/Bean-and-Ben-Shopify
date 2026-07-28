# Bean & Ben Shopify Theme — Project Progress

Last updated: July 27, 2026

## Workflow Constraint

- Do not run `shopify theme dev` or start the local preview server from Codex.
- The developer will control the Shopify development server and visual preview.

## Navigation / Header

Status: Complete — ready for content setup and visual review in Shopify.

Reference images:

- `docs/screens/hero-section-phone.jpg`
- `docs/screens/hero-section-phone-nav.png`
- `docs/screens/hero-section-pc.jpg`

Implemented:

- Connected the header section to the storefront through `layout/theme.liquid`.
- Enabled the reusable Shopify header section group in `sections/header-group.json`.
- Added a mobile-first header with the Bean & Ben logo on the left and hamburger control on the right.
- Added a full-screen, scrollable mobile navigation drawer based on `hero-section-phone-nav.png`.
- Added mobile active-page accent color and underline treatment.
- Added editable opening hours, reservation button, and Facebook, Instagram, and TikTok links to the mobile drawer.
- Added the transparent desktop navigation layout shown in `hero-section-pc.jpg`.
- Added separate desktop and mobile menu selectors so each viewport can follow its reference navigation.
- Added responsive logo sizing with a text fallback when no logo has been uploaded.
- Added an uploadable header logo in the Header section settings.
- Added an editable brand title beside symbol-only logo uploads.
- Added separate mobile and desktop logo-mark width controls.
- Updated the header component layouts to use Flexbox wherever a one-dimensional layout is appropriate.
- Added fallback support for the global light and primary logos in Theme settings.
- The home-page header overlays the hero area. On other page types, it uses a normal black header so page content is not covered.
- Added keyboard Escape handling, menu closing after link selection, reduced-motion support, and accessible navigation labels.
- Connected header colors, borders, desktop spacing, and button radius to the global CSS variables.
- Added the required LiquidDoc header to `snippets/css-variables.liquid`.
- Fixed the invalid trailing comma in `sections/header-group.json`.

Files updated:

- `sections/header.liquid`
- `sections/header-group.json`
- `layout/theme.liquid`
- `snippets/css-variables.liquid`
- `docs/project/PROJECT PROGRESS.MD`

Validation:

- Shopify Theme Check: passed.
- Result: 40 theme files inspected with no offenses.

## Shopify Theme Editor Setup

The navigation code is complete, but the store content must be assigned in the Theme Editor:

1. Open the Header section.
2. Upload the approved transparent light logo under **Header logo**.
3. Enable **Show brand title beside logo** and change **Brand title** as needed.
4. Adjust the mobile or desktop logo-mark width if the uploaded symbol is too large.
5. Select the desktop navigation menu under **Desktop menu**.
6. Select the full mobile navigation menu under **Mobile menu**.
7. Set the opening hours, reservation link, and social URLs.

Recommended desktop menu order from the reference:

1. Menu
2. Cowork
3. Gaming
4. Our Space
5. About
6. Location

Recommended mobile menu order from the reference:

1. Home
2. About Us
3. Coffee
4. Food
5. Coworking
6. Gaming
7. Rooftop
8. Events
9. Gallery
10. Visit Us
11. Contact

## Hero Section

Status: Complete - ready for image assignment and visual review in Shopify.

Implemented:

- Added the hero to `templates/index.json` so it renders directly beneath the overlaid header.
- Built the section mobile-first from `hero-section-phone.jpg`, with responsive desktop behavior from `hero-section-pc.jpg`.
- Added separate uploadable phone and desktop background images; both are empty by default.
- Added automatic image fallback so one uploaded image can serve both screen sizes.
- Added editable eyebrow, multiline heading, description, primary action, secondary action, and scroll cue.
- Kept **Explore the space** visible as a non-navigating button when its link is empty; assigning a link automatically makes it functional.
- Added independent phone and desktop image-position controls to keep the subject visible after cropping.
- Added adjustable dark-overlay strength and minimum-height controls.
- Used Flexbox for the content, action buttons, and scroll-cue layouts.
- Added clear Liquid and CSS comments inside `sections/hero-section.liquid`.
- Connected the global display-font setting to CSS variables for the condensed hero heading.

Validation:

- Shopify Theme Check: passed.
- Result: 41 theme files inspected with no offenses.
- `templates/index.json`: valid JSON.
- Hero CSS: no CSS Grid layout used.

Theme Editor setup:

1. Open the home page in the Theme Editor.
2. Open **Hero section**.
3. Upload the portrait artwork under **Mobile background image**.
4. Upload the landscape artwork under **Desktop background image**.
5. Adjust the image-position controls if the cup or venue focal point is cropped.
6. Optionally assign the secondary button link; when empty, **Explore the space** stays visible without redirecting.

## Venue Information Strip

Status: Complete - connected immediately below the homepage hero.

Reference images:

- `docs/screens/info-strip-phone.jpg`
- `docs/screens/info-strip-pc.jpg`

Implemented:

- Built the phone layout as a vertical timeline with large outlined icons, editable titles, editable details, rules, stems, and timeline dots.
- Built the desktop layout as six evenly distributed information columns along one horizontal rule.
- Matched the phone reference by showing location, hours, and dine-in/takeaway by default while retaining all six facts on desktop.
- Added a **Show on mobile** control to every fact block for future content changes.
- Used Flexbox for the mobile list, desktop row, individual facts, icon alignment, and text alignment.
- Added six reorderable Theme Editor blocks: location, parking, hours, dine-in and takeaway, coworking, and gaming.
- Added a built-in SVG icon selector so the section needs no external icon library or asset request.
- Added editable background, text, accent, divider, and accessibility-label settings.
- Reduced the phone and desktop icon scale by about 20% and tightened the related timeline and section spacing.
- Added explanatory Liquid and CSS comments in `sections/venue-info-strip.liquid`.
- Connected the section after the hero in `templates/index.json`.

Validation:

- Shopify Theme Check: passed.
- Result: 42 theme files inspected with no offenses.
- `templates/index.json`: valid JSON.
- Venue information CSS: no CSS Grid layout used.

Theme Editor setup:

1. Open the home page and select **Venue information**.
2. Reorder or remove facts as needed.
3. Open each **Venue fact** block to change its icon, title, or detail.
4. Use **Show on mobile** to control which facts appear in the phone timeline.
5. Verify parking, opening hours, service availability, Wi-Fi, outlets, and gaming wording before publishing.

## Featured Menu

Status: Complete - connected below the venue information strip.

Reference images:

- `docs/screens/menu-section-phone.jpg`
- `docs/screens/menu-section-pc.jpg`

Implemented:

- Built the section mobile-first with one large lead-product card followed by responsive supporting cards.
- Built the desktop composition with one dominant product beside four smaller product cards.
- Used Flexbox for the section, product regions, supporting cards, content, empty state, and menu action.
- Added a Shopify **Featured products** selector supporting up to five manually ordered products.
- Added an optional Shopify collection fallback when no individual products are selected.
- Rendered product image, title, description, price, availability, URL, and supported product-tag badges from Shopify data.
- Added automatic badge support for `Bestseller`, `Seasonal`, and `Signature` product tags.
- Added a Shopify-generated image placeholder only when a selected product has no featured image.
- Added a branded **The menu is brewing** empty state when no products are available, without fake products or prices.
- Added an optional uploadable section background image with editable position and dark-overlay strength.
- Kept the existing dark textured CSS background as the fallback when no background image is uploaded.
- Added explanatory Liquid and CSS comments in `sections/featured-menu.liquid`.
- Added a documented reusable product-card snippet in `snippets/featured-menu-card.liquid`.
- Connected the component spacing to the global mobile and desktop section-spacing settings.
- Connected the section after the venue information strip in `templates/index.json`.
- Rebuilt the featured-menu cards against the supplied phone and desktop references: a cinematic lead product, two-column supporting products, image-and-copy card splits, orange badges/rules, and the bordered full-menu CTA.
- Grouped each Shopify product's heading and details so the title, description, and price follow the reference's editorial spacing without hard-coded product content.
- Updated the default section description and accent orange to match the approved reference more closely.

Validation:

- Shopify Theme Check: passed.
- Result: 45 theme files inspected with no offenses after the reference-alignment rebuild.
- `templates/index.json`: valid JSON.
- Featured menu CSS: no CSS Grid layout used.

Theme Editor setup:

1. Open the home page and select **Featured menu**.
2. Select up to five products under **Featured products**; the first becomes the large card.
3. Optionally select a **Fallback collection**.
4. Add `Bestseller`, `Seasonal`, or `Signature` tags to Shopify products when a badge is needed.
5. Set the menu link, or allow it to use the selected collection or all-products page.
6. Ensure each selected Shopify product has a featured image, description, current price, and correct availability.
7. Optionally upload a **Background image**, then adjust its position and overlay strength for readable text.

## Rooftop Carousel

Status: Complete - connected below the Featured menu.

Reference images:

- `docs/screens/rooftop-section-phone.jpg`
- `docs/screens/rooftop-section-pc.jpg`

Implemented:

- Built the warm-ivory mobile-first intro with editable eyebrow, multiline heading, description, and CTA.
- Built the dark filmstrip carousel treatment with framed images, captions, slide numbering, and film perforation rails.
- Added reorderable **Gallery image** blocks supporting an image, caption, alternative text, and image position.
- Added automatic horizontal slide movement with an editable interval.
- Added native swipe and trackpad scrolling, previous/next buttons, slide dots, and keyboard arrow controls.
- Paused automatic movement while the carousel is hovered or keyboard-focused and while it is outside the viewport.
- Disabled automatic movement for visitors who prefer reduced motion.
- Added responsive mobile and desktop slide-width controls.
- Reduced the default phone and desktop slide widths and removed the oversized fixed image heights so gallery images retain compact landscape proportions.
- Reduced the film rails and caption heights to keep the entire carousel visually lighter.
- Added three branded sample slides when no image blocks exist.
- Added a branded placeholder when a gallery block exists without an uploaded image.
- Used Flexbox for the intro, carousel track, slides, captions, controls, dots, and fallback layouts.
- Added explanatory Liquid, CSS, and JavaScript comments in `sections/rooftop-carousel.liquid`.
- Connected the section below the Featured menu in `templates/index.json`.

Validation:

- Shopify Theme Check: passed.
- Result: 45 theme files inspected with no offenses.
- `templates/index.json`: valid JSON.
- Rooftop carousel JavaScript: syntax check passed.
- Rooftop carousel CSS: no CSS Grid layout used.

Theme Editor setup:

1. Open the home page and select **Rooftop carousel**.
2. Add a **Gallery image** block for each venue image.
3. Upload the image, add a short caption, and write useful alternative text.
4. Reorder the blocks to change the carousel sequence.
5. Adjust image position when an important subject is cropped.
6. Set autoplay behavior, interval, and responsive slide widths.
7. Assign the CTA link when the destination page is ready.

## Visit Bean & Ben

Status: Complete - connected below the Rooftop carousel.

Reference images:

- `docs/screens/direction-section-phone.jpg`
- `docs/screens/direction-section-pc.jpg`

Implemented:

- Built the bordered black venue panel mobile-first from the supplied phone reference.
- Built the desktop Flexbox composition with venue information on the left and the uploaded map filling the right side.
- Added editable heading, address, opening hours, parking information, and nearby landmark settings.
- Added inline location, clock, parking, map, and message SVG icons without external icon dependencies.
- Added editable **Get directions** and **Message us** action labels and links.
- Kept actions visible but safely disabled when their links have not been assigned.
- Added an optional setting to open the directions link in a new browser tab.
- Added an uploadable map image, alternative text, and image-position control in the Theme Editor.
- Added a branded map-style fallback so the section remains complete before a map image is uploaded.
- Added editable section, panel, text, border, and primary-button colors.
- Added explanatory Liquid and CSS comments throughout `sections/visit-bean-ben.liquid`.
- Used Flexbox for the panel, venue facts, actions, map fallback, and responsive desktop composition.
- Connected the section after the Rooftop carousel in `templates/index.json`.

Validation:

- Shopify Theme Check: passed.
- Result: 46 theme files inspected with no offenses.
- `templates/index.json`: valid JSON.
- Visit Bean & Ben CSS: no CSS Grid layout used.

Theme Editor setup:

1. Open the home page and select **Visit Bean & Ben**.
2. Confirm the address, operating hours, parking details, and nearby landmark.
3. Add the Google Maps or other approved destination URL to **Directions link**.
4. Add the approved Messenger, contact page, or other channel to **Message link**.
5. Upload the approved map under **Map image**.
6. Add meaningful map alternative text and adjust **Map image position** if the marker is cropped.

## Footer

Status: Complete - globally connected after page content.

Reference images:

- `docs/screens/footer-section-phone.jpg`
- `docs/screens/footer-section-pc.jpg`

Implemented:

- Rebuilt the existing footer section mobile-first from the supplied phone reference.
- Built the wide desktop composition with brand, three navigation columns, and newsletter in one Flexbox row.
- Enabled the existing `footer-group` in `layout/theme.liquid`, placing it below Visit Bean & Ben on the homepage and below content on all other storefront templates.
- Added editable brand title, tagline, copyright name, copyright message, and location.
- Added editable Facebook, Instagram, and TikTok URLs with inline SVG icons.
- Kept social icons visible as non-clickable placeholders until their URLs are assigned.
- Added selectable Shopify navigation menus for **Explore**, **Experiences**, and **Information**.
- Added reference-matching fallback link labels when navigation menus have not yet been selected.
- Added a functional Shopify customer newsletter form with editable heading, text, placeholder, and success message.
- Added newsletter validation and success/error feedback.
- Added editable footer, text, muted text, border, and newsletter-button colors.
- Added a dynamic copyright year so it updates automatically.
- Corrected the social SVG paint rules so filled Facebook/TikTok marks and the outlined Instagram mark render cleanly.
- Reduced mobile and desktop footer height with smaller typography, tighter navigation/newsletter spacing, shorter controls, and more natural website-footer padding.
- Applied the theme's full-width section utility so the footer background spans the complete screen while its inner content remains centered.
- Added explanatory Liquid and CSS comments throughout `sections/footer.liquid`.
- Used Flexbox for the complete mobile and desktop layout; no CSS Grid was added.

Validation:

- Shopify Theme Check: passed.
- Result: 46 theme files inspected with no offenses.
- Homepage template: valid JSON.
- Footer CSS: no CSS Grid layout used.

Theme Editor setup:

1. Open the Shopify Theme Editor and select **Footer** in the global footer group.
2. Select Shopify menus for **Explore menu**, **Experiences menu**, and **Information menu**.
3. Add the approved Facebook, Instagram, and TikTok URLs.
4. Confirm the brand title, tagline, newsletter copy, copyright text, and location.
5. Adjust footer colors only if the approved design palette changes.
6. Submit a test email through the storefront after previewing to confirm the Shopify customer/newsletter capture.

## Contact Page

Status: Complete - available as the Shopify `contact` page template.

Source:

- `docs/project/PROJECT THEME.MD`
- `docs/project/PROJECT DESCRIPTIONS.MD`
- No dedicated contact-page screenshot was supplied, so the page extends the approved dark, condensed, thin-rule design system.

Implemented:

- Built a full-width mobile-first contact screen with one semantic page heading.
- Added a real Shopify native contact form without external services, scripts, API keys, or fake submission behavior.
- Added required name, email, inquiry type, and message fields.
- Added optional phone and subject fields.
- Added inquiry categories for general questions, coworking, gaming, events/group visits, menu/allergen questions, and other inquiries.
- Added clear required-field guidance, Shopify error output, focus styles, and a configurable success state.
- Added an inquiry-guidance panel that asks visitors for the practical details needed for qualified coworking, gaming, event, or group inquiries.
- Clearly states that form submission does not confirm a booking or reservation.
- Added optional verified email, phone, address, hours, and Facebook details.
- Kept public contact details blank by default so unverified information is never published.
- Added an optional approved privacy-note setting that remains blank until compliant language is supplied.
- Added locale strings for fixed form labels and messages in `locales/en.default.json`.
- Used only Liquid and component CSS; no JavaScript or CSS Grid was added.
- Created `templates/page.contact.json`, which makes **contact** available as a Shopify page template.

Validation:

- Shopify Theme Check: passed.
- Result: 48 theme files inspected with no offenses.
- `templates/page.contact.json`: valid JSON.
- `locales/en.default.json`: valid JSON.
- Contact page CSS: no CSS Grid layout used.
- Contact page JavaScript: none required.

Theme Editor setup:

1. In Shopify Admin, create or open the Contact page.
2. Assign **Theme template: contact**.
3. Open that page in the Theme Editor and select **Contact page**.
4. Confirm the introduction, form guidance, success message, and inquiry instructions.
5. Add only verified public email, phone, address, opening hours, and Facebook details.
6. Add approved contact-form privacy language when supplied.
7. Submit a real test inquiry and confirm delivery to the Shopify store contact email.

## Product Catalog

Status: Complete - replaces the Shopify collection page starter.

Source:

- `docs/project/PROJECT THEME.MD`
- `docs/project/PROJECT DESCRIPTIONS.MD`
- No dedicated full-menu screenshot was supplied, so the catalog extends the approved featured-menu visual system.

Implemented:

- Rebuilt `sections/collection.liquid` as the complete Shopify product catalog screen.
- Uses Shopify collections for product categories and Shopify products for names, descriptions, media, prices, variants, and availability.
- Added mobile-first category navigation with horizontal overflow and desktop wrapping.
- Added selectable category collections in the Theme Editor.
- Added accessible Shopify-native sorting that works without JavaScript.
- Added one-column phone, two-column tablet, and three-column desktop Flexbox layouts.
- Added responsive Shopify product imagery and a Shopify placeholder when a product image is missing.
- Added one badge per product using `custom.menu_badge`, with supported tag fallbacks.
- Added optional `custom.dietary_note` output for verified dietary or allergen information.
- Added explicit product variant names, prices, and availability.
- Added product price ranges, descriptions, sold-out treatment, and product-detail links.
- Kept purchase controls hidden because online ordering remains outside the approved MVP scope.
- Added merchant-configurable pagination, descriptions, badges, and variant limits.
- Added a branded collection empty state and accessible custom pagination.
- Added fixed catalog labels to `locales/en.default.json`.
- Added documented reusable `menu-product-card` and `price-variants` snippets as recommended by the theme plan.
- Removed the starter section's CSS Grid and implemented the screen with Flexbox.
- Removed the unsupported long range-setting unit from the description word-limit schema so Shopify theme upload accepts the section.

Validation:

- Shopify Theme Check: passed.
- Result: 50 theme files inspected with no offenses.
- `templates/collection.json`: valid JSON data.
- `locales/en.default.json`: valid JSON.
- Catalog CSS: no CSS Grid layout used.
- Catalog JavaScript: none required.

Theme Editor setup:

1. Open a Shopify collection in the Theme Editor.
2. Select **Product catalog**.
3. Add and order the approved collections under **Menu categories**.
4. Choose the products-per-page count and card content settings.
5. Populate product images, descriptions, variants, prices, and availability in Shopify Products.
6. Optionally create `custom.menu_badge` and `custom.dietary_note` product metafields.
7. Add products to the correct Shopify collections.

## Next Work

- Review the navigation, hero, venue information strip, featured menu, rooftop carousel, Visit Bean & Ben section, and footer using the developer-controlled Shopify preview.
- Fine-tune dimensions only after the approved logo, hero images, real menus, verified venue facts, and real products are assigned.
- Build the next homepage section after visual review.
