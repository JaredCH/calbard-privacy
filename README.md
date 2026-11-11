# CalBard Legal Pages

Public hosting for CalBard's privacy policy, terms of use, and third-party
license notices, served via GitHub Pages.

**Live URLs:**

- <https://jaredch.github.io/calbard-privacy/> — privacy policy
- <https://jaredch.github.io/calbard-privacy/terms.html> — terms of use
- <https://jaredch.github.io/calbard-privacy/licenses.html> — third-party notices

These URLs are referenced from:

- The Google Play and Amazon Appstore listings (privacy policy, terms)
- The CalBard app: Settings → About → Privacy, Terms of use, Third-party licenses
  (`LEGAL_BASE_URL` in `web/src/settings/panes/AboutPane.tsx`)

## Why this repo exists

Google Play requires every app to have a publicly reachable privacy policy URL,
and the app distribution carries third-party license obligations. The CalBard
source repository is private, so the legal pages and the full license texts are
mirrored here in a public repo and published as static pages.

## Structure

| Path | Purpose |
|---|---|
| `privacy-policy.md` | Privacy policy source. Mirrors `docs/privacy-policy.md` in the app repo. |
| `terms.md` | Terms of use source. |
| `licenses.md` | Third-party notices and data-source terms. |
| `licenses/*.txt` | Full Apache-2.0, MIT, and SIL OFL 1.1 texts. |
| `build.mjs` | Converts the three Markdown files to `index.html`, `terms.html`, `licenses.html`. |
| `*.html` | Generated output. **Do not edit by hand.** |

## Updating a page

```powershell
# 1. Edit the Markdown source and bump its "Last updated" date.
# 2. Regenerate the HTML.
npm install          # first time only
node build.mjs
# 3. Commit and push — Pages redeploys automatically.
git add -A
git commit -m "Update privacy policy"
git push
```

The privacy policy promises that changes appear "at the same URL." Keeping this
repo and its Pages site alive is what makes that promise true. If the site ever
moves to a custom domain, keep a redirect from this URL.

## Keeping in sync with the app repo

`privacy-policy.md` here is a copy of `docs/privacy-policy.md` in the private
CalBard repository. When you change one, change the other. The app repo's copy is
what the Play Console's Data safety form is checked against, so a divergence is a
review risk. The license texts here should match
`web/public/legal/` and `web/public/fonts/OFL.txt` in the app repo.

The app's About screen links to all three pages. If a page path changes, update
`AboutPane.tsx` and rebuild the app.

## Local preview

```powershell
node build.mjs
start index.html
```
