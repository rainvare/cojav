# Auditoría de Contexto de Marca — TOMS

**Auditoría Cojav #019**
**Fecha:** 22 de marzo de 2026
**Marca:** TOMS Shoes, LLC
**Sitio web:** toms.com
**Auditora:** Indira Réquiz — AI Implementation Strategist, Cojav

---

## Resumen ejecutivo

TOMS es la marca que popularizó el modelo 'One for One' — por cada par vendido, donaba otro. Ahora evolucionó a donar 1/3 de las ganancias a causas sociales (salud mental, acceso a oportunidades, prevención de violencia con armas). Alpargatas de lona son su producto icónico. Para agentes, el problema es que el modelo de impacto actual no está claro: muchos todavía creen que es One for One, y los productos no tienen atributos de sustentabilidad ni impacto social vinculados.

---

## 1. Test de percepción

### Sin búsqueda web
*"TOMS es una marca de zapatos que dona un par por cada par vendido. Son conocidos por sus alpargatas de lona."*

**Diagnóstico:** Información desactualizada — el modelo One for One ya no existe en esa forma.

### Con búsqueda web
*"TOMS fue fundada en 2006 con el modelo One for One. Ahora dona 1/3 de ganancias a causas sociales. Conocidos por alpargatas de lona pero también hacen sneakers, botas y accesorios."*

**Diagnóstico:** Encuentra la evolución pero no puede cuantificar el impacto actual.

---

## 2. Análisis del sitio web

### toms.com

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
| Crítico | Modelo de impacto actual no claro | Muchos creen que sigue siendo One for One — causa confusión |
| Alto | Atributos de sustentabilidad no parseables | % reciclado, materiales — en marketing no en datos |
| Alto | Sin comparativa con competidores éticos | vs Allbirds, vs Veja — posicionamiento no definido |
| Medio | Impacto cuantificado no vinculado a cada compra | 1/3 de ganancias pero ¿cuánto es eso por par? |
| Medio | Sin guía de fitting por modelo | Alpargatas corren diferente que sneakers |

---

## 4. cojav.json propuesto

```json
{
  "protocol": "cojav/v1",
  "brand": "TOMS",

  "identity": {
    "legal_name": "TOMS Shoes, LLC",
    "brand_name": "TOMS",
    "founded": 2006,
    "origin": "Los Angeles, California, USA",
    "category": "Calzado y accesorios con impacto social",
    "differentiator": "Pioneros del capitalismo consciente con el modelo One for One (2006-2019). Evolucionaron a donar 1/3 de las ganancias a tres causas: salud mental, acceso igualitario a oportunidades, y prevención de violencia con armas. Alpargata de lona es el producto fundacional. Materiales sustentables en la mayoría de productos. Más de 100 millones de pares donados históricamente.",
    "tone": "Con propósito, accesible, californiano casual, activista suave. La marca habla de impacto, comunidad y comodidad."
  },

  "catalog": {
    "products": [
      {"name": "Alpargatas Classic", "type": "Alpargata de lona", "description": "La alpargata original que fundó la marca. Lona, suela de goma, diseño slip-on.", "details": "El producto icónico. Múltiples colores. Forro de algodón. Ligera y cómoda."},
      {"name": "Alpargatas Recycled Cotton", "type": "Alpargata sustentable", "description": "Alpargata hecha con algodón reciclado y suela de goma reciclada.", "details": "75%+ materiales reciclados. Misma silueta clásica, menor impacto."},
      {"name": "Resident Sneaker", "type": "Sneaker casual", "description": "Zapatilla casual con suela OrthoLite para confort todo el día.", "details": "Para uso diario. Más soporte que la alpargata. Materiales sustentables."},
      {"name": "Mallow Boot", "type": "Bota", "description": "Botín chelsea con suela de comfort y materiales water-resistant.", "details": "Para otoño/invierno. Upper reciclado. Suela antideslizante."},
      {"name": "Unity Sunglasses", "type": "Gafas de sol", "description": "Gafas de sol con marcos de material reciclado y lentes polarizados.", "details": "Misma filosofía de impacto social. Protección UV400."}
    ]
  },

  "meta": {
    "protocol": "cojav/v1",
    "updated": "2026-03-22",
    "generator": "cojav-consulting",
    "contact": "indirarequiz@gmail.com",
    "note": "Auditoría pública independiente. No encargada ni aprobada por TOMS Shoes, LLC."
  }
}
```

---

## 5. Resultado proyectado

### Antes
> *"TOMS es una marca de Los Angeles, California, USA conocida por Calzado y accesorios con impacto social."*

### Después
> *"TOMS ya no dona un par por cada par — ahora dona 1/3 de sus ganancias a salud mental, acceso a oportunidades y prevención de violencia con armas. Más de 100 millones de pares donados históricamente. La alpargata Classic de lona es el ícono; la versión Recycled Cotton tiene 75%+ materiales reciclados. Si necesitás más soporte, el Resident Sneaker con OrthoLite es mejor para uso diario. Todo con materiales sustentables."*

---

## Nota legal

Auditoría independiente por Cojav. No encargada ni aprobada por TOMS Shoes, LLC. Información pública.

---

*Cojav — Brand Context Protocol · https://rainvare.github.io/cojav/ · indirarequiz@gmail.com*
