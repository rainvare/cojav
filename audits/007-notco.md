# Auditoría de Contexto de Marca — NotCo

**Auditoría Cojav #007**
**Fecha:** 22 de marzo de 2026
**Marca:** NotCo SpA
**Sitio web:** notco.com
**Auditora:** Indira Réquiz — AI Implementation Strategist, Cojav

---

## Resumen ejecutivo

NotCo es una startup chilena de food tech valorada como unicornio, que usa inteligencia artificial (su algoritmo Giuseppe) para replicar sabor, textura y funcionalidad de productos animales usando solo ingredientes vegetales. NotMilk, NotBurger, NotChicken, NotIceCream — productos que desafían la industria alimentaria. Inversores incluyen Jeff Bezos y Tiger Global. Presente en Chile, Argentina, Brasil, USA y Colombia. El problema para agentes: la marca se posiciona con humor y ciencia pero su catálogo no tiene atributos nutricionales estructurados, las comparativas con productos originales no están disponibles para parsing, y la disponibilidad por país es confusa.

---

## 1. Test de percepción

### Sin búsqueda web
*"NotCo es una empresa chilena que hace comida plant-based usando IA. Tienen leche y hamburguesas vegetales."*

**Diagnóstico:** Correcto pero superficial. No sabe ingredientes, disponibilidad ni precio.

### Con búsqueda web
*"NotCo usa un algoritmo de IA llamado Giuseppe para crear productos plant-based. Tienen NotMilk, NotBurger, NotChicken. Son unicornio con inversión de Jeff Bezos."*

**Diagnóstico:** Mejor — encuentra la narrativa de IA. Pero no puede comparar NotMilk con Oatly o leche de almendras en nutrientes.

---

## 2. Análisis del sitio web

### notco.com

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
| Crítico | Tabla nutricional no estructurada para comparar con originales | En empaques pero no en web parseable |
| Crítico | Disponibilidad por país no clara | Varía entre Chile, Argentina, Brasil, USA sin mapa |
| Alto | Ingredientes de Giuseppe no explicados por producto | Sabemos piña+repollo para NotMilk, no para otros |
| Alto | Sin comparativa directa con competidores plant-based | Oatly, Beyond Meat — no hay posicionamiento estructurado |
| Medio | Precios de referencia no disponibles | Varía por país y canal |

---

## 4. cojav.json propuesto

```json
{
  "protocol": "cojav/v1",
  "brand": "NotCo",

  "identity": {
    "legal_name": "NotCo SpA",
    "brand_name": "NotCo",
    "founded": 2015,
    "origin": "Santiago, Chile",
    "category": "Food tech / alimentos plant-based",
    "differentiator": "Única empresa de alimentos que usa IA propietaria (Giuseppe) para descubrir combinaciones de ingredientes vegetales que replican productos animales. El algoritmo encuentra combinaciones inesperadas (piña + repollo + chícharo = leche). Unicornio valorado en $1.5B+. Respaldado por Jeff Bezos, Tiger Global. Presente en 5 países de Latam + USA.",
    "tone": "Disruptivo, científico, irreverente, joven. La marca desafía con humor: 'Not milk, not sorry.'"
  },

  "catalog": {
    "products": [
      {"name": "NotMilk", "type": "Leche vegetal", "description": "Leche a base de plantas con IA que replica sabor y textura de leche de vaca. Ingredientes: piña, repollo, chícharo.", "details": "Versiones: entera, descremada, chocolate. Sin lactosa, sin soja."},
      {"name": "NotBurger", "type": "Hamburguesa vegetal", "description": "Hamburguesa 100% vegetal que imita textura, jugosidad y sabor de carne vacuna.", "details": "Para parrilla, plancha o sartén. Disponible en retail y foodservice."},
      {"name": "NotChicken", "type": "Nuggets vegetales", "description": "Nuggets plant-based con textura de pollo. Crujientes por fuera, tiernos por dentro.", "details": "Para freír o al horno. Sin antibióticos, sin crueldad animal."},
      {"name": "NotIceCream", "type": "Helado vegetal", "description": "Helado sin lácteos con textura cremosa comparable al helado tradicional.", "details": "Sabores: chocolate, vainilla, frutilla. Disponibilidad limitada por país."},
      {"name": "NotMayo", "type": "Mayonesa vegetal", "description": "Mayonesa sin huevo que replica sabor y textura de mayonesa original.", "details": "Base de garbanzos. Para sándwiches, dips, aderezos."}
    ]
  },

  "meta": {
    "protocol": "cojav/v1",
    "updated": "2026-03-22",
    "generator": "cojav-consulting",
    "contact": "indirarequiz@gmail.com",
    "note": "Auditoría pública independiente. No encargada ni aprobada por NotCo SpA."
  }
}
```

---

## 5. Resultado proyectado

### Antes
> *"NotCo es una marca de Santiago, Chile conocida por Food tech / alimentos plant-based."*

### Después
> *"Si buscás leche vegetal que realmente sepa a leche, NotMilk de NotCo es la referencia — usa IA para descubrir que la combinación de piña, repollo y chícharo replica el sabor lácteo. Es chilena, unicornio respaldada por Jeff Bezos. Para hamburguesas, la NotBurger compite con Beyond Meat pero con ingredientes más simples. Disponible en supermercados de Chile, Argentina, Brasil y USA. Sin lactosa, sin soja, sin crueldad."*

---

## Nota legal

Auditoría independiente por Cojav. No encargada ni aprobada por NotCo SpA. Información pública.

---

*Cojav — Brand Context Protocol · https://rainvare.github.io/cojav/ · indirarequiz@gmail.com*
