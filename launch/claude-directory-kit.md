# Week 1 — Claude Connectors Directory submission kit

Submit via the **MCP Directory Server Review Form** (Anthropic). Review takes ~2 weeks,
so submit early in Week 1 to target approval before launch. The #1 rejection cause
(missing `readOnlyHint`) is already solved — all our tools carry it.

## Reviewer kit (assemble before submitting)
- [ ] **Throwaway Profesional `cvr_` key** so reviewers can exercise the 4 premium tools.
      Generate one on a test Profesional account; paste it into the form's auth field /
      reviewer notes. Rotate/revoke it after approval.
- [x] **Privacy policy URL:** https://www.conversoriaecnae.es/politica-privacidad
- [ ] **IP access:** confirm nothing blocks Anthropic's IPs from the endpoint
      (Vercel is public, no WAF allowlist — just sanity-check it responds; the
      `initialize` handshake was verified green on 2026-06-02).
- [x] **Connector docs:** https://www.conversoriaecnae.es/mcp + https://github.com/conversoriaecnae/mcp

## Form answers (paste)

**Server name:** Conversor IAE-CNAE — MCP for Spanish tax data

**Server (registry) name:** io.github.conversoriaecnae/conversor-iae-cnae

**Transport / endpoint:** Streamable HTTP — https://www.conversoriaecnae.es/api/mcp/mcp

**Authentication:** None required for the 6 free tools. The 4 premium tools accept an
optional `Authorization: Bearer cvr_…` header (Profesional plan) OR Supabase OAuth.
A throwaway Profesional key is provided in the reviewer notes.

**Short description:** The first fiscal MCP server for Spain — IAE/CNAE 2025, AEAT modelos, RETA.

**Long description:**
> The first fiscal MCP server for Spain. It connects any AI agent to live Spanish tax
> data — 1,187 IAE codes (AEAT), 1,060 CNAE 2025 codes (INE), the IAE↔CNAE crosswalk,
> IRPF/IVA módulos, AEAT obligations and the 2026 RETA brackets — sourced from official
> AEAT/INE/BOE data, not scrapers. 6 of the 10 tools are free (no key, no signup);
> 4 premium tools serve gestorías and fintech. Spain-only, by design.

**Tools (10) — all read-only (`readOnlyHint: true`):**
- Free: buscar_codigo, detalle_iae, detalle_cnae, detalle_cnae_2009, calendario_fiscal, describe_conversor
- Premium: obligaciones_fiscales, modulos_irpf_iva, consulta_masiva, cuota_reta

**Categories:** Finance / Tax / Government data / Developer Tools

**Privacy policy:** https://www.conversoriaecnae.es/politica-privacidad

**3 demo prompts for reviewers (try-this):**
1. `¿A qué código CNAE 2025 corresponde el epígrafe IAE 501.3?`  (free path)
2. `What tax forms apply to Spanish IAE code 501.3?`  (free path)
3. `I'm a freelance developer in Spain — which IAE and CNAE codes apply to me?`  (free path)
   - Premium check (needs the `cvr_` key): `¿Qué obligaciones fiscales y módulos tengo con el IAE 501.3?`

**Why it qualifies (notes to reviewer):**
- All tools are strictly read-only and annotated with `readOnlyHint`.
- Hosted remote server — nothing to install; the endpoint is public and stable on Vercel.
- Data is official (AEAT/INE/BOE); each response carries a freshness signal and
  `describe_conversor` exposes catalogs and update dates.
- Single-country scope (Spain) keeps the tool surface precise and low-risk.
