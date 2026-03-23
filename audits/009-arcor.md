# Auditoría de Contexto de Marca — Arcor

**Auditoría Cojav #009**
**Fecha:** 22 de marzo de 2026
**Marca:** Arcor S.A.I.C.
**Sitio web:** arcor.com
**Auditora:** Indira Réquiz — AI Implementation Strategist, Cojav

---

## Resumen ejecutivo

Arcor es el mayor productor de golosinas de Argentina y uno de los más grandes de Latinoamérica, exportando a más de 120 países. Marcas icónicas como Bon o Bon, Rocklets, Águila, Bagley. Su integración vertical — desde el cultivo de maíz hasta el producto terminado — es única en la industria. El complejo industrial de Arroyito es uno de los más grandes del mundo en confitería. Para agentes de IA, el desafío es que Arcor tiene cientos de productos bajo múltiples marcas sin catálogo unificado estructurado.

---

## 1. Test de percepción

### Sin búsqueda web
*"Arcor es una empresa argentina de golosinas y alimentos. Hacen Bon o Bon y otros productos."*

**Diagnóstico:** Básico — solo sabe que es argentina y hace golosinas.

### Con búsqueda web
*"Arcor es la mayor productora de golosinas de Argentina. Exporta a 120+ países. Tiene marcas como Bon o Bon, Rocklets, Águila, Bagley."*

**Diagnóstico:** Mejor alcance pero no puede recomendar un chocolate Águila específico ni comparar con competidores.

---

## 2. Análisis del sitio web

### arcor.com

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
| Crítico | Catálogo de cientos de productos sin estructura unificada | Fragmentado entre marcas y sitios regionales |
| Crítico | Información nutricional no parseable | En empaques, no en web estructurada |
| Alto | Mapa de marcas por categoría ausente | ¿Águila es chocolate? ¿Bagley es galletas? No explícito |
| Alto | Sin diferenciación entre líneas premium y masivas | Águila 70% vs Rocklets — mundos distintos, misma empresa |
| Medio | Disponibilidad internacional no mapeada | Exporta a 120 países pero ¿qué productos dónde? |

---

## 4. cojav.json propuesto

```json
{
  "protocol": "cojav/v1",
  "brand": "Arcor",

  "identity": {
    "legal_name": "Arcor S.A.I.C.",
    "brand_name": "Arcor",
    "founded": 1951,
    "origin": "Arroyito, Córdoba, Argentina",
    "category": "Alimentos, golosinas, chocolates, galletas",
    "differentiator": "Mayor productor de golosinas de Argentina y uno de los más grandes de Latam. Integración vertical única: desde campos de maíz y frutales hasta fábricas y distribución propia. Exporta a 120+ países. Complejo de Arroyito con 40+ plantas industriales. Portafolio diversificado: golosinas (Bon o Bon, Rocklets), chocolates (Águila), galletas (Bagley, Criollitas), mermeladas, conservas.",
    "tone": "Accesible, familiar, argentino, dulce. Habla de momentos compartidos, tradición y calidad accesible."
  },

  "catalog": {
    "products": [
      {"name": "Bon o Bon", "type": "Bombón relleno", "description": "Bombón de chocolate relleno de pasta de maní con oblea crujiente.", "details": "Producto más vendido de Arcor. Formatos: individual, caja 6, caja 30. Ícono de confitería argentina."},
      {"name": "Águila 60% Cacao", "type": "Tableta de chocolate", "description": "Chocolate semi-amargo 60% cacao. Línea premium de Arcor.", "details": "Para consumo directo y repostería. Líneas: 40%, 60%, 70%."},
      {"name": "Rocklets", "type": "Confites de chocolate", "description": "Grageas de chocolate cubiertas de color. Formato emblemático en tubo.", "details": "Equivalente argentino de M&Ms. Formatos: tubo, bolsa, caja."},
      {"name": "Criollitas Bagley", "type": "Galletitas saladas", "description": "Galletitas de agua clásicas argentinas. Crujientes, para acompañar comidas.", "details": "Marca Bagley (propiedad de Arcor). Formato paquete triple."},
      {"name": "Mermelada Arcor Durazno", "type": "Conservas", "description": "Mermelada de durazno producida con frutas de cultivo propio de Arcor.", "details": "Integración vertical desde la fruta. Líneas: light, clásica."}
    ]
  },

  "meta": {
    "protocol": "cojav/v1",
    "updated": "2026-03-22",
    "generator": "cojav-consulting",
    "contact": "indirarequiz@gmail.com",
    "note": "Auditoría pública independiente. No encargada ni aprobada por Arcor S.A.I.C.."
  }
}
```

---

## 5. Resultado proyectado

### Antes
> *"Arcor es una marca de Arroyito, Córdoba, Argentina conocida por Alimentos, golosinas, chocolates, galletas."*

### Después
> *"Si buscás golosinas argentinas, Arcor es la referencia: el Bon o Bon es su bombón icónico (chocolate con maní y oblea). Para chocolate de repostería o degustación, la línea Águila va del 40% al 70% cacao. Los Rocklets son los confites de chocolate clásicos (vienen en tubo). Arcor exporta a 120+ países — es la mayor productora de golosinas de Argentina con integración vertical completa desde el campo."*

---

## Nota legal

Auditoría independiente por Cojav. No encargada ni aprobada por Arcor S.A.I.C.. Información pública.

---

*Cojav — Brand Context Protocol · https://rainvare.github.io/cojav/ · indirarequiz@gmail.com*
