# CalBard Privacy Policy

**Last updated: 2026-11-02**

CalBard is a personal dashboard app for Android TV, tablets, and phones. It shows
weather and calendar events on a single screen.

This policy explains what CalBard does with your information. The short version:
**CalBard has no server and no account system. Your data stays on your device.**

---

## 1. Who we are

CalBard is developed and published by an individual developer. For any privacy
question, contact:

**Email:** Hicksjaredc@gmail.com

---

## 2. What CalBard stores on your device

Everything CalBard remembers is stored locally on the device where you installed
it. Nothing is uploaded to a CalBard server, because no such server exists.

| Data | Why it is stored | Where it lives |
|---|---|---|
| Your location (ZIP code or latitude/longitude that **you type in**) | To fetch weather for that place | App preferences |
| Calendar feeds you add (ICS URLs) | To display your events | App preferences |
| Cached weather and calendar responses | To show data instantly and work offline | Local database |
| Display preferences (theme, layout, which sections are visible) | To remember your setup | App preferences |

On Android, any credentials you enter are held in `EncryptedSharedPreferences`,
which is backed by the Android Keystore. On the web build, they are held in the
browser's `localStorage` for the site you loaded. Version 1.0.0 has no Google
sign-in, so in practice the only credential-like value stored is the ICS feed URL
you paste in.

**CalBard does not collect:** your name, your contacts, your device identifiers,
your advertising ID, your precise GPS location, or any analytics or crash
telemetry.

---

## 3. Where CalBard sends data

CalBard makes direct requests from your device to the services below. Each
request necessarily reveals your IP address and a User-Agent string to that
service. No other information about you is included unless noted.

| Service | What is sent | Purpose |
|---|---|---|
| **Open-Meteo** (`api.open-meteo.com`, `geocoding-api.open-meteo.com`) | Latitude/longitude or a place name you typed | Weather forecast and geocoding |
| **National Weather Service** (`api.weather.gov`) | Latitude/longitude | Active weather alerts (US only) |
| **Your calendar host** (whatever ICS URL you add) | A plain HTTPS GET for the feed | Read-only calendar events |

CalBard does not operate a proxy or relay for these requests in the published
Android app. Your device talks to each service directly.

### Services not used in this version

Version 1.0.0 ships without the following integrations. They are listed here so
this policy stays accurate if a later version enables them; **none of them is
contacted by the app you installed**:

| Service | Would be used for | Status in 1.0.0 |
|---|---|---|
| **Google Calendar API** (`www.googleapis.com`) | Read-only calendar events via OAuth | Not enabled — no Google sign-in in this version |
| **ESPN** (`site.api.espn.com`) | Sports scores and schedules | Not enabled — sports section not included |
| **RainViewer** (`api.rainviewer.com`, `tilecache.rainviewer.com`) | Weather radar imagery | Not enabled — radar section not included |
| **OpenStreetMap** (`tile.openstreetmap.org`) | Base map tiles | Not enabled — no map is rendered |

If a future version enables any of these, this policy will be updated before that
version is published, and the "Last updated" date above will change.

---

## 4. Google Calendar data

**This section does not apply to version 1.0.0.** The Google sign-in flow is not
included in this version, so CalBard cannot request a Google scope and never
receives Google Calendar data. It is kept here for a future version that adds
Google sign-in.

If a later version offers Google sign-in, this is what it would do:

- CalBard requests the scope `https://www.googleapis.com/auth/calendar.readonly`.
  This is **read-only**. CalBard cannot create, edit, or delete events.
- CalBard also requests `https://www.googleapis.com/auth/userinfo.email` so it can
  show you which account is connected.
- Calendar data is used **only** to render your dashboard. It is not sent to any
  third party, not used for advertising, not used to train models, and not sold.
- The OAuth refresh token is stored in encrypted storage on your device.
- You can revoke access at any time at
  <https://myaccount.google.com/permissions>, or by removing the account inside
  CalBard's settings.

CalBard's use of information received from Google APIs adheres to the
[Google API Services User Data Policy](https://developers.google.com/terms/api-services-user-data-policy),
including the Limited Use requirements.

---

## 5. Data sharing and sale

CalBard does not sell, rent, or share your personal information with anyone. The
only outbound data flows are the direct service requests listed in section 3.

---

## 6. Children

CalBard is not directed at children under 13 and does not knowingly collect
information from them. Because CalBard collects no personal information at all,
it does not fall under COPPA's data-collection provisions.

---

## 7. Security

- All network requests use HTTPS. Cleartext HTTP is disabled in the Android app.
- Credentials are stored using Android's Keystore-backed encrypted preferences.
- Android backup is disabled for CalBard, so your credentials are not copied to
  Google Drive or transferred to a new device.
- The Android WebView is locked down: file access, content access, and
  cross-origin file access are all disabled, and mixed content is blocked.

No system is perfectly secure. If you believe your CalBard data has been
compromised, contact the address in section 1.

---

## 8. Data retention and deletion

All CalBard data lives on your device and is under your control.

- **To delete everything:** uninstall the app, or use Android's *Settings → Apps →
  CalBard → Storage → Clear data*.
- **To delete only cached data:** use the refresh/clear-cache control in CalBard's
  settings.
- **To revoke Google access:** not applicable in version 1.0.0 — there is no
  Google sign-in. If a later version adds it, you would remove the account in
  CalBard's settings and confirm at <https://myaccount.google.com/permissions>.

Because there is no CalBard server, there is no server-side copy to delete and no
deletion request to file.

---

## 9. Changes to this policy

If this policy changes, the "Last updated" date above will change and the new
version will be published at the same URL. Material changes will also be noted in
the app's release notes.

---

## 10. Attribution

CalBard displays data from the services in section 3. Weather data by
[Open-Meteo](https://open-meteo.com/) (CC BY 4.0). Alerts by NOAA/NWS (public
domain). Calendar data comes from the ICS feeds you add yourself.

The same attribution is shown in the app under Settings → About → Data sources,
so it is visible without visiting this page.
