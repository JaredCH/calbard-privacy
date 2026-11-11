# CalBard Privacy Policy

**Last updated: 2026-11-11**

CalBard is a personal dashboard app for Android TV, tablets, and phones. It shows
weather, calendars, sports schedules, and to-dos on a single screen.

This policy explains what CalBard does with your information. The short version:
**CalBard has no server and no account system. Your settings and saved dashboard
data stay on your device. When you use a network feature, the request goes
directly to the provider that supplies that data.**

---

## 1. Who we are

CalBard is developed and published by an individual developer. For any privacy
question, contact:

**Email:** Hicksjaredc@gmail.com

---

## 2. What CalBard stores on your device

Everything CalBard remembers is stored locally on the device where you installed
it. CalBard does not operate a server and does not receive a copy of this data.

| Data | Why it is stored | Where it lives |
|---|---|---|
| Your location (ZIP code or latitude/longitude that **you type in**) | To fetch weather for that place | App preferences |
| Calendar feeds you add (ICS URLs) | To display your events | App preferences |
| Cached weather, calendar, and sports responses | To show data instantly and work offline | Local database |
| Display preferences (theme, layout, which sections are visible) | To remember your setup | App preferences |
| To-do items | To show your checklist | App preferences |

When you use the weather section, the place you typed is sent to the weather
providers described in section 3 so they can answer the request. It is not sent
to a CalBard server.

On Android, any credentials you enter are held in `EncryptedSharedPreferences`,
which is backed by the Android Keystore. On the web build, they are held in the
browser's `localStorage` for the site you loaded. Version 1.3.0 has no Google
sign-in, so in practice the only credential-like value stored is the ICS feed URL
you paste in.

**CalBard does not ask for or store:** your name, your contacts, your advertising
ID, your precise GPS location, or any analytics or crash telemetry. CalBard does
not read your device's GPS; it uses the place you type.

---

## 3. Where CalBard sends data

CalBard makes direct requests from your device to the services below. CalBard
does not operate a proxy or relay for these requests in the published Android
app, and no CalBard server receives them.

Each request necessarily reveals your IP address and a User-Agent string to that
service. The service may also log the request — including coordinates or the feed
URL — in order to answer it. Those services process the request under their own
privacy policies.

| Service | What is sent | Purpose |
|---|---|---|
| **Open-Meteo** (`api.open-meteo.com`, `geocoding-api.open-meteo.com`) | A place name you typed, or latitude/longitude | Weather forecast and geocoding |
| **National Weather Service** (`api.weather.gov`) | Latitude/longitude | Active weather alerts (US only) |
| **Your calendar host** (whatever ICS URL you add) | A plain HTTPS GET for the feed | Read-only calendar events |
| **AllGameTimes** (schedule feeds) | A plain HTTPS GET for the public schedule feed of the leagues you follow | Sports schedules |

The sports section is on by default. You can turn it off in Settings → Display → Sections,
and no request is made to AllGameTimes while it is off.

### Services not used in this version

Version 1.3.0 ships without the following integrations. They are listed here so
this policy stays accurate if a later version enables them; **none of them is
contacted by the app you installed**:

| Service | Would be used for | Status in 1.3.0 |
|---|---|---|
| **Google Calendar API** (`www.googleapis.com`) | Read-only calendar events via OAuth | Not enabled — no Google sign-in in this version |
| **RainViewer** (`api.rainviewer.com`, `tilecache.rainviewer.com`) | Weather radar imagery | Not enabled — radar section not included |
| **OpenStreetMap** (`tile.openstreetmap.org`) | Base map tiles | Not enabled — no map is rendered |

If a future version enables any of these, this policy will be updated before that
version is published, and the "Last updated" date above will change.

---

## 4. Google Calendar data

**This section does not apply to version 1.3.0.** The Google sign-in flow is not
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

CalBard does not sell or rent your personal information, and does not share it
for advertising. To provide the features you request, CalBard sends the data in
section 3 directly to the providers named there. Those providers process it to
return the weather, calendar, or sports data; CalBard does not receive a copy.

CalBard does not use a relay for these requests in the published Android app. The
optional development proxy in the web build is not deployed in the store app.

---

## 6. Children

CalBard is not directed at children under 13 and does not knowingly collect
personal information from them. It does not require an account or ask for a name.
If you believe a child has provided personal information, contact the address in
section 1.

---

## 7. Security

- All requests the app completes use HTTPS. The Android bridge refuses non-HTTPS
  URLs, and the web build blocks them as mixed content.
- Credentials are stored using Android's Keystore-backed encrypted preferences.
- Android backup is disabled for CalBard, so your credentials are not copied to
  Google Drive or transferred to a new device.
- The Android WebView is locked down: file access, content access, and
  cross-origin file access are all disabled, and mixed content is blocked.

No system is perfectly secure. If you believe your CalBard data has been
compromised, contact the address in section 1.

---

## 8. Data retention and deletion

All CalBard data lives on your device and is under your control. There is no
CalBard server and no server-side copy.

- **To delete everything:** uninstall the app, or use Android's *Settings → Apps →
  CalBard → Storage → Clear data*.
- **To delete only cached data:** use Android's *Settings → Apps → CalBard →
  Storage → Clear cache*. On the web build, clear the site's storage in your
  browser.
- **To revoke Google access:** not applicable in version 1.3.0 — there is no
  Google sign-in. If a later version adds it, you would remove the account in
  CalBard's settings and confirm at <https://myaccount.google.com/permissions>.

---

## 9. Changes to this policy

If this policy changes, the "Last updated" date above will change and the new
version will be published at the same URL. Material changes will also be noted in
the app's release notes.

---

## 10. Attribution

CalBard displays data from the services in section 3. Weather data by
[Open-Meteo](https://open-meteo.com/) (CC BY 4.0 — attribution required). Alerts
by NOAA/NWS (public domain). Sports schedules by AllGameTimes (unofficial feeds;
no published terms). Calendar data comes from the ICS feeds you add yourself.

The weather, calendar, and sports attribution is shown in the app under
Settings → About → Data sources, so it is visible without visiting this page.
The third-party software notices (fonts, React, and Android libraries) are
published at <https://jaredch.github.io/calbard-privacy/licenses.html> and are
also bundled in the app.
