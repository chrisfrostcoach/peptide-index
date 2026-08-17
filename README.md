# Peptide Index — go-live checklist

This folder is the deployed static site (GitHub Pages, `gh-pages` branch root).

## What's already done
- Standalone `index.html` (the full app) + `privacy.html`.
- Consent banner (UK PECR/GDPR): non-essential OFF by default, Reject == Accept, granular, remembered, revocable via the footer "Cookie settings" link.
- Meta Pixel scaffold: **inert** — it contacts no one until BOTH (a) you set a real Pixel ID and (b) a visitor opts in to marketing. Fires PageView only.

## Before you run real ads — fill these in
1. **`index.html`**: replace `[FB_PIXEL_ID]` (in the pixel `<script>`) with your Meta Pixel ID.
2. **`index.html`** `<head>`: uncomment + paste your `facebook-domain-verification` meta tag, then verify the domain in Meta Business Settings → Brand Safety → Domains.
3. **`privacy.html`**: replace `[PLACEHOLDER — OPERATOR NAME]`, `[PLACEHOLDER — DOMAIN]`, `[PLACEHOLDER-EMAIL]`, `[PLACEHOLDER — PIXEL-ID]`. Have it reviewed by a professional.
4. **Custom domain** (recommended before ad spend): add a `CNAME` file here containing your domain, point DNS at GitHub Pages, and re-verify the domain in Meta.

## The rules the pixel MUST keep (baked in, keep it that way)
- PageView only. Never send compound names, on-site search queries, which cards were viewed, dosing, stacks, or any health-interest signal — in ANY field (event name, params, content_ids, or the URL).
- Advanced Matching OFF (no PII to Meta). No Conversions API.
- Audiences stay first-party in your ad account. Build Custom Audiences from "all visitors" + newsletter `Lead` only; Lookalikes from those. Never export or sell the list.
- One leaked compound name = Meta auto-detects sensitive health data and can ban the pixel + ad account. This is the whole ballgame for a health-adjacent site.

## Ad creative angle (Meta restricts this category)
Run education / newsletter-signup ads to the neutral homepage — never "buy/get/dose/results" and never a compound name as the call-to-action. There is nothing to buy here, which is the point.
