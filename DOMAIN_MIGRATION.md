# Of Use Apps domain migration

Status: prepared; no live DNS or GitHub Pages custom-domain change has been made by this task.

Owner-confirmed new domain: **ofuseapps.com**, 29 October 2026. Existing site: **springsxyz.com**, repository springsxyz/springs-xyz.

## Verified starting state

Read-only checks on 29 October 2026 found:

- GitHub Pages: built, legacy publishing from main at /.
- Pages custom domain: springsxyz.com; HTTPS enforcement false.
- ofuseapps.com apex A: 192.64.119.65.
- www.ofuseapps.com CNAME: parkingpage.namecheap.com.
- Nameservers: dns1.registrar-servers.com and dns2.registrar-servers.com.
- No apex AAAA answer was returned.

These new-domain records are parking records, not GitHub Pages destinations. The registrar account has not been authenticated in this task.

## Planned connection

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

Changing this repository's custom domain does not create a redirect from springsxyz.com. An old-domain redirect needs its own hosting or registrar configuration and verification. No redirect has been claimed or configured here.

## Local verification

The landing page and vector logo have been inspected at desktop size and mobile widths 390 and 320 CSS pixels. The logo loads, app navigation reaches the apps section, and no horizontal overflow was found. The local preview returned HTTP 200. Source checks cover local paths, unique anchors, brand/domain metadata and SVG XML. Screenshots are retained in the parent workspace's Branding/of-use-website-2026-10-29 folder.

Publication remains separate from these local checks.
