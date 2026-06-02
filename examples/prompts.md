# Example prompts

Once the server is connected (see the [README](../README.md#connect-in-30-seconds)), try these. They are written to exercise the tools the way a real autónomo or gestoría would ask.

## Free (no key)

**1 — Convert and look up a code**

> _ES:_ "¿A qué código CNAE 2025 corresponde el epígrafe IAE 501.3? Dame también la ficha del IAE."
>
> _EN:_ "What CNAE 2025 code corresponds to Spanish IAE code 501.3? Also give me the IAE record."

Uses `buscar_codigo` / `detalle_iae`.

**2 — Find the code for an activity by description**

> _ES:_ "Soy desarrollador de software freelance. ¿Qué epígrafe IAE y qué código CNAE 2025 me corresponden?"
>
> _EN:_ "I'm a freelance software developer in Spain. Which IAE epígrafe and CNAE 2025 code apply to me?"

Uses `buscar_codigo`.

**3 — Fiscal calendar for a code**

> _ES:_ "¿Qué modelos de la AEAT y qué plazos próximos tengo con el epígrafe IAE 501.3?"
>
> _EN:_ "Which AEAT forms and upcoming deadlines apply to IAE code 501.3?"

Uses `calendario_fiscal`.

**4 — Migrate an old CNAE 2009 code**

> _ES:_ "Tengo el CNAE 2009 4711. ¿Cuál es su equivalente en CNAE 2025 y qué tengo que hacer para actualizarlo?"
>
> _EN:_ "I have CNAE 2009 code 4711. What is its CNAE 2025 equivalent and how do I update it?"

Uses `detalle_cnae_2009`.

## Premium (Profesional plan — `cvr_` key)

**5 — What must I actually file?**

> _ES:_ "¿Qué obligaciones fiscales tengo con el epígrafe IAE 501.3? Dame los modelos con su periodicidad y plazo."
>
> _EN:_ "What tax obligations do I have with IAE code 501.3? List the forms with frequency and deadline."

Uses `obligaciones_fiscales`.

**6 — Módulos régimen**

> _ES:_ "¿El epígrafe IAE 722 puede tributar en módulos? ¿Cuáles aplican?"
>
> _EN:_ "Can IAE code 722 use the módulos (estimación objetiva) régimen? Which ones apply?"

Uses `modulos_irpf_iva`.

**7 — Bulk lookup for a client portfolio (gestoría)**

> _ES:_ "Dame la ficha de estos 12 epígrafes IAE de mis clientes: 501.3, 504.1, 722, 833.1, …"
>
> _EN:_ "Give me the records for these 12 client IAE codes: 501.3, 504.1, 722, 833.1, …"

Uses `consulta_masiva`.

**8 — RETA quota**

> _ES:_ "Un autónomo con un rendimiento neto de 28.000 €/año, ¿en qué tramo del RETA 2026 está y cuál es su cuota mínima?"
>
> _EN:_ "An autónomo with €28,000/yr net income — which 2026 RETA bracket are they in and what is the minimum quota?"

Uses `cuota_reta`.
