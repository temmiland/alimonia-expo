# alimonia 🍚

[![Platform](https://img.shields.io/badge/Platform-iOS%20%2F%20Android-lightgrey)](https://temmi.land/blog)
[![License](https://img.shields.io/badge/License-Proprietary-red)](#status)

**alimonia** is a local-first recipe & weekly meal planner app for iOS and
Android. Plan meals, generate shopping lists, and organize recipes — fully
usable offline, with an optional cloud sync for backup and shared households.

alimonia grew out of two earlier prototypes, [**alimonia-ios**](https://github.com/temmiland/alimonia-ios)
(native iOS) and [**alimonia-expo-old**](https://github.com/temmiland/alimonia-expo-old)
(Expo / React Native), before being rebuilt as the current, actively
developed app.

> ℹ️ **Note:** The current version of alimonia is **closed source**. This
> repository's `public` branch only holds the app's translation files — it
> does not contain any app source code.

## Download

<a href="https://apps.apple.com/app/alimonia/id6781319686"><img src="assets/badges/app-store-badge.svg" alt="Download on the App Store" width="150"></a><br/>
<a href="https://play.google.com/store/apps/details?id=land.temmi.alimonia"><img src="assets/badges/google-play-badge.png" alt="Get it on Google Play" width="150"></a>

More about the app: [temmi.land/projects/alimonia](https://temmi.land/projects/alimonia)

## About this branch (`public`)

This is a **headless (orphan) branch** with no shared history with `main`. It
intentionally holds only a slice of the project — currently the
translations — and none of the app source, secrets, or internal history.

```
src/i18n/locales/<lang>/common.json
```

Copied 1:1 from `main` (identical path). New languages or corrections can be
contributed here without access to the rest of the repository.

### Getting changes back into `main`

`public` shares **no history** with `main` (it's an orphan branch). A regular
`git merge public` into `main` would try to merge unrelated histories and pull
`public`'s structure/history into `main` — that's not what we want.

Instead, individual commits are transferred via **cherry-pick** (this works
because the file paths are identical):

```bash
git checkout main
git cherry-pick <commit-hash-from-public>
```

For a range of commits:

```bash
git cherry-pick <first-hash>^..<last-hash>
```

**Important:** cherry-picks only apply cleanly as long as the path
`src/i18n/locales/<lang>/common.json` stays unchanged in `public`. If the
i18n structure is ever restructured in `main`, `public` needs to be updated
accordingly (e.g. re-run `git checkout main -- src/i18n/locales`).

### Don't

- Don't `git merge` `public` into `main` (unrelated histories, see above).
- Don't commit app source, `.env`, secrets, or any other code to this branch —
  it exists for external contributors (e.g. translators).

## Related

- [alimonia-ios](https://github.com/temmiland/alimonia-ios) — the first native iOS prototype
- [alimonia-expo-old](https://github.com/temmiland/alimonia-expo-old) — the early Expo / React Native prototype

## Status

🔒 **Closed source** — actively developed, available on the App Store and
Google Play.
