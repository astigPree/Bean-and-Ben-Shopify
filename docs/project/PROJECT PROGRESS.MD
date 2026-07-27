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

## Next Work

- Review the navigation, hero, and venue information strip using the developer-controlled Shopify preview.
- Fine-tune dimensions only after the approved logo, hero images, real menus, and verified venue facts are assigned.
- Build the next homepage section after visual review.
