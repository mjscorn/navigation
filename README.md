# Navigation prototype

Public interactive prototype for **QuickBooks navigation customer research** (FY26/27). Four left-nav concepts you can explore in the browser — no login, no build step.

**Live site:** https://mjscorn.github.io/navigation/

## Quick links

| Concept | Description | URL |
|---------|-------------|-----|
| **A** | Side-panel L1 navigation; Feed + App Store in primary nav | [https://mjscorn.github.io/navigation/](https://mjscorn.github.io/navigation/) |
| **B** | Click-to-open flyouts, customize modal, apps edit mode | [https://mjscorn.github.io/navigation/3.0/](https://mjscorn.github.io/navigation/3.0/) |
| **C** | Reports + More apps in primary nav; home greeting animation | [https://mjscorn.github.io/navigation/c/](https://mjscorn.github.io/navigation/c/) |
| **D** | Equal-width icon pill tabs, integrations tab, home edit mode | [https://mjscorn.github.io/navigation/d/](https://mjscorn.github.io/navigation/d/) |

Archived tab bar playground (previous D): `d/playgrounds/ios-like-tab-bar/`

**E** redirects to **D** (`/e/` → `/d/`).

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
- Concept D — http://127.0.0.1:8081/d/

(`/e/` redirects to `/d/`. Previous D tab bar: `d/playgrounds/ios-like-tab-bar/`.)

## Updating the prototype

Source of truth lives on Intuit GitHub Enterprise. To refresh this public copy:

```bash
./scripts/deploy-all.sh
```

Or public export only (skips Intuit GHE push):

```bash
PUBLIC_PASSKEY=1234 PUSH_PUBLIC=1 ./scripts/export-public-prototype.sh
```

By default `PUBLIC_PASSKEY` is `auto`: the passkey is today's local calendar date as MMDD (e.g. `0626` on June 26, `0627` on June 27). Set a fixed 4-digit code instead if needed. The gate is injected only in the public export, not the Intuit source files.

(Run from the internal `nav-concept-tests` repo after exporting.)

## GitHub Pages

**Live site:** https://mjscorn.github.io/navigation/

Deploys automatically via GitHub Actions on every push to `main`.
