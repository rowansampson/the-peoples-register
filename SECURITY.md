# Security Policy

The People's Register is a production civic platform. Security is treated as
an engineering discipline, not an afterthought.

## What is in place (verified on the live site)

- Strict Content-Security-Policy (`object-src 'none'`, `upgrade-insecure-requests`, `block-all-mixed-content`)
- HSTS with 2-year max-age
- Versioned secure media pipeline
- Form-abuse protection on all newsletter flows
- Double opt-in enforcement on every subscription

## Reporting a vulnerability

If you discover a vulnerability, please report it privately rather than
opening a public issue:

- **Email:** info.rowansampson@gmail.com
- Subject line: `Security — The People's Register`

You will receive an acknowledgement within 48 hours. Once a fix is shipped,
the finding may be disclosed with credit.

## Supported versions

Only the version currently in production receives security fixes.
