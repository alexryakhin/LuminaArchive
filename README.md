# Lumina Archive — website

Static marketing + legal site for [luminaarchive.app](https://luminaarchive.app).  
Design inspiration: bold hero + pill nav pattern from [tryclucky.com](https://tryclucky.com), restyled for Lumina’s dark vault palette.

## Pages

| Path | Purpose |
|------|---------|
| `/` | Landing |
| `/help/` | Help center (App Constants `helpURL`) |
| `/privacy/` | Privacy Policy (`privacyURL`) |
| `/terms/` | Terms of Use (`termsURL`) |
| `/support/` | Support / contact |

## Local preview

```bash
cd LuminaArchive-Web
python3 -m http.server 8080
# open http://localhost:8080
```

## Deploy (Cloudflare Pages example)

1. Push this repo to GitHub (e.g. `LuminaArchive-Web`).
2. Cloudflare Pages → Connect repo → output directory `/` (static).
3. Attach custom domain `luminaarchive.app` (+ `www` redirect).
4. Confirm `/privacy`, `/terms`, and `/help` return HTTP 200 (required for App Store).

## Submodule

Used from the iOS app repo as `website/`:

```bash
# from LuminaArchiveApp (parent)
git submodule update --init --recursive
```

After you create a GitHub remote for this site, update the parent `.gitmodules` URL from the local path to the HTTPS remote.

## Before go-live

- [ ] Replace App Store button href on the home page with the real listing URL
- [ ] Confirm `support@luminaarchive.app` receives mail
- [ ] Legal review of Privacy + Terms
- [ ] Optional: favicon / OG image
