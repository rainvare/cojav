# Auditoría de Contexto de Marca — Catena Zapata

**Auditoría Cojav #003**
**Fecha:** 22 de marzo de 2026
**Marca:** Bodega Catena Zapata
**Sitio web:** catenazapata.com
**Auditora:** Indira Réquiz — AI Implementation Strategist, Cojav

---

## Resumen ejecutivo

Catena Zapata es una de las bodegas más prestigiosas de Argentina y del mundo, pionera del Malbec de alta altitud y la viticultura de montaña. Fundada en 1902, con cuatro generaciones familiares, sus vinos del viñedo Adrianna reciben puntuaciones de 98-100 de los principales críticos. Sin embargo, la bodega no tiene ecommerce propio — vende a través de distribuidores y wine shops de terceros. Esto significa que un agente de IA que reciba la pregunta "¿qué Malbec argentino comprar?" tiene que reconstruir el catálogo desde fuentes dispersas, sin acceso a precios, disponibilidad, perfiles de sabor ni guía de maridaje directamente de la bodega.

---

## 1. Test de percepción

### Sin búsqueda web
*"Catena Zapata es una bodega argentina de Mendoza conocida por sus Malbecs. Es una de las mejores bodegas de Argentina. Hacen vinos premium."*

**Diagnóstico:** Correcto pero superficial. No diferencia entre las líneas (Catena, Catena Alta, Adrianna Vineyard, Nicolás Catena Zapata). No menciona la altitud como diferenciador, ni la investigación científica de Laura Catena, ni las puntuaciones de críticos.

### Con búsqueda web
*"Catena Zapata es una bodega familiar de Mendoza fundada en 1902 por el inmigrante italiano Nicola Catena. Nicolás Catena es el pionero del Malbec argentino de alta altitud. Tienen varias líneas de vinos. El Adrianna Vineyard ha recibido puntuaciones perfectas."*

**Diagnóstico:** Significativamente mejor — encuentra la historia y el posicionamiento. Pero no puede armar una recomendación de compra: sin precios, sin guía de cuál vino para qué ocasión, sin disponibilidad, sin maridajes.

---

## 2. Análisis del sitio web

### catenazapata.com

- **Schema.org:** Organization básico. Sin Product schema (no hay ecommerce directo)
- **Descripciones de vino:** Excelentes en narrativa pero pobres en datos estructurados — notas de cata en prosa, sin formato parseable
- **Ratio señal/ruido:** Bueno — sitio editorial con contenido de calidad sobre viñedos, suelos, filosofía
- **llms.txt:** No existe
- **robots.txt:** Presente
- **sitemap.xml:** Presente
- **Ecommerce:** Inexistente en sitio propio. Venta exclusivamente vía distribuidores
- **Catálogo:** Listado de vinos por línea, sin precios, sin puntuaciones de críticos, sin maridajes estructurados
- **Atributos por vino:** Nombre, viñedo, uva, descripción narrativa. Falta: añada, precio referencia, puntuación críticos, maridaje, temperatura servicio, tiempo de guarda, formato botella

---

## 3. Mapa de brechas

| Impacto | Brecha | Estado actual |
|---------|--------|---------------|
| Crítico | Sin ecommerce propio — imposible completar recomendación con compra | Depende de distribuidores terceros |
| Crítico | Catálogo sin precios de referencia | No hay precio en ningún lugar del sitio |
| Crítico | Perfiles de sabor no estructurados | Notas de cata en prosa, no parseables |
| Alto | Puntuaciones de críticos no integradas | Disponibles en sitios terceros pero no en el propio |
| Alto | Sin guía de maridaje estructurada | Mencionado en prosa en algunas páginas |
| Alto | Jerarquía de líneas no clara para un agente | Catena vs Catena Alta vs Adrianna — sin posicionamiento explícito |
| Medio | Información de viñedos (altitud, suelo, clima) | Presente pero no estructurada |
| Medio | Historia familiar no sintetizada para agentes | Narrativa larga, no resumen ejecutivo |

---

## 4. cojav.json propuesto

