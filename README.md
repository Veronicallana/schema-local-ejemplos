# Schema orientado a SEO Local  
### Modelado de entidades para Proximidad, Relevancia y Prominencia

Este repositorio recopila **ejemplos y patrones de marcado de datos estructurados (schema.org)** pensados específicamente para **SEO local**, no para rich snippets ni validadores.

El objetivo no es “activar resultados enriquecidos”, sino **ayudar a los motores de búsqueda a entender correctamente las entidades locales**, reducir ambigüedad y consolidar señales reales relacionadas con **proximidad, relevancia y prominencia**.

---

## Enfoque del repositorio

El marcado de datos estructurados **no sustituye** los factores de ranking local.  
Su función es **modelar y conectar información que ya existe** de forma coherente y legible para buscadores y sistemas basados en entidades.

Este repositorio se centra en responder a tres preguntas clave:

- ¿Dónde está esta entidad y qué presencia local real tiene?
- ¿Qué servicios presta y para qué tipo de búsquedas es relevante?
- ¿Qué reputación, referencias externas y señales de autoridad tiene?

---

## Marco conceptual: los 3 factores del SEO Local

### 1. Proximidad (cercanía al usuario)

La proximidad no se “optimiza” con schema, pero **sí se puede desambiguar**.

El marcado correcto ayuda a Google a entender:
- qué entidad corresponde a qué ubicación
- dónde existe presencia física real
- qué sede es relevante para una búsqueda concreta

#### Propiedades clave
- `address` (NAP limpio y consistente)
- `geo` (`GeoCoordinates`)
- `hasMap` (URL directa de Google Maps)
- `openingHoursSpecification`
- `telephone`
- `@id` estable por sede

#### Principios
- Cada sede física debe ser **una entidad propia**
- No mezclar zonas de servicio con ubicaciones físicas
- No usar una única dirección para “cubrir” múltiples ciudades

---

### 2. Relevancia (coincidencia con la búsqueda)

La relevancia no consiste en repetir keywords, sino en **definir con claridad de qué trata una página y qué servicio representa**.

El schema ayuda a:
- desambiguar servicios
- contextualizar páginas locales
- diferenciar marca, sede y servicio

#### Propiedades clave
- `about` (conceptos, no la empresa)
- `additionalType` (Wikidata del sector)
- `Service`, `Offer`, `provider`
- `serviceArea`
- `isPartOf`

#### Principios
- `about` se usa para **temas**, no para enlazar a la propia entidad
- Las páginas de servicio local no siempre son sedes físicas
- El objetivo es alinear **intención + contexto + entidad**

---

### 3. Prominencia (reputación y autoridad)

La prominencia no se crea con schema, pero **sí se consolida**.

El marcado permite conectar la entidad con:
- perfiles oficiales
- asociaciones profesionales
- menciones en medios
- reseñas reales

#### Propiedades clave
- `sameAs`
- `memberOf`
- `award`
- `brand`
- `subjectOf`
- `review`
- `aggregateRating` (solo si es real y coherente)

#### Principios
- No inventar señales
- No enlazar perfiles no oficiales
- Las reseñas deben coincidir con lo que ve el usuario

---

## Qué entra en este repositorio

### Sí entra
- Modelado de `LocalBusiness` y subtipos correctos
- Separación clara entre:
  - organización (marca)
  - sede física
  - página de servicio
- Ejemplos para:
  - Home
  - páginas de localización
  - páginas de servicio local
  - páginas de contacto
- Uso de `@graph` cuando hay múltiples entidades
- IDs canónicos y reutilizables

### No entra
- Hacks de posicionamiento
- Rich snippets (FAQ, HowTo, etc.)
- “Trucos” para forzar el Local Pack
- Listados masivos de ciudades en `areaServed`
- Propiedades solo porque “existen en schema.org”
- Datos no verificables o inventados

---

## Principios de uso

- El schema debe reflejar **lo que ve el usuario**
- Menos propiedades bien conectadas > muchas sin contexto
- Una entidad mal definida es peor que ninguna
- La coherencia entre páginas es más importante que el detalle extremo

---

## Nota final

Este repositorio no pretende “hacer ranking”, sino **modelar entidades locales de forma correcta y sostenible**.

El objetivo es que:
- Google entienda mejor quién es la entidad
- no haya ambigüedad entre sedes, servicios y marca
- las señales reales de proximidad, relevancia y prominencia se consoliden a largo plazo


## Anti-patterns y errores comunes

Antes de aplicar cualquiera de los ejemplos de este repositorio, es importante entender qué **no** hacer al trabajar con datos estructurados para SEO local.

👉 [Ver anti-patterns y errores comunes](anti-patterns.md)


