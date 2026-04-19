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
2. **No AI-consultancy framing.** AI is a *layer* inside Workflow Automation, not a standalone pillar or headline offering. Do not add phrases like "AI transformation", "AI strategy", or "bespoke AI".
3. **Bespoke Builds ≠ bespoke AI.** The pillar is about custom integrations, dashboards, and data plumbing. Do not list "AI agents" or "LLM-powered workflows" under this pillar.
4. **No Azure OpenAI anywhere.** Azure as a cloud platform is fine. Azure OpenAI is the employer's stack — keep it off the site.
5. **No fake metrics or superlatives.** No client-count stats, no productivity-gain numbers, no "leader" / "best" claims. Company has no clients yet. Capability claims only.

## Service pillars (canonical list)

1. **Workflow Automation** — n8n, Zapier, Power Automate; AI where it helps
2. **Bespoke Builds** — Python/Node/TS/Postgres; custom APIs, dashboards, data pipelines
3. **Cloud Migration** — AWS, Azure, GCP, or self-hosted

**Tools explicitly removed — do not re-add:** Make, UiPath.

## Design system

- Dark Cyber-Maghreb theme. Colors tokenised in `style.css` section 1.
- Fonts: Syne (display), Space Grotesk (body), Space Mono (mono) — via Google Fonts.
- Per-pillar accent color: cyan (Automation), violet (Bespoke), gold (Cloud).

## Accessibility & motion

- All animations gated by `prefers-reduced-motion: reduce`.
- Scroll reveals use IntersectionObserver; fall back to immediate visibility when reduced motion or no IO support.

## Deployment

GitHub Pages from `main` branch, repo root. Custom domain set in repo Settings → Pages. DNS via GoDaddy — 4 A records at apex + CNAME on `www` pointing to `ahmedseyfeddine-tag.github.io`.

## Before committing

- Never skip hooks or sign-off bypasses.
- Keep commits focused and describe *why*, not just *what*.
- Don't amend pushed commits; create new ones.
