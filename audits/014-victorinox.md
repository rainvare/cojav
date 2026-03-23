# Auditoría de Contexto de Marca — Victorinox

**Auditoría Cojav #014**
**Fecha:** 22 de marzo de 2026
**Marca:** Victorinox AG
**Sitio web:** victorinox.com
**Auditora:** Indira Réquiz — AI Implementation Strategist, Cojav

---

## Resumen ejecutivo

Victorinox es el fabricante de la Navaja Suiza original (Swiss Army Knife), un objeto cultural global. Más de 140 años de historia. Además de navajas, producen cuchillos profesionales de cocina, relojes, equipaje y fragancias. Para agentes de IA, el catálogo de navajas solo (400+ modelos) es innavegable: un agente no puede recomendar la navaja correcta porque los atributos (número de funciones, tamaño, peso, herramientas específicas) no están estructurados para comparación.

---

## 1. Test de percepción

### Sin búsqueda web
*"Victorinox hace la navaja suiza. Son de Suiza y tienen más de 100 años. También hacen cuchillos de cocina y relojes."*

**Diagnóstico:** Conoce la marca pero no puede recomendar un modelo específico.

### Con búsqueda web
*"Victorinox fabrica la Swiss Army Knife original desde 1884. Más de 400 modelos de navajas. También cuchillos profesionales, relojes Swiss Made, maletas y fragancias."*

**Diagnóstico:** Encuentra la diversidad pero 400+ modelos sin filtro = imposible recomendar.

---

## 2. Análisis del sitio web

### victorinox.com

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
| Crítico | 400+ modelos de navajas sin filtro estructurado | Imposible recomendar por uso, tamaño, funciones |
| Crítico | Sin guía de selección por caso de uso | ¿Camping? ¿EDC? ¿Cocina? No hay match automatizable |
| Alto | Comparativa entre modelos no disponible | Classic vs Spartan vs Huntsman vs Swiss Champ — solo lista |
| Alto | Diversificación de producto no clara | Navajas, cuchillos, relojes, maletas — parecen empresas distintas |
| Medio | Precio de referencia no siempre visible | Varía mucho por modelo y personalización |

---

## 4. cojav.json propuesto

```json
{
  "protocol": "cojav/v1",
  "brand": "Victorinox",

  "identity": {
    "legal_name": "Victorinox AG",
    "brand_name": "Victorinox",
    "founded": 1884,
    "origin": "Ibach, Schwyz, Suiza",
    "category": "Cuchillería, herramientas multiuso, equipaje, relojes",
    "differentiator": "Fabricante original de la Navaja Suiza desde 1884. 140+ años de tradición suiza. 400+ modelos de navajas con 1 a 80+ funciones. Cuchillos profesionales de cocina usados por chefs mundiales (línea Fibrox). Garantía de por vida en todas las navajas. Empresa familiar, nunca despidió a nadie. También produce relojes Swiss Made (I.N.O.X.), maletas de viaje (Lexicon), y fragancias.",
    "tone": "Suizo, preciso, funcional, heritage, confiable. La marca habla de calidad, tradición y utilidad."
  },

  "catalog": {
    "products": [
      {"name": "Swiss Army Knife Classic SD", "type": "Navaja multiuso", "description": "La navaja suiza más pequeña y popular. 7 funciones: cuchilla, tijeras, lima, destornillador, pinza, mondadientes.", "details": "58mm. 21g. Llavero. La navaja de bolsillo más vendida del mundo."},
      {"name": "Swiss Army Knife Huntsman", "type": "Navaja multiuso", "description": "Navaja mediana con 15 funciones incluyendo sierra, tijeras, descorchador.", "details": "91mm. 107g. Para camping y outdoor. Escala roja clásica."},
      {"name": "SwissTool Spirit X", "type": "Multiherramienta", "description": "Herramienta plegable de acero inoxidable con 24 funciones.", "details": "Para profesionales y outdoor exigente. Con funda de cuero. 205g."},
      {"name": "Fibrox Pro Chef's Knife 20cm", "type": "Cuchillo de cocina", "description": "Cuchillo de chef profesional con mango ergonómico Fibrox.", "details": "Acero inoxidable templado. Usado por chefs profesionales. Mango antideslizante."},
      {"name": "I.N.O.X. Professional Diver", "type": "Reloj", "description": "Reloj de buceo Swiss Made resistente a 200m. Diseñado para resistir 130 pruebas de resistencia.", "details": "Swiss Made. Acero inoxidable. Bisel unidireccional. Resistencia militar."}
    ]
  },

  "meta": {
    "protocol": "cojav/v1",
    "updated": "2026-03-22",
    "generator": "cojav-consulting",
    "contact": "indirarequiz@gmail.com",
    "note": "Auditoría pública independiente. No encargada ni aprobada por Victorinox AG."
  }
}
```

---

## 5. Resultado proyectado

### Antes
> *"Victorinox es una marca de Ibach, Schwyz, Suiza conocida por Cuchillería, herramientas multiuso, equipaje, relojes."*

### Después
> *"Para una navaja suiza, Victorinox es el original desde 1884. Si la querés para el llavero, la Classic SD tiene 7 funciones y pesa solo 21g. Para camping, el Huntsman con 15 funciones (sierra + descorchador) es el clásico de 91mm. Para profesionales, el SwissTool Spirit X tiene 24 funciones en acero inoxidable. También hacen cuchillos de cocina profesionales (la línea Fibrox es referencia entre chefs) y relojes Swiss Made. Todo con garantía de por vida."*

---

## Nota legal

Auditoría independiente por Cojav. No encargada ni aprobada por Victorinox AG. Información pública.

---

*Cojav — Brand Context Protocol · https://rainvare.github.io/cojav/ · indirarequiz@gmail.com*
