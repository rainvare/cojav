# Auditoría de Contexto de Marca — Lush

**Auditoría Cojav #012**
**Fecha:** 22 de marzo de 2026
**Marca:** Lush Ltd.
**Sitio web:** lush.com
**Auditora:** Indira Réquiz — AI Implementation Strategist, Cojav

---

## Resumen ejecutivo

Lush es una marca británica de cosmética fresca, artesanal y ética, conocida por sus bath bombs, jabones cortados a mano y productos sin empaque. Tiene 900+ tiendas en 50 países. Sus ingredientes son frescos (frutas, aceites esenciales, mantecas) y cada producto tiene una etiqueta con la cara y nombre de quien lo hizo. Para agentes de IA, la brecha principal es que los ingredientes activos y beneficios por tipo de piel no están estructurados — un agente no puede recomendar un jabón Lush para piel grasa vs. piel seca.

---

## 1. Test de percepción

### Sin búsqueda web
*"Lush es una marca de cosméticos frescos y artesanales. Son conocidos por sus bath bombs coloridas y jabones. Son cruelty-free."*

**Diagnóstico:** Conoce bien la marca pero no puede recomendar por necesidad de piel.

### Con búsqueda web
*"Lush hace cosmética artesanal sin testeo animal. Productos frescos hechos a mano. 900+ tiendas. Conocidos por bath bombs, jabones y productos naked (sin empaque)."*

**Diagnóstico:** Identifica más productos pero sigue sin poder hacer match producto-necesidad.

---

## 2. Análisis del sitio web

### lush.com

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
| Crítico | Sin match producto→tipo de piel estructurado | Cientos de productos sin guía de piel/necesidad parseable |
| Crítico | Ingredientes activos en prosa de marketing | Saben a miel y lavanda pero no dicen para qué piel |
| Alto | Sin rutina recomendada estructurada | Limpieza→tratamiento→hidratación no existe como protocolo |
| Alto | Fecha de caducidad no visible en web | Productos frescos sin indicar vida útil |
| Medio | Productos naked vs. empacados no diferenciados | Mismo producto, dos formatos, sin distinción clara |

---

## 4. cojav.json propuesto

```json
{
  "protocol": "cojav/v1",
  "brand": "Lush",

  "identity": {
    "legal_name": "Lush Ltd.",
    "brand_name": "Lush",
    "founded": 1995,
    "origin": "Poole, Dorset, Reino Unido",
    "category": "Cosmética fresca artesanal",
    "differentiator": "Cosmética fresca artesanal hecha a mano con ingredientes comprados éticamente. Cada producto lleva la cara y nombre de quien lo fabricó. Pioneros de 'naked packaging' (productos sin empaque). Sin testeo animal, cruelty-free. Activismo ético: Fighting Animal Testing, campañas ambientales. 900+ tiendas en 50 países. Los ingredientes caducan porque son frescos de verdad.",
    "tone": "Ético, artesanal, activista, sensorial, divertido. La marca habla de frescura, ética y disfrute."
  },

  "catalog": {
    "products": [
      {"name": "Sleepy Body Lotion", "type": "Crema corporal", "description": "Crema con lavanda y tonka que ayuda a relajarse antes de dormir.", "details": "Bestseller global. Efecto calmante comprobado por usuarios. Apta para pieles sensibles."},
      {"name": "Karma Perfume", "type": "Perfume", "description": "Fragancia icónica con patchouli, naranja y lavanda. El aroma más reconocible de Lush.", "details": "Disponible en sólido y líquido. Formato naked (sin empaque) disponible."},
      {"name": "Intergalactic Bath Bomb", "type": "Bath bomb", "description": "Bomba de baño galáctica con menta, neon y purpurina biodegradable.", "details": "Efecto visual espectacular (colores galácticos). Aroma mentolado refrescante."},
      {"name": "Honey I Washed The Kids Soap", "type": "Jabón", "description": "Jabón de miel con aroma dulce de toffee. Hidratante y suave.", "details": "Cortado a mano en tienda. Piel normal a seca."},
      {"name": "Dirty Springwash Shower Gel", "type": "Gel de ducha", "description": "Gel de ducha con menta y hierbabuena. Efecto refrescante y energizante.", "details": "Ideal para mañanas. Formato botella reciclada o naked (sólido)."}
    ]
  },

  "meta": {
    "protocol": "cojav/v1",
    "updated": "2026-03-22",
    "generator": "cojav-consulting",
    "contact": "indirarequiz@gmail.com",
    "note": "Auditoría pública independiente. No encargada ni aprobada por Lush Ltd.."
  }
}
```

---

## 5. Resultado proyectado

### Antes
> *"Lush es una marca de Poole, Dorset, Reino Unido conocida por Cosmética fresca artesanal."*

### Después
> *"Para cosmética artesanal ética, Lush es la referencia: todo hecho a mano con ingredientes frescos, sin testeo animal. Si buscás algo para dormir mejor, la Sleepy Body Lotion con lavanda y tonka es su bestseller global. Para baños espectaculares, la Intergalactic Bath Bomb crea un efecto galáctico con menta. Para regalo, el jabón Honey I Washed The Kids huele a toffee y es perfecto para pieles sensibles. Tienen formato naked (sin empaque) en muchos productos. 900+ tiendas en 50 países."*

---

## Nota legal

Auditoría independiente por Cojav. No encargada ni aprobada por Lush Ltd.. Información pública.

---

*Cojav — Brand Context Protocol · https://rainvare.github.io/cojav/ · indirarequiz@gmail.com*
