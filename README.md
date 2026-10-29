# Of Use Apps website

Static company landing page prepared for https://ofuseapps.com/. The owner selected the Of Use Apps name and logo 01 / Plainly Useful. The page uses a black-and-white umbrella identity, with the workout timer's existing chartreuse accent.

Only the published Start Your Round app is advertised. The timer illustration is explicitly an example session. Contact links retain the existing springsxyz.com@gmail.com inbox; buying a domain does not create a new email mailbox.

## Files

- index.html: content, metadata, canonical URL and working links.
- styles.css: responsive Direct Utility presentation, visible focus and reduced-motion support.
- assets/of-use-apps-wordmark.svg: path-based optical re-creation of the selected wordmark.
- assets/of-use-apps-favicon.svg: compact version using the same lettering.
- CNAME: target custom domain ofuseapps.com.

The SVGs have no external font, script or embedded raster dependency. The wordmark is a vector re-creation, not an exact trace of the concept image. Older assets remain in the repository as historical files and are not used by this page.

## Preview

From this directory:

```powershell
python -m http.server 4174 --bind 127.0.0.1
```

Then open http://127.0.0.1:4174/. No installation or build step is needed. Stop the preview with Ctrl+C.

## Hosting and domain handoff

Keep the existing GitHub Pages repository, springsxyz/springs-xyz, published from main at the repository root. This is not a new hosting project.

The landing update is published at https://ofuseapps.com/, and the new domain's DNS points to GitHub Pages. Normal certificate verification, HTTPS page/logo checks and HTTP/www redirects passed on 29 October 2026. HTTPS enforcement is enabled.

Follow [DOMAIN_MIGRATION.md](DOMAIN_MIGRATION.md) to coordinate the Pages custom-domain change, DNS, certificate and HTTPS checks. Do not describe ofuseapps.com as live until those checks succeed.
