---
name: Atlas
description: An architectural portfolio of considered homes.
colors:
  bg: "#fafaf7"
  surface: "#fff"
  ink: "#273c34"
  muted: "#69746d"
  line: "#dfe3dc"
  soft: "#eff1eb"
  green: "#294b3c"
  cream: "#f0f0e7"
  terracotta: "#af795b"
  focus: "#ad704d"
  green-hover: "#41614c"
  available-bg: "#e9f0e6"
  available-ink: "#37523d"
  reserved-bg: "#f4e9d8"
  reserved-ink: "#7a5727"
  sold-bg: "#eeedea"
  sold-ink: "#62645e"
typography:
  display:
    fontFamily: "Georgia, serif"
    fontSize: "clamp(42px, 4.6vw, 70px)"
    fontWeight: 400
    lineHeight: 1.06
    letterSpacing: "-0.035em"
  headline:
    fontFamily: "Georgia, serif"
    fontSize: "32px"
    fontWeight: 400
    letterSpacing: "-0.7px"
  title:
    fontFamily: "Manrope, sans-serif"
    fontSize: "17px"
    fontWeight: 700
    letterSpacing: "-0.4px"
  body:
    fontFamily: "DM Sans, sans-serif"
    fontSize: "14px"
    fontWeight: 400
    lineHeight: 1.9
  label:
    fontFamily: "DM Sans, sans-serif"
    fontSize: "10px"
    fontWeight: 600
rounded:
  tag: "4px"
  control: "5px"
  icon: "6px"
  filter: "7px"
  container: "8px"
  card: "9px"
  circle: "50%"
spacing:
  icon-gap: "8px"
  control-gap: "13px"
  cell: "16px"
  card: "21px"
  section: "25px"
  content: "30px"
  workspace: "35px"
components:
  button-primary:
    backgroundColor: "{colors.green}"
    textColor: "{colors.surface}"
    rounded: "{rounded.control}"
    padding: "13px 19px"
  button-primary-hover:
    backgroundColor: "{colors.green-hover}"
  button-secondary:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.ink}"
    rounded: "{rounded.control}"
    padding: "13px 19px"
  model-preview:
    textColor: "#fff"
    rounded: "0"
  model-arrow:
    backgroundColor: "{colors.soft}"
    textColor: "{colors.ink}"
    rounded: "{rounded.circle}"
    width: "40px"
    height: "40px"
  status-available:
    backgroundColor: "{colors.available-bg}"
    textColor: "{colors.available-ink}"
    rounded: "{rounded.tag}"
    padding: "6px 9px"
---

# Design System: Atlas

## Overview

**Creative North Star: The Architectural Portfolio.**

Atlas pairs warm ivory surfaces and forest ink with carefully cropped residential photography. The public experience is a preview-only collection of 15 house models in a borderless accordion slider, followed by About Us and ten FAQs; the administrative workspace retains the same materials while using compact aligned inventory rows. Public previews show model names and imagery, without prices, availability, specifications, or detail actions. This document records the implemented source in `src/style.css` and `src/main.tsx`; it has not been verified in a browser.

**Key Characteristics:**
- A borderless photographic accordion and serif display type.
- Georgia model names, Manrope administrative figures, and DM Sans controls and supporting copy.
- Fine rules, restrained corners, tonal separation, and small terracotta accents.

## Colors

### Primary
- **Forest green** (`green`): primary actions, brand mark, active navigation underline, and notifications.
- **Forest ink** (`ink`): primary text; use muted ink for supporting metadata.

### Secondary
- **Terracotta** (`terracotta`): the brand dot; the related `focus` color marks keyboard focus. These accents remain small.

### Neutral
- **Warm ivory** (`bg`): page ground. **White** (`surface`): cards, fields, tables, sidebar.
- **Linen** (`cream`): hero and closing section. **Soft sage** (`soft`): selected controls, table headers, and grouped surfaces.
- **Stone rule** (`line`): borders and dividers. **Muted sage ink** (`muted`): secondary copy.

Availability uses green, warm amber, and stone pairs, always accompanied by a text label. Dark mode replaces the eight root surface/text tokens under `[data-theme=dark]`; retain those semantic assignments rather than inverting photographs. Its final values are bg `#141e19`, surface `#1d2b22`, ink `#f5f6ec`, muted `#c4cec1`, line `#475549`, soft `#304033`, green `#3b6248`, and cream `#202f24`. Body explicitly inherits ink and background tokens, including form foreground and caret colors. Dark focus is `#e6b08b`; dark italic emphasis is `#c7d4b2`. Status treatments and overrides are recorded in the sidecar.

## Typography

Georgia supplies display and section headlines. Manrope supplies the wordmark, property titles, prices, and metric figures. DM Sans supplies navigation, controls, labels, tables, and prose. Fonts are imported from Google Fonts except Georgia, which is a system serif.

The collection display uses the frontmatter clamp, regular weight, and italic sage emphasis. Expanded model captions use 36px Georgia; collapsed captions are 31px, vertical and rotated on desktop. About headings use `clamp(32px,3.1vw,46px)` and FAQ headings 37px. Public prose is 14–15px with 1.9–1.95 line height. Model index controls are 12px DM Sans; public model names are not Manrope property titles.

