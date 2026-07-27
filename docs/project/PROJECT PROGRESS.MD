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

## Next Work

- Review the navigation at mobile and desktop sizes using the developer-controlled Shopify preview.
- Fine-tune dimensions only after the approved logo asset and real Shopify menus are assigned.
- Build the hero section and visually connect its content beneath the overlaid home-page header.
