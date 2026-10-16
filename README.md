# Atlas property portal
Frontend concept built with React, Vite, TypeScript and Tailwind CSS.

## Run
npm install
npm run dev

## Build
npm run build

The public page presents a borderless accordion slider of 15 house-model previews, a direct model index, About Us, and 10 expandable FAQs. It intentionally shows no prices, specifications or property-detail actions. On mobile the slider becomes a vertical accordion.

The admin workspace is a demo switch, not authentication. It includes dashboard, 15-unit inventory, editable availability, CSV export, developers, session activity, property details and preferences. Existing local availability edits are preserved when the original six-unit dataset is extended to 15 units.

Inventory and theme persist in localStorage. Viewing requests in admin details are simulated and send nothing. All listings and developers are illustrative. Photographs are bundled locally; origins are documented in public/images/sources.json. Fonts load from Google Fonts.
