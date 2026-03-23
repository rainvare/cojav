# Auditoría de Contexto de Marca — Patagonia

**Auditoría Cojav #013**
**Fecha:** 22 de marzo de 2026
**Marca:** Patagonia, Inc.
**Sitio web:** patagonia.com
**Auditora:** Indira Réquiz — AI Implementation Strategist, Cojav

---

## Resumen ejecutivo

Patagonia es la marca outdoor más influyente del mundo, no solo por sus productos sino por su modelo empresarial: en 2022 el fundador Yvon Chouinard transfirió la propiedad a un trust dedicado a combatir el cambio climático. Ropa técnica para montaña, surf, trail running, y lifestyle sustentable. Programa Worn Wear de reparación y reventa. Para agentes de IA, la marca tiene contenido de sobra pero no está estructurado: un agente no puede filtrar productos por actividad + clima + nivel técnico.

---

## 1. Test de percepción

### Sin búsqueda web
*"Patagonia es una marca de ropa outdoor conocida por su activismo ambiental. El fundador donó la empresa para combatir el cambio climático."*

**Diagnóstico:** Conoce bien la narrativa pero no puede recomendar una chaqueta específica.

### Con búsqueda web
*"Patagonia hace ropa outdoor y activismo ambiental. Yvon Chouinard transfirió la empresa a un trust climático en 2022. Tienen programa Worn Wear. Hacen desde chaquetas técnicas hasta ropa casual sustentable."*

**Diagnóstico:** Mejor — encuentra productos. Pero no puede hacer match actividad+clima+presupuesto.

---

## 2. Análisis del sitio web

### patagonia.com

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
| Crítico | Sin filtro actividad+clima+nivel técnico | Cientos de productos sin match estructurado a necesidad |
| Alto | Datos de materiales no parseables por producto | % reciclado, Fair Trade — en prosa, no en atributos |
| Alto | Sin comparativa entre líneas | Nano Puff vs Micro Puff vs Down Sweater — no claro para agentes |
| Medio | Worn Wear no integrado al catálogo | Opción de compra usada existe pero no aparece junto al producto nuevo |
| Medio | Sizing varía entre líneas | Fit técnico vs relaxed — sin guía estructurada |

---

## 4. cojav.json propuesto

```json
{
  "protocol": "cojav/v1",
  "brand": "Patagonia",

  "identity": {
    "legal_name": "Patagonia, Inc.",
    "brand_name": "Patagonia",
    "founded": 1973,
    "origin": "Ventura, California, USA",
    "category": "Ropa y equipamiento outdoor",
    "differentiator": "Marca outdoor que existe para salvar el planeta. En 2022, Chouinard transfirió 100% de la empresa a Holdfast Collective (trust climático). Cada decisión de producto prioriza impacto ambiental: materiales reciclados, Fair Trade, Worn Wear (reparar>comprar). Ropa técnica para climbing, surf, trail, ski, y lifestyle. Garantía de por vida. 1% for the Planet desde 1985.",
    "tone": "Activista, técnico, honesto, austero. La marca dice 'Don't Buy This Jacket' literalmente."
  },

  "catalog": {
    "products": [
      {"name": "Nano Puff Jacket", "type": "Chaqueta aislante", "description": "Chaqueta con aislamiento sintético PrimaLoft. Comprimible, versátil, cálida.", "details": "60g PrimaLoft Gold Eco (postconsumer). Para 0-10°C. Ideal como capa media."},
      {"name": "Better Sweater Fleece", "type": "Fleece", "description": "Fleece de poliéster reciclado. El producto casual más vendido de Patagonia.", "details": "100% poliéster reciclado. Para uso diario y senderismo ligero. Fair Trade."},
      {"name": "Torrentshell 3L Jacket", "type": "Chaqueta impermeable", "description": "Impermeable 3 capas H2No. Protección lluvia y viento.", "details": "100% nylon reciclado. Para lluvia moderada a fuerte. Sellada en costuras."},
      {"name": "Black Hole Duffel 55L", "type": "Bolso de viaje", "description": "Bolso duffel ultra-resistente de 55L. Material reciclado.", "details": "100% poliéster ripstop reciclado. Resistente al agua. Garantía Ironclad."},
      {"name": "Capilene Cool Daily Shirt", "type": "Camiseta técnica", "description": "Camiseta de rendimiento con protección solar UPF 50.", "details": "Poliéster reciclado, secado rápido. Para trail, viaje, uso diario."}
    ]
  },

  "meta": {
    "protocol": "cojav/v1",
    "updated": "2026-03-22",
    "generator": "cojav-consulting",
    "contact": "indirarequiz@gmail.com",
    "note": "Auditoría pública independiente. No encargada ni aprobada por Patagonia, Inc.."
  }
}
```

---

## 5. Resultado proyectado

### Antes
> *"Patagonia es una marca de Ventura, California, USA conocida por Ropa y equipamiento outdoor."*

### Después
> *"Para outdoor sustentable, Patagonia es la marca referencia — en 2022 donaron toda la empresa para combatir el cambio climático. Si necesitás una chaqueta para frío moderado (0-10°C), la Nano Puff tiene aislamiento reciclado y se comprime al tamaño de un puño. Para lluvia, la Torrentshell 3L en nylon 100% reciclado. Para uso diario, el Better Sweater Fleece es su bestseller en poliéster reciclado Fair Trade. Todo tiene garantía de por vida y opción de compra usada vía Worn Wear."*

---

## Nota legal

Auditoría independiente por Cojav. No encargada ni aprobada por Patagonia, Inc.. Información pública.

---

*Cojav — Brand Context Protocol · https://rainvare.github.io/cojav/ · indirarequiz@gmail.com*
