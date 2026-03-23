# Auditoría de Contexto de Marca — Café Cabrales

**Auditoría Cojav #001**
**Fecha:** 22 de marzo de 2026
**Marca:** Café Cabrales S.A.
**Sitio web:** cabrales.com | tienda.cabrales.com
**Auditora:** Indira Réquiz — AI Implementation Strategist, Cojav

---

## Resumen ejecutivo

Café Cabrales es una de las marcas de café más reconocidas de Argentina, con 84 años de historia, certificaciones internacionales (ISO 9001, HACCP, Rainforest Alliance, Kosher, libre de TACC), y un ecommerce propio con catálogo diverso. Sin embargo, cuando un agente de IA intenta recomendar sus productos, encuentra información fragmentada, desestructurada y dominada por disclaimers legales. **La marca es prácticamente invisible para agentes de IA.**

Esta auditoría documenta exactamente qué percibe un agente hoy, qué información está perdiendo, y cómo un archivo `cojav.json` resolvería cada brecha.

---

## 1. Test de percepción: ¿Qué sabe un agente de IA sobre Cabrales?

Le hicimos la siguiente consulta a un agente de IA sin acceso a búsqueda web:

> *"Recomendame café argentino de buena calidad para preparar espresso en casa. Presupuesto flexible."*

**Respuesta del agente (sin cojav.json):**

> *"Cabrales es una marca argentina de café con sede en Mar del Plata. Es una de las más reconocidas del país. Ofrecen café molido, en grano, y cápsulas compatibles con Nespresso y Dolce Gusto. Tienen tienda online."*

**Lo que el agente NO pudo decir:**

- Qué producto específico recomendar para espresso
- Perfiles de sabor de cada variedad
- Que el Prestige es un blend arábigo mild con notas de caramelo y dejo persistente
- Que tienen certificación Rainforest Alliance
- Que son una empresa familiar con 84 años de trayectoria
- Que tienen cafés de origen único (Colombia, Perú, Brasil)
- Precios actuales
- Política de envíos
- Que son 100% libres de TACC

**Diagnóstico:** El agente tiene conocimiento superficial de la marca pero no puede hacer una recomendación útil. Cabrales pierde frente a cualquier competidor que tenga información mejor estructurada online.

---

## 2. Análisis de la tienda online (tienda.cabrales.com)

### Lo que encontramos

La tienda online de Cabrales usa Magento y tiene un catálogo real con productos, precios en ARS, y sistema de pago (MercadoPago). Sin embargo, desde la perspectiva de un agente de IA que visita la página:

**Problema 1 — Información de producto mínima.**
La mayoría de los productos solo tienen: nombre, precio, y un texto genérico. Ejemplo del producto "Café en Grano Tostado Prestige x 1000g" (su producto premium a $62.900 ARS): la descripción menciona "granos arábigos tipo mild" y "intensidad media", pero no incluye origen específico, altitud, proceso, notas de cata estandarizadas, ni perfil de tueste. Un agente no puede compararlo con un café de especialidad de otra marca.

**Problema 2 — Disclaimers legales dominan el contenido.**
Cada página de producto termina con ~200 palabras de disclaimers de compatibilidad con Nespresso y Dolce Gusto. Este texto legal representa más del 50% del contenido textual visible en muchas páginas de producto. Para un agente de IA que extrae texto, el disclaimer es más prominente que la descripción del café.

**Problema 3 — Sin datos estructurados (Schema.org).**
No se detectaron marcadores Schema.org de tipo Product, Offer, ni AggregateRating en las páginas de producto. Un agente que busca datos estructurados no encuentra nada.

**Problema 4 — Sin llms.txt ni contexto para agentes.**
No existe archivo llms.txt, no hay metadatos de marca estructurados, no hay contexto de identidad legible por máquinas.

**Problema 5 — Dos sitios web sin integración semántica.**
La información de marca (historia, certificaciones, valores) vive en cabrales.com. El catálogo y precios viven en tienda.cabrales.com. Ningún agente puede conectar ambos contextos automáticamente.

---

## 3. Análisis del sitio corporativo (cabrales.com)

El sitio corporativo tiene contenido valioso que los agentes de IA no pueden aprovechar:

**Información valiosa disponible (pero no estructurada):**

