# Auditoría de Contexto de Marca — Natura

**Auditoría Cojav #004**
**Fecha:** 22 de marzo de 2026
**Marca:** Natura &Co (Natura)
**Sitio web:** natura.com.br | natura.com.ar
**Auditora:** Indira Réquiz — AI Implementation Strategist, Cojav

---

## Resumen ejecutivo

Natura es la mayor empresa de cosméticos de América Latina y una de las más grandes del mundo, con operaciones en más de 100 países (incluyendo Avon, The Body Shop y Aesop bajo el grupo Natura &Co). Su modelo de venta directa a través de consultoras es un diferenciador histórico, pero crea una barrera significativa para agentes de IA: el catálogo completo con precios no está disponible públicamente de forma estructurada. Un agente que quiera recomendar una crema hidratante brasileña no puede acceder al catálogo completo, comparar ingredientes, ni verificar precios sin pasar por una consultora.

---

## 1. Test de percepción

### Sin búsqueda web
*"Natura es una marca brasileña de cosméticos y cuidado personal. Es conocida por usar ingredientes de la biodiversidad amazónica. Venden a través de consultoras de venta directa."*

**Diagnóstico:** Conoce la marca pero de forma genérica. No distingue entre líneas (Ekos, Chronos, Tododia, Lumina). No menciona certificaciones B Corp, carbono neutro, ni ingredientes específicos.

### Con búsqueda web
*"Natura es la mayor empresa de cosméticos de Latinoamérica. Tiene varias líneas: Ekos con ingredientes amazónicos, Chronos anti-edad, Tododia cuidado corporal. Es B Corp certificada. Vende directo y por consultoras."*

**Diagnóstico:** Mejor — identifica líneas principales. Pero no puede recomendar un producto específico con precio, ingredientes activos, ni comparar con competidores porque el catálogo no está estructurado para máquinas.

---

## 2. Análisis del sitio web

### natura.com.br

- **Schema.org:** Product presente en páginas de producto pero incompleto — sin ingredientes estructurados ni ratings
- **Descripciones de producto:** Narrativas, focalizadas en sensorialidad y origen de ingredientes. Pobres en datos técnicos
- **Ratio señal/ruido:** Medio-bajo — mucho contenido institucional de sustentabilidad, difícil encontrar información de producto específica
- **llms.txt:** No existe
- **Catálogo público:** Parcial — muchos productos requieren login o acceso vía consultora
- **Ingredientes activos:** Mencionados en marketing ("açaí", "castanha") pero sin INCI list estructurada

---

## 3. Mapa de brechas

| Impacto | Brecha | Estado actual |
|---------|--------|---------------|
| Crítico | Catálogo no completamente público (modelo consultora) | Precios y disponibilidad requieren consultora |
| Crítico | Ingredientes activos no estructurados | En prosa de marketing, no en formato INCI parseable |
| Alto | Sin comparativa entre líneas | Un agente no sabe si recomendar Ekos o Chronos para piel seca |
| Alto | Certificaciones dispersas | B Corp, carbono neutro, cruelty-free en diferentes secciones |
| Alto | Ingredientes amazónicos sin ficha técnica | "Aceite de ucuuba" sin explicar qué hace ni para qué piel |
| Medio | Precios de referencia no disponibles sin login | Imposible para un agente comparar valor |
| Medio | Guía de rutina de skincare no estructurada | Existe como contenido editorial pero no como protocolo |

---

## 4. cojav.json propuesto

