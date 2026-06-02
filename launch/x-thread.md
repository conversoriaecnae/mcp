# X / Twitter — launch thread

**Channel language:** English (global). Post on launch day alongside PH/HN. Tag relevant MCP/Anthropic community accounts where it's natural, not spammy. Also drop in the MCP community Discord #showcase.

---

**1/ (hook + demo)**

> I built the first fiscal MCP server for Spain. 🇪🇸
>
> Connect any AI agent — Claude, ChatGPT, Cursor, Gemini — and it answers about Spanish tax codes (IAE/CNAE 2025) and AEAT obligations from official data. No scrapers. No hallucinated tax facts.
>
> 6 tools free, no key. 👇
>
> [demo GIF: Claude answering "¿Qué obligaciones tengo con el IAE 501.3?"]

**2/ (the problem)**

> Autónomos and accountants in Spain lose hours mapping IAE ↔ CNAE codes and guessing which modelos (036/130/303…) apply.
>
> Ask a general AI and it invents answers — confidently. A wrong tax code isn't a typo, it's a fine.

**3/ (what it is)**

> So I exposed the real data as MCP tools:
> • search codes semantically
> • IAE / CNAE 2025 records + crosswalk
> • fiscal calendar (AEAT forms + deadlines)
> • obligations, módulos, bulk lookup, RETA quota
>
> Sources: AEAT, INE, BOE. Every response carries a freshness signal.

**4/ (zero-friction connect)**

> 6 of 10 tools are free — no key, no signup. Just add the endpoint:
>
> { "type": "streamable-http",
>   "url": "https://www.conversoriaecnae.es/api/mcp/mcp" }
>
> Try: "I'm a freelance dev in Spain — which IAE & CNAE codes apply to me?"

**5/ (CTA)**

> Repo + docs + examples: https://github.com/conversoriaecnae/mcp
> Connect page: https://www.conversoriaecnae.es/mcp
>
> It's Spain-only by design. Building with MCP? I'd love your feedback. 🙏

---

## Notes
- Thread shape: hook → problem → solution → zero-friction proof → CTA (AIDA).
- Lead tweet must stand alone with the demo GIF (most people only see #1).
- "first… for Spain" + "6 free, no key" are the repeated hooks (mere exposure across the thread).
