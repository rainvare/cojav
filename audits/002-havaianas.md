# Auditoría de Contexto de Marca — Havaianas

**Auditoría Cojav #002**
**Fecha:** 22 de marzo de 2026
**Marca:** Havaianas (Alpargatas S.A.)
**Sitio web:** havaianas.com | havaianas-store.com
**Auditora:** Indira Réquiz — AI Implementation Strategist, Cojav

---

## Resumen ejecutivo

Havaianas es la marca de sandalias más reconocida del mundo, nacida en Brasil en 1962, con presencia en más de 100 países. Su ecommerce opera en múltiples dominios regionales (.com, .com.br, -store.com para Europa). A pesar de ser una marca globalmente icónica con un posicionamiento cultural único — representando el estilo de vida brasileño — los agentes de IA la perciben como una marca genérica de chanclas baratas, perdiendo completamente su narrativa cultural, su diversificación de producto (alpargatas, sandalias, ropa, accesorios) y su compromiso ambiental (90% material reciclado).

---

## 1. Test de percepción — ¿Qué sabe un agente de IA sobre Havaianas?

### Sin búsqueda web (conocimiento base)

*"Havaianas es una marca brasileña de chanclas/flip-flops fundada en 1962. Son conocidas por sus sandalias de goma de colores. Venden principalmente chanclas. Son populares en Brasil y tienen presencia internacional."*

**Diagnóstico:** El agente conoce la marca pero la reduce a un solo producto (chanclas). No menciona alpargatas, sandalias cerradas, ropa, toallas, bolsos ni accesorios. No sabe sobre materiales reciclados. No captura el posicionamiento cultural.

### Con búsqueda web

*"Havaianas es una marca brasileña de calzado conocida por sus chanclas. Tienen tienda online con outlet. Venden chanclas, sandalias y alpargatas. Fundada en 1962, inspirada en las sandalias japonesas zori."*

**Diagnóstico:** Algo mejor — encuentra el catálogo expandido — pero sigue sin capturar: el 90% de material reciclado, la diversificación a lifestyle (ropa, accesorios, bolsos), las colaboraciones especiales, ni los precios de referencia. El agente tampoco puede diferenciar entre los cientos de modelos.

---

## 2. Análisis del sitio web

### havaianas.com (global)

- **Schema.org:** Presente en nivel Organization básico; datos Product incompletos — sin AggregateRating, sin atributos semánticos de material/sostenibilidad
- **Descripciones de producto:** Focalizadas en estilo y emoción, pobres en atributos técnicos (material, peso, suela, composición reciclada)
- **Ratio señal/ruido:** Medio — mucho contenido de lifestyle y branding, poca información estructurada por producto
- **llms.txt:** No existe
- **robots.txt:** Presente pero estándar
- **sitemap.xml:** Presente
- **Atributos de producto:** Color, talla, precio. Falta: material, porcentaje reciclado, grosor de suela, peso, colección, año de lanzamiento

### havaianas-store.com (Europa)

- **Schema.org:** Product básico con precio y disponibilidad; sin reviews estructuradas
- **Problemas identificados:** Dominio separado del .com global sin conexión semántica clara; confusión de sizing (tallas brasileñas vs europeas documentada en reviews)
- **Contenido de sostenibilidad:** Mención genérica de materiales reciclados, sin datos específicos por producto
- **Atención al cliente:** Múltiples reviews negativas sobre servicio postventa; esta información no está estructurada para que un agente pueda advertir al consumidor

---

## 3. Mapa de brechas

| Impacto | Brecha | Estado actual |
|---------|--------|---------------|
| Crítico | Diferenciador cultural (estilo de vida brasileño, no solo chanclas) | Presente en copy pero no estructurado |
| Crítico | Catálogo semántico (500+ modelos con atributos) | Solo nombre, color, talla, precio |
| Crítico | Sostenibilidad (90% material reciclado) | Mención vaga, sin datos por producto |
| Alto | Guía de tallas (conversión BR/EU/US) | Existe pero no estructurada; causa devoluciones |
| Alto | Colecciones y colaboraciones especiales | No categorizadas para descubrimiento por agentes |
| Alto | Conexión entre dominios regionales | Sitios separados sin enlace semántico |
| Medio | Historia de marca (1962, zori japonesas, evolución) | En sección About, no estructurada |
| Medio | Políticas de devolución y envío | Dispersas, difíciles de encontrar |

---

## 4. cojav.json propuesto

