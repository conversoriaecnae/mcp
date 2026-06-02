# Week 1 — Tier-2 directory submissions (ready to paste)

Goal: ≥4 live/pending before launch day. All copy is pre-written. Each directory
gets a `?source=<directory>` param on the `/mcp` link so you can see which
directory drives traffic in analytics.

## Shared facts (reuse everywhere)
- **Name:** Conversor IAE-CNAE — MCP for Spanish tax data
- **Server (registry) name:** `io.github.conversoriaecnae/conversor-iae-cnae`
- **Transport:** Streamable HTTP (remote) — `https://www.conversoriaecnae.es/api/mcp/mcp`
- **Auth:** none for the 6 free tools; optional `Authorization: Bearer cvr_…` for the 4 premium
- **Tools:** 10 total — 6 free (no key, no signup), 4 premium
- **Repo:** https://github.com/conversoriaecnae/mcp
- **Homepage / connect page:** https://www.conversoriaecnae.es/mcp
- **License:** see repo (docs/manifest repo)
- **Categories/tags:** Finance, Tax, Spain, Government data, Developer Tools, API
- **Tool list:** `buscar_codigo`, `detalle_iae`, `detalle_cnae`, `detalle_cnae_2009`,
  `calendario_fiscal`, `describe_conversor` (free) · `obligaciones_fiscales`,
  `modulos_irpf_iva`, `consulta_masiva`, `cuota_reta` (premium)

### Short descriptions (pick by length limit)
- **≤60:** `Spanish tax data for AI agents: IAE/CNAE 2025, AEAT, RETA.`  (57)
- **≤80:** `The first fiscal MCP server for Spain — IAE/CNAE 2025, AEAT modelos, RETA.`  (73)
- **One-liner:** The first fiscal MCP server for Spain. Connect any AI agent to live IAE,
  CNAE 2025, AEAT tax-form and RETA data — official AEAT/INE/BOE sources, no scrapers.

### Long description (paste where a paragraph is allowed)
> The first fiscal MCP server for Spain. Autónomos and gestorías lose hours mapping
> IAE ↔ CNAE 2025 codes and guessing which AEAT forms (036/130/303/347…) apply —
> and general AI agents confidently hallucinate tax facts. This server gives any
> MCP client a direct line to the real data: 1,187 IAE codes (AEAT), 1,060 CNAE 2025
> codes (INE), the IAE↔CNAE crosswalk, IRPF/IVA módulos, AEAT obligations and the
> 2026 RETA brackets — answering from official sources instead of guessing.
> 6 of the 10 tools are free (no key, no signup); 4 premium tools (obligations,
> módulos, bulk lookup, RETA quota) target gestorías and fintech, from €29/mo.
> Spain-only, by design. Every tool carries the `readOnlyHint` annotation.

---

## 1. PulseMCP — https://www.pulsemcp.com (click "Submit" in nav)
- **Name:** Conversor IAE-CNAE
- **Short description:** Spanish tax data for AI agents: IAE/CNAE 2025, AEAT, RETA.
- **URL / repo:** https://github.com/conversoriaecnae/mcp
- **Homepage:** https://www.conversoriaecnae.es/mcp?source=pulsemcp
- **Remote URL:** https://www.conversoriaecnae.es/api/mcp/mcp (Streamable HTTP)
- **Long description:** (paste the long description above)
- **Tags:** finance, tax, spain, government, api

## 2. Smithery — https://smithery.ai (Add server)
Smithery can ingest from the official registry once published — list the registry
name first. If it asks for a manual entry:
- **Qualified name:** io.github.conversoriaecnae/conversor-iae-cnae
- **Display name:** Conversor IAE-CNAE — MCP for Spanish tax data
- **Description:** The first fiscal MCP server for Spain — IAE/CNAE 2025, AEAT modelos, RETA.
- **Connection type:** Remote / Streamable HTTP → https://www.conversoriaecnae.es/api/mcp/mcp
- **Repo:** https://github.com/conversoriaecnae/mcp
- **Homepage:** https://www.conversoriaecnae.es/mcp?source=smithery

## 3. Glama — https://glama.ai/mcp/servers (Add server) — wants name/desc/repo/transport/tool-count
- **Name:** Conversor IAE-CNAE
- **Description:** The first fiscal MCP server for Spain — IAE/CNAE 2025, AEAT modelos, RETA.
- **Repository:** https://github.com/conversoriaecnae/mcp
- **Transport:** Streamable HTTP (remote) — https://www.conversoriaecnae.es/api/mcp/mcp
- **Tool count:** 10 (6 free, 4 premium)
- **Homepage:** https://www.conversoriaecnae.es/mcp?source=glama

## 4. mcp.so — https://mcp.so (Submit)
- **Name:** Conversor IAE-CNAE — MCP for Spanish tax data
- **Description:** Spanish tax data for AI agents: IAE/CNAE 2025, AEAT, RETA. 6 free tools, no key.
- **GitHub:** https://github.com/conversoriaecnae/mcp
- **Website:** https://www.conversoriaecnae.es/mcp?source=mcp_so
- **Remote endpoint:** https://www.conversoriaecnae.es/api/mcp/mcp

## 5. Cursor Directory — https://cursor.directory/mcp (near-zero effort, deeplink exists)
- The "Add to Cursor" deeplink already lives on https://www.conversoriaecnae.es/mcp
- **Name:** Conversor IAE-CNAE
- **Description:** Spanish tax data for AI agents: IAE/CNAE 2025, AEAT, RETA.
- **Homepage:** https://www.conversoriaecnae.es/mcp?source=cursor

## 6. Awesome MCP Servers — PR (see separate task; handled via GitHub PR)
- Entry drafted and PR opened from the conversoriaecnae fork (see `claude-directory-kit.md`
  is unrelated; PR status reported in chat).

---

## Skip (low fit, per playbook)
Docker MCP Catalog, Cline marketplace, mcp-get, mcpmarket — they favor
containerized / stdio npm packages; we're a hosted remote server.
