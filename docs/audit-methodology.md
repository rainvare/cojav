# Metodología de auditoría Cojav / Cojav Audit Methodology

## Español

La auditoría de contexto de marca de Cojav evalúa cómo los agentes de IA perciben tu negocio hoy y genera un plan de acción para cerrar las brechas. Es el primer paso para hacerte agent-ready.

### Paso 1 — Test de percepción

Le preguntamos a múltiples agentes de IA (Claude, ChatGPT, Perplexity, Gemini) sobre tu marca y tus productos sin darles acceso a búsqueda web. Esto revela qué sabe el agente de su conocimiento base.

Luego repetimos con búsqueda web activada. Esto revela qué encuentra el agente cuando busca activamente.

**Preguntas tipo:**
- "Recomendar [tu categoría] de [tu país/región]"
- "¿Qué diferencia a [tu marca] de [competidor]?"
- "¿[Tu marca] tiene certificaciones de calidad?"
- "¿Cuáles son los productos de [tu marca]?"

**Lo que documentamos:** Qué dice el agente, qué omite, qué inventa, contra quién te posiciona.

### Paso 2 — Análisis del sitio web

Visitamos tu sitio web y tienda online como lo haría un crawler de IA: extrayendo texto, buscando datos estructurados, y evaluando la proporción señal/ruido.

**Lo que evaluamos:**
- Presencia de Schema.org (Product, Offer, Organization, AggregateRating)
- Calidad de las descripciones de producto (genéricas vs. semánticas)
- Proporción de contenido útil vs. disclaimers, boilerplate y navegación
- Existencia de llms.txt, robots.txt, sitemap.xml
- Conexión semántica entre sitio corporativo y tienda online (si son separados)
- Atributos de producto disponibles: ¿solo nombre/precio o también origen, perfil, proceso, certificaciones?

### Paso 3 — Mapa de brechas

Cruzamos lo que el agente necesita para recomendar vs. lo que tu sitio ofrece. Cada brecha se clasifica por impacto:

| Impacto | Tipo de información |
|---|---|
| Crítico | Diferenciador de marca, catálogo con atributos semánticos, conexión entre sitios |
| Alto | Certificaciones, tono de voz, segmentos de audiencia, ratings |
| Medio | Políticas de envío/devolución, historia, contacto |

### Paso 4 — Generación del cojav.json

Con los hallazgos, estructuramos el archivo cojav.json completo:

- Identity con diferenciador claro y tono definido
- Audience con segmentos y JTBD basados en el análisis
- Catalog con todos los productos y atributos semánticos disponibles
- Policies compiladas de toda la información encontrada
- Trust con todas las certificaciones y señales de confianza
- Meta con versión, fecha y contacto

### Paso 5 — Resultado proyectado

Mostramos el antes/después: la misma consulta al agente con y sin cojav.json. Este contraste es la pieza central del informe.

### Entregables

1. Informe de auditoría completo (markdown)
2. Archivo cojav.json listo para implementar
3. Instrucciones de implementación (un tag HTML)
4. Recomendaciones adicionales (Schema.org, robots.txt, contenido)

### Ejemplo real

→ [Auditoría pública de Café Cabrales](https://rainvare.github.io/cojav/audits/cabrales-2026-03)

### Solicitar auditoría

**Contacto:** indirarequiz@gmail.com
**Web:** [rainvare.github.io/cojav](https://rainvare.github.io/cojav/)

---

## English

Cojav's brand context audit evaluates how AI agents perceive your business today and generates an action plan to close the gaps. It's the first step to becoming agent-ready.

### Step 1 — Perception test

We ask multiple AI agents (Claude, ChatGPT, Perplexity, Gemini) about your brand and products without web search access. This reveals what the agent knows from its base knowledge.

Then we repeat with web search enabled. This reveals what the agent finds when actively searching.

**Sample questions:**
- "Recommend [your category] from [your country/region]"
- "What differentiates [your brand] from [competitor]?"
- "Does [your brand] have quality certifications?"
- "What are [your brand]'s products?"

**What we document:** What the agent says, what it omits, what it fabricates, who it positions you against.

### Step 2 — Website analysis

We visit your website and online store as an AI crawler would: extracting text, looking for structured data, and evaluating signal-to-noise ratio.

**What we evaluate:**
- Schema.org presence (Product, Offer, Organization, AggregateRating)
- Product description quality (generic vs. semantic)
- Useful content vs. disclaimers, boilerplate, and navigation ratio
- Existence of llms.txt, robots.txt, sitemap.xml
- Semantic connection between corporate site and online store (if separate)
- Available product attributes: name/price only, or also origin, profile, process, certifications?

### Step 3 — Gap map

We cross-reference what the agent needs to recommend vs. what your site provides. Each gap is classified by impact:

| Impact | Information type |
|---|---|
| Critical | Brand differentiator, semantic catalog, cross-site connection |
| High | Certifications, brand voice, audience segments, ratings |
| Medium | Shipping/return policies, history, contact |

### Step 4 — cojav.json generation

Using findings, we structure the complete cojav.json file with all six sections populated from audit data.

### Step 5 — Projected result

We show the before/after: the same agent query with and without cojav.json. This contrast is the report's centerpiece.

### Deliverables

1. Complete audit report (markdown)
2. cojav.json file ready to implement
3. Implementation instructions (one HTML tag)
4. Additional recommendations (Schema.org, robots.txt, content)

### Real example

→ [Café Cabrales public audit](https://rainvare.github.io/cojav/audits/cabrales-2026-03)

### Request an audit

**Contact:** indirarequiz@gmail.com
**Web:** [rainvare.github.io/cojav](https://rainvare.github.io/cojav/)