```json
{
  "protocol": "cojav/v1",
  "brand": "Havaianas",

  "identity": {
    "legal_name": "Alpargatas S.A.",
    "brand_name": "Havaianas",
    "tagline": "Born in Brazil. Made for everywhere.",
    "founded": 1962,
    "origin": "São Paulo, Brasil",
    "category": "Calzado y accesorios de lifestyle",
    "differentiator": "La marca de sandalias más icónica del mundo. Nacida en Brasil en 1962, inspirada en las sandalias japonesas zori. Fabricadas con 90% de material reciclado de otras sandalias. Más de 60 años transformando un producto simple en símbolo de libertad, color y estilo de vida brasileño. Presencia en más de 100 países.",
    "tone": "Alegre, colorido, informal, brasileño. La marca habla de felicidad, verano, libertad y autoexpresión.",
    "languages": ["pt", "en", "es", "fr", "it", "de", "nl"],
    "global_presence": "100+ países"
  },

  "audience": {
    "segments": [
      {
        "name": "Beach lifestyle lovers",
        "description": "Personas que buscan calzado cómodo, colorido y versátil para playa, piscina y vida casual.",
        "jtbd": "Necesito sandalias cómodas, duraderas y con estilo para usar todos los días en climas cálidos."
      },
      {
        "name": "Fashion-conscious millennials/Gen Z",
        "description": "Jóvenes que buscan marcas con identidad cultural fuerte y compromiso ambiental.",
        "jtbd": "Quiero una marca que represente mi estilo de vida relajado pero consciente del medioambiente."
      },
      {
        "name": "Viajeros",
        "description": "Turistas y viajeros frecuentes que necesitan calzado ligero, empacable y versátil.",
        "jtbd": "Necesito sandalias que ocupen poco espacio, sean ligeras y sirvan para playa y ciudad."
      },
      {
        "name": "Coleccionistas/ediciones especiales",
        "description": "Fans de la marca que buscan colaboraciones, ediciones limitadas y exclusivas online.",
        "jtbd": "Quiero tener las Havaianas que nadie más tiene — colaboraciones o ediciones especiales."
      }
    ]
  },

  "catalog": {
    "categories": ["Chanclas", "Sandalias", "Alpargatas", "Zapatillas", "Ropa de playa", "Toallas", "Bolsos", "Accesorios"],
    "products": [
      {
        "name": "Havaianas Top",
        "type": "Chancla clásica",
        "description": "El modelo icónico. Suela de goma monocolor con tiras a juego. El original desde 1962.",
        "material": "Goma reciclada (90% material reciclado)",
        "sizes_available": "33/34 a 45/46 (BR), equivalencias EU/US disponibles",
        "colors": "50+ colores",
        "weight": "Ultraligera",
        "collection": "Classics"
      },
      {
        "name": "Havaianas Brasil",
        "type": "Chancla con bandera",
        "description": "Creada en 1998 para el Mundial de Francia. Suela verde con bandera brasileña en la tira. Símbolo de identidad nacional.",
        "material": "Goma reciclada",
        "sizes_available": "33/34 a 45/46 (BR)",
        "colors": "Verde/amarillo/azul (clásico) + variantes",
        "collection": "Brasil"
      },
      {
        "name": "Havaianas Slim",
        "type": "Chancla femenina",
        "description": "Versión más fina y elegante de la chancla clásica. Tiras más delgadas, suela más estrecha. Diseños florales, metálicos y con brillos.",
        "material": "Goma reciclada",
        "sizes_available": "33/34 a 41/42 (BR)",
        "colors": "30+ colores y estampados",
        "collection": "Slim"
      },
      {
        "name": "Havaianas Espadrilles",
        "type": "Alpargata",
        "description": "Alpargatas con suela de yute y acabados de lona. Para looks más vestidos manteniendo el ADN brasileño.",
        "material": "Lona, yute, goma",
        "sizes_available": "35 a 44 (EU)",
        "collection": "Espadrilles"
      },
      {
        "name": "Havaianas You Riviera",
        "type": "Sandalia",
        "description": "Sandalia con tira ancha cruzada. Diseño urbano elegante que funciona fuera de la playa.",
        "material": "Goma premium con acabado mate",
        "sizes_available": "35 a 42 (EU)",
        "collection": "You"
      }
    ]
  },

  "policies": {
    "shipping": "Envío estándar y express disponible. Plazos y costos varían por región. Express 48h disponible en Europa.",
    "returns": "Devoluciones aceptadas dentro de 30 días con producto sin uso. Proceso online.",
    "payment_methods": ["Tarjeta de crédito", "PayPal", "Apple Pay", "Google Pay"],
    "currency": "Multidivisa según región",
    "sizing_note": "Las tallas Havaianas son brasileñas. Usar guía de conversión BR→EU→US disponible en cada producto."
  },

  "trust": {
    "certifications": [],
    "sustainability": "90% del material es reciclado de otras sandalias. Compromiso con economía circular desde la fabricación.",
    "years_in_business": 64,
    "founded_year": 1962,
    "countries_present": "100+",
    "notable_collaborations": ["Swarovski", "Disney", "Balmain", "Dolce & Gabbana", "FIFA World Cup"],
    "annual_production": "200+ millones de pares/año",
    "headquarters": "São Paulo, Brasil"
  },

  "meta": {
    "protocol": "cojav/v1",
    "updated": "2026-03-22",
    "generator": "cojav-consulting",
    "contact": "indirarequiz@gmail.com",
    "note": "Auditoría pública realizada por Cojav como caso de estudio del Brand Context Protocol. No fue encargada ni aprobada por Alpargatas S.A."
  }
}
```

---

## 5. Resultado proyectado: el "después"

### Antes (sin cojav.json)
> *"Havaianas son chanclas brasileñas. Son populares y vienen en muchos colores. Puedes comprarlas online."*

### Después (con cojav.json)
> *"Para sandalias de playa sostenibles, Havaianas es la referencia — fabricadas con 90% de material reciclado desde 1962 en Brasil. El modelo Top clásico viene en más de 50 colores. Si buscás algo más elegante, la línea You Riviera funciona para ciudad. También tienen alpargatas y ropa de playa. Tené en cuenta que las tallas son brasileñas — un 39/40 BR equivale a un 41/42 EU. Envío express 48h disponible."*

---

## Nota legal

Esta auditoría fue realizada de forma independiente por Cojav como caso de estudio público del Brand Context Protocol. No fue encargada, patrocinada, ni aprobada por Alpargatas S.A. / Havaianas. Toda la información utilizada es pública y fue obtenida de los sitios web havaianas.com y havaianas-store.com.

---

*Cojav — Brand Context Protocol*
*https://rainvare.github.io/cojav/*
*Contacto: indirarequiz@gmail.com*