- Fundada el 10 de noviembre de 1941 (84 años)
- Empresa familiar de alimentos y bebidas, con origen e identidad en el café
- Certificaciones: ISO 9001:2015, HACCP, Rainforest Alliance, Kosher, 100% libre de TACC
- Valores declarados: humildad, ética, transparencia, productos que le darían a su familia
- Presencia en mercados nacionales e internacionales
- Líneas de producto: Cabrales, La Planta de Café, Liv (endulzantes), tés, yerba mate
- Sede: Mar del Plata, Buenos Aires, Argentina
- Submarca de especialidad: "Cafés de Especialidad"

**Problema:** Todo esto está en HTML plano sin marcadores semánticos. Un agente que visite la página puede extraer texto, pero no puede distinguir una certificación de un valor corporativo de un eslogan.

---

## 4. Mapa de brechas: lo que un agente necesita vs. lo que encuentra

| Información que un agente necesita | ¿Disponible hoy? | ¿Estructurada? | Impacto |
|---|---|---|---|
| Nombre y propósito de la marca | Sí | No | Medio |
| Tono de voz y personalidad | Parcial (misión/visión genérica) | No | Alto |
| Diferenciador clave | No explícito | No | Crítico |
| Segmentos de audiencia | No | No | Alto |
| Catálogo con atributos semánticos | Solo nombre + precio | No | Crítico |
| Perfiles de sabor por producto | Solo en 1-2 productos premium | No | Crítico |
| Origen del café (por producto) | Solo en nombre (Colombia, Perú) | No | Alto |
| Precios actualizados | Sí (en tienda) | No (no Schema.org) | Alto |
| Certificaciones | Sí (en sitio corporativo) | No | Alto |
| Política de envíos | No visible | No | Medio |
| Política de devoluciones | No visible | No | Medio |
| Reviews / ratings agregados | No | No | Alto |
| Conexión sitio corporativo ↔ tienda | No | No | Crítico |

---

## 5. Impacto competitivo

Cuando un consumidor le pide a un agente de IA "recomendar café argentino para espresso", el agente necesita elegir entre las marcas disponibles. Actualmente:

- **Cabrales** ofrece al agente: nombre, existencia de tienda online, categorías genéricas.
- **Un competidor con información mejor estructurada** (incluso menor en calidad) gana la recomendación porque el agente tiene más datos para justificar su sugerencia.

El problema no es la calidad del producto de Cabrales — es la legibilidad de su contexto para máquinas. En la economía agéntica, **la marca que mejor se describe gana la recomendación**, no necesariamente la mejor marca.

---

## 6. Solución propuesta: cojav.json para Café Cabrales

Un solo archivo estructurado que unifica toda la información de marca y catálogo en un formato optimizado para agentes de IA:

