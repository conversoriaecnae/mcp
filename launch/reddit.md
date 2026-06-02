# Reddit

**Rule:** Follow each subreddit's self-promo rules; lead with utility, not pitch. Reply to every comment. Post the English ones on launch day; post r/Autonomos in the Spanish push (Week 3).

---

## r/mcp — the on-topic home (English)

**Title:** I built a remote MCP server for Spanish tax data — 6 tools free, no key. Feedback welcome.

**Body:**

> Quick share for the MCP crowd: I built a hosted, remote (Streamable HTTP) MCP server that gives an agent live Spanish fiscal data — IAE and CNAE 2025 codes, the IAE↔CNAE crosswalk, AEAT form calendars, módulos and the RETA quota.
>
> 6 of the 10 tools are free, no key, no signup. Add the endpoint and ask:
> ```json
> { "type": "streamable-http", "url": "https://www.conversoriaecnae.es/api/mcp/mcp" }
> ```
> Dual auth (cvr_ key or claude.ai OAuth) for the 4 premium tools. There's a `describe_conversor` tool so the agent can introspect catalogs + data freshness.
>
> Repo (server.json + 10-tool table + examples): https://github.com/conversoriaecnae/mcp
>
> It's niche on purpose — first fiscal MCP for one country. Curious what the folks here think of the free-tier-as-acquisition approach, and whether the OAuth auto-connect setup matches how you'd expect a remote server to behave.

---

## r/ClaudeAI (English)

**Title:** Add this connector to Claude and ask it about Spanish taxes (free, no key)

**Body:**

> If you ever need Spanish tax info, you can now connect Claude directly to official data instead of hoping it doesn't hallucinate. I built an MCP server exposing IAE/CNAE 2025 codes + AEAT obligations.
>
> Add `https://www.conversoriaecnae.es/api/mcp/mcp` as a custom connector (or drop the streamable-http block in Claude Desktop's config) and try: *"¿Qué obligaciones fiscales tengo con el epígrafe IAE 501.3?"*
>
> [demo GIF]
>
> 6 tools free, no key. Details: https://github.com/conversoriaecnae/mcp — happy to answer setup questions.

---

## r/Anthropic (English)

**Title:** A real-world MCP connector: official Spanish tax data for agents

**Body:**

> Sharing a connector I built on MCP + Streamable HTTP that's now live as a claude.ai custom connector. It answers from official AEAT/INE data (Spanish tax codes, obligations, RETA) rather than the model's guesses.
>
> What I found neat building on the platform: claude.ai's OAuth auto-connect via DCR + an `aud`-stamping access-token hook just works once the PRM resource identifier is set up right. 6 free tools, no key.
>
> [demo GIF] · https://github.com/conversoriaecnae/mcp

---

## r/Autonomos (Spanish — Week 3 conversion push)

**Title:** He hecho que la IA pueda decirte tu código IAE/CNAE y qué modelos te tocan (gratis, sin registro)

**Body:**

> Hola 👋 Llevo tiempo con conversoriaecnae.es (la herramienta gratis para convertir IAE ↔ CNAE 2025). Acabo de conectar todos esos datos a la IA mediante MCP, así que ahora puedes preguntarle a Claude/ChatGPT/Cursor directamente y responde con datos oficiales de AEAT e INE, no inventados.
>
> Lo gratis (sin clave ni registro): buscar tu código por descripción, ficha del IAE/CNAE, correspondencia del CNAE 2009 antiguo al 2025, y el calendario de modelos. Solo añades el endpoint en tu cliente y preguntas, p. ej.: *"Soy fontanero autónomo, ¿qué epígrafe IAE y CNAE 2025 me corresponden?"*
>
> Cómo conectarlo: https://www.conversoriaecnae.es/mcp
>
> Lo cuento por si os ahorra el lío de siempre. Cualquier duda os respondo por aquí. (No vendo nada para usar lo gratis; las herramientas avanzadas para gestorías son de pago, pero eso es aparte.)
