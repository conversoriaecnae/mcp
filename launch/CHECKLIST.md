# MCP GTM — external-action checklist

The artifacts and code are built. **Everything below needs YOU** (your accounts, credentials, manual submission/posting). Ordered by the playbook's phases.

Legend: ✅ done in this build · ⬜ your action.

---

## Already done in this build (for reference)
- ✅ In-app code (`feat/mcp-gtm-artifacts` branch, repo `conversor-iae-cnae-v3`):
  - `_source: "conversoriaecnae.es"` on the 6 free-tool JSON responses.
  - `?source=mcp_tool` appended to the premium-denial CTA URL (`lib/mcp/auth.ts`).
  - `server.json` namespace → `io.github.conversoriaecnae/conversor-iae-cnae`.
  - `public/llms.txt` → added repo + registry URLs.
  - `/mcp` page `openGraph`/`twitter` block (dynamic `/api/og?…&type=mcp` card).
  - Tests added/green (full suite passed). **✅ reviewed (no issues) & squash-merged to `main` as PR #58 (`afa1f99`).**
- ✅ This public repo (`conversor-mcp-public/`): README, server.json, manifest.json, examples, LICENSE, this `/launch` copy bank + OG SVG.
- ✅ `/api-precios` already has the "Más popular" highlight on Profesional (no change needed).

---

