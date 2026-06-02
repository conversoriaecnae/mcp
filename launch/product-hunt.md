# Product Hunt

**Channel language:** English (global MCP ecosystem).
**Best day/time:** Tue–Thu, 00:01 PT (early US morning). Concentrate the whole launch on this one day so PH + Show HN + r/mcp signals stack.

## Name
Conversor IAE-CNAE — MCP for Spanish tax data

## Tagline (≤40 chars)
`Live Spanish tax data (IAE/CNAE) for AI agents`
<!-- 46 chars; PH allows 60. Shorter alt (39): "Spanish tax data (IAE/CNAE) for AI agents" -->

## Topics
Artificial Intelligence · Developer Tools · API · SaaS · Open Source

## Gallery / assets
1. OG image (1200×630) — "El primer servidor MCP fiscal de España" + connect JSON on dark `#121212`.
2. 30–45s demo video/GIF — Claude Desktop answering "¿Qué obligaciones fiscales tengo con el epígrafe IAE 501.3?" → tool call → answer with AEAT modelos.
3. Tool-catalog screenshot (the 10-tool grid from /mcp).

## First comment (maker)

> Hi Product Hunt 👋
>
> I'm Brian, an indie maker from Spain. I run conversoriaecnae.es — a free tool that converts Spanish tax codes (IAE ↔ CNAE 2025) and explains which AEAT forms an autónomo has to file.
>
> Here's the problem I kept seeing: freelancers and accountants in Spain burn hours mapping codes and guessing obligations — and when they ask a general AI, it confidently invents tax facts that are just wrong. Wrong tax data isn't a typo; it's a fine.
>
> So I built **the first fiscal MCP server for Spain.** Connect any AI agent — Claude, ChatGPT in dev mode, Cursor, Gemini CLI — and it answers from official AEAT/INE/BOE data instead of hallucinating. No scrapers, no tables to maintain.
>
> **6 of the 10 tools are free — no key, no signup.** Just add the endpoint:
> ```json
> { "type": "streamable-http", "url": "https://www.conversoriaecnae.es/api/mcp/mcp" }
> ```
> Try one of these:
> - "¿A qué CNAE 2025 corresponde el IAE 501.3?"
> - "What tax forms apply to IAE code 501.3?"
> - "I'm a freelance developer in Spain — which IAE and CNAE codes apply to me?"
>
> It's Spain-only, by design — I'd rather be the best at one country's fiscal data than mediocre everywhere. The 4 premium tools (obligations, módulos, bulk lookup, RETA quota) are for gestorías and fintech in production, from €29/mo.
>
> Repo + docs: https://github.com/conversoriaecnae/mcp · Connect page: https://www.conversoriaecnae.es/mcp
>
> I'll be here all day — would genuinely love feedback from anyone building with MCP, and from any Spanish autónomos in the room. What would make this a no-brainer for you?

## Notes (psychology baked in)
- **Founder story + "why"** → liking/unity; opens with the real pain, not features.
- **"the first… for Spain"** → category creation + novelty (headlines everything).
- **"6 free, no key, no signup"** → zero-price effect + kills activation energy (acquisition wedge).
- **"It's Spain-only, by design"** → pratfall effect (admitting a limit builds trust).
- **3 try-this prompts** → reduce activation energy; vivid outcome (availability heuristic).
- Line up ~10–15 friends/network to upvote + comment in the first 2 hours (goal-gradient on ranking). Do NOT fake it — real comments only.
