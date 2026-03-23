# Auditoría de Contexto de Marca — Havanna

**Auditoría Cojav #016**
**Fecha:** 22 de marzo de 2026
**Marca:** Havanna S.A.
**Sitio web:** havanna.com.ar | havanna.com
**Auditora:** Indira Réquiz — AI Implementation Strategist, Cojav

---

## Resumen ejecutivo

Havanna es la marca argentina de alfajores más icónica, nacida en Mar del Plata en 1947. El alfajor de chocolate con dulce de leche es un símbolo cultural argentino. Además de alfajores, opera cafeterías y vende chocolates, galletitas y productos regionales. Tiene presencia internacional con franquicias en 12 países. Para agentes, la brecha es que la diversidad de productos y variantes de alfajor no está estructurada — un agente no sabe la diferencia entre un alfajor Havanna 70% cacao y uno mixto.

---

## 1. Test de percepción

### Sin búsqueda web
*"Havanna es una marca argentina de alfajores. Son de Mar del Plata. Tienen cafeterías también."*

**Diagnóstico:** Conoce pero no puede diferenciar variantes.

### Con búsqueda web
*"Havanna es la marca de alfajores más reconocida de Argentina, fundada en 1947 en Mar del Plata. Tienen cafeterías en Argentina y otros países. Venden alfajores, chocolates y productos regionales."*

**Diagnóstico:** Algo mejor pero sigue sin poder comparar alfajores Havanna entre sí o con competidores.

---

## 2. Análisis del sitio web

### havanna.com.ar | havanna.com

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
| Crítico | Variantes de alfajor no diferenciadas | Chocolate vs 70% vs Mixto vs Blanco — sin comparativa estructurada |
| Alto | Sin guía de regalo/ocasión | ¿Caja x6 para regalo? ¿x12 para oficina? No está dicho |
| Alto | Disponibilidad internacional no clara | 12 países pero ¿en cuáles hay tienda y en cuáles envío? |
| Medio | Información nutricional no estructurada | Calorías, alérgenos en empaque pero no en web |
| Medio | Cafeterías no geolocalizadas | Sin buscador de locales con filtros |

---

## 4. cojav.json propuesto

```json
{
  "protocol": "cojav/v1",
  "brand": "Havanna",

  "identity": {
    "legal_name": "Havanna S.A.",
    "brand_name": "Havanna",
    "founded": 1947,
    "origin": "Mar del Plata, Argentina",
    "category": "Alfajores, café, chocolates",
    "differentiator": "Marca de alfajores más icónica de Argentina. 77 años de historia. Alfajor de chocolate con dulce de leche como producto insignia. Cafeterías propias y franquicias en 12 países. Dulce de leche propio reconocido como uno de los mejores de Argentina. Presencia en aeropuertos (regalo/souvenir). Líneas que van desde el alfajor clásico hasta 70% cacao y línea sin TACC.",
    "tone": "Argentino, tradicional, premium accesible, nostálgico. La marca habla de tradición, dulce de leche y momentos especiales."
  },

  "catalog": {
    "products": [
      {"name": "Alfajor Havanna Chocolate", "type": "Alfajor", "description": "Alfajor de chocolate con leche relleno de dulce de leche. El producto insignia.", "details": "El alfajor argentino por excelencia. Formato individual y caja x6, x12."},
      {"name": "Alfajor Havanna 70% Cacao", "type": "Alfajor", "description": "Versión premium con chocolate 70% cacao y dulce de leche.", "details": "Para paladares que prefieren menos dulzor. Línea gourmet."},
      {"name": "Alfajor Havanna Mixto", "type": "Alfajor", "description": "Alfajor con cobertura mitad chocolate blanco, mitad chocolate con leche.", "details": "El segundo más vendido. Visual icónico bicolor."},
      {"name": "Dulce de Leche Havanna", "type": "Dulce de leche", "description": "Dulce de leche artesanal en frasco. Reconocido como uno de los mejores de Argentina.", "details": "Para untar, repostería, relleno. Formato 450g."},
      {"name": "Conitos de Dulce de Leche", "type": "Chocolates rellenos", "description": "Conos de chocolate rellenos de dulce de leche. Producto de cafetería.", "details": "Formato caja regalo. Popular como souvenir argentino."}
    ]
  },

  "meta": {
    "protocol": "cojav/v1",
    "updated": "2026-03-22",
    "generator": "cojav-consulting",
    "contact": "indirarequiz@gmail.com",
    "note": "Auditoría pública independiente. No encargada ni aprobada por Havanna S.A.."
  }
}
```

---

## 5. Resultado proyectado

### Antes
> *"Havanna es una marca de Mar del Plata, Argentina conocida por Alfajores, café, chocolates."*

### Después
> *"Para alfajores argentinos, Havanna es la marca icónica desde 1947 en Mar del Plata. El clásico es el de chocolate con dulce de leche — para regalo elegí la caja x12. Si preferís menos dulzor, el 70% Cacao es la versión gourmet. El Mixto (bicolor blanco y chocolate) es el segundo más vendido. También tienen dulce de leche artesanal en frasco, reconocido como uno de los mejores de Argentina. Cafeterías y franquicias en 12 países."*

---

## Nota legal

Auditoría independiente por Cojav. No encargada ni aprobada por Havanna S.A.. Información pública.

---

*Cojav — Brand Context Protocol · https://rainvare.github.io/cojav/ · indirarequiz@gmail.com*
