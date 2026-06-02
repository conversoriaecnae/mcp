# Launch creative — OG image + demo

## OG / social image (1200×630)
- Source: [`og-image.svg`](./og-image.svg) — dark `#121212`, headline "El primer servidor MCP fiscal de España", connect JSON snippet, "6 herramientas gratis · sin clave · sin registro".
- Rasterize to PNG before uploading:
  ```bash
  npx sharp-cli -i og-image.svg -o og-image.png
  # or: rsvg-convert -w 1200 -h 630 og-image.svg > og-image.png
  ```
- Use on: Product Hunt gallery, Twitter/X card, LinkedIn, the flywheel blog post.
- ⚠️ **Site OG gap found during build:** `app/mcp/page.tsx` defines `metadata` (title/description/canonical) but **no `openGraph` block**, so `/mcp` currently falls back to the root layout's default OG image. Add an `openGraph` (and `twitter`) entry to the `/mcp` metadata pointing at this image so shared `/mcp` links render the branded card. (Small in-app edit — not done in this pass because it depends on where you host the PNG.)

## Demo video / GIF (30–45s) — the single highest-leverage asset
**Shot list:**
1. (0–4s) Claude Desktop (or claude.ai) with the connector already added. Show the connect JSON for 1s.
2. (4–10s) Type: **"¿Qué obligaciones fiscales tengo con el epígrafe IAE 501.3?"**
3. (10–18s) Show the MCP tool call firing (`calendario_fiscal` / `obligaciones_fiscales`) — the tool-use chip is the "wow".
4. (18–35s) Claude's answer listing the AEAT modelos with periodicidad/plazo.
5. (35–45s) End card = the OG image + `conversoriaecnae.es/mcp`.

**Tips:** record at 1280×720+, keep captions in Spanish, no audio needed (autoplay-friendly GIF), export an MP4 *and* a GIF. Reuse on PH, repo README, the `/mcp` page, LinkedIn, X.

## The 3 reusable demo prompts ("try this")
Drop these verbatim into every post to cut activation energy:
1. `¿A qué código CNAE 2025 corresponde el epígrafe IAE 501.3?`
2. `What tax forms apply to Spanish IAE code 501.3?`
3. `I'm a freelance developer in Spain — which IAE and CNAE codes apply to me?`

(Full set with the premium tools in [`../examples/prompts.md`](../examples/prompts.md).)
