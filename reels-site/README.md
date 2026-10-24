# reels-site

Public pages for the Candlewake TikTok (and Meta) developer apps: Privacy Policy, Terms of Service, and a login
callback page for `scripts/tiktok_auth.py`. Ready to upload; no personal details in any file. Contact on every
page is "send a direct message to @candlewake on TikTok or @candlewake1 on Instagram".

## Keep your identity off GitHub too

The site address is `https://<github-username>.github.io/reels-site/`, so your GitHub username is public.

- If your username is your real name, create a separate GitHub account for the channel (e.g. `candlewake`)
  and make this repo there. Your private pipeline repo can stay on your main account.
- Settings → Emails → turn on **Keep my email addresses private**, so commits use a no-reply address.

## Publish on GitHub Pages (free)

1. Create a **public** repo named `reels-site`.
2. Add file → Upload files → drag in everything here, including the `callback` folder → Commit changes.
3. Settings → Pages → Source: *Deploy from a branch* → `main`, folder `/ (root)` → Save.
4. After a minute the pages are live at:
   - `https://<github-username>.github.io/reels-site/privacy.html`
   - `https://<github-username>.github.io/reels-site/terms.html`
   - `https://<github-username>.github.io/reels-site/callback/`  ← TikTok Login Kit redirect URI

## In the TikTok developer portal

- Terms of Service URL and Privacy Policy URL: the first two links above.
- Login Kit → Redirect URI: the `callback/` link, exactly, including the trailing slash.
- URL properties: if asked to verify, add `https://<github-username>.github.io/reels-site/`, download the
  verification file, upload it to this repo's root, wait a minute, then click Verify.

Then on your PC:

```
python scripts/tiktok_auth.py --client-key KEY --client-secret SECRET --redirect-uri https://<github-username>.github.io/reels-site/callback/
```

These pages are a starting point written for a single-user publishing tool, not legal advice.
