# COJAV — Brand Context Protocol

**Hacé tu marca legible para agentes de IA.**

Los agentes de IA son los nuevos compradores. Recomiendan, comparan y deciden — pero no pueden leer tu web como los humanos. Cojav estructura el contexto de tu marca en un solo archivo `cojav.json` que cualquier agente entiende.

---

## ¿Qué es cojav.json?

`cojav.json` es un archivo estructurado que contiene todo lo que un agente de IA necesita para entender, recomendar y representar tu marca con precisión:

- **identity** — Nombre, propósito, tono de voz, diferenciador
- **audience** — Segmentos de audiencia con jobs-to-be-done
- **catalog** — Productos con atributos semánticos tipados
- **policies** — Envío, devoluciones, métodos de pago, regiones
- **trust** — Certificaciones, antigüedad, señales de calidad
- **meta** — Versión del protocolo, fecha de actualización, contacto

## ¿Cómo se implementa?

Un solo tag en el `<head>` de tu sitio:

```html
<link rel="brand-context" type="application/json" href="https://rainvare.github.io/cojav/ctx/tu-marca.json">
```

Funciona en cualquier plataforma: Shopify, WordPress, Tiendanube, WooCommerce, landing page, o sitio custom.

## ¿Dónde encaja cojav.json?

| Estándar | Propósito | Target | Complejidad |
|---|---|---|---|
| llms.txt | Índice de documentación para LLMs | Dev tools, SaaS | Baja |
| **cojav.json** | **Contexto de marca completo para agentes** | **Cualquier negocio** | **Baja (done-for-you)** |
| UCP (Google/Shopify) | Checkout y transacciones agénticas | Merchants Shopify | Media |
| AMP (Azoma) | Inteligencia de producto enterprise | Marcas globales | Alta |

`llms.txt` le dice a la IA dónde buscar. `cojav.json` le dice a la IA qué entender de tu marca.

---

## Estructura del repo

```
cojav/
├── index.html              # Landing page (ES/EN bilingüe)
├── README.md               # Este archivo
├── ctx/
│   ├── cojav.json          # Contexto de marca de Cojav (dogfooding)
│   └── cabrales.json       # Ejemplo: Café Cabrales (caso de estudio)
├── audits/
│   └── cabrales-2026-03.md # Auditoría pública de Café Cabrales
└── schema/
    └── v1.json             # Especificación del schema cojav/v1
```

## Caso de estudio: Café Cabrales

Realizamos una auditoría pública de Café Cabrales, una de las marcas de café más reconocidas de Argentina (84 años de historia), para demostrar el valor del Brand Context Protocol.

**Hallazgos clave:**

- Los disclaimers legales de compatibilidad Nespresso representan más del 50% del texto en páginas de producto
- Sin Schema.org en ninguna página de producto
- Cinco certificaciones internacionales (ISO 9001, HACCP, Rainforest Alliance, Kosher, libre de TACC) no estructuradas para agentes
- Sin conexión semántica entre el sitio corporativo y la tienda online

→ [Ver auditoría completa](audits/cabrales-2026-03.md)

---

## Servicio de consultoría

Cojav ofrece consultoría done-for-you para crear e implementar tu archivo de contexto de marca:

1. **Auditoría** — Analizamos cómo los agentes de IA perciben tu marca hoy
2. **Estructuración** — Creamos tu cojav.json con atributos semánticos completos
3. **Implementación** — Lo hosteamos, mantenemos y actualizamos

**Contacto:** [indirarequiz@gmail.com](mailto:indirarequiz@gmail.com)

---

## Sobre

Cojav fue creado por **Indira Réquiz** — Estratega de Implementación de IA, lingüista y data engineer basada en Buenos Aires.

El Brand Context Protocol nace de una observación simple: en la economía agéntica, la marca que mejor se describe gana la recomendación — no necesariamente la mejor marca.

---

*© 2026 Cojav — Brand Context Protocol*
