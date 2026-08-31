# Lumina Archive — website

Static marketing + legal site for the iOS app.  
**Live:** [https://alexriakhin.com/LuminaArchive/](https://alexriakhin.com/LuminaArchive/) (GitHub Pages).

## Pages

| Path | Purpose |
|------|---------|
| `/LuminaArchive/` | Landing |
| `/LuminaArchive/help/` | Help center (`AppConstants.helpURL`) |
| `/LuminaArchive/privacy/` | Privacy Policy (`privacyURL`) |
| `/LuminaArchive/terms/` | Terms of Use (`termsURL`) |
| `/LuminaArchive/support/` | Support / contact |

Links and CSS use **relative** paths so the site works under the `/LuminaArchive/` GitHub Pages base.

## Local preview

```bash
cd LuminaArchive-Web
python3 -m http.server 8080
# open http://localhost:8080
```

## Deploy (GitHub Pages)

1. Push this repo (or the parent app’s `website/` submodule) to GitHub.
2. Enable GitHub Pages (deploy from `main`, site root `/`).
3. Serve under the personal site path so the public URL is `https://alexriakhin.com/LuminaArchive/`.
4. Confirm these return HTTP 200 (required for App Store):
   - https://alexriakhin.com/LuminaArchive/privacy/
   - https://alexriakhin.com/LuminaArchive/terms/
   - https://alexriakhin.com/LuminaArchive/help/

## Submodule

Used from the iOS app repo as `website/`. The parent may still point at a local sibling path until the GitHub remote is set:

```bash
# from LuminaArchive (parent)
git -c protocol.file.allow=always submodule update --init --recursive
```

When the remote exists:

```bash
git submodule set-url website https://github.com/<owner>/LuminaArchive-Web.git
```

## Before go-live

- [x] Replace App Store button href on the home page with the real listing URL
- [ ] Confirm `support@alexriakhin.com` receives mail (or update email everywhere)
- [ ] Legal review of Privacy + Terms
- [x] Favicon set (RealFaviconGenerator) at site root
- [ ] Optional: OG image
