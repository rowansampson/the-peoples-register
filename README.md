# The People's Register — Architecture

> Architecture documentation for the flagship build of Digital Origin: a live civic publication platform for the ANC Nelson Mandela Region, engineered end to end.
>
> **Live:** [thepeoplesregister.co.za](https://www.thepeoplesregister.co.za)

![Production](https://img.shields.io/badge/status-production-3ecf6e) ![Vercel](https://img.shields.io/badge/hosting-vercel-0e141d) ![Zero dependencies](https://img.shields.io/badge/stack-zero%20dependencies-0e141d) ![Trilingual](https://img.shields.io/badge/i18n-EN%2FisiXhosa%2FAF-b8860b)

---

## What this platform is

A recurring-issue civic publication: an interactive 12-page field journal covering six clusters and all 60 wards, an article pipeline, a consent-first newsletter system, and verified election information, in three languages (English, isiXhosa, Afrikaans).

This repository documents the engineering behind it. It is documentation-first by design: the platform's working code lives in the production deployment, while this repo exists so the build can be read, audited, and judged.

---

## The five phases

| Phase | What happened |
|---|---|
| **01 · Discover** | Product concept and content model — issues → cluster chapters → field reports. Information architecture before markup; sitemap first. |
| **02 · Architect** | Design system from zero: colour tokens, serif-editorial / sans-UI type scale, spacing grid, component library. No framework, no template. |
| **03 · Build** | Interactive journal, article pages, multilingual preference system; Python PDF edition pipeline; SEO architecture; security hardening. |
| **04 · Ship** | Production deployment (Vercel, HTTP/2), robots.txt + XML sitemap, strict transport security. |
| **05 · Operate & Improve** | Release cadence, versioned content, IEC notice verification, newsletter system maintenance — continuous improvement as the platform rolls out. |

---

## Systems shipped

| # | System | Notes |
|---|---|---|
| 01 | Interactive Field Journal | 12-page editorial reader, cluster navigation, datelines, issue indexing |
| 02 | PDF Edition Pipeline | Python-generated document editions, versioned per release (`?v=2`) |
| 03 | SEO Architecture | Unique titles/descriptions per route, canonicals, Open Graph, JSON-LD (NewsMediaOrganization · NewsArticle), robots.txt + sitemap |
| 04 | Email Automation | Brevo double opt-in, welcome and cadence sequences, language segmentation |
| 05 | IEC Verification Module | Public-notice status kept current against the Electoral Commission |
| 06 | Multilingual System | Dictionary-level i18n — EN / isiXhosa / Afrikaans across flows |
| 07 | Secure Media Pipeline | Versioned secure asset delivery under a strict CSP |
| 08 | Production Operations | Release cadence, monitoring, continuous upgrades |

---

## Security posture (verified on the live site)

- Strict Content-Security-Policy (`object-src 'none'`, `upgrade-insecure-requests`, `block-all-mixed-content`)
- HSTS with 2-year max-age
- Form-abuse protection (honeypot) on all newsletter flows
- Double opt-in enforcement — nothing is sent until the subscriber confirms

## Stack: deliberately boring-proof

Semantic HTML5 · hand-rolled CSS design tokens · vanilla JavaScript · Python (document pipeline) · Brevo (automation). Zero frameworks, zero CDN dependencies, builds measured in kilobytes.

---

*Author: Rowan Sampson — Digital Origin. This documentation is public; the publication's editorial content remains the property of its publishers.*
