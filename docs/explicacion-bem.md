# Justificación de Decisiones de Diseño BEM

## Metodología Utilizada
Todo el proyecto sigue la metodología BEM (Block, Element, Modifier) para garantizar un código CSS escalable, mantenible y reutilizable.

## Decisiones de Nomenclatura

### 1. Bloques Independientes
Cada sección de la página es un bloque independiente con un nombre descriptivo:
- `.header` (cabecera)
- `.hero` (sección principal)
- `.features` (características)
- `.testimonials` (testimonios)
- `.pricing` (precios)
- `.contact-form` (formulario de contacto)
- `.footer` (pie de página)

**Justificación:** Los bloques deben tener sentido por sí mismos y no depender de su entorno. Por ejemplo, `.features` podría reutilizarse en otra página sin conflictos.

### 2. Elementos con Doble Guión Bajo (__)
Los elementos internos de cada bloque se nombran con el patrón `.bloque__elemento`:
- `.hero__title`
- `.feature-card__icon`
- `.testimonial__avatar`

**Justificación:** Esta convención deja claro a qué bloque pertenece cada elemento y evita anidamientos complejos como `.hero__title__subtitle` (lo cual sería incorrecto en BEM).

### 3. Modificadores con Doble Guión Medio (--)
Las variaciones de bloques o elementos usan `.bloque--modificador`:
- `.button--primary` (variación de color)
- `.button--large` (variación de tamaño)
- `.feature-card--featured` (tarjeta destacada)
- `.pricing-card--featured` (plan destacado)
- `.testimonial--featured` (testimonio destacado)

**Justificación:** Los modificadores definen la apariencia, estado o comportamiento. Todos los botones comparten la clase base `.button`, pero cada variante añade su modificador específico. Esto permite reutilizar el bloque base y solo cambiar lo necesario.

### 4. Nombres Descriptivos (No Apariencia)
- ✓ `.button--primary` (propósito)
- ✗ `.button--red` (apariencia)
- ✓ `.feature-card--featured` (propósito)
- ✗ `.feature-card--big` (apariencia)

**Justificación:** Si el día de mañana cambiamos el color primario de rojo a azul, el nombre `.button--primary` sigue siendo válido, mientras que `.button--red` quedaría obsoleto.

### 5. Estados con Pseudo-clases
Para estados interactivos usamos pseudo-clases CSS sobre las clases BEM:
- `.header__link:hover`
- `.button--primary:hover`
- `.contact-form__input:focus`

**Justificación:** Mantenemos la especificidad baja y evitamos clases adicionales como `.button--hover`.

## Conclusión
La aplicación consistente de BEM permite que el código sea predecible, fácil de mantener y escalable. Cualquier desarrollador que conozca BEM puede entender la estructura del proyecto rápidamente.