# Strata · Product Catalog Brief

A bilingual (EN + ES) product brief that explains, in non-technical language, what the **Strata Product Catalog** workspace does, how it consolidates the legacy reference tabs (MRL, Dealer/Quote, Figma), and the value it delivers to a Dealer.

**Live**: https://diegoagentic.github.io/strata-catalog-brief/

**Prototype it describes**: https://github.com/diegoagentic/expert-catalog

---

## Structure

```
strata-catalog-brief/
├── index.html      # The brief itself · 8 bilingual sections
├── style.css       # Strata DS tokens as CSS variables + layout + dark mode
├── img/            # Screenshots (drop yours here)
└── README.md       # This file
```

Zero build, zero framework. Static HTML + CSS served straight from `main`.

---

## Preview locally

Double-click `index.html`. The browser opens it directly — no server, no `npm install`.

If you want a real HTTP context (useful for testing image paths as they will resolve on GitHub Pages):

```bash
python -m http.server 8000
# then visit http://localhost:8000
```

---

## Edit the content

All copy lives in `index.html`. Sections are numbered in comments:

1. Hero
2. What problem this solves / Qué problema resuelve
3. How to read the five tabs / Cómo leer los cinco tabs
4. The reference tabs / Los tabs de referencia
5. The current version · Product Catalog + My Selection / La versión actual
6. What a Dealer gets out of this / Qué gana el Dealer
7. Try it in five steps / Probalo en cinco pasos
8. Fact sheet / Ficha rápida

Each section has an EN block and an ES block. Keep them in sync when you edit.

---

## Add or replace screenshots

Drop `.png` files into `img/` with these exact names — they're already referenced from `index.html`:

| Filename | What it should show |
|---|---|
| `hero-overview.png` | The prototype full-app view with Product Catalog active. |
| `tab-mrl.png` | MRL landing (brand library grid). |
| `tab-dealer-quote.png` | Dealer / Quote tab with imported catalog cards. |
| `tab-figma.png` | Figma tab with filter sidebar and brand pills. |
| `tab-product-catalog-products.png` | Product Catalog in Products mode. |
| `tab-product-catalog-spaces.png` | Product Catalog in Spaces mode. |
| `tab-my-selection.png` | My Selection with drafts + line items. |
| `flow-add-bundle.png` | (Optional) Space Type Detail Page with Add-all CTA. |

If a file is missing, the browser shows the `alt` text over a subtle placeholder — the layout doesn't break.

---

## Publish changes

```bash
git add .
git commit -m "content: update section X"
git push
```

GitHub Pages picks up the push and redeploys within ~1 minute.

---

## Design system alignment

CSS variables in `style.css` are mapped 1:1 from the Strata Design System tokens (`Strata Design System/strata-ds/src/styles/tokens/variables.css` and its dark counterpart). Dark mode swaps automatically based on the visitor's OS preference.

Rules applied:
- Zero raw color classes (`green-500`, `red-500`, etc.).
- Zero hardcoded hex values in layout code (only in the `--variable` declarations, sourced verbatim from the DS).
- Brand lime is used only as background (never as text color).

---

## Related

- **Prototype**: [diegoagentic/expert-catalog](https://github.com/diegoagentic/expert-catalog)
- **Design system**: [strata-ds.vercel.app](https://strata-ds.vercel.app)
