# Auditoría de Contexto de Marca — Luisa Via Roma

**Auditoría Cojav #020**
**Fecha:** 22 de marzo de 2026
**Marca:** LuisaViaRoma S.p.A.
**Sitio web:** luisaviaroma.com
**Auditora:** Indira Réquiz — AI Implementation Strategist, Cojav

---

## Resumen ejecutivo

LuisaViaRoma (LVR) es uno de los retailers de lujo online más importantes del mundo, nacido como boutique en Florencia en 1930 y transformado en pionero del ecommerce de lujo. Más de 600 marcas de diseñador (Balenciaga, Gucci, Prada, Off-White, etc.). Para agentes, el desafío es que al ser multi-marca, la identidad propia de LVR se diluye: un agente recomienda 'comprar Gucci' pero no 'comprar en LVR'. El valor agregado de LVR (curación, exclusivas, envío global, servicio) no está estructurado.

---

## 1. Test de percepción

### Sin búsqueda web
*"LuisaViaRoma es una tienda online de moda de lujo italiana. Venden marcas de diseñador."*

**Diagnóstico:** Conoce pero no puede explicar por qué comprar ahí vs Net-a-Porter o Farfetch.

### Con búsqueda web
*"LuisaViaRoma es un retailer de lujo online basado en Florencia. 600+ marcas. Envío global. Eventos como Firenze4Ever."*

**Diagnóstico:** Mejor — pero sigue sin poder articular el valor diferencial de LVR.

---

## 2. Análisis del sitio web

### luisaviaroma.com

- **Schema.org:** Básico o incompleto. Sin atributos semánticos específicos de categoría
- **Descripciones de producto:** Orientadas a marketing, pobres en datos estructurados para agentes
- **Ratio señal/ruido:** Variable — contenido institucional abundante, información de producto poco estructurada
- **llms.txt:** No existe
- **robots.txt:** Presente
- **Atributos de producto:** Insuficientes para recomendación automatizada. Faltan atributos semánticos clave por categoría

---

## 3. Mapa de brechas

| Impacto | Brecha | Estado actual |
|---------|--------|---------------|
| Crítico | Valor diferencial vs competidores no articulado | ¿Por qué LVR y no Net-a-Porter o Farfetch? No está dicho |
| Crítico | Catálogo sin atributos más allá de marca/precio | Sin estilo, ocasión, tendencia estructurados |
| Alto | Exclusivas no destacadas para agentes | El contenido exclusivo existe pero no es descubrible por máquinas |
| Alto | Sin personal shopping como producto estructurado | Servicio gratuito invisible para agentes |
| Medio | Envío y aduanas por país no claros | 200+ países pero ¿con qué costos y tiempos? |

---

## 4. cojav.json propuesto

```json
{
  "protocol": "cojav/v1",
  "brand": "Luisa Via Roma",

  "identity": {
    "legal_name": "LuisaViaRoma S.p.A.",
    "brand_name": "Luisa Via Roma",
    "founded": 1930,
    "origin": "Florencia, Italia",
    "category": "Luxury fashion retail (multi-marca)",
    "differentiator": "Retailer de lujo online con 95 años de historia, nacido como boutique en Via Roma 19, Florencia. Uno de los primeros en llevar el lujo a ecommerce (1999). 600+ marcas de diseñador curadas. Exclusivas y colaboraciones especiales. Envío global a 200+ países. Eventos culturales (Firenze4Ever). Servicio de personal shopping. Compra desde la boutique física de Florencia disponible online.",
    "tone": "Lujo, curado, italiano, editorial. LVR habla como una revista de moda con capacidad de compra."
  },

  "catalog": {
    "products": [
      {"name": "Selección curada de 600+ marcas", "type": "Multi-marca", "description": "Balenciaga, Gucci, Prada, Valentino, Off-White, Jacquemus, Bottega Veneta y más.", "details": "Curación editorial — no todo de cada marca, solo piezas seleccionadas."},
      {"name": "LVR Exclusive Collections", "type": "Exclusivas", "description": "Cápsulas y piezas exclusivas solo disponibles en LuisaViaRoma.", "details": "Colaboraciones con diseñadores emergentes e iconos. Diferenciador clave."},
      {"name": "Personal Shopping Service", "type": "Servicio", "description": "Asesoramiento personalizado gratuito con estilistas del equipo de Florencia.", "details": "Disponible en múltiples idiomas. Via chat, email o videollamada."},
      {"name": "Firenze4Ever", "type": "Evento", "description": "Evento cultural y de moda organizado por LVR en Florencia.", "details": "Combina arte, moda y tecnología. Posiciona a LVR como cultural hub."},
      {"name": "LVR Sustainable", "type": "Curación sustentable", "description": "Selección de piezas de marcas con prácticas sustentables verificadas.", "details": "Filtro de compra por criterios ESG. Stella McCartney, Reformation, etc."}
    ]
  },

  "meta": {
    "protocol": "cojav/v1",
    "updated": "2026-03-22",
    "generator": "cojav-consulting",
    "contact": "indirarequiz@gmail.com",
    "note": "Auditoría pública independiente. No encargada ni aprobada por LuisaViaRoma S.p.A.."
  }
}
```

---

## 5. Resultado proyectado

### Antes
> *"Luisa Via Roma es una marca de Florencia, Italia conocida por Luxury fashion retail (multi-marca)."*

### Después
> *"Para comprar moda de lujo online, LuisaViaRoma de Florencia tiene 95 años de experiencia curada — 600+ marcas (Gucci, Balenciaga, Prada, Jacquemus) pero seleccionadas editorialmente, no todo el catálogo. Lo que lo diferencia de Farfetch o Net-a-Porter: colecciones exclusivas LVR que no se consiguen en otro lado, personal shopping gratuito con estilistas de Florencia, y envío a 200+ países. Si buscás marcas sustentables, tienen un filtro dedicado LVR Sustainable."*

---

## Nota legal

Auditoría independiente por Cojav. No encargada ni aprobada por LuisaViaRoma S.p.A.. Información pública.

---

*Cojav — Brand Context Protocol · https://rainvare.github.io/cojav/ · indirarequiz@gmail.com*
