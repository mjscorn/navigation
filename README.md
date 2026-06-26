# Navigation prototype

Public interactive prototype for **QuickBooks navigation customer research** (FY26/27). Three left-nav concepts you can explore in the browser — no login, no build step.

**Live site:** https://mjscorn.github.io/navigation/

## Quick links

| Concept | Description | URL |
|---------|-------------|-----|
| **A** | Side-panel L1 navigation; Feed + App Store in primary nav | [https://mjscorn.github.io/navigation/](https://mjscorn.github.io/navigation/) |
| **B** | Click-to-open flyouts, customize modal, apps edit mode | [https://mjscorn.github.io/navigation/3.0/](https://mjscorn.github.io/navigation/3.0/) |
| **C** | Reports + More apps in primary nav; home greeting animation | [https://mjscorn.github.io/navigation/c/](https://mjscorn.github.io/navigation/c/) |

Use the **FAB** (floating menu, bottom-right) to switch between concepts while exploring.

## What you can test

- Left nav: collapse/expand, app L0 → L1 navigation, bookmarks, reports, feed
- **Create** menu (condensed + expanded mega-menu)
- Global search and Ask AI panel (mock data)
- Customize modal (appearance, pinned apps, nav behavior)
- Profile flyout and company switcher

All interactions use static mock data — nothing hits a real backend.

## Local preview

```bash
git clone https://github.com/mjscorn/navigation.git
cd navigation
python3 -m http.server 8081
```

Then open:

- Concept A — http://127.0.0.1:8081/
- Concept B — http://127.0.0.1:8081/3.0/
- Concept C — http://127.0.0.1:8081/c/

## Updating the prototype

Source of truth lives on Intuit GitHub Enterprise. To refresh this public copy:

```bash
PUSH_PUBLIC=1 ./scripts/export-public-prototype.sh
```

(Run from the internal `nav-concept-tests` repo after exporting.)

## GitHub Pages

**Live site:** https://mjscorn.github.io/navigation/

If you see a 404, enable Pages once:

1. Open [Settings → Pages](https://github.com/mjscorn/navigation/settings/pages)
2. **Build and deployment → Source:** Deploy from a branch
3. **Branch:** `gh-pages` → folder `/(root)` → **Save**
4. Wait 1–2 minutes for the site to build

The `gh-pages` branch is updated automatically on every push to `main`.
