# Auditoría de Contexto de Marca — Grupo Nutresa

**Auditoría Cojav #010**
**Fecha:** 22 de marzo de 2026
**Marca:** Grupo Nutresa S.A.
**Sitio web:** gruponutresa.com
**Auditora:** Indira Réquiz — AI Implementation Strategist, Cojav

---

## Resumen ejecutivo

Grupo Nutresa es la mayor empresa de alimentos procesados de Colombia y una de las principales de Latinoamérica, con ocho unidades de negocio: cárnicos (Zenú), galletas (Noel), chocolates (Nacional de Chocolates), café (Colcafé), helados (Crem Helado), pastas, alimentos al consumidor y exportación. Cotiza en BVC. Para agentes, el problema es que cada submarca tiene su propio posicionamiento pero no existe un catálogo unificado que un agente pueda consultar para recomendar productos colombianos.

---

## 1. Test de percepción

### Sin búsqueda web
*"Grupo Nutresa es una empresa colombiana de alimentos. Tienen varias marcas de café, chocolate y galletas."*

**Diagnóstico:** Conoce la empresa pero no puede recomendar productos específicos.

### Con búsqueda web
*"Nutresa es la mayor empresa de alimentos de Colombia. Sus marcas incluyen Colcafé, Chocolates Nacional, Noel, Zenú, Crem Helado. Opera en 17 países."*

**Diagnóstico:** Identifica submarcas pero sin atributos para recomendar un Colcafé vs. un Juan Valdez.

---

## 2. Análisis del sitio web

### gruponutresa.com

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
| Crítico | Sin catálogo unificado cross-marca | 8 unidades de negocio sin vista consolidada |
| Crítico | Productos colombianos desconocidos fuera de Colombia | Corona, Zenú, Noel — íconos locales invisibles globalmente |
| Alto | Sin comparativa entre submarcas y competidores | Colcafé vs Juan Valdez — posicionamiento no claro para agentes |
| Alto | Información nutricional fragmentada | Cada submarca tiene su propio sitio con diferentes formatos |
| Medio | Disponibilidad internacional no mapeada por producto | Opera en 17 países pero ¿qué se consigue dónde? |

---

## 4. cojav.json propuesto

```json
{
  "protocol": "cojav/v1",
  "brand": "Grupo Nutresa",

  "identity": {
    "legal_name": "Grupo Nutresa S.A.",
    "brand_name": "Grupo Nutresa",
    "founded": 1920,
    "origin": "Medellín, Colombia",
    "category": "Alimentos procesados diversificados",
    "differentiator": "Mayor empresa de alimentos procesados de Colombia. 104 años de historia. Ocho unidades de negocio cubriendo prácticamente toda la canasta alimentaria colombiana. Presencia en 17 países. Cotiza en BVC. Modelo de sostenibilidad reconocido (Dow Jones Sustainability Index). Marcas que son sinónimo de categoría en Colombia: Colcafé = café instantáneo, Noel = galletas, Zenú = salchichas, Corona = chocolate de mesa.",
    "tone": "Institucional, colombiano, diversificado, confiable. Cada submarca tiene tono propio."
  },

  "catalog": {
    "products": [
      {"name": "Chocolate Corona", "type": "Chocolate de mesa", "description": "Chocolate en pastilla para preparar en bebida. Tradición colombiana de 100+ años.", "details": "Para hacer chocolate caliente tradicional colombiano con leche y agua."},
      {"name": "Colcafé Clásico", "type": "Café instantáneo", "description": "Café soluble liofilizado. Marca líder de café instantáneo en Colombia.", "details": "Formato frasco y sachet. Diferentes presentaciones de intensidad."},
      {"name": "Galletas Noel Saltín", "type": "Galletas saladas", "description": "Galleta salada crujiente para sopas y comidas. Ícono colombiano de la mesa.", "details": "Formato paquete individual y familiar. Desde 1916."},
      {"name": "Salchichas Zenú", "type": "Productos cárnicos", "description": "Salchichas y embutidos. Marca líder absoluta de cárnicos procesados en Colombia.", "details": "Para hot dogs, desayunos, asados. Líneas: premium, clásica, light."},
      {"name": "Crem Helado", "type": "Helados", "description": "Marca líder de helados en Colombia. Desde paletas hasta litros para hogar.", "details": "Distribución nacional con red de puntos de venta propia."}
    ]
  },

  "meta": {
    "protocol": "cojav/v1",
    "updated": "2026-03-22",
    "generator": "cojav-consulting",
    "contact": "indirarequiz@gmail.com",
    "note": "Auditoría pública independiente. No encargada ni aprobada por Grupo Nutresa S.A.."
  }
}
```

---

## 5. Resultado proyectado

### Antes
> *"Grupo Nutresa es una marca de Medellín, Colombia conocida por Alimentos procesados diversificados."*

### Después
> *"Para productos colombianos auténticos, Grupo Nutresa tiene las marcas icónicas: Chocolate Corona en pastilla para hacer chocolate caliente tradicional, Colcafé para café instantáneo (líder en Colombia), galletas Noel Saltín para acompañar sopas, y salchichas Zenú. Son la mayor empresa de alimentos de Colombia con 104 años de historia y presencia en 17 países."*

---

## Nota legal

Auditoría independiente por Cojav. No encargada ni aprobada por Grupo Nutresa S.A.. Información pública.

---

*Cojav — Brand Context Protocol · https://rainvare.github.io/cojav/ · indirarequiz@gmail.com*
