# Cómo hacer tu marca visible para agentes de IA / How to Make Your Brand Visible to AI Agents

## Español

Los agentes de IA son los nuevos compradores. ChatGPT, Claude, Perplexity y Gemini recomiendan productos, comparan marcas y toman decisiones de compra en nombre de los usuarios. Pero no pueden leer tu web como los humanos — necesitan información estructurada.

### Por qué tu marca es invisible

Cuando alguien le pregunta a un agente "recomendar zapatillas para terreno húmedo, menos de $100", el agente no scrollea tus páginas de producto. Sintetiza información de lo que encuentra: Reddit, reviews desactualizados, descripciones de competidores. Tu voz de marca, tus diferenciales, tu catálogo real se pierden.

El problema no es la calidad de tu producto — es la legibilidad de tu contexto para máquinas. En la economía agéntica, la marca que mejor se describe gana la recomendación, no necesariamente la mejor marca.

### Qué necesitan los agentes de IA para recomendarte

Un agente que recibe la pregunta "necesito café para espresso, comercio justo" necesita saber:

1. Qué vendés exactamente (no solo "café" sino "blend arábigo mild, intensidad media, notas de caramelo")
2. Para quién es (segmentos de audiencia con jobs-to-be-done)
3. Qué te diferencia de la competencia
4. Tus certificaciones y señales de confianza
5. Tus políticas de envío, pago y devoluciones
6. Tu tono de voz (para representarte con precisión)

### La solución: cojav.json

Un solo archivo estructurado que contiene todo tu contexto de marca. Se implementa con una línea de código en el `<head>` de tu sitio:

```html
<link rel="brand-context" type="application/json" href="https://tu-hosting/ctx/tu-marca.json">
```

Funciona en cualquier plataforma: Shopify, WordPress, Tiendanube, WooCommerce, o sitio custom.

### Pasos para hacerlo

1. **Auditar** — Preguntale a ChatGPT, Claude y Perplexity sobre tu marca. Documentá qué dicen y qué no dicen. Ese es tu punto de partida.
2. **Estructurar** — Creá tu cojav.json con identity, audience, catalog (con atributos semánticos), policies y trust.
3. **Implementar** — Agregá el tag link en tu HTML y hosteá el archivo.
4. **Testear** — Volvé a preguntar a los agentes. La diferencia antes/después es tu métrica de éxito.

### Ejemplo real: Café Cabrales

Café Cabrales tiene 84 años de historia, cinco certificaciones internacionales, y productos de origen único. Pero un agente de IA solo podía decir: "es una marca argentina de café con tienda online." Los disclaimers legales de compatibilidad con Nespresso representaban más del 50% del texto en sus páginas de producto — un agente veía más texto legal que información sobre el café.

→ [Ver auditoría completa de Cabrales](https://rainvare.github.io/cojav/audits/cabrales-2026-03)

### Consultoría Cojav

Si preferís que lo hagamos nosotros: auditamos tu marca, estructuramos tu contexto, lo implementamos y lo mantenemos actualizado.

**Contacto:** indirarequiz@gmail.com
**Web:** [rainvare.github.io/cojav](https://rainvare.github.io/cojav/)

---

## English

AI agents are the new shoppers. ChatGPT, Claude, Perplexity, and Gemini recommend products, compare brands, and make purchase decisions on behalf of users. But they can't read your website like humans — they need structured information.

### Why your brand is invisible

When someone asks an agent "recommend running shoes for wet terrain, under $100," the agent doesn't scroll your product pages. It synthesizes information from whatever it finds: Reddit, outdated reviews, competitor descriptions. Your brand voice, your differentiators, your actual catalog get lost.

The problem isn't your product quality — it's your context legibility for machines. In the agent economy, the brand that describes itself best wins the recommendation, not necessarily the best brand.

### What AI agents need to recommend you

An agent receiving the query "I need espresso coffee, fair trade" needs to know:

1. What you sell exactly (not just "coffee" but "mild arabica blend, medium intensity, caramel notes")
2. Who it's for (audience segments with jobs-to-be-done)
3. What differentiates you from competitors
4. Your certifications and trust signals
5. Your shipping, payment, and return policies
6. Your brand voice (to represent you accurately)

### The solution: cojav.json

A single structured file containing your complete brand context. Implemented with one line of code in your site's `<head>`:

```html
<link rel="brand-context" type="application/json" href="https://your-hosting/ctx/your-brand.json">
```

Works on any platform: Shopify, WordPress, Tiendanube, WooCommerce, or custom site.

### Steps to do it

1. **Audit** — Ask ChatGPT, Claude, and Perplexity about your brand. Document what they say and what they miss. That's your starting point.
2. **Structure** — Create your cojav.json with identity, audience, catalog (with semantic attributes), policies, and trust.
3. **Implement** — Add the link tag to your HTML and host the file.
4. **Test** — Ask the agents again. The before/after difference is your success metric.

### Real example: Café Cabrales

Café Cabrales has 84 years of history, five international certifications, and single-origin products. But an AI agent could only say: "it's an Argentine coffee brand with an online store." Nespresso compatibility disclaimers made up over 50% of text on product pages — an agent saw more legal text than coffee information.

→ [See full Cabrales audit](https://rainvare.github.io/cojav/audits/cabrales-2026-03)

### Cojav consulting

If you'd rather we handle it: we audit your brand, structure your context, implement it, and keep it updated.

**Contact:** indirarequiz@gmail.com
**Web:** [rainvare.github.io/cojav](https://rainvare.github.io/cojav/)
