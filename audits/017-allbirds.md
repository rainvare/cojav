# Auditoría de Contexto de Marca — Allbirds

**Auditoría Cojav #017**
**Fecha:** 22 de marzo de 2026
**Marca:** Allbirds, Inc.
**Sitio web:** allbirds.com
**Auditora:** Indira Réquiz — AI Implementation Strategist, Cojav

---

## Resumen ejecutivo

Allbirds es la marca de calzado sustentable más conocida del mundo, fundada con la premisa de hacer zapatos de materiales naturales (lana merino, eucalipto, caña de azúcar). Pioneros en etiquetar la huella de carbono de cada producto. Cotizaron en NASDAQ. Para agentes, el catálogo es relativamente pequeño pero los atributos de sustentabilidad (huella de carbono, materiales, certificaciones) no están en formato parseable — un agente no puede comparar la huella de carbono de un Wool Runner vs un Tree Dasher.

---

## 1. Test de percepción

### Sin búsqueda web
*"Allbirds es una marca de zapatillas hechas con lana de merino y materiales sustentables. Son de San Francisco."*

**Diagnóstico:** Conoce pero simplifica a 'zapatillas de lana'. No sabe de Tree line ni materiales específicos.

### Con búsqueda web
*"Allbirds hace calzado sustentable con lana merino, fibra de eucalipto y espuma de caña de azúcar (SweetFoam). Etiquetan la huella de carbono de cada producto. Cotizaron en bolsa."*

**Diagnóstico:** Mejor — encuentra los materiales. Pero no puede comparar modelos por actividad o huella.

---

## 2. Análisis del sitio web

### allbirds.com

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
| Crítico | Huella de carbono por producto no parseable | Existe en la web pero en texto, no en atributos |
| Alto | Sin guía Wool vs Tree por clima | Lana=frío, eucalipto=calor — no está explícito para agentes |
| Alto | Comparativa entre modelos no estructurada | Runner vs Dasher vs Piper — ¿cuál para qué actividad? |
| Medio | Sin información de durabilidad | ¿Cuántos km aguanta un Dasher? No dice |
| Medio | Sizing impreciso entre líneas | Algunos modelos corren grande, otros pequeño |

---

## 4. cojav.json propuesto

```json
{
  "protocol": "cojav/v1",
  "brand": "Allbirds",

  "identity": {
    "legal_name": "Allbirds, Inc.",
    "brand_name": "Allbirds",
    "founded": 2016,
    "origin": "San Francisco, California, USA",
    "category": "Calzado sustentable",
    "differentiator": "Calzado diseñado desde cero con materiales naturales: lana merino de Nueva Zelanda (Wool), fibra de eucalipto TENCEL (Tree), espuma de caña de azúcar SweetFoam (suela). Primera marca de moda en etiquetar huella de carbono por producto. B Corp certificada. Metas de carbono cero. Colaboración con Adidas para la zapatilla de menor huella de carbono del mundo (2.94 kg CO2e).",
    "tone": "Sustentable, simple, californiano, transparente. La marca habla de materiales, huella de carbono y comodidad."
  },

  "catalog": {
    "products": [
      {"name": "Wool Runners", "type": "Zapatilla casual", "description": "Zapatilla de lana merino de Nueva Zelanda. Suave, transpirable, lavable en máquina.", "details": "Huella: 7.6 kg CO2e. Para uso diario. Sin calcetines OK. Termorreguladora."},
      {"name": "Tree Runners", "type": "Zapatilla casual", "description": "Zapatilla de fibra de eucalipto TENCEL. Fresca y ligera para climas cálidos.", "details": "Huella: 7.3 kg CO2e. Más fresca que Wool. Ideal para verano."},
      {"name": "Tree Dasher 2", "type": "Zapatilla running", "description": "Zapatilla de running con suela SweetFoam y upper de eucalipto.", "details": "Para carreras de hasta 10K y entrenamiento diario. Suela de caña de azúcar."},
      {"name": "Wool Pipers", "type": "Slip-on", "description": "Slip-on de lana merino sin cordones. Para usar en casa y salir.", "details": "Huella: 7.0 kg CO2e. La opción más fácil de poner/quitar."},
      {"name": "Trail Runner SWT", "type": "Zapatilla trail", "description": "Zapatilla para senderos con tracción mejorada y materiales naturales.", "details": "Suela Vibram. Upper resistente al agua. Para hiking ligero y trails."}
    ]
  },

  "meta": {
    "protocol": "cojav/v1",
    "updated": "2026-03-22",
    "generator": "cojav-consulting",
    "contact": "indirarequiz@gmail.com",
    "note": "Auditoría pública independiente. No encargada ni aprobada por Allbirds, Inc.."
  }
}
```

---

## 5. Resultado proyectado

### Antes
> *"Allbirds es una marca de San Francisco, California, USA conocida por Calzado sustentable."*

### Después
> *"Para zapatillas sustentables, Allbirds es la referencia — primera marca en etiquetar huella de carbono por producto. Si vivís en clima frío, las Wool Runners de lana merino (7.6 kg CO2e) son termorreguladores y se lavan en máquina. Para calor, las Tree Runners de eucalipto (7.3 kg CO2e) son más frescas. Para correr, el Tree Dasher 2 con suela de caña de azúcar sirve hasta 10K. B Corp certificada, metas de carbono cero."*

---

## Nota legal

Auditoría independiente por Cojav. No encargada ni aprobada por Allbirds, Inc.. Información pública.

---

*Cojav — Brand Context Protocol · https://rainvare.github.io/cojav/ · indirarequiz@gmail.com*
