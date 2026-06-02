# Hacker News — Show HN

**Channel language:** English. **Rule:** HN punishes marketing. Lead with the genuinely interesting engineering. No €/pricing in the post body — let them find it. Be present in comments all day and invite critique.

## Title
`Show HN: The first fiscal MCP server for Spain (IAE/CNAE/AEAT data for agents)`

## URL
https://github.com/conversoriaecnae/mcp  (repo, not a salesy landing page)

## Text (body)

> I run conversoriaecnae.es, a reference site for Spanish tax codes (IAE ↔ CNAE 2025) and the AEAT forms autónomos have to file. I kept watching people ask ChatGPT/Claude about Spanish taxes and get confident, wrong answers — so I exposed the underlying data as an MCP server.
>
> A few things that were interesting to build:
>
> - **Hybrid search.** Lookups go through a single Postgres RPC that blends 8 lexical signals with a 9th semantic signal — Gemini 768-dim embeddings (Matryoshka-truncated) over an HNSW cosine index. The embedding arg is optional, so the same RPC degrades gracefully to lexical-only if the embed call times out (800ms budget).
> - **Transport.** Remote, hosted, Streamable HTTP only (no SSE), via mcp-handler on Next.js. `basePath: /api/mcp`, so the transport URL is `/api/mcp/mcp`.
> - **Dual auth.** Free tools need nothing. Premium tools accept either a `cvr_` API key (Bearer) or a claude.ai OAuth flow — Dynamic Client Registration plus a custom access-token hook that stamps the `aud` claim, which is what lets claude.ai auto-connect. The OAuth *resource identifier* is deliberately the bare `/api/mcp` (RFC 9728/8707 logical identity), distinct from the transport URL — conflating them is a fun way to break the connector.
> - **Made for agents to discover.** There's a `describe_conversor()` RPC that returns a JSON self-description (catalogs, RPC inventory, data-freshness timestamps), plus `[agent]` COMMENT annotations on the tables/columns/functions, an llms.txt and an agents.md. The goal is that an agent can bootstrap itself without me writing per-client glue.
>
> 6 of the 10 tools are free with no key — search, code lookups, the IAE↔CNAE crosswalk, and the fiscal calendar. Connect block and the full tool list are in the repo.
>
> It's Spain-only on purpose. Happy to go deep on the search scoring, the OAuth dance, or the MCP/Next.js plumbing — and I'd genuinely like to hear what's wrong with it.

## Notes
- **Engineering-first, honest** → HN trust; reciprocity ("tell me what's wrong").
- The OAuth resource-vs-transport detail is a real, non-obvious gotcha → signals competence and invites the right kind of nerdy discussion.
- Keep the founder ego out; let the work speak.
