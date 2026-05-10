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

These rules exist because TAG's founder currently works at a German/EU AI consultancy that *also builds AI solutions* (not just strategy). The differentiator is therefore not "we build vs they advise" — they do both. Safety comes from **geographic separation (Tunisia only)** and **segment separation (Tunisian SMBs only)**:

1. **Tunisia-only scope.** Site says "PME tunisiennes uniquement" / "Tunisian SMBs only". Do not reintroduce EU, Germany, MENA, or international targeting.
2. **Tunisian SMBs only.** No enterprise framing, no large-scale claims. The segment is small and mid-sized businesses based in Tunisia.
3. **Operational positioning, not advisory.** TAG is positioned as an automation builder and operator — it ships things and maintains them. The site is benefit-led; do not lean heavily on contrast against consultancies (the employer also builds AI). One soft anti-strategy reference in the hero body is allowed; nowhere else.
4. **No Azure OpenAI anywhere.** Azure OpenAI is the employer's stack — keep it off the site.
5. **No fake metrics or superlatives.** No client-count stats, no "leader" / "best" claims. Company has no clients yet. Stats must be framed as "estimates based on results at similar companies."

## Service pillars (canonical list)

TAG builds and operates automations for Tunisian SMBs — with or without AI, depending on what the use case actually needs.

The 4 pillars:
1. **Traitement de Documents** — Invoice, contract, PO, HR document extraction → ERP / SAP / Excel
2. **Recherche & Mémoire Interne** — RAG / semantic search over internal files, manuals, reports
3. **Pipelines de Données** — Sync between systems, automated reports, transformations and validation
4. **Outils IA & Automatisation de Processus** — Approval workflows, custom AI assistants, internal chatbots, recurring reports

Integration targets: SAP, ERP, Excel, API REST.
AI/extraction stack: Python, OpenAI, Claude, OCR.
Supported formats: PDF, JPEG, PNG, Word, Email.

## Design system

- Professional blue/navy theme. Colors tokenised in `style.css` section 1.
- Primary: `--color-cyan: #1D5BE0` (electric blue), `--color-violet: #4F46E5` (indigo), `--color-gold: #D97706` (amber), `--color-emerald: #0D9488` (teal).
- Fonts: Syne (display), Space Grotesk (body), Space Mono (mono) — via Google Fonts.
- Per-pillar accent: cyan (Documents), violet (Search), emerald (Pipelines), gold (AI tools & process).

## Accessibility & motion

- All animations gated by `prefers-reduced-motion: reduce`.
- Scroll reveals use IntersectionObserver; fall back to immediate visibility when reduced motion or no IO support.

## Deployment

GitHub Pages from `main` branch, repo root. Custom domain set in repo Settings → Pages. DNS via GoDaddy — 4 A records at apex + CNAME on `www` pointing to `ahmedseyfeddine-tag.github.io`.

## Before committing

- Never skip hooks or sign-off bypasses.
- Keep commits focused and describe *why*, not just *what*.
- Don't amend pushed commits; create new ones.
