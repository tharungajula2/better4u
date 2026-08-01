---

# 4. better4u

═══════════════════════════════════════════════════

# better4u

A gut health web portal built around swapping everyday defaults for better ones, rather than restrictive dieting. Designed end to end as a working web experience.

**Live:** [better4u.vercel.app](https://better4u.vercel.app/)

---

## What it does

Ultra-processed defaults follow almost every meal. The usual alternative is a clinical one: powders, restriction, and routines that feel like a chore and get abandoned.

better4u takes the other route. The organising idea is the swap, replacing a habit with something equally satisfying rather than removing it. The portal presents a beverage universe of 26 SKUs across six sub-brands alongside two structured recipe collections, one everyday Indian and one global comfort food.

The design brief was to make healthy look premium enough that someone reaches for it without being persuaded. Textured, editorial, closer to a physical wellness journal than a supplement website.

## Key numbers

| Item | Count |
|---|---|
| Beverage SKUs | 26 |
| Sub-brands | 6 |
| Everyday Indian recipes | 21 |
| Global comfort recipes | 12 |
| Retired standalone recipe hub | 23 |

## What is real and what is a demo

**Shipped:** the landing and approach pages, the product lab with card flipping to inspect back-of-label ingredients, a 2K image zoom modal, a shopping cart persisted to local storage, both recipe collections, and an interactive plant points calculator where selecting recipes sums points against a weekly target.

**Mocked or partial:**

| Feature | Status |
|---|---|
| Checkout | Clears the cart and shows a success overlay. No server-side dispatch |
| PAUSE brand specifications | Placeholder tokens, because those recipes are not finalised |
| Product video assets | Fall back to a single shared sample file |
| Passcodes in config | Client-side constants with no verification layer. No real security |
| Legacy recipe hub | Fully coded, deliberately retired and unlinked from navigation |

There is no backend, no database and no API. Everything runs client-side from static TypeScript data modules, with interactive state held in React and synchronised to browser storage.

## Hardest problems solved

**Cross-component state without a state library.** The cart and the plant points selection need to stay in sync across pages that do not share a parent. Solved with a custom event emitter and listener system over local storage, rather than pulling in Redux or Zustand for two pieces of state.

**Layered card interactions.** Card flipping and image zoom both manipulate the same element with Framer Motion shared layout transitions. Getting flip state and zoom state to coexist without one cancelling the other took careful ordering of the animation states.

**Scroll performance with heavy motion.** The editorial design leans on scroll-linked animation. Making that stay smooth, and respecting reduced-motion preferences, meant limiting what animates during scroll rather than adding more.

## Limitations

1. Nothing can actually be bought. Checkout is a demo.
2. Five PAUSE SKUs carry placeholder specifications.
3. Video assets are incomplete and share a fallback file.
4. The passcode constants offer no security whatsoever.
5. All content is static. There is no content management layer.
6. This is a concept brand. The products do not exist.

## Stack

Next.js 16.2, React 19.2, TypeScript 5, Tailwind CSS 4, Framer Motion 12.40, lucide-react. No backend.

## Running it

```bash
git clone https://github.com/tharungajula2/better4u.git
cd better4u
npm install
npm run dev
```

## Contact

Tharun Gajula · Bengaluru, India
[tharun.gajula.2@gmail.com](mailto:tharun.gajula.2@gmail.com) · [LinkedIn](https://linkedin.com/in/tharungajula) · [Portfolio](https://tharungajula.vercel.app)

═══════════════════════════════════════════════════

---
