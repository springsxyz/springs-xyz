# Of Use Apps domain migration

Status: landing page published, domain connected and HTTPS verified on 29 October 2026.

Owner-confirmed new domain: **ofuseapps.com**, 29 October 2026. Existing site: **springsxyz.com**, repository springsxyz/springs-xyz.

## Verified starting state

Read-only checks on 29 October 2026 found:

- GitHub Pages: built, legacy publishing from main at /.
- Pages custom domain: springsxyz.com; HTTPS enforcement false.
- ofuseapps.com apex A: 192.64.119.65.
- www.ofuseapps.com CNAME: parkingpage.namecheap.com.
- Nameservers: dns1.registrar-servers.com and dns2.registrar-servers.com.
- No apex AAAA answer was returned.

These were the starting parking records. The owner subsequently signed in to the Namecheap account for this domain and authorized continuing the connection.

## Connection receipt — 29 October 2026

- Published [pull request #2](https://github.com/springsxyz/springs-xyz/pull/2), merge commit `0ff8996046bcc6dc9f47b276c88ccb0c32b0de1b`, at 22:06:36 UTC (19:06:36 America/Santiago).
- GitHub Pages reports `built`, using `ofuseapps.com` and the existing `main:/` source.
- Replaced the `www` parking CNAME with `springsxyz.github.io.`.
- Converted the apex parking redirect to `185.199.108.153` and added the remaining three GitHub Pages A records listed below. All four were confirmed by the public resolver at `1.1.1.1`.
- The Namecheap host table shows exactly the four intended apex A records and the `www` CNAME. The existing email-forwarding setting and SPF record remain present; nameservers, email and security settings were not changed.
- Public HTTP returns the correct Of Use Apps page and both SVG logos. `http://www.ofuseapps.com/` returns 301 to `http://ofuseapps.com/`.
- GitHub's domain-health response marks both hostnames valid, served by Pages and eligible for HTTPS, with no CAA error.
- GitHub approved a certificate for both hostnames, expiring 27 January 2027. HTTPS enforcement was enabled and confirmed saved.
- Final normal-certificate checks passed: HTTPS apex returns 200 with the correct page and both SVG assets; HTTP apex redirects to HTTPS; HTTPS `www` redirects to the HTTPS apex; HTTP `www` redirects through the apex to HTTPS. No TLS error was bypassed.
- Live browser verification confirmed the title, canonical URL, loaded wordmark and Start Your Round destination. Proof is retained at `../Branding/of-use-website-2026-10-29/landing-live-https.jpg`.

## Connection procedure

1. Confirm access to the domain's DNS account and review existing records.
2. Set the existing GitHub Pages custom domain to ofuseapps.com, with CNAME aligned. This should precede pointing the new domain at GitHub.
3. Replace only the apex parking destination with these A records:

| Type | Host | Value |
| --- | --- | --- |
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |
| CNAME | www | springsxyz.github.io |

4. Preserve unrelated MX, TXT, email, verification and other records. Keep the existing nameservers.
5. Verify public DNS, GitHub's domain check, certificate readiness and the actual new page over HTTPS. Enable Enforce HTTPS when available.
6. Verify www redirects to the apex once both DNS and Pages are ready.

GitHub documents the addresses, configuration order and www behavior in [Managing a custom domain](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site). Certificate and enforcement details are in [Securing Pages with HTTPS](https://docs.github.com/en/pages/getting-started-with-github-pages/securing-your-github-pages-site-with-https).

**Owner decision, 29 October 2026:** use **ofuseapps.com** as the sole brand domain and leave **springsxyz.com** unused. Old-domain forwarding is intentionally omitted and is not an outstanding migration task.

## Local verification

The landing page and vector logo have been inspected at desktop size and mobile widths 390 and 320 CSS pixels. The logo loads, app navigation reaches the apps section, and no horizontal overflow was found. The local preview returned HTTP 200. Source checks cover local paths, unique anchors, brand/domain metadata and SVG XML. Screenshots are retained in the parent workspace's Branding/of-use-website-2026-10-29 folder.

Publication and connection results are recorded above; local checks alone do not establish HTTPS readiness.
