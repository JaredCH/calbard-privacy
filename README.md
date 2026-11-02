# CalBard Privacy Policy

Public hosting for the CalBard privacy policy, served via GitHub Pages.

**Live URL:** https://jaredch.github.io/calbard-privacy/

This URL is referenced from:

- The Google Play store listing (Store presence → Privacy policy)
- The CalBard app: Settings → About → Privacy policy
  (`PRIVACY_POLICY_URL` in `web/src/settings/panes/AboutPane.tsx`)

## Why this repo exists

Google Play requires every app to have a publicly reachable privacy policy URL.
The CalBard source repository is private, so the policy is mirrored here in a
public repo and published as a static page.

## Structure

| File | Purpose |
|---|---|
| `privacy-policy.md` | Source of truth. Edit this. |
| `build.mjs` | Converts the markdown to `index.html`. |
| `index.html` | Generated output. **Do not edit by hand.** |

## Updating the policy

```powershell
# 1. Edit privacy-policy.md (and bump the "Last updated" date)
# 2. Regenerate the HTML
npm install          # first time only
node build.mjs
# 3. Commit and push — Pages redeploys automatically
git add -A
git commit -m "Update privacy policy"
git push
```

The policy's section 9 promises that changes appear "at the same URL." Keeping
this repo and its Pages site alive is what makes that promise true. If the site
ever moves to a custom domain, keep a redirect from this URL.

## Keeping in sync with the app repo

`privacy-policy.md` here is a copy of `docs/privacy-policy.md` in the private
CalBard repository. When you change one, change the other. The app repo's copy is
what the Play Console's Data safety form is checked against, so a divergence is a
review risk.

## Local preview

```powershell
node build.mjs
start index.html
```
