# ¿Qué es cojav.json? / What is cojav.json?

## Español

**cojav.json** es un archivo de Brand Context Protocol — un documento JSON estructurado que contiene todo lo que un agente de IA necesita para entender, recomendar y representar tu marca con precisión.

### El problema que resuelve

Cuando un usuario le pide a un agente de IA "recomendar café argentino para espresso", el agente no navega tu tienda online como lo haría un humano. Busca información estructurada: qué vendés, para quién, qué te diferencia, cuáles son tus certificaciones, cuáles son tus políticas. Si esa información no existe en un formato que el agente pueda procesar, tu marca es invisible.

### Cómo funciona

Un archivo `cojav.json` vive en una URL pública y se referencia desde el `<head>` de tu sitio web:

```html
<link rel="brand-context" type="application/json" href="https://rainvare.github.io/cojav/ctx/tu-marca.json">
```

El archivo contiene seis bloques:

- **identity** — Nombre, propósito, tono de voz, diferenciador, ubicación
- **audience** — Segmentos de audiencia con jobs-to-be-done
- **catalog** — Productos con atributos semánticos tipados (no solo nombre y precio, sino origen, perfil de sabor, intensidad, proceso, etc.)
- **policies** — Envío, devoluciones, métodos de pago, restricciones dietarias
- **trust** — Certificaciones, años en el mercado, ratings, señales de calidad
- **meta** — Versión del protocolo, fecha de actualización, contacto

### Cómo se diferencia de otros estándares

| Estándar | Propósito | Para quién |
|---|---|---|
| **llms.txt** | Índice de documentación técnica para LLMs | Devtools, SaaS, APIs |
| **cojav.json** | Contexto de marca completo para agentes de IA | Cualquier negocio |
| **UCP (Google/Shopify)** | Checkout y transacciones agénticas | Merchants de Shopify |
| **AMP (Azoma)** | Inteligencia de producto enterprise | Marcas globales (L'Oréal, Unilever) |

**llms.txt** le dice a la IA dónde buscar documentación. **cojav.json** le dice a la IA qué entender de tu marca.

### Caso de estudio: Café Cabrales

Auditamos a Café Cabrales, una de las marcas de café más reconocidas de Argentina con 84 años de historia y certificaciones Rainforest Alliance, ISO 9001, HACCP, Kosher y libre de TACC. Sin embargo, un agente de IA solo podía decir: "es una marca argentina de café con tienda online". Con un cojav.json, el agente puede recomendar productos específicos con perfil de sabor, certificaciones y políticas de envío.

→ [Ver auditoría completa](https://rainvare.github.io/cojav/audits/cabrales-2026-03)
→ [Ver ejemplo de cojav.json para Cabrales](https://rainvare.github.io/cojav/ctx/cabrales.json)

### Cómo obtener tu cojav.json

Cojav ofrece consultoría done-for-you: auditamos tu marca, estructuramos tu contexto, y lo implementamos. Contacto: indirarequiz@gmail.com

→ [Especificación del schema v1](https://rainvare.github.io/cojav/schema/v1.json)
→ [Sitio web de Cojav](https://rainvare.github.io/cojav/)

---

## English

**cojav.json** is a Brand Context Protocol file — a structured JSON document containing everything an AI agent needs to understand, recommend, and accurately represent a brand.

### The problem it solves

When a user asks an AI agent to "recommend Argentine coffee for espresso," the agent doesn't browse your online store like a human would. It looks for structured information: what you sell, who you serve, what differentiates you, your certifications, your policies. If that information doesn't exist in a machine-processable format, your brand is invisible.

### How it works

A `cojav.json` file lives at a public URL and is referenced from your site's `<head>`:

```html
<link rel="brand-context" type="application/json" href="https://rainvare.github.io/cojav/ctx/your-brand.json">
```

The file contains six blocks:

- **identity** — Name, purpose, tone, differentiator, location
- **audience** — Audience segments with jobs-to-be-done
- **catalog** — Products with typed semantic attributes (not just name and price, but origin, flavor profile, intensity, process, etc.)
- **policies** — Shipping, returns, payment methods, dietary info
- **trust** — Certifications, years in business, ratings, quality signals
- **meta** — Protocol version, last update date, contact

### How it differs from other standards

| Standard | Purpose | Target |
|---|---|---|
| **llms.txt** | Technical documentation index for LLMs | Devtools, SaaS, APIs |
| **cojav.json** | Complete brand context for AI agents | Any business |
| **UCP (Google/Shopify)** | Agentic checkout & transactions | Shopify merchants |
| **AMP (Azoma)** | Enterprise product intelligence | Global brands (L'Oréal, Unilever) |

**llms.txt** tells AI where to find documentation. **cojav.json** tells AI what to understand about your brand.

### Case study: Café Cabrales

We audited Café Cabrales, one of Argentina's most recognized coffee brands with 84 years of history and Rainforest Alliance, ISO 9001, HACCP, Kosher, and gluten-free certifications. Yet an AI agent could only say: "it's an Argentine coffee brand with an online store." With a cojav.json, the agent can recommend specific products with flavor profiles, certifications, and shipping policies.

→ [Full audit](https://rainvare.github.io/cojav/audits/cabrales-2026-03)
→ [Example cojav.json for Cabrales](https://rainvare.github.io/cojav/ctx/cabrales.json)

### How to get your cojav.json

Cojav offers done-for-you consulting: we audit your brand, structure your context, and implement it. Contact: indirarequiz@gmail.com

→ [Schema v1 specification](https://rainvare.github.io/cojav/schema/v1.json)
→ [Cojav website](https://rainvare.github.io/cojav/)
