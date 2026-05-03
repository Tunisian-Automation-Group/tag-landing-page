# TAG Landing Page — Contributor Guide

Static landing page for **Tunisian Automation Group (TAG)**. Plain HTML + CSS + minimal inline JS (no build step, no framework). Deployed via GitHub Pages → `tunisian-automation.com`.

## Files

- `index.html` — single page, all sections
- `style.css` — single stylesheet, sections numbered in comments
- `assets/` — static assets (favicon, future images)

## Git identity

This repo uses a **local-override git identity** that must not be changed:

- `user.email` = `ahmed.seyfeddine@tunisian-automation.com`
- `user.name` = `Tunisian Automation Group`

Pushes go to `github.com:Tunisian-Automation-Group/tag-landing-page` via SSH as GitHub user `ahmedseyfeddine-tag`. This is **intentionally separate** from the owner's personal GitHub identity. Never commit as the personal identity here.

## Content guardrails

These rules exist because TAG's founder currently works at a German AI consultancy serving EU clients. The site is positioned so there is **no competitive overlap**:

1. **Tunisia-only scope.** The site says "Tunisian clients only" / "exclusively small and mid-sized businesses based in Tunisia". Do not reintroduce EU, MENA, or international targeting.
2. **IDP only — no consultancy framing.** TAG does Intelligent Document Processing (IDP): extract data from documents, structure it, push it to ERP/SAP/Excel. Do not add workflow automation, web development, cloud migration, or AI-strategy services.
3. **No Azure OpenAI anywhere.** Azure OpenAI is the employer's stack — keep it off the site.
4. **No fake metrics or superlatives.** No client-count stats, no "leader" / "best" claims. Company has no clients yet. Stats must be framed as "estimates based on results at similar companies."

## Service pillars (canonical list)

TAG does one thing: **Intelligent Document Processing (IDP)**

Document types handled:
1. **Factures & Comptabilité** — PDF and scanned invoices, debit/credit notes, bank statements
2. **Contrats & Documents Légaux** — Supplier/client contracts, NDAs, amendments
3. **Logistique & Commerce** — Purchase orders, delivery notes, customs documents
4. **RH & Documents Internes** — Pay slips, HR records, internal forms

Integration targets: SAP, ERP, Excel, API REST.
AI/extraction stack: Python, OpenAI, Claude, OCR.
Supported formats: PDF, JPEG, PNG, Word, Email.

**Do not re-add:** workflow automation (n8n, Zapier), web development, cloud migration.

## Design system

- Professional blue/navy theme. Colors tokenised in `style.css` section 1.
- Primary: `--color-cyan: #1D5BE0` (electric blue), `--color-violet: #4F46E5` (indigo), `--color-gold: #D97706` (amber), `--color-emerald: #0D9488` (teal).
- Fonts: Syne (display), Space Grotesk (body), Space Mono (mono) — via Google Fonts.
- Per-document-type accent: blue (Invoices), indigo (Contracts), teal (Logistics), amber (HR).

## Accessibility & motion

- All animations gated by `prefers-reduced-motion: reduce`.
- Scroll reveals use IntersectionObserver; fall back to immediate visibility when reduced motion or no IO support.

## Deployment

GitHub Pages from `main` branch, repo root. Custom domain set in repo Settings → Pages. DNS via GoDaddy — 4 A records at apex + CNAME on `www` pointing to `ahmedseyfeddine-tag.github.io`.

## Before committing

- Never skip hooks or sign-off bypasses.
- Keep commits focused and describe *why*, not just *what*.
- Don't amend pushed commits; create new ones.