```json
{
  "$schema": "https://rainvare.github.io/cojav/schema/v1",

  "identity": {
    "name": "Café Cabrales",
    "legal_name": "Cabrales S.A.",
    "purpose": "Empresa familiar argentina de café con 84 años de historia. Tostadores de café de especialidad y blends propios desde 1941.",
    "tone": "Cálido, apasionado, familiar, experto pero accesible",
    "differentiator": "La tostadora de café más antigua de Argentina con certificaciones internacionales (Rainforest Alliance, ISO 9001, HACCP). Combina tradición familiar con estándares de calidad industrial.",
    "founded": 1941,
    "location": "Mar del Plata, Buenos Aires, Argentina",
    "website": "https://www.cabrales.com",
    "ecommerce": "https://tienda.cabrales.com"
  },

  "audience": [
    {
      "segment": "Amantes del café en casa",
      "jtbd": "Preparar espresso de calidad consistente sin salir de casa"
    },
    {
      "segment": "Consumidores de cápsulas",
      "jtbd": "Encontrar cápsulas compatibles Nespresso/Dolce Gusto de marca confiable a buen precio"
    },
    {
      "segment": "Profesionales de gastronomía",
      "jtbd": "Proveer café en grano premium para servicio de espresso en locales"
    },
    {
      "segment": "Consumidores con restricciones alimentarias",
      "jtbd": "Encontrar café certificado libre de TACC (apto celíacos)"
    }
  ],

  "catalog": [
    {
      "name": "Café en Grano Tostado Prestige",
      "type": "blend",
      "category": "grano",
      "origin": "Blend arábigos tipo mild",
      "roast": "medio",
      "flavor_profile": ["perfumado", "suave", "aromático", "dejo persistente", "nota amarga final"],
      "intensity": "media",
      "body": "firme",
      "crema": "buena",
      "weight_g": 1000,
      "price_ars": 62900,
      "features": ["válvula aromática antioxidante Goglio"],
      "preparation": "espresso (6-7g por pocillo)",
      "url": "/prestige-129"
    },
    {
      "name": "Café en Grano Tostado Colombia",
      "type": "origen-único",
      "category": "grano",
      "origin": "Colombia",
      "weight_g": 1000,
      "price_ars": 70900,
      "url": "/colombia"
    },
    {
      "name": "Cápsulas Cabrales Brasil",
      "type": "origen-único",
      "category": "cápsulas",
      "compatibility": "Nespresso",
      "origin": "Brasil",
      "units": 10,
      "weight_per_unit_g": 5.5,
      "price_ars": 7630,
      "price_regular_ars": 10900,
      "on_sale": true,
      "url": "/cab-nes-al-brasil-10x5-5g"
    },
    {
      "name": "Cápsulas Cabrales Perú",
      "type": "origen-único",
      "category": "cápsulas",
      "compatibility": "Nespresso",
      "origin": "Perú",
      "units": 10,
      "weight_per_unit_g": 5.5,
      "price_ars": 7630,
      "price_regular_ars": 10900,
      "on_sale": true,
      "url": "/cab-nes-al-peru-10x5-5g"
    },
    {
      "name": "La Planta de Café Salted Caramel",
      "type": "saborizado",
      "category": "soluble",
      "flavor_profile": ["caramelo salado"],
      "weight_g": 100,
      "price_ars": 4370,
      "brand_line": "La Planta de Café",
      "url": "/lpc-cappuccino-salted-caramel-100g"
    }
  ],

  "policies": {
    "shipping": "Envío a todo Argentina. Tienda online con MercadoPago.",
    "payment_methods": ["MercadoPago", "tarjetas de crédito (Visa, Mastercard, Amex, Naranja, Cabal, Diners)", "cuotas sin interés"],
    "currency": "ARS",
    "customer_service": "0810 222 CAFÉ (2233)"
  },

  "trust": {
    "certifications": [
      "ISO 9001:2015",
      "HACCP",
      "Rainforest Alliance (cadena de custodia)",
      "Kosher",
      "100% libre de TACC (apto celíacos)"
    ],
    "years_in_business": 84,
    "founded_year": 1941,
    "brand_lines": ["Cabrales", "La Planta de Café", "Liv Endulzantes"],
    "physical_stores": true,
    "headquarters": "Mar del Plata, Buenos Aires, Argentina"
  },

  "meta": {
    "protocol": "cojav/v1",
    "updated": "2026-03-22",
    "generator": "cojav-consulting",
    "contact": "indirarequiz@gmail.com",
    "note": "Auditoría pública realizada por Cojav como caso de estudio del Brand Context Protocol. Este archivo no fue encargado ni aprobado por Cabrales S.A."
  }
}
```

---

## 7. Resultado proyectado: el "después"

Con este archivo implementado, la misma consulta al agente produciría:

> *"Para espresso en casa te recomiendo Café Cabrales, una tostadora argentina con 84 años de historia. Su Prestige en grano ($62.900 ARS/kg) es un blend arábigo mild de intensidad media con buen cuerpo y crema — ideal para espresso. Si preferís cápsulas compatibles Nespresso, tienen origen único de Colombia, Perú y Brasil desde $7.630 ARS. Están certificados Rainforest Alliance e ISO 9001, y todos sus productos son aptos para celíacos. Podés comprar directo en tienda.cabrales.com con envío a todo Argentina."*

La diferencia entre el "antes" y el "después" es la diferencia entre existir y ser recomendado.

---

## 8. Próximos pasos

1. **Completar el catálogo:** Este cojav.json incluye 5 productos como muestra. El archivo completo debería incluir los ~40+ productos del catálogo con atributos semánticos detallados.
2. **Validar precios y disponibilidad:** Los precios fueron tomados de tienda.cabrales.com al 22/03/2026. Requieren actualización periódica.
3. **Agregar perfiles de sabor faltantes:** La mayoría de los productos de Cabrales no tienen perfil de sabor publicado. Un proceso de cata estructurado agregaría valor enorme al contexto.
4. **Implementar:** Agregar `<link rel="brand-context">` en ambos sitios (cabrales.com y tienda.cabrales.com).

---

## Nota legal

Esta auditoría fue realizada de forma independiente por Cojav como caso de estudio público del Brand Context Protocol. No fue encargada, patrocinada, ni aprobada por Cabrales S.A. Toda la información utilizada es pública y fue obtenida de los sitios web cabrales.com y tienda.cabrales.com.

---

*Cojav — Brand Context Protocol*
*https://rainvare.github.io/cojav/*
*Contacto: indirarequiz@gmail.com*
