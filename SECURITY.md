# Security Policy

## Reporting a vulnerability

If you discover a security vulnerability in the Conversor IAE-CNAE MCP server or API,
please report it privately. **Do not open a public GitHub issue for security problems.**

- **Email:** seguridad@conversoriaecnae.es (alias to brian@conversoriaecnae.es)
- **Subject:** `[SECURITY] <short summary>`
- Please include: affected endpoint/tool, steps to reproduce, impact, and any PoC.

You can report in English or Spanish.

## What to expect

- **Acknowledgement:** within 3 business days.
- **Triage & status update:** within 7 business days.
- **Fix / mitigation:** prioritized by severity; we will keep you updated until resolved.
- We will credit reporters who wish to be acknowledged once a fix is shipped.

## Scope

In scope:
- The MCP endpoint `https://www.conversoriaecnae.es/api/mcp/mcp`
- The REST API under `https://www.conversoriaecnae.es/api/`
- Authentication / authorization of the `cvr_` API keys and OAuth flows

Out of scope:
- Reports from automated scanners without a demonstrated, reproducible impact
- Volumetric DoS / brute-force without a concrete vulnerability
- Issues in third-party platforms we build on (Vercel, Supabase) — report those upstream

## Handling of data

The MCP tools are read-only over public Spanish fiscal reference data (AEAT/INE/BOE).
The server does not read Claude memory, chat history, or user files, and collects only
the request context needed to serve a tool call. See the privacy policy:
https://www.conversoriaecnae.es/politica-privacidad