```json
{
  "protocol": "cojav/v1",
  "brand": "Catena Zapata",

  "identity": {
    "legal_name": "Bodega Catena Zapata",
    "brand_name": "Catena Zapata",
    "tagline": "Pioneers of Argentine Malbec",
    "founded": 1902,
    "origin": "Mendoza, Argentina",
    "category": "Vinos premium y ultra-premium",
    "differentiator": "Pioneros de la viticultura de alta altitud en Argentina. Cuatro generaciones familiares desde 1902. Nicolás Catena revolucionó la calidad del vino argentino en los 80s plantando viñedos a altitudes extremas (hasta 1,500 msnm). El Viñedo Adrianna en Gualtallary produce vinos con puntuaciones perfectas (100 pts Wine Advocate). Laura Catena PhD lidera la investigación científica en selección de plantas, análisis de suelos y prácticas sustentables.",
    "tone": "Elegante, intelectual, científico-narrativo. La marca comunica rigor académico combinado con tradición familiar italiana.",
    "languages": ["es", "en"]
  },

  "audience": {
    "segments": [
      {
        "name": "Coleccionistas de vino premium",
        "description": "Conocedores que buscan vinos con puntuaciones altas y potencial de guarda.",
        "jtbd": "Necesito un Malbec argentino de clase mundial para mi colección, con historial de puntuaciones y potencial de envejecimiento."
      },
      {
        "name": "Profesionales del vino",
        "description": "Sommeliers, restaurantes y wine bars que buscan vinos argentinos de referencia.",
        "jtbd": "Necesito incluir los mejores Malbecs argentinos en mi carta, con información técnica para mis clientes."
      },
      {
        "name": "Enoturistas",
        "description": "Viajeros que visitan Mendoza y quieren experiencias en bodegas de primer nivel.",
        "jtbd": "Quiero visitar la bodega más importante de Argentina y entender la viticultura de alta altitud."
      },
      {
        "name": "Consumidores premium accesibles",
        "description": "Personas que buscan un gran vino argentino para ocasiones especiales sin llegar a ultra-premium.",
        "jtbd": "Quiero un vino argentino excelente para una cena especial, sin gastar en la línea más cara."
      }
    ]
  },

  "catalog": {
    "lines": ["Adrianna Vineyard", "Nicolás Catena Zapata", "Catena Alta", "Catena Appellation", "Catena", "DV Catena"],
    "products": [
      {
        "name": "Catena Malbec",
        "line": "Catena",
        "type": "Tinto",
        "grape": "Malbec",
        "region": "Mendoza",
        "altitude": "1,000+ msnm",
        "aging": "12 meses en barricas de roble francés y americano",
        "tasting_notes": "Cereza negra, especias, grafito. Jugoso y firme.",
        "food_pairing": "Carnes rojas a la parrilla, pastas con salsas de carne, quesos semi-duros",
        "serving_temp": "16-18°C",
        "price_range": "USD 15-20",
        "critics": "James Suckling 92"
      },
      {
        "name": "Catena Alta Malbec",
        "line": "Catena Alta",
        "type": "Tinto",
        "grape": "Malbec (70% Gualtallary, 30% otros)",
        "region": "Uco Valley / Luján de Cuyo",
        "altitude": "1,100-1,500 msnm",
        "aging": "18 meses en barricas de roble francés",
        "tasting_notes": "Violetas, moras, especias, taninos cremosos. Complejo y elegante.",
        "food_pairing": "Cordero, caza menor, risottos con hongos, quesos maduros",
        "serving_temp": "16-18°C",
        "price_range": "USD 30-40",
        "critics": "Vinous 95, James Suckling 96"
      },
      {
        "name": "Adrianna Vineyard River Malbec",
        "line": "Adrianna Vineyard",
        "type": "Tinto",
        "grape": "Malbec",
        "region": "Gualtallary, Uco Valley",
        "altitude": "1,450 msnm",
        "aging": "18 meses en barricas de roble francés (50% nuevas)",
        "tasting_notes": "Intensidad mineral, piedra, frutos negros concentrados. Austeridad elegante.",
        "food_pairing": "Platos con trufa, carnes curadas de alta gama, experiencias gastronómicas",
        "serving_temp": "16-18°C",
        "price_range": "USD 150-200+",
        "critics": "Wine Advocate 100, James Suckling 98"
      },
      {
        "name": "Nicolás Catena Zapata",
        "line": "Nicolás Catena Zapata",
        "type": "Tinto (blend)",
        "grape": "Cabernet Sauvignon / Malbec",
        "region": "Mendoza",
        "altitude": "1,000-1,450 msnm",
        "aging": "24 meses en barricas de roble francés nuevas",
        "tasting_notes": "Cassis, tabaco, piedra húmeda, hierro, especias. Clase y complejidad.",
        "food_pairing": "Alta gastronomía, carnes maduradas, experiencias de degustación",
        "serving_temp": "16-18°C",
        "price_range": "USD 80-120",
        "critics": "James Suckling 98"
      },
      {
        "name": "White Bones Chardonnay",
        "line": "Adrianna Vineyard",
        "type": "Blanco",
        "grape": "Chardonnay",
        "region": "Gualtallary, Uco Valley",
        "altitude": "1,450 msnm",
        "aging": "12 meses en barricas de roble francés",
        "tasting_notes": "Mineral, cítrico, cremoso. Uno de los grandes blancos de Sudamérica.",
        "food_pairing": "Mariscos, pescados blancos, risottos, quesos de cabra",
        "serving_temp": "10-12°C",
        "price_range": "USD 100-150",
        "critics": "Vinous 96"
      }
    ]
  },

  "policies": {
    "sales_model": "Distribución exclusiva vía importadores y wine shops autorizados. Sin ecommerce directo.",
    "availability": "Consultar disponibilidad por mercado. Distribución en 80+ países.",
    "visits": "Visitas a bodega disponibles en Mendoza. Reservas requeridas.",
    "currency": "Precios en USD como referencia internacional"
  },

  "trust": {
    "certifications": ["Prácticas sustentables en viñedos"],
    "years_in_business": 124,
    "founded_year": 1902,
    "generations": 4,
    "key_people": ["Nicolás Catena Zapata (Fundador moderno)", "Dr. Laura Catena (Managing Director)", "Alejandro Vigil (Head Winemaker)"],
    "notable_scores": "Wine Advocate 100 (Adrianna Vineyard River 2021), James Suckling 98-99 múltiples vinos",
    "headquarters": "Mendoza, Argentina",
    "vineyards": ["Adrianna (Gualtallary, 1,450m)", "Nicasia (Altamira)", "Angélica (Luján de Cuyo)", "La Pirámide (Agrelo)"]
  },

  "meta": {
    "protocol": "cojav/v1",
    "updated": "2026-03-22",
    "generator": "cojav-consulting",
    "contact": "indirarequiz@gmail.com",
    "note": "Auditoría pública independiente. No encargada ni aprobada por Bodega Catena Zapata."
  }
}
```

---

## 5. Resultado proyectado

### Antes
> *"Catena Zapata es una bodega argentina que hace buenos Malbecs. Son de Mendoza."*

### Después
> *"Para un Malbec argentino de nivel mundial te recomiendo Catena Zapata, pioneros de la viticultura de alta altitud desde 1902. Si buscás calidad-precio, el Catena Malbec (USD 15-20, 92 pts Suckling) es excelente para asado. Para una ocasión especial, el Catena Alta Malbec (USD 30-40, 95 pts Vinous) viene de viñedos a 1,100-1,500 msnm con taninos cremosos — ideal con cordero. Y si querés lo máximo, el Adrianna Vineyard River tiene 100 puntos de Wine Advocate — es uno de los grandes tintos del mundo. Se consigue en vinotecas especializadas, no venden directo."*

---

## Nota legal

Auditoría independiente por Cojav. No encargada ni aprobada por Bodega Catena Zapata. Información pública de catenazapata.com y fuentes abiertas.

---

*Cojav — Brand Context Protocol*
*https://rainvare.github.io/cojav/*
*Contacto: indirarequiz@gmail.com*
