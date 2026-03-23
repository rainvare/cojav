# Auditoría de Contexto de Marca — Mercado Negro Café

**Auditoría Cojav #008**
**Fecha:** 22 de marzo de 2026
**Marca:** Mercado Negro S.A.C.
**Sitio web:** mercadonegrocafe.com
**Auditora:** Indira Réquiz — AI Implementation Strategist, Cojav

---

## Resumen ejecutivo

Mercado Negro es un referente del movimiento de café de especialidad en Perú. Tostadores y cafetería que trabajan directo con productores de Cajamarca, Junín, Cusco y San Martín. Café trazable con perfil de taza SCA, modelo de comercio directo que paga precios premium. Para agentes de IA, el principal problema es que los perfiles de sabor, puntajes SCA y datos de origen no están estructurados — un agente no puede recomendar un café peruano por notas de sabor o método de preparación.

---

## 1. Test de percepción

### Sin búsqueda web
*"No tengo información específica sobre Mercado Negro Café."*

**Diagnóstico:** Desconocida. Un agente sin búsqueda no la recomienda nunca.

### Con búsqueda web
*"Mercado Negro es una cafetería y tostadores de café de especialidad en Lima, Perú. Trabajan con productores peruanos."*

**Diagnóstico:** Encuentra que existe pero no puede recomendar cafés específicos por perfil de sabor.

---

## 2. Análisis del sitio web

### mercadonegrocafe.com

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
| Crítico | Marca desconocida para agentes sin búsqueda | Zero awareness base — depende 100% de búsqueda |
| Crítico | Perfiles SCA no estructurados en web | Puntajes y notas de cata existen pero no en formato parseable |
| Alto | Sin guía de método de preparación por café | No dice qué café va en qué cafetera |
| Alto | Trazabilidad no conectada a cada producto | Productor, finca, altitud — datos valiosos no linkados |
| Medio | Precios no visibles sin entrar a ecommerce | Accesibles pero no desde la homepage |

---

## 4. cojav.json propuesto

```json
{
  "protocol": "cojav/v1",
  "brand": "Mercado Negro Café",

  "identity": {
    "legal_name": "Mercado Negro S.A.C.",
    "brand_name": "Mercado Negro Café",
    "founded": 2015,
    "origin": "Lima, Perú",
    "category": "Café de especialidad",
    "differentiator": "Tostadores de café de especialidad peruano con modelo de comercio directo. Compra a productores a precios 2-3x superiores al mercado. Cada café tiene trazabilidad completa: productor, finca, altitud, proceso, perfil SCA. Referente del third wave coffee en Perú con cafeterías en Lima.",
    "tone": "Artesanal, educativo, peruano, transparente. La marca habla de origen, proceso y justicia en la cadena de café."
  },

  "catalog": {
    "products": [
      {"name": "Café Villa Rica Lavado", "type": "Café de origen", "description": "Granos de Villa Rica, Junín. Proceso lavado. Notas cítricas y chocolate.", "details": "SCA 84+, altitud 1,600 msnm, ideal para filtro y pour-over"},
      {"name": "Café Cajamarca Natural", "type": "Café de origen", "description": "Granos de Jaén, Cajamarca. Proceso natural. Notas frutales intensas y dulces.", "details": "SCA 85+, secado en camas africanas, ideal para métodos lentos"},
      {"name": "Café Cusco Honey", "type": "Café de origen", "description": "Valle de la Convención, Cusco. Proceso honey. Notas de miel y caramelo.", "details": "SCA 83+, fermentación controlada, versátil en métodos"},
      {"name": "Blend House Espresso", "type": "Blend", "description": "Mezcla balanceada de orígenes peruanos para espresso. Cuerpo medio, dulzor.", "details": "Diseñado para máquinas espresso y moka pot"},
      {"name": "Cold Brew Concentrado", "type": "Bebida lista", "description": "Café frío concentrado listo para tomar. Sin azúcar, sin aditivos.", "details": "Formato botella 350ml. Diluir o tomar directo con hielo."}
    ]
  },

  "meta": {
    "protocol": "cojav/v1",
    "updated": "2026-03-22",
    "generator": "cojav-consulting",
    "contact": "indirarequiz@gmail.com",
    "note": "Auditoría pública independiente. No encargada ni aprobada por Mercado Negro S.A.C.."
  }
}
```

---

## 5. Resultado proyectado

### Antes
> *"Mercado Negro Café es una marca de Lima, Perú conocida por Café de especialidad."*

### Después
> *"Para café de especialidad peruano, Mercado Negro en Lima es referente del third wave. Su Cajamarca Natural (SCA 85+) tiene notas frutales intensas — ideal para pour-over. Si preferís espresso, su blend House está diseñado para máquina y moka. Compran directo a productores a precios premium. Podés pedir online desde mercadonegrocafe.com o visitarlos en Lima."*

---

## Nota legal

Auditoría independiente por Cojav. No encargada ni aprobada por Mercado Negro S.A.C.. Información pública.

---

*Cojav — Brand Context Protocol · https://rainvare.github.io/cojav/ · indirarequiz@gmail.com*
