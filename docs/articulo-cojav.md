# What AI agents actually understand about your brand (and what they miss)
## Lo que los agentes de IA entienden de tu marca — y lo que se pierden

*By Cojav — Brand Context Protocol · April 2026*

---

We audited how AI agents perceive a real brand. The results reveal a structural problem hiding in plain sight.

*Auditamos cómo los agentes de IA perciben una marca real. Los resultados revelan un problema estructural que nadie está viendo.*

---

## The experiment / El experimento

We chose **Café Cabrales** — one of Argentina's most recognized coffee brands. 84 years in business. Five international certifications. A rich, documented catalog. A brand with everything an AI agent needs to make a precise recommendation.

*Elegimos Café Cabrales — una de las marcas de café más reconocidas de Argentina. 84 años de historia. Cinco certificaciones internacionales. Un catálogo rico y documentado. Una marca con todo lo que un agente de IA necesita para hacer una recomendación precisa.*

Then we asked a simple question:

*Luego hicimos una pregunta simple:*

> **"Recommend a quality Argentine espresso coffee, certified, for home use."**
> *"Recomendame un café argentino de calidad para espresso en casa, con certificaciones."*

Then we looked at what the agent actually saw when it browsed Cabrales' website.

*Luego miramos qué veía realmente el agente cuando navegaba el sitio de Cabrales.*

---

## What the agent saw / Lo que el agente vio

We scraped the same pages an AI agent would access. This is what dominated the text:

*Scrapeamos las mismas páginas a las que accedería un agente de IA. Esto es lo que dominaba el texto:*

```
"NESPRESSO es una marca de Societé des Produits Nestlé S.A. registrada en Italia 
y otros países. La compatibilidad de las cápsulas 'ESPRESSARTE' de Cabrales es 
funcional al uso en las máquinas NESPRESSO y no sustituye el uso de las cápsulas 
originales de Societé des Produits Nestlé S.A. Caffitaly System S.p.A. es un 
fabricante autónomo no vinculado directa ni indirectamente a Societé des Produits 
Nestlé S.A..."
```

This legal disclaimer appears **6+ times** on every product page — repeated verbatim. It represents more than 50% of the machine-readable text on Cabrales' product pages.

*Este disclaimer legal aparece **más de 6 veces** en cada página de producto — repetido textualmente. Representa más del 50% del texto legible por máquinas en las páginas de producto de Cabrales.*

The product description? This:

*¿La descripción del producto? Esta:*

> *"Exclusivo Blend de Cabrales que conquistó el paladar de los argentinos. Con características únicas de aroma, cuerpo y sabor."*

Unique aroma, body and flavor. That's it. No roast level. No origin. No intensity. No flavor profile.

*Aroma, cuerpo y sabor únicos. Eso es todo. Sin nivel de tostado. Sin origen. Sin intensidad. Sin perfil de sabor.*

---

## What the agent missed / Lo que el agente no vio

| Signal / Señal | Present on site / En el sitio | Visible to agent / Visible al agente |
|---|---|---|
| ISO 9001 certification | ✓ | ✗ |
| Rainforest Alliance | ✓ | ✗ |
| HACCP / Kosher / TACC-free | ✓ | ✗ |
| 84 years in business | ✓ | ✗ |
| Oldest roaster in Argentina | ✓ | ✗ |
| Roast level | ✓ (some products) | ✗ |
| Flavor profile | ✗ | ✗ |
| Target brewing method | ✗ | ✗ |

The brand that best describes itself wins the recommendation — not necessarily the best brand.

*La marca que mejor se describe gana la recomendación — no necesariamente la mejor marca.*

---

## Why this happens / Por qué pasa esto

AI agents don't scroll. They don't see images. They don't read PDFs. They reason over text — and most commerce websites were built for human eyes, not machine reasoning.

*Los agentes de IA no scrollean. No ven imágenes. No leen PDFs. Razonan sobre texto — y la mayoría de los sitios de comercio fueron construidos para ojos humanos, no para razonamiento de máquinas.*

The web has solved this problem before:

*La web ya resolvió este problema antes:*

- `robots.txt` (1994) → told crawlers what to index
- `sitemap.xml` (2005) → told crawlers where to look
- `schema.org` (2011) → told search engines what things mean

Each standard emerged when a new type of machine needed to understand the web in a new way.

