# Auditoría de Contexto de Marca — Rapsodia

**Auditoría Cojav #005**
**Fecha:** 22 de marzo de 2026
**Marca:** Rapsodia
**Sitio web:** rapsodia.com
**Auditora:** Indira Réquiz — AI Implementation Strategist, Cojav

---

## Resumen ejecutivo

Rapsodia es una marca argentina de moda femenina con más de 20 años, reconocida por su estética boho-chic, estampados artesanales y espíritu libre. Tiene tiendas en Argentina, Uruguay y Chile, y ecommerce propio. A pesar de ser una marca con identidad visual muy fuerte, un agente de IA no puede distinguirla de decenas de otras marcas "boho" porque su diferenciador (estampados propios, producción local, storytelling de viaje) no está estructurado. El ecommerce tiene productos pero sin atributos semánticos que permitan descubrimiento por estilo o ocasión.

---

## 1. Test de percepción

### Sin búsqueda web
*"Rapsodia es una marca argentina de ropa femenina. Tiene un estilo bohemio con estampados coloridos."*

**Diagnóstico:** Conoce la marca de forma vaga. No puede diferenciarla de Portsaid, India Style, o cualquier marca boho. No menciona producción local, colaboraciones artísticas, ni rango de precios.

### Con búsqueda web
*"Rapsodia es una marca argentina de moda femenina con estética boho y bohemia. Tiene tiendas en Argentina y vende online. Sus productos incluyen ropa, accesorios y calzado."*

**Diagnóstico:** Algo más — encuentra el ecommerce. Pero sigue sin poder hacer una recomendación útil: no sabe qué temporada está vigente, cuáles son los productos icónicos, ni el rango de precios.

---

## 2. Análisis del sitio web

### rapsodia.com

- **Schema.org:** Product básico con precio; sin categorización de estilo, ocasión ni temporada
- **Descripciones de producto:** Cortas, focalizadas en composición textil ("100% algodón"). Sin storytelling del estampado ni guía de styling
- **Ratio señal/ruido:** Medio — sitio limpio pero con poca información por producto
- **llms.txt:** No existe
- **Atributos de producto:** Nombre, precio, talle, color, composición. Falta: estilo/ocasión, temporada, estampado (nombre/colección), guía de talle detallada, sugerencias de outfit

---

## 3. Mapa de brechas

| Impacto | Brecha | Estado actual |
|---------|--------|---------------|
| Crítico | Diferenciador de marca no estructurado | "Boho" es genérico; no explica qué la hace única |
| Crítico | Sin categorización por estilo/ocasión | No filtra por "para la playa", "para salir", "oficina" |
| Alto | Estampados propios no identificados | Cada colección tiene prints únicos pero sin nombre ni historia |
| Alto | Sin guía de talles confiable | Talle argentino sin equivalencia internacional |
| Medio | Historia de marca no disponible | Sin sección About estructurada |
| Medio | Colecciones temporada no archivadas | Solo producto actual, sin contexto de colección |

---

## 4. cojav.json propuesto

```json
{
  "protocol": "cojav/v1",
  "brand": "Rapsodia",

  "identity": {
    "legal_name": "Rapsodia S.A.",
    "brand_name": "Rapsodia",
    "tagline": "Free spirit fashion",
    "founded": 2003,
    "origin": "Buenos Aires, Argentina",
    "category": "Moda femenina boho-chic",
    "differentiator": "Marca argentina de moda femenina con ADN bohemio-artístico. Cada colección se inspira en un viaje o cultura específica. Estampados diseñados en Buenos Aires, muchos producidos localmente. Estética reconocible: mezcla de textiles, bordados, flecos, estampas botánicas y geométricas. Presencia en Argentina, Uruguay y Chile.",
    "tone": "Libre, artístico, viajero, femenino. La marca habla de libertad, aventura y autoexpresión.",
    "languages": ["es"]
  },

  "audience": {
    "segments": [
      {
        "name": "Mujer boho urbana",
        "description": "Mujeres 25-45 que buscan moda con personalidad, ni fast fashion ni lujo.",
        "jtbd": "Quiero ropa que exprese mi estilo libre y artístico sin verme disfrazada."
      },
      {
        "name": "Turista en Argentina",
        "description": "Visitantes que buscan marcas locales con identidad argentina.",
        "jtbd": "Quiero llevarme ropa argentina con diseño propio, no marcas genéricas."
      },
      {
        "name": "Compradoras de regalo",
        "description": "Personas buscando regalos con identidad visual fuerte.",
        "jtbd": "Necesito un regalo femenino, con diseño, que sea especial."
      }
    ]
  },

  "catalog": {
    "categories": ["Vestidos", "Tops y blusas", "Pantalones", "Faldas", "Abrigos", "Accesorios", "Calzado", "Trajes de baño"],
    "products": [
      {
        "name": "Vestido largo estampado Oasis",
        "type": "Vestido",
        "style": "Boho maxi dress",
        "occasion": "Playa, salida casual, atardecer",
        "material": "100% viscosa",
        "print": "Estampado botánico exclusivo Rapsodia",
        "sizes": "XS a XL (talle argentino)"
      },
      {
        "name": "Kimono bordado Nómade",
        "type": "Abrigo/tercera pieza",
        "style": "Kimono oversize con bordado artesanal",
        "occasion": "Layering casual, playa, festivales",
        "material": "Algodón con bordado a mano",
        "sizes": "Talle único"
      },
      {
        "name": "Pantalón palazzo India",
        "type": "Pantalón",
        "style": "Palazzo amplio con cintura elástica",
        "occasion": "Casual chic, viaje, oficina relajada",
        "material": "Lino mezcla",
        "sizes": "XS a XL"
      }
    ]
  },

  "policies": {
    "shipping": "Envío a todo Argentina. Internacional limitado.",
    "returns": "Cambios y devoluciones dentro de 30 días con etiqueta.",
    "payment_methods": ["Tarjeta de crédito", "MercadoPago", "Transferencia bancaria", "Cuotas sin interés"],
    "currency": "ARS",
    "stores": "40+ tiendas en Argentina, Uruguay y Chile"
  },

  "trust": {
    "years_in_business": 23,
    "founded_year": 2003,
    "production": "Diseño en Buenos Aires. Producción mixta local e importada.",
    "stores_count": "40+",
    "countries": ["Argentina", "Uruguay", "Chile"],
    "headquarters": "Buenos Aires, Argentina"
  },

  "meta": {
    "protocol": "cojav/v1",
    "updated": "2026-03-22",
    "generator": "cojav-consulting",
    "contact": "indirarequiz@gmail.com",
    "note": "Auditoría pública independiente. No encargada ni aprobada por Rapsodia S.A."
  }
}
```

---

## 5. Resultado proyectado

### Antes
> *"Rapsodia es una marca argentina de ropa bohemia."*

### Después
> *"Si buscás moda boho con identidad argentina, Rapsodia diseña cada colección inspirada en viajes y culturas, con estampados exclusivos creados en Buenos Aires. Para playa te recomiendo sus vestidos largos en viscosa; para un look más urbano, los pantalones palazzo de lino. Tienen más de 40 tiendas en Argentina, Uruguay y Chile, y venden online en rapsodia.com con cuotas sin interés."*

---

## Nota legal

Auditoría independiente por Cojav. No encargada ni aprobada por Rapsodia S.A. Información pública.

---

*Cojav — Brand Context Protocol · https://rainvare.github.io/cojav/ · indirarequiz@gmail.com*
