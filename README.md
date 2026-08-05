# Ultimate Player — Support &amp; Legal

Public support, privacy and terms pages for the **Ultimate Player** apps, served by GitHub Pages from the
`main` branch of this repo.

## Pages

| Page | URL | Used by |
| --- | --- | --- |
| Hub | <https://vnikie1.github.io/ultimate-player-support/> | Landing page — links every platform |
| iOS support | <https://vnikie1.github.io/ultimate-player-support/ios/support.html> | App Store Connect **Support URL**; in-app Settings → About & Legal |
| iOS privacy | <https://vnikie1.github.io/ultimate-player-support/ios/privacy.html> | App Store Connect **Privacy Policy URL** (required); in-app |
| iOS terms | <https://vnikie1.github.io/ultimate-player-support/ios/terms.html> | In-app |
| Android privacy | <https://vnikie1.github.io/ultimate-player-support/android-privacy.html> | Google Play listing **Privacy Policy URL** |

## ⚠️ Two listings depend on these paths

- **Google Play.** The Android privacy policy used to live at the repo root (`index.html`) and now lives at
  `android-privacy.html`. The Play Console listing must point at the new URL, or Google flags the app for a
  missing privacy policy. Its content was moved **verbatim** — only the filename changed.
- **App Store Connect.** The iOS URLs above are also hardcoded in the app at
  `ultimate player ios/Core/AppLinks.swift`. Renaming a page here breaks the in-app links; change both
  together.

## Editing

Plain static HTML. No build step, no Jekyll (`.nojekyll` is present), no JavaScript, and no external fonts
or CDNs — a privacy page that loads third-party resources is a bad look. Edit, commit, push; Pages
redeploys in about a minute.

`styles.css` at the root styles the hub and the iOS pages (they reference it as `../styles.css`).
`android-privacy.html` is self-contained with its own inline stylesheet and does not use it.

Preview locally with any static server:

```
python3 -m http.server 8000
```

## Keeping the pages honest

The privacy policies make specific factual claims about the apps — for iOS: that credentials are
AES-256-GCM encrypted under a Keychain-held key, that MetricKit diagnostics are opt-in and never
transmitted, that no analytics or advertising SDK is present, and exactly which third-party services get
contacted. If any of that changes in an app, the matching page has to change with it, and the "Last
updated" date at the top should move.
