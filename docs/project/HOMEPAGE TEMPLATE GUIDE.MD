# Homepage Template Guide

This guide explains `templates/index.json`, which controls the sections rendered
on the Shopify homepage.

## Why the JSON file has no inline comments

Shopify template files must use strict JSON. Strict JSON does not support `//`
or `/* ... */` comments. Adding comments directly to `templates/index.json`
would make the file invalid and could prevent the theme from uploading.

The examples below use JSON-with-comments only for learning. Do not paste the
comment lines into the real template.

## Root structure

```jsonc
{
  "sections": {
    // Registers every section instance available to this homepage template.
  },
  "order": [
    // Controls the top-to-bottom rendering order of those section instances.
  ]
}
```

- `sections` is an object containing the homepage section instances.
- Each key such as `hero` or `venue_info` is a unique instance ID.
- `order` contains those instance IDs in storefront display order.
- An instance can exist under `sections`, but it will not render unless its ID
  is also included in `order`.

## 1. Hero section

```jsonc
"hero": {
  // Loads sections/hero-section.liquid. The .liquid extension is omitted.
  "type": "hero-section",

  // No template-level overrides are saved, so the section schema defaults apply.
  "settings": {}
}
```

Purpose:

- Displays the homepage hero content.
- Supports separate uploadable desktop and mobile background images.
- Contains the main hero heading, supporting copy, and call-to-action settings.
- Its editable controls are defined inside the schema in
  `sections/hero-section.liquid`.

## 2. Venue information strip

```jsonc
"venue_info": {
  // Loads sections/venue-info-strip.liquid.
  "type": "venue-info-strip",

  // Each child object is one repeatable fact displayed by the section.
  "blocks": {
    "location": {
      // Must match the "fact" block type in the section schema.
      "type": "fact",
      "settings": {
        // Chooses the inline icon rendered by the section.
        "icon": "location",

        // Main short label shown for this fact.
        "title": "ROOFTOP CAFÉ",

        // Supporting information shown below or beside the title.
        "detail": "Silang, Cavite",

        // A Boolean: true shows this item on phones; false hides it on phones.
        "show_on_mobile": true
      }
    }
  },

  // Controls the left-to-right order in which the block IDs are rendered.
  "block_order": [
    "location",
    "parking",
    "hours",
    "takeaway",
    "cowork",
    "gaming"
  ],

  // The section-level schema defaults apply.
  "settings": {}
}
```

The configured venue blocks are:

| Block ID | Icon | Meaning | Phone |
| --- | --- | --- | --- |
| `location` | `location` | Rooftop café location | Shown |
| `parking` | `parking` | Parking availability | Hidden |
| `hours` | `hours` | Daily closing time | Shown |
| `takeaway` | `takeaway` | Dine-in and takeaway | Shown |
| `cowork` | `cowork` | Wi-Fi and outlets | Hidden |
| `gaming` | `gaming` | Gaming experience | Hidden |

Important relationships:

- Every ID in `block_order` must exist under `blocks`.
- The block `type` must exist in `venue-info-strip.liquid`'s schema.
- `show_on_mobile` affects only phone visibility; all facts remain available for
  the wider layout.
- The merchant can add, remove, edit, and reorder these facts in the Theme
  Editor.

## 3. Featured menu

```jsonc
"featured_menu": {
  // Loads sections/featured-menu.liquid.
  "type": "featured-menu",

  // Uses the section's default heading, colors, empty state, and other settings.
  "settings": {}
}
```

Purpose and data flow:

- Displays products selected from the Shopify store.
- A manually selected product list has first priority.
- When that list is empty, the selected collection supplies the products.
- When neither source contains products, the branded empty state is displayed.
- The first product becomes the large lead card and up to four more products
  become supporting cards.
- The background image, product source, colors, labels, and menu link are
  configured in the Theme Editor.

## 4. Rooftop carousel

```jsonc
"rooftop_carousel": {
  // Loads sections/rooftop-carousel.liquid.
  "type": "rooftop-carousel",

  // Uses schema defaults until the merchant changes the section settings.
  "settings": {}
}
```

Purpose and data flow:

- Displays the rooftop introduction and horizontally moving image carousel.
- Image slides are repeatable `image` blocks added through the Theme Editor.
- This template currently defines no image blocks, so the section renders its
  built-in three-item sample state instead of appearing broken.
- The merchant can upload images, add captions and alternative text, reorder
  slides, and configure autoplay and slide widths.
- Native horizontal scrolling remains available when JavaScript is unavailable.

## 5. Visit Bean & Ben

```jsonc
"visit_bean_ben": {
  // Loads sections/visit-bean-ben.liquid.
  "type": "visit-bean-ben",

  // Uses default venue copy and presentation settings from the section schema.
  "settings": {}
}
```

Purpose:

- Displays the venue address, hours, parking, landmark, and visit actions.
- Supports an uploadable map image.
- Directions and message controls become real links only after URLs are
  assigned. Otherwise, they remain visible but disabled.
- The merchant should replace default or placeholder facts with verified
  business information before launch.

## 6. Homepage rendering order

```jsonc
"order": [
  "hero",
  "venue_info",
  "featured_menu",
  "rooftop_carousel",
  "visit_bean_ben"
]
```

The storefront renders:

1. Hero section
2. Venue information strip
3. Featured menu
4. Rooftop carousel
5. Visit Bean & Ben

Changing the array order changes the homepage order. The safest way to reorder
sections is through the Shopify Theme Editor because Shopify updates this array
automatically.

## Why the header and footer are not listed

The header and footer are global section groups rather than homepage-only
sections:

- `sections/header-group.json` renders the header.
- `sections/footer-group.json` renders the footer.
- `layout/theme.liquid` places those groups around `content_for_layout`.
- `templates/index.json` supplies only the homepage content inserted into
  `content_for_layout`.

The final page structure is:

```text
Global header
  Homepage sections from templates/index.json
Global footer
```

## Safe editing rules

1. Keep this file valid JSON: no comments, trailing commas, or Liquid code.
2. A section `type` must match an existing file under `sections/`.
3. Every section ID in `order` must exist under `sections`.
4. Every block ID in `block_order` must exist under that section's `blocks`.
5. Use `true` and `false` without quotation marks for Boolean settings.
6. Prefer the Theme Editor for adding, removing, and reordering sections or
   blocks.
7. Edit JSON manually only when creating reliable template defaults in code.
