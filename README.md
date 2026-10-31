# better4u

**A better-for-you food concept, explored as an editorial storefront and recipe journal.**

better4u turns the everyday “swap” idea into a browseable web prototype: explore imagined food and drink ranges, inspect product concepts, browse cooking collections, and build a temporary recipe plate. Its warm, premium visual language is part of the product experiment.

> **Project stage:** concept and front-end prototype. Catalog, prices, ingredients, nutrition and health copy are authored sample content. There is no live inventory, checkout, payment, order service, user account or product business represented by this repository.

## Explore

| Area | What the source implements |
|---|---|
| [Landing page](app/page.tsx) | Brand story, concept range overview and navigation |
| [The Approach](app/approach/page.tsx) | “Better swap” positioning and concept examples |
| [Product Lab](app/product-lab/page.tsx) | Seven concept brand views, product cards, label flips, image zoom, cart editing and a simulated checkout |
| [Journal](app/journal/page.tsx) | Entry point to two recipe collections |
| [First Batch](app/journal/first-batch/page.tsx) | 21 Indian everyday recipes, filters, recipe selection and an in-memory plant-points sum |
| [Second Batch](app/journal/second-batch/page.tsx) | Searchable, filterable global comfort recipe collection and standards content |
| [Draft Recipe Hub](app/recipes/page.tsx) | Separate 23-item recipe draft, still linked from the Product Lab |
| [Technical blueprint](PROJECT_BLUEPRINT.md) | Product, architecture, data flow, setup and troubleshooting guide |

## What is implemented

- Responsive Next.js App Router pages with a shared desktop/mobile navigation component.
- A source-defined sample catalog of **31 product entries** across **7 concept brands**, with product imagery and content under `public/all_image_files/`.
- Product card interactions, front/back label views, an image zoom overlay, cart quantities and removal. Cart state is saved in this browser’s `localStorage` under `better4u_lab_cart`.
- A mock checkout action that copies the current cart into a temporary success screen and empties the local cart. It does not create or send an order.
- Two Journal collections: 21 first-batch recipes and a second-batch collection backed by local TypeScript data. The first collection supports group/tag filters, recipe details and a session-only selection whose plant points are summed in React state.
- A separate 23-recipe draft at `/recipes`, with text search, category/tag filters and recipe detail modals.
- An editorial design built with Tailwind CSS, Geist fonts, Framer Motion transitions and Lucide icons.

See [PROJECT_BLUEPRINT.md](PROJECT_BLUEPRINT.md) for the route map, implementation details and source-linked walkthrough.

## Stack

| Layer | Technology |
|---|---|
| Framework and routes | Next.js 16 App Router, React 19 |
| Language | TypeScript 5, strict mode configured |
| Styling | Tailwind CSS 4, global CSS and inline utility classes |
| Motion and icons | Framer Motion 12, Lucide React |
| Data and persistence | Local TypeScript modules, React state and browser `localStorage` |

There is no application API, database, authentication provider, payment integration or content-management system in the source. Product and recipe data are bundled with the app.

## Run locally

Requirements: Node.js and npm compatible with the versions used by this project’s Next.js and lockfile.

```bash
git clone https://github.com/tharungajula2/better4u.git
cd better4u
npm install
npm run dev
```

Open the local address printed by Next.js. Available package scripts are `dev`, `build`, `start` and `lint`; there is no test script in `package.json`. No app-specific environment variables are defined by the source.

## Maturity and boundaries

This repository is best evaluated as a **brand, content and interaction prototype**, not as a functioning e-commerce operation or evidence of product efficacy. Prices and product specifications are illustrative source data, not verified commercial or scientific claims. The checkout is simulated, cart data is local to the browser, and recipe selections are not a persisted account or nutrition record. The plant/ferment storage helper in `lib/log-store.ts` currently has no app callers.

The legacy `/vault` route redirects to `/product-lab`; it does not provide access control. The passcode constants in `lib/config.ts` are not wired to an authentication flow. The separate `/recipes` route is labeled “Phase 3 Draft” in its UI.

## Preserve the source trail

The repository also retains its [design-system notes](DESIGN_SYSTEM.md) and [public-content audit](BETTER4U_Content_Audit_Full.md). They are useful historical/reference material; this README and the [blueprint](PROJECT_BLUEPRINT.md) explain what the current source actually implements.
