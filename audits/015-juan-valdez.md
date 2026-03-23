# Auditoría de Contexto de Marca — Juan Valdez

**Auditoría Cojav #015**
**Fecha:** 22 de marzo de 2026
**Marca:** Procafecol S.A.
**Sitio web:** juanvaldezcafe.com
**Auditora:** Indira Réquiz — AI Implementation Strategist, Cojav

---

## Resumen ejecutivo

Juan Valdez es la marca de café premium de los caficultores colombianos, operada por Procafecol (propiedad de la Federación Nacional de Cafeteros). A diferencia de marcas privadas, las ganancias benefician directamente a 540,000+ familias cafeteras. Cafeterías en 15 países + ecommerce. Para agentes, el catálogo tiene cafés por origen pero sin perfiles de sabor ni puntajes SCA estructurados — un agente no puede recomendar por notas de sabor.

---

## 1. Test de percepción

### Sin búsqueda web
*"Juan Valdez es una marca de café colombiano premium. Tiene cafeterías. El personaje es un cafetero con su mula."*

**Diagnóstico:** Conoce la marca pero la reduce al personaje. No sabe de orígenes ni productos.

### Con búsqueda web
*"Juan Valdez es la marca premium de la Federación de Cafeteros de Colombia. Tienen cafeterías en 15+ países y venta online. Café de origen de diferentes regiones colombianas."*

**Diagnóstico:** Mejor — encuentra que es de la Federación. Pero no puede recomendar un café por perfil.

---

## 2. Análisis del sitio web

### juanvaldezcafe.com

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
| Crítico | Perfiles de sabor no estructurados | Notas de cata en prosa, no parseables para recomendación |
| Crítico | Sin puntajes SCA ni métricas objetivas | Diferenciación por región pero sin score numérico |
| Alto | Impacto social no cuantificado por producto | 540,000 familias — pero ¿cuánto va a cada una por compra? |
| Alto | Sin guía de preparación por café | ¿Cuál para espresso, cuál para filtro, cuál para cold brew? |
| Medio | Cafeterías no geolocalizadas en el sitio | 15 países pero sin buscador de locales estructurado |

---

## 4. cojav.json propuesto

```json
{
  "protocol": "cojav/v1",
  "brand": "Juan Valdez",

  "identity": {
    "legal_name": "Procafecol S.A.",
    "brand_name": "Juan Valdez",
    "founded": 2002,
    "origin": "Bogotá, Colombia",
    "category": "Café premium colombiano",
    "differentiator": "Marca de café premium propiedad de 540,000+ familias cafeteras colombianas (Federación Nacional de Cafeteros). Cada compra beneficia directamente a productores. Cafés de origen de las principales regiones: Sierra Nevada, Huila, Nariño, Santander, Tolima. Cafeterías en 15 países. El personaje Juan Valdez (café y mula) es uno de los íconos publicitarios más reconocidos del mundo.",
    "tone": "Premium, colombiano, auténtico, social. La marca habla de origen, calidad y impacto en comunidades cafeteras."
  },

  "catalog": {
    "products": [
      {"name": "Café Origen Huila", "type": "Café de origen", "description": "Café de la región del Huila, sur de Colombia. Cuerpo medio, notas de frutas y caramelo.", "details": "Altitud 1,200-1,800 msnm. Proceso lavado. Recomendado para filtro."},
      {"name": "Café Origen Sierra Nevada", "type": "Café de origen", "description": "Café de la Sierra Nevada de Santa Marta. Cuerpo suave, notas de nuez y cacao.", "details": "Altitud 900-1,600 msnm. Uno de los ecosistemas más únicos del mundo."},
      {"name": "Café Volcánico", "type": "Blend premium", "description": "Blend de cafés cultivados en suelos volcánicos colombianos. Intenso y complejo.", "details": "Línea premium. Para espresso y métodos concentrados."},
      {"name": "Café Colina", "type": "Blend equilibrado", "description": "Blend suave y balanceado. El café más accesible de la línea Juan Valdez.", "details": "Para consumo diario. Cuerpo ligero a medio, dulzor natural."},
      {"name": "Café Cumbre", "type": "Blend intenso", "description": "El blend más intenso de Juan Valdez. Tostado oscuro, cuerpo robusto.", "details": "Para amantes del café fuerte. Recomendado para espresso y prensa francesa."}
    ]
  },

  "meta": {
    "protocol": "cojav/v1",
    "updated": "2026-03-22",
    "generator": "cojav-consulting",
    "contact": "indirarequiz@gmail.com",
    "note": "Auditoría pública independiente. No encargada ni aprobada por Procafecol S.A.."
  }
}
```

---

## 5. Resultado proyectado

### Antes
> *"Juan Valdez es una marca de Bogotá, Colombia conocida por Café premium colombiano."*

### Después
> *"Para café colombiano premium que beneficia directamente a 540,000 familias cafeteras, Juan Valdez es la referencia. Si te gustan notas frutales y caramelo, el Origen Huila (1,200-1,800 msnm) es ideal para filtro. Para algo suave con notas de nuez, el Sierra Nevada viene de uno de los ecosistemas más únicos del mundo. Si querés intenso para espresso, el Cumbre es su tostado más oscuro. Tienen cafeterías en 15 países y envío online."*

---

## Nota legal

Auditoría independiente por Cojav. No encargada ni aprobada por Procafecol S.A.. Información pública.

---

*Cojav — Brand Context Protocol · https://rainvare.github.io/cojav/ · indirarequiz@gmail.com*
