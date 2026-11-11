# CalBard Third-Party Notices

**Last updated: 2026-11-10**

CalBard is proprietary software; see the [terms of use](terms.html). This page
records the third-party work bundled in the app and the licences that apply to
it. The same notice texts ship inside the app under **Settings → About → Terms
and licenses**.

---

## 1. Bundled fonts

| Family | Licence | Copyright |
|---|---|---|
| Inter | SIL Open Font License 1.1 | 2020 The Inter Project Authors (<https://github.com/rsms/inter>) |
| Outfit | SIL Open Font License 1.1 | 2021 The Outfit Project Authors (<https://github.com/Outfitio/Outfit-Fonts>) |

Full notice and licence text: [OFL-1.1.txt](licenses/OFL-1.1.txt).

The font files are self-hosted so the app works offline. The OFL requires the
copyright notice and licence to accompany the fonts; both ship next to them and
are reproduced here.

## 2. Runtime libraries

| Component | Licence | Notice |
|---|---|---|
| React, React DOM | MIT | [MIT.txt](licenses/MIT.txt) |
| AndroidX (Core, Lifecycle, Activity, WebKit, Security) | Apache-2.0 | [Apache-2.0.txt](licenses/Apache-2.0.txt) |
| Jetpack Compose (UI, Material 3) | Apache-2.0 | [Apache-2.0.txt](licenses/Apache-2.0.txt) |
| Kotlin standard library and coroutines | Apache-2.0 | [Apache-2.0.txt](licenses/Apache-2.0.txt) |
| OkHttp and Okio | Apache-2.0 | [Apache-2.0.txt](licenses/Apache-2.0.txt) |
| Hilt / Dagger | Apache-2.0 | [Apache-2.0.txt](licenses/Apache-2.0.txt) |
| Room | Apache-2.0 | [Apache-2.0.txt](licenses/Apache-2.0.txt) |
| WorkManager | Apache-2.0 | [Apache-2.0.txt](licenses/Apache-2.0.txt) |

The release build strips `META-INF/LICENSE*` and `META-INF/NOTICE*` from the
package to keep it small. The files above are the authoritative notices for the
shipped app and are bundled as web assets.

## 3. Data sources

| Source | Terms | Attribution in the app |
|---|---|---|
| Open-Meteo (forecast and geocoding) | CC BY 4.0 — attribution required; free API for non-commercial use. <https://open-meteo.com/en/license> | Settings → About → Data sources; [privacy policy](index.html) §10 |
| NOAA / National Weather Service | Public domain (US Government work) | Settings → About → Data sources |
| ICS / webcal feeds | The user's own feed URLs; CalBard does not redistribute them | Settings → About → Data sources |
| AllGameTimes schedule feeds | No published terms. Used as an unofficial source; the exposure is accepted and documented in the app repo's publishing guide | Settings → About → Data sources |
| RainViewer | Free tier is personal, non-commercial only | **Not enabled**; no tiles are requested |
| OpenStreetMap | ODbL | **Not used**; no base map is rendered |
| Google Calendar API | Google API Services User Data Policy | **Not enabled**; no Google request is made in 1.3.0 |

CalBard itself has no server and does not redistribute provider data beyond
rendering the response the user requested. The app is free, has no ads and no
subscriptions.

## 4. Development-only tools

Vite, TypeScript, Vitest, Playwright, and the npm test stack are used to build
and verify the app but are **not distributed** in the APK or the web bundle.
Their licences are recorded in the app repo's `web/package-lock.json`.

---

[Privacy policy](index.html) · [Terms of use](terms.html)