## Week 0 — Prep (your actions)
- ✅ **GitHub repo created & pushed** — [`github.com/conversoriaecnae/mcp`](https://github.com/conversoriaecnae/mcp) is live (PUBLIC); this `conversor-mcp-public/` folder is pushed to `main`. README + connect block verified rendering via GitHub's GFM API. Note: `conversoriaecnae` is a **User** account, not an org — fine for the registry (the `io.github.conversoriaecnae/*` namespace verifies via GitHub OAuth on whoever owns the repo).
- ✅ **`/mcp` page OG/twitter** — added an `openGraph`/`twitter` block to `app/mcp/page.tsx` pointing at the site's existing dynamic generator (`/api/og?title=…&type=mcp`), so shared `/mcp` links render a branded card. No PNG hosting needed for the page itself. **(merged to `main` via PR #58.)**
- ⬜ **Rasterize the OG image** (`launch/og-image.svg` → `og-image.png`) and host it — now only needed for the *external* surfaces that can't call `/api/og`: Product Hunt gallery, Twitter/X card upload, LinkedIn, the flywheel blog post.
- ⬜ **Record the 30–45s demo** (shot list in `og-and-demo.md`).
- ⬜ **Reviewer kit for the Claude Directory** (needed Week 1):
  - A throwaway **Profesional `cvr_` key** so reviewers can exercise the 4 premium tools.
  - Privacy URL ready: https://www.conversoriaecnae.es/politica-privacidad
  - Confirm nothing blocks Anthropic's IPs from the endpoint (Vercel = public no-op; just verify).
  - The 3 demo prompts + connector docs link (`/mcp` + this repo).

## Week 1 — Listings (your actions)
- ✅ **Official MCP Registry — PUBLISHED & LIVE.** `io.github.conversoriaecnae/conversor-iae-cnae` **v1.0.1** is `isLatest`/`active`. Verify: `curl "https://registry.modelcontextprotocol.io/v0.1/servers?search=io.github.conversoriaecnae/conversor-iae-cnae"`.
  - ⚠️ **Encoding gotcha (for future version bumps):** the Windows `mcp-publisher` binary double-encodes non-ASCII when publishing (v1.0.0 got mojibake'd: `España`→`EspaÃ±a`, `↔`→`â†"`). Keep `server.json` prose **ASCII-only**; that's why the registry description is English/ASCII while the README/site keep full accents. v1.0.0 is superseded (`isLatest:false`).
- ◐ **Claude Connectors Directory** — submission kit + form answers drafted in [`claude-directory-kit.md`](./claude-directory-kit.md). **Remaining (yours):** generate a throwaway Profesional `cvr_` key for reviewers, then submit the MCP Directory Server Review Form. Review takes ~2 weeks — submit this week. (`readOnlyHint` already present — #1 rejection cause pre-solved.)
- ◐ **Tier-2 community directories** (aim ≥4 live/pending) — all submission copy pre-written in [`tier2-directories.md`](./tier2-directories.md):
  - ✅ **Awesome MCP Servers** — PR opened: [punkpeye/awesome-mcp-servers#7266](https://github.com/punkpeye/awesome-mcp-servers/pull/7266) (Finance & Fintech, agent fast-track).
  - ⬜ PulseMCP · Smithery · Glama · mcp.so · Cursor Directory — paste from `tier2-directories.md` (each link carries `?source=<directory>`).
- ⬜ **Skip** (low fit, not a gap): Docker MCP Catalog, Cline marketplace, mcp-get, mcpmarket (they favor containerized/stdio npm packages).

## Week 2 — Launch day (one day, Tue–Thu, early US morning)
- ⬜ **Product Hunt** — copy in `product-hunt.md`. Post first, add maker comment, line up ~10–15 real early upvoters/commenters for first-2-hours momentum.
- ⬜ **Show HN** — `show-hn.md`. Be in comments all day.
- ⬜ **Reddit r/mcp / r/ClaudeAI / r/Anthropic** — `reddit.md`. Follow each sub's self-promo rules.
- ⬜ **X/Twitter thread + MCP Discord #showcase** — `x-thread.md`.
- ⬜ Use the demo asset on every surface.

## Week 3 — Spanish conversion push
- ⬜ **LinkedIn** posts 1 & 2 — `linkedin.md`; share into gestoría/asesoría/autónomo groups.
- ⬜ **r/Autonomos** + Spanish forums/Telegram — `reddit.md` (Spanish post).
- ⬜ **Press micro-pitch** to Genbeta / Xataka / El Output — `press-pitch.md`.

## Week 4+ — Flywheel
- ⬜ **Blog post** (Sanity, ES or bilingual): "Cómo conectar tu IA a los datos fiscales de España con MCP" — reuse demo + prompts; permanent link to drop in threads.
- ⬜ Keep `llms.txt` / `agents.md` / `describe_conversor()` fresh (repo + registry URLs already added to llms.txt).
- ⬜ Add "Listed on [registry/PulseMCP/Glama]" badges to README + `/mcp` as they go live (uncomment the badge stub in README).
- ⬜ Retarget/email `/mcp` visitors & free-key holders toward Profesional via Resend (loss-framed).
- ⬜ **Inverse check:** don't let the endpoint 404, don't post the marketing copy to HN, don't pitch premium before the free hook lands.

---

## Verification / definition of done
1. ◐ Endpoint green: ✅ `/mcp`, `/llms.txt`, `/agents.md`, `/.well-known/oauth-protected-resource`, `/api/og` all 200; ✅ MCP `initialize` handshake on `/api/mcp/mcp` returns protocol `2025-11-25` + `tools.listChanged`. Remaining: live Claude Desktop connect smoke-test.
2. ✅ Registry live: `server.json` validates and the listing resolves — v1.0.1 published, `isLatest`/`active`.
3. ◐ Repo public with README connect block + 10-tool table: ✅ done & connect block verified rendering via GitHub GFM API. Remaining: demo asset embed.
4. ✅ Response channel: premium denial returns the Spanish CTA with `?source=mcp_tool`; free-tool JSON carries `_source`. (Tests green.)
5. ⬜ Listings: registry published + Claude Directory form submitted (Week 1) + ≥4 Tier-2 directories live/pending before launch.
6. ⬜ Launch executed: PH + Show HN + r/mcp same day, all with the demo asset.
7. ⬜ Attribution working: `?source=` params (incl. `mcp_tool`) land in analytics; you can see which channel drives free-key grabs and Profesional signups.
8. ⬜ Conversion review: run the **buy-or-bounce** persona simulator against `/mcp` → `/api-precios?source=mcp` to pressure-test the free→paid funnel.
