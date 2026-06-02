# Conversor IAE-CNAE — MCP Server

[![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg)](./LICENSE)
[![Transport](https://img.shields.io/badge/transport-streamable--http-111.svg)](#connect-in-30-seconds)
[![Tools](https://img.shields.io/badge/tools-10%20(6%20free)-22c55e.svg)](#the-10-tools)
<!-- Add once live: [![MCP Registry](https://img.shields.io/badge/listed-MCP%20Registry-orange.svg)](https://registry.modelcontextprotocol.io/v0/servers/io.github.conversoriaecnae/conversor-iae-cnae) -->

> **The first fiscal MCP server for Spain.** Connect any AI agent to live IAE, CNAE 2025, AEAT tax-form and RETA data — official sources, no scrapers.

**6 tools free. No key. No signup.** Add the endpoint and start asking.

This is the public manifest + docs repo for the hosted Conversor IAE-CNAE MCP server. The server runs at [conversoriaecnae.es](https://www.conversoriaecnae.es) — there is nothing to install or self-host. This repo holds the [`server.json`](./server.json) registry manifest, the connection details, the tool catalog, and copy-paste [examples](./examples/prompts.md).

---

## Why this exists

Autónomos and gestorías in Spain lose hours mapping IAE ↔ CNAE codes and guessing which AEAT forms (modelos 036/130/303/347…) apply to an activity. General-purpose AI agents make it worse: they confidently hallucinate tax facts that are wrong.

This server gives your agent a direct line to the real data — 1,187 IAE codes from the AEAT, 1,060 CNAE 2025 codes from the INE, the IAE↔CNAE crosswalk, módulos IRPF/IVA, AEAT obligations, and the 2026 RETA brackets — so it answers from official sources instead of guessing.

It is Spain-only, by design.

## Connect in 30 seconds

The server speaks **Streamable HTTP** (MCP spec 2025-11-25; SSE is not exposed). Add it to your MCP client config:

```json
{
  "mcpServers": {
    "conversor-iae-cnae": {
      "type": "streamable-http",
      "url": "https://www.conversoriaecnae.es/api/mcp/mcp"
    }
  }
}
```

For the 4 premium tools, add your `cvr_` API key as a Bearer header inside the server block:

```json
{
  "mcpServers": {
    "conversor-iae-cnae": {
      "type": "streamable-http",
      "url": "https://www.conversoriaecnae.es/api/mcp/mcp",
      "headers": { "Authorization": "Bearer cvr_your_api_key" }
    }
  }
}
```

Works with **Claude Desktop / claude.ai** (also available as a native connector), **ChatGPT** (developer-mode connectors), **Cursor**, **Gemini CLI**, and any MCP-compatible client.

- **Cursor one-click:** the "Add to Cursor" deeplink lives on the [connect page](https://www.conversoriaecnae.es/mcp).
- **claude.ai connector:** add `https://www.conversoriaecnae.es/api/mcp/mcp` as a custom connector (OAuth handles auth automatically).

## The 10 tools

**6 free** (no key, no signup) · **4 premium** (Profesional plan, from €29/mo — via a `cvr_` key or Supabase OAuth).

| Tool | Tier | What it does |
|------|------|--------------|
| `buscar_codigo` | Free | Semantic search across IAE / CNAE 2025 / CNAE 2009 by description |
| `detalle_iae` | Free | Full record for an IAE code + its associated CNAE codes |
| `detalle_cnae` | Free | Full record for a CNAE 2025 code + its associated IAE codes |
| `detalle_cnae_2009` | Free | A (legacy) CNAE 2009 code and its CNAE 2025 correspondence |
| `calendario_fiscal` | Free | AEAT forms and upcoming deadlines for a code |
| `describe_conversor` | Free | Self-description: catalogs, RPCs and data freshness |
| `obligaciones_fiscales` | Premium | Applicable AEAT forms with confidence, reason, frequency, deadline |
| `modulos_irpf_iva` | Premium | Estimación objetiva (módulos) régimen for an IAE code |
| `consulta_masiva` | Premium | Up to 50 IAE or CNAE records in a single call |
| `cuota_reta` | Premium | 2026 RETA bracket + minimum quota from net income |

## Free vs premium

- **Free** answers *what your code is* — search, look up, convert, and see the fiscal calendar. Enough to be useful on its own, with no account.
- **Premium** answers *what you must file* — the obligations, the módulos régimen, bulk lookups for client portfolios, and the RETA quota. Built for gestorías, asesorías and fintech in production. From **€29/mo**, no commitment.

→ Get a key: **[conversoriaecnae.es/api-precios?source=mcp](https://www.conversoriaecnae.es/api-precios?source=mcp)**

## Data sources

Official only: **AEAT** (Agencia Tributaria) for IAE codes and modelos, **INE** (Instituto Nacional de Estadística) for CNAE 2025, and the **BOE** for the underlying regulation. Every response carries a freshness signal, and `describe_conversor` exposes the catalogs and their update dates.

## Links

- Connect / landing page — https://www.conversoriaecnae.es/mcp
- Agent docs — https://www.conversoriaecnae.es/agents.md
- Technical config (MCP section of the API docs) — https://www.conversoriaecnae.es/api/v1/docs#mcp
- API pricing (premium keys) — https://www.conversoriaecnae.es/api-precios?source=mcp
- Example prompts — [examples/prompts.md](./examples/prompts.md)

---
---

# Conversor IAE-CNAE — Servidor MCP (Español)

> **El primer servidor MCP fiscal de España.** Conecta tu agente de IA a códigos IAE, CNAE 2025, obligaciones AEAT y cuota RETA con datos oficiales.

**6 herramientas gratis. Sin clave. Sin registro.** Añade el endpoint y empieza a preguntar.

Este es el repositorio público de documentación y manifiesto del servidor MCP de Conversor IAE-CNAE. El servidor está alojado en [conversoriaecnae.es](https://www.conversoriaecnae.es) — no hay nada que instalar. Aquí encontrarás el manifiesto [`server.json`](./server.json), cómo conectarte, el catálogo de herramientas y [ejemplos](./examples/prompts.md).

## Por qué existe

Las gestorías y los autónomos pierden horas mapeando códigos IAE ↔ CNAE y comprobando qué modelos AEAT (036/130/303/347…) aplican a cada actividad. Los agentes de IA genéricos lo empeoran: alucinan datos fiscales con total seguridad, y muchas veces son incorrectos.

Este servidor da a tu agente acceso directo a los datos reales —1.187 epígrafes IAE de la AEAT, 1.060 códigos CNAE 2025 del INE, la correspondencia IAE↔CNAE, módulos IRPF/IVA, obligaciones AEAT y los tramos del RETA 2026— para que responda con fuentes oficiales en lugar de adivinar.

Es solo para España, por diseño.

## Conéctalo en 30 segundos

El servidor usa **Streamable HTTP** (MCP spec 2025-11-25; no se expone SSE). Añádelo a la configuración de tu cliente MCP:

```json
{
  "mcpServers": {
    "conversor-iae-cnae": {
      "type": "streamable-http",
      "url": "https://www.conversoriaecnae.es/api/mcp/mcp"
    }
  }
}
```

Para las 4 herramientas premium, añade tu clave `cvr_` como cabecera Bearer dentro del bloque del servidor:

```json
"headers": { "Authorization": "Bearer cvr_tu_clave_api" }
```

Compatible con **Claude Desktop / claude.ai** (también como conector nativo), **ChatGPT** (conectores en modo desarrollador), **Cursor**, **Gemini CLI** y cualquier cliente compatible con MCP.

## Las 10 herramientas

**6 gratis** (sin clave ni registro) · **4 premium** (plan Profesional, desde 29 €/mes — con clave `cvr_` o Supabase OAuth).

| Herramienta | Plan | Qué hace |
|-------------|------|----------|
| `buscar_codigo` | Gratis | Búsqueda semántica en IAE / CNAE 2025 / CNAE 2009 por descripción |
| `detalle_iae` | Gratis | Ficha completa de un epígrafe IAE y sus CNAE asociados |
| `detalle_cnae` | Gratis | Ficha completa de un CNAE 2025 y sus IAE asociados |
| `detalle_cnae_2009` | Gratis | Un CNAE 2009 (obsoleto) y su correspondencia a CNAE 2025 |
| `calendario_fiscal` | Gratis | Modelos AEAT y próximos plazos de un código |
| `describe_conversor` | Gratis | Auto-descripción: catálogos, RPCs y frescura de datos |
| `obligaciones_fiscales` | Premium | Modelos AEAT aplicables con confianza, motivo, periodicidad y plazo |
| `modulos_irpf_iva` | Premium | Régimen de estimación objetiva (módulos) de un IAE |
| `consulta_masiva` | Premium | Hasta 50 fichas IAE o CNAE en una sola llamada |
| `cuota_reta` | Premium | Tramo y cuota mínima del RETA 2026 por rendimiento neto |

## Gratis vs premium

- **Gratis** responde *cuál es tu código* — buscar, consultar, convertir y ver el calendario fiscal. Útil por sí solo, sin cuenta.
- **Premium** responde *qué tienes que presentar* — obligaciones, régimen de módulos, consultas masivas para carteras de clientes y la cuota del RETA. Pensado para gestorías, asesorías y fintech en producción. Desde **29 €/mes**, sin permanencia.

→ Consigue tu clave: **[conversoriaecnae.es/api-precios?source=mcp](https://www.conversoriaecnae.es/api-precios?source=mcp)**

## Fuentes de datos

Solo oficiales: **AEAT** para epígrafes IAE y modelos, **INE** para CNAE 2025 y **BOE** para la normativa. Cada respuesta incluye la frescura de los datos, y `describe_conversor` expone los catálogos y sus fechas de actualización.

## Contacto

- Web: https://www.conversoriaecnae.es
- Email: brian@conversoriaecnae.es
