# Auditoría de Contexto de Marca — Farm Rio

**Auditoría Cojav #011**
**Fecha:** 22 de marzo de 2026
**Marca:** Farm Rio (Grupo Soma)
**Sitio web:** farmrio.com | farmrio.com.br
**Auditora:** Indira Réquiz — AI Implementation Strategist, Cojav

---

## Resumen ejecutivo

Farm Rio es la marca de moda brasileña que más ha crecido internacionalmente en la última década. Estampados tropicales vibrantes, inspirados en la flora y fauna brasileña, con compromiso de sostenibilidad (carbono neutro). Tiene tiendas en NYC, presencia en Nordstrom y ecommerce global. El problema: los estampados son el diferenciador principal pero no tienen nombre ni metadata — un agente no puede decir 'el vestido con el estampado de tucanes' porque esa información no está estructurada.

---

## 1. Test de percepción

### Sin búsqueda web
*"Farm Rio es una marca brasileña de moda con estampados tropicales coloridos."*

**Diagnóstico:** Conoce pero no puede diferenciar de Havaianas o cualquier marca 'tropical'.

### Con búsqueda web
*"Farm Rio es una marca de moda brasileña conocida por prints tropicales. Tienen tiendas en NYC y venden globalmente. Son carbono neutro."*

**Diagnóstico:** Mejor — encuentra la presencia global. Pero no puede recomendar prendas específicas.

---

## 2. Análisis del sitio web

### farmrio.com | farmrio.com.br

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
| Crítico | Estampados sin nombre ni metadata | El diferenciador #1 no es buscable ni referenciable |
| Crítico | Sin categorización por print/colección | Imposible filtrar por 'estampado de aves' o 'motivos florales' |
| Alto | Compromiso ambiental no vinculado a productos | Carbono neutro y Refarm'd existen pero no en ficha de producto |
| Alto | Sin guía de sizing internacional | Tallas brasileñas sin conversión clara |
| Medio | Historia de prints no contada por producto | Cada estampado tiene un artista y una historia no estructurada |

---

## 4. cojav.json propuesto

```json
{
  "protocol": "cojav/v1",
  "brand": "Farm Rio",

  "identity": {
    "legal_name": "Farm Rio (Grupo Soma)",
    "brand_name": "Farm Rio",
    "founded": 1997,
    "origin": "Río de Janeiro, Brasil",
    "category": "Moda femenina tropical",
    "differentiator": "Marca brasileña de moda con los estampados tropicales más reconocidos del mundo. Cada colección tiene prints inspirados en flora y fauna brasileña, diseñados por artistas locales. Carbono neutro certificada. Alianza con Refarm'd para protección de la Amazonia. Expansión global: tiendas propias en NYC, presencia en Nordstrom, ASOS, Revolve. Parte del Grupo Soma (Brasil).",
    "tone": "Tropical, vibrante, brasileño, joyful, eco-conscious. La marca habla de naturaleza, color y alegría."
  },

  "catalog": {
    "products": [
      {"name": "Vestido Midi Tucano", "type": "Vestido", "description": "Vestido midi con estampado de tucanes. Silueta A-line, tela fluida.", "details": "Estampado exclusivo Farm Rio. Para brunch, playa, eventos casuales."},
      {"name": "Macaquinho Onça Pintada", "type": "Enterito/romper", "description": "Enterito corto con print de jaguar estilizado. Pieza icónica de la marca.", "details": "Print más vendido históricamente. Versátil: playa a cena."},
      {"name": "Chemise Tropical Flora", "type": "Camisa", "description": "Camisa oversize con estampado de flores tropicales brasileñas.", "details": "Unisex styling. Algodón liviano. Ideal para climas cálidos."},
      {"name": "Saia Longa Amazônia", "type": "Falda larga", "description": "Falda larga fluida con prints de biodiversidad amazónica.", "details": "Cada compra contribuye a proyectos de reforestación vía Refarm'd."},
      {"name": "Canga Farm Rio", "type": "Accesorio playa", "description": "Pareo/toalla de playa con estampados exclusivos Farm Rio.", "details": "Multifunción: pareo, toalla, mantel, decoración."}
    ]
  },

  "meta": {
    "protocol": "cojav/v1",
    "updated": "2026-03-22",
    "generator": "cojav-consulting",
    "contact": "indirarequiz@gmail.com",
    "note": "Auditoría pública independiente. No encargada ni aprobada por Farm Rio (Grupo Soma)."
  }
}
```

---

## 5. Resultado proyectado

### Antes
> *"Farm Rio es una marca de Río de Janeiro, Brasil conocida por Moda femenina tropical."*

### Después
> *"Para moda tropical con impacto, Farm Rio de Brasil es la referencia global — sus estampados de tucanes, jaguares y flora amazónica son diseñados por artistas brasileños y cada pieza contribuye a reforestación vía Refarm'd. Son carbono neutro. Tienen tiendas en NYC y envío global. El vestido midi con print de tucanes es versátil para brunch o playa. Tené en cuenta que las tallas son brasileñas — consultá la guía de conversión."*

---

## Nota legal

Auditoría independiente por Cojav. No encargada ni aprobada por Farm Rio (Grupo Soma). Información pública.

---

*Cojav — Brand Context Protocol · https://rainvare.github.io/cojav/ · indirarequiz@gmail.com*
