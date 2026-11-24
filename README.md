# e-food Rubies – interactive prototype

A static, dependency-free HTML prototype of the Rubies loyalty flow: earn a ruby with every order from a store, see your progress, and unlock a coupon.

**Flow:** Home ("Your Rubies and coupons" cards) → Food, coffee → Coffee Lab store (stamp card, tap an item to add it) → Order (payment) → Order status (the stamp card drops in, a new ruby stamp lands with a burst, then the map and pin appear). Each order adds one ruby; after the 4th ruby the demo ends and a **Start over** button resets it.

## Run

Open `index.html` in a browser, or serve the folder:

```bash
python3 -m http.server 8000
```

then visit http://localhost:8000. Deep links work with a hash, e.g. `index.html#store` or `index.html#status` (a reload always goes back to Home).

## Publish with GitHub Pages

Push this folder to the root of a repository, then in **Settings → Pages** choose **Deploy from a branch** (`main`, `/ (root)`). Paths are relative, so it also works from a sub-folder.

## What's inside

```
index.html     the whole prototype (HTML, CSS and JS in one file)
assets/        store photos, menu items and logos
assets/fig/    vectors and images taken from the Figma design (icons, ruby stamp, placeholders, banners, map)
```

## Design

- Figma file: https://www.figma.com/design/RVq8xpelpTfVAu9PGUjkGr/exploration
  - Section **Rubies – main flow (current prototype)**: every screen as editable designs, wired as a prototype.
  - **Design System – presentation → Components → Rubies & stamps**: the stamp, the stamp cards (home, store, order confirmation) and the Start over button.
- The `:root` block at the top of `index.html` mirrors the Figma **Mapped** variables (colour tokens such as `--surface-default`, `--brand-primary`; type tokens `--font-size-s1…s8`). Change a value there and every screen follows.
- Every screen is built in HTML/CSS from the Figma components. Icons, rubies, stamps and placeholders are the Figma vectors (SVG); only real image fills (photos, banner artwork, menu illustrations, map, hero illustration) are raster.

## Accessibility

Buttons are real `<button>` elements with visible keyboard focus, state changes are announced to screen readers, and all motion respects **Reduce motion**.

## Notes

- **How to find the store:** the delivery address is **Sevastias 1**. Tap **Food,coffee** in the nav bar to find **Coffee Lab**.
- **Reset:** press **Cmd + R** (Ctrl + R on Windows) to reload the page. The prototype always starts again from Home, with Coffee Lab at 1 ruby and an empty basket.

- Store logos, covers, menu photos and banners are e-food images, used here for design mock-ups only. Check you have the right to publish them before making the repository public.
- This is a design prototype: there is no backend, and no real orders or payments are made.
