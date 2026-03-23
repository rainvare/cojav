# Brand Context Protocol — Especificación / Specification

## Español

El Brand Context Protocol es un estándar abierto para hacer marcas legibles para agentes de IA. Define un formato de archivo JSON (`cojav.json`) que estructura el contexto completo de una marca en un documento que cualquier agente puede consumir.

### Motivación

En 2026, los agentes de IA median una proporción creciente de decisiones de compra. Google lanzó el Universal Commerce Protocol (UCP) para transacciones. Azoma lanzó el Agentic Merchant Protocol (AMP) para marcas enterprise. El estándar llms.txt sirve como índice de documentación técnica. Pero ninguno resuelve el problema del negocio mediano que necesita ser entendido por agentes sin infraestructura enterprise.

El Brand Context Protocol llena ese espacio: contexto de marca completo, en un solo archivo, implementable en cualquier plataforma con una línea de HTML.

### Principios de diseño

1. **Simplicidad** — Un archivo JSON, un tag HTML. Sin SDK, sin API, sin integración compleja.
2. **Universalidad** — Funciona en Shopify, WordPress, Tiendanube, WooCommerce, landing pages, sitios custom.
3. **Semántica** — Los atributos de producto son tipados y descriptivos, no solo nombre/precio.
4. **Completitud** — Cubre identity, audience, catalog, policies, trust y metadata.
5. **Apertura** — Schema público, documentación libre, implementación sin costo de licencia.

### Estructura del archivo

```json
{
  "$schema": "https://rainvare.github.io/cojav/schema/v1",
  "identity": { },
  "audience": [ ],
  "catalog": [ ],
  "policies": { },
  "trust": { },
  "meta": { }
}
```

### Secciones

**identity** (requerido): Nombre de la marca, propósito (qué hace y por qué existe), tono de voz, diferenciador clave, año de fundación, ubicación, URLs del sitio web y ecommerce.

**audience** (recomendado): Array de segmentos de audiencia. Cada segmento tiene un nombre y un job-to-be-done (JTBD) — lo que ese segmento intenta lograr. Esto permite que los agentes conecten queries de usuarios con los segmentos correctos.

**catalog** (recomendado): Array de productos o servicios con atributos semánticos. No solo nombre y precio, sino tipo, categoría, origen, perfil de sabor, intensidad, peso, URL, disponibilidad, y cualquier atributo relevante para la categoría. El schema es extensible (`additionalProperties: true`) para permitir atributos específicos de cada industria.

**policies** (recomendado): Políticas de negocio que un agente necesita para completar una recomendación — envío, devoluciones, métodos de pago, moneda, regiones de operación, información dietaria o regulatoria.

**trust** (recomendado): Señales de confianza — certificaciones, años en el mercado, rating promedio, cantidad de reviews, año de fundación. Estas señales le dan al agente confianza para recomendar la marca sobre alternativas.

**meta** (requerido): Versión del protocolo (`cojav/v1`), fecha de última actualización (ISO 8601), contacto, y opcionalmente el generador del archivo y notas.

### Implementación

Agregar al `<head>` del sitio:

```html
<link rel="brand-context" type="application/json" href="URL_DEL_ARCHIVO">
```

El archivo puede hostearse en cualquier servidor que sirva JSON con los headers CORS apropiados. GitHub Pages funciona perfectamente.

### Referencia del schema

La especificación formal del schema está disponible como JSON Schema (draft 2020-12):

→ [Schema v1](https://rainvare.github.io/cojav/schema/v1.json)

---

## English

The Brand Context Protocol is an open standard for making brands legible to AI agents. It defines a JSON file format (`cojav.json`) that structures complete brand context in a single document any agent can consume.

### Motivation

In 2026, AI agents mediate a growing share of purchase decisions. Google launched the Universal Commerce Protocol (UCP) for transactions. Azoma launched the Agentic Merchant Protocol (AMP) for enterprise brands. The llms.txt standard serves as a technical documentation index. But none solve the problem of the mid-market business that needs AI legibility without enterprise infrastructure.

The Brand Context Protocol fills that gap: complete brand context, single file, implementable on any platform with one line of HTML.

### Design principles

1. **Simplicity** — One JSON file, one HTML tag. No SDK, no API, no complex integration.
2. **Universality** — Works on Shopify, WordPress, Tiendanube, WooCommerce, landing pages, custom sites.
3. **Semantics** — Product attributes are typed and descriptive, not just name/price.
4. **Completeness** — Covers identity, audience, catalog, policies, trust, and metadata.
5. **Openness** — Public schema, free documentation, no licensing cost.

### File structure

```json
{
  "$schema": "https://rainvare.github.io/cojav/schema/v1",
  "identity": { },
  "audience": [ ],
  "catalog": [ ],
  "policies": { },
  "trust": { },
  "meta": { }
}
```

### Sections

**identity** (required): Brand name, purpose, tone, differentiator, founding year, location, website and ecommerce URLs.

**audience** (recommended): Array of audience segments with jobs-to-be-done (JTBD), enabling agents to match user queries to the right segments.

**catalog** (recommended): Array of products/services with semantic attributes — type, category, origin, flavor profile, intensity, weight, URL, availability, plus any industry-specific attributes. The schema is extensible (`additionalProperties: true`).

**policies** (recommended): Business policies an agent needs to complete a recommendation — shipping, returns, payment methods, currency, operating regions, dietary/regulatory info.

**trust** (recommended): Trust signals — certifications, years in business, average rating, review count. These give agents confidence to recommend over alternatives.

**meta** (required): Protocol version (`cojav/v1`), last update date (ISO 8601), contact, optionally the generator and notes.

### Implementation

Add to your site's `<head>`:

```html
<link rel="brand-context" type="application/json" href="FILE_URL">
```

The file can be hosted on any server serving JSON with appropriate CORS headers. GitHub Pages works perfectly.

### Schema reference

The formal schema specification is available as JSON Schema (draft 2020-12):

→ [Schema v1](https://rainvare.github.io/cojav/schema/v1.json)