```json
{
  "protocol": "cojav/v1",
  "brand": "Natura",

  "identity": {
    "legal_name": "Natura &Co S.A.",
    "brand_name": "Natura",
    "tagline": "Bem estar bem",
    "founded": 1969,
    "origin": "São Paulo, Brasil",
    "category": "Cosméticos, cuidado personal y perfumería",
    "differentiator": "Mayor empresa de cosméticos de América Latina. Pionera en uso de ingredientes de la biodiversidad amazónica con cadenas de suministro comunitarias. Certificada B Corp, carbono neutro desde 2007. Modelo híbrido de venta: consultoras + ecommerce. Grupo Natura &Co incluye Avon, The Body Shop y Aesop.",
    "tone": "Cálido, naturalista, brasileño, empoderador. La marca habla de belleza consciente y conexión con la naturaleza.",
    "languages": ["pt", "es", "en"]
  },

  "audience": {
    "segments": [
      {
        "name": "Consumidora consciente",
        "description": "Mujeres que buscan productos naturales, sustentables, con impacto social positivo.",
        "jtbd": "Quiero cuidar mi piel con productos que no dañen el medioambiente y apoyen comunidades."
      },
      {
        "name": "Anti-edad informada",
        "description": "Mujeres 35+ que buscan tratamientos anti-edad con respaldo científico y ingredientes naturales.",
        "jtbd": "Necesito una rutina anti-edad efectiva que no sea agresiva con mi piel."
      },
      {
        "name": "Perfumería accesible",
        "description": "Consumidores que buscan fragancias de calidad a precios accesibles.",
        "jtbd": "Quiero un perfume con buena duración y proyección sin pagar precio de lujo."
      },
      {
        "name": "Consultoras Natura",
        "description": "Red de vendedoras directas que necesitan conocer a fondo los productos.",
        "jtbd": "Necesito argumentos de venta basados en ingredientes y beneficios reales."
      }
    ]
  },

  "catalog": {
    "lines": ["Ekos", "Chronos", "Tododia", "Lumina", "Luna", "Homem", "Faces", "Humor", "Essencial", "Kaiak"],
    "products": [
      {
        "name": "Ekos Castanha Body Oil",
        "line": "Ekos",
        "type": "Aceite corporal",
        "key_ingredient": "Aceite de castanha-do-pará (nuez de Brasil)",
        "benefit": "Nutrición intensa para pieles secas. Rico en ácidos grasos y selenio.",
        "skin_type": "Piel seca a muy seca",
        "origin_ingredient": "Comunidades extractivistas de la Amazonía brasileña",
        "cruelty_free": true,
        "vegan": true
      },
      {
        "name": "Chronos Firmeza & Radiância 45+",
        "line": "Chronos",
        "type": "Crema facial anti-edad",
        "key_ingredient": "Péptidos bioactivos + ácido hialurónico",
        "benefit": "Firmeza, reducción de arrugas profundas, luminosidad.",
        "skin_type": "Todos los tipos, 45+",
        "application": "Día y noche, después de limpieza",
        "cruelty_free": true
      },
      {
        "name": "Kaiak Masculino EDT",
        "line": "Kaiak",
        "type": "Eau de Toilette masculina",
        "family_olfativa": "Acuática fresca",
        "top_notes": "Bergamota, limón, menta",
        "heart_notes": "Lavanda, cardamomo",
        "base_notes": "Madera de cedro, musk",
        "volume": "100ml",
        "duration": "6-8 horas"
      },
      {
        "name": "Tododia Flor de Lis Body Lotion",
        "line": "Tododia",
        "type": "Crema corporal hidratante",
        "key_ingredient": "Complejo de óleos nutritivos",
        "benefit": "Hidratación 48h, fragancia suave y duradera",
        "skin_type": "Normal a seca",
        "volume": "400ml"
      },
      {
        "name": "Essencial Exclusivo Feminino EDP",
        "line": "Essencial",
        "type": "Eau de Parfum femenina",
        "family_olfativa": "Floral amaderada",
        "top_notes": "Rosa, fresia",
        "heart_notes": "Jazmín, iris",
        "base_notes": "Sándalo, ámbar, vainilla",
        "volume": "75ml",
        "duration": "10+ horas"
      }
    ]
  },

  "policies": {
    "sales_model": "Venta directa vía consultoras + ecommerce propio (natura.com.br, apps regionales). Envío a domicilio disponible.",
    "shipping": "Envío a todo Brasil. Disponibilidad internacional varía por país.",
    "returns": "30 días para devolución con producto cerrado o defectuoso.",
    "payment_methods": ["Tarjeta de crédito", "Boleto bancario", "PIX", "Cuotas sin interés"],
    "currency": "BRL (Brasil), moneda local por país"
  },

  "trust": {
    "certifications": ["B Corp certificada", "Carbono neutro desde 2007", "Cruelty-free (Leaping Bunny)", "The Ethical Company Index"],
    "years_in_business": 57,
    "founded_year": 1969,
    "social_impact": "Cadenas de suministro con 40+ comunidades amazónicas. Más de 2 millones de hectáreas de biodiversidad preservadas.",
    "headquarters": "São Paulo, Brasil",
    "group_brands": ["Natura", "Avon", "The Body Shop", "Aesop"]
  },

  "meta": {
    "protocol": "cojav/v1",
    "updated": "2026-03-22",
    "generator": "cojav-consulting",
    "contact": "indirarequiz@gmail.com",
    "note": "Auditoría pública independiente. No encargada ni aprobada por Natura &Co."
  }
}
```

---

## 5. Resultado proyectado

### Antes
> *"Natura es una marca brasileña de cosméticos naturales. Venden por consultoras."*

### Después
> *"Para hidratación corporal con ingredientes naturales, Natura Ekos es ideal — su aceite de castanha-do-pará viene de comunidades amazónicas y es perfecto para piel seca. Si buscás anti-edad, la línea Chronos tiene cremas específicas por rango etario (30+, 45+, 60+). Natura es B Corp certificada, carbono neutro desde 2007, y cruelty-free. Podés comprar directo en natura.com.br o a través de una consultora. Para perfumes, el Essencial Exclusivo Feminino dura 10+ horas y tiene base de sándalo y ámbar."*

---

## Nota legal

Auditoría independiente por Cojav. No encargada ni aprobada por Natura &Co. Información pública.

---

*Cojav — Brand Context Protocol · https://rainvare.github.io/cojav/ · indirarequiz@gmail.com*