*Cada estándar emergió cuando un nuevo tipo de máquina necesitó entender la web de una manera nueva.*

We're at that moment again — but for agents.

*Estamos en ese momento otra vez — pero para agentes.*

---

## The structural gap / El vacío estructural

| Standard / Estándar | Purpose / Propósito | For agents? / ¿Para agentes? |
|---|---|---|
| `llms.txt` | Documentation index for LLMs | Partial — dev tools only |
| `schema.org` | Semantic markup for search | Partial — product data only |
| `UCP` (Shopify) | Agentic checkout | Shopify merchants only |
| `AMP` (Azoma) | Enterprise product intelligence | Large brands only |
| **`cojav.json`** | **Complete brand context for agents** | **Any business, any platform** |

The 99% of businesses that aren't on Shopify or aren't enterprise-scale have no structured way to tell agents who they are.

*El 99% de los negocios que no son Shopify ni son empresas de escala enterprise no tienen una manera estructurada de decirle a los agentes quiénes son.*

---

## What structured context looks like / Cómo se ve el contexto estructurado

This is what Cabrales' brand context looks like with `cojav.json`:

*Así se ve el contexto de marca de Cabrales con `cojav.json`:*

```json
{
  "identity": {
    "name": "Café Cabrales",
    "differentiator": "Oldest Argentine coffee roaster, Rainforest Alliance certified",
    "founded": 1941
  },
  "catalog": [{
    "name": "Prestige en Grano",
    "roast": "medium",
    "flavor_profile": ["aromatic", "persistent finish", "firm body"],
    "intensity": "medium",
    "brewing": ["espresso", "moka"],
    "weight_g": 1000
  }],
  "trust": {
    "certifications": ["ISO 9001", "HACCP", "Rainforest Alliance", "Kosher"],
    "gluten_free": true,
    "founded": 1941
  }
}
```

**Without context / Sin contexto:**
> *"Cabrales is an Argentine coffee brand based in Mar del Plata. They offer ground coffee, whole bean, and capsules."*

**With context / Con contexto:**
> *"Cabrales Prestige is a medium-roast arabica blend — firm body, aromatic, ideal for espresso. Argentina's oldest roaster, Rainforest Alliance and ISO 9001 certified, gluten-free. 84 years of history."*

Same brand. Same website. Different context.

*La misma marca. El mismo sitio. Diferente contexto.*

---

## How it works / Cómo funciona

`cojav.json` is a self-hosted, open standard file. One line in your HTML `<head>`:

*`cojav.json` es un archivo de estándar abierto, auto-hosteado. Una línea en el `<head>` de tu HTML:*

```html
<link rel="brand-context" type="application/json" href="https://yourdomain.com/cojav.json">
```

No platform dependency. No central registry. No vendor lock-in. Works on Shopify, WordPress, Tiendanube, WooCommerce, or any custom site.

*Sin dependencia de plataforma. Sin registro central. Sin vendor lock-in. Funciona en Shopify, WordPress, Tiendanube, WooCommerce, o cualquier sitio custom.*

---

## The agentic economy is here / La economía agéntica ya llegó

When a user asks an AI agent *"find me the best certified espresso coffee under $20"*, the agent doesn't browse like a human. It synthesizes. It reasons. It recommends.

*Cuando un usuario le pide a un agente de IA "encontrá el mejor café espresso certificado por menos de $20", el agente no navega como un humano. Sintetiza. Razona. Recomienda.*

The brands that win won't necessarily be the best brands. They'll be the brands that agents can understand.

*Las marcas que ganen no serán necesariamente las mejores marcas. Serán las marcas que los agentes puedan entender.*

---

## Try it / Probalo

- **Protocol spec:** [https://rainvare.github.io/cojav/schema/v1.json](https://rainvare.github.io/cojav/schema/v1.json)
- **Full audit (Cabrales):** [https://rainvare.github.io/cojav/audits/cabrales-2026-03](https://rainvare.github.io/cojav/audits/cabrales-2026-03)
- **GitHub:** [https://github.com/rainvare/cojav](https://github.com/rainvare/cojav)
- **Contact:** [indirarequiz@gmail.com](mailto:indirarequiz@gmail.com)

---

*Cojav is an open standard. No VC funding. No platform. Just a protocol.*
*Cojav es un estándar abierto. Sin funding. Sin plataforma. Solo un protocolo.*