Administrative section headings remain 24px Georgia. Operational UI is generally 10–13px; inventory prices use tabular numerals. In dark mode admin paragraphs, table cells, and search input become 13px; admin small text, metric labels, notices, table headers, sidebar identity, and status labels become 11px, with 1.65 line height for supporting text. Footer small text also becomes 11px.

## Layout

The desktop header is 88px tall with 4.4% horizontal padding. Public collection padding is 55px 4.4% 45px. The introduction pairs a large serif heading with short supporting copy. The slider shows five of fifteen model panels at a time in a 510px-tall flex row with 8px gaps. Inactive panels have flex 1; the selected panel has flex 4.8. Previous/next controls wrap through all fifteen models, and the full numbered index below uses five columns. Selection changes the visible group of five.

About Us uses equal columns, an 8% gap, 65px 7% padding, a 490px-tall photograph, and linen background. FAQ uses a `1fr 1.7fr` grid with a 7% gap and 75px 7% 85px padding. Ten native disclosures share one group name.

Admin uses a 224px sidebar and 35px main padding. Metrics form four columns separated by rules. Fifteen inventory rows use 16px cells and horizontal overflow rather than squeezing information.

At 1050px the slider reduces to 450px. At 750px it becomes 420px, expanded panels use flex 5.5, the full index becomes three columns, and About/FAQ stack. At 560px the slider becomes a 610px vertical accordion with 6px gaps, 48px minimum collapsed panels, and flex 6 for the selected panel; all names become horizontal. The intro stacks and arrow controls become 36px circles. Admin retains its 1150px density reduction, 850px navigation/sidebar adjustments, and 560px horizontal navigation rail.

## Elevation & Depth

Most surfaces are flat, separated by tonal fills and 1px rules. Public previews are borderless and unrounded, with image shading and `0 2px 10px #0009` caption text shadows for legibility. Images scale to 1.035 on hover; inactive images use brightness .85. The detail drawer uses `-20px 0 60px #0003`; the toast uses `0 8px 35px #0003`. The modal backdrop is `#0e1c16a8`. Model photographs use a dark vertical gradient for caption legibility. The drawer remains an administrative inventory detail surface.

## Shapes

The system uses modest 4–9px radii, straight dividers, and rectangular architectural photography. Public model panels and About photography have square corners and no borders. Administrative table containers use 8px and primary controls 5px. Model arrows and avatars are circles. Crop photographs with `object-fit: cover` and preserve their prominent proportions.

## Components

### Buttons

Primary buttons pair forest green with white, 13px 19px padding, 12px DM Sans, and a 5px radius. Hover uses `green-hover`. Secondary buttons use the surface color, ink text, and a 1px line border; hover uses soft sage. Text actions are 11px semibold with arrow icons and terracotta hover. Disabled buttons use half opacity. All keyboard targets receive a 2px focus outline with 4px offset.

### Model accordion and index

Five borderless full-height image buttons show one expanded model at a time. Desktop collapsed names run vertically; expanded names become horizontal with an arrow. Panel number and name remain white over a shaded photograph. Each trigger exposes `aria-expanded` and controls its caption. Its light-mode focus is an inset 3px `#e2bc86` outline; dark focus follows the theme override. A polite live selection counter, wrapping previous/next buttons, and all fifteen numbered model buttons provide alternate selection routes. Current index text is bold and underlined; `aria-pressed` exposes selection.

### About and FAQ

About pairs one photograph with serif heading, two narrative paragraphs, an illustrative-concept note, and a text action back to models. FAQs use ten native `details`/`summary` disclosures separated by 1px rules. Summary text is 14px medium, becoming bold when open; the chevron rotates 180 degrees. Focus uses the shared outline with 5px offset. Public disclosures do not launch inventory details or viewing forms.

### Fields, status, and inventory

Admin search is a bordered surface; its status filter sits alongside refresh. Form inputs use surface fill, a 1px line border, 4px corners, and 12px padding. Inventory aligns thumbnail, property/unit, developer/model, specifications, tabular price, and editable availability. Availability labels use compact 4px rectangles with green, amber, or stone pairing. Search, status editing, export, reset, and detail interactions remain inside the administrative workspace.

### Navigation

Public navigation links to House models, About us, and FAQs. Desktop text is muted 13px with a 2px forest underline on the active collection item. On smaller screens a menu toggle reveals the section links and exposes `aria-expanded`/`aria-controls`. At 380px and below, the admin switch uses the compact Admin/Website label. Admin navigation retains a soft selected fill.

### Detail drawer and feedback

Administrative property details open in a native modal dialog with a right-aligned panel up to 650px wide, a 300px image, and a scrollable body. The demo viewing form expands within that panel. Toasts appear bottom-center above the modal. Skeletons pulse while refresh is simulated. Reduced-motion preference removes animations and transitions and disables smooth scrolling.

## Do's and Don'ts

### Do:
- **Do** preserve the shared palette and typography across public and admin screens.
- **Do** use borderless model photography in public previews and aligned compact rows in operations.
- **Do** pair status colors with text and preserve keyboard focus.
- **Do** retain demo and illustrative-data explanations where decisions are made.

### Don't:
- **Don't** add decorative dashboard charts to the inventory workspace.
- **Don't** replace the quiet rules with heavy shadows on every card.
- **Don't** add public prices, availability, specifications, inventory detail actions, or booking flows to the preview collection.
- **Don't** imply backend persistence, authentication, or real viewing requests in this frontend concept.
