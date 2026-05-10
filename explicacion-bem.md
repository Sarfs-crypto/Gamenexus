# Justificación de Decisiones de Diseño BEM - GameNexus

## 1. Estructura de Bloques
Se crearon bloques independientes y reutilizables para cada sección principal de la landing page, siguiendo el principio de que cada bloque debe tener sentido por sí mismo:
- **header:** Contiene la navegación y la identidad de la marca. Es independiente del contenido.
- **hero:** Sección de presentación principal con un alto impacto visual.
- **features, testimonials, pricing, contact-form, footer:** Cada uno encapsula su propio contenido y estilos.

## 2. Nomenclatura de Elementos
Se utilizó la convención `bloque__elemento` para identificar las partes internas de un bloque, dejando claro que no tienen sentido fuera de él:
- `.hero__title`, `.hero__subtitle`: Definen la tipografía y el layout del texto dentro del héroe.
- `.feature-card__icon`, `.feature-card__title`, `.feature-card__description`: Organizan el contenido visual de las tarjetas de características.
- `.testimonial__avatar`, `.testimonial__quote`, `.testimonial__author`: Estructuran cada tarjeta de testimonio.

## 3. Uso de Modificadores
Se aplicó la convención `bloque--modificador` para variantes de un mismo componente base, evitando la duplicación de código CSS:
- **`.button--primary` / `.button--secondary` / `.button--large`:** El botón base (`.button`) define la estructura general, mientras que los modificadores solo cambian el color de fondo o el tamaño. Si en el futuro se desea cambiar el color primario de la marca, solo se edita el modificador.
- **`.feature-card--featured`, `.testimonial--featured`, `.pricing-card--featured`:** Todas las secciones tienen una variante "destacada" que aplica un borde de color acento y una sombra especial para resaltar un elemento sobre los demás.

## 4. Nombres Descriptivos (Propósito vs. Apariencia)
Los nombres de las clases describen la función o el propósito, no el estilo visual. Esto asegura que el código sea mantenible a largo plazo:
- *Correcto:* `.button--primary` (describe su importancia).
- *Incorrecto:* `.button--red` (si el color cambia, el nombre queda obsoleto).
- *Correcto:* `.pricing-card--featured` (describe su función de destacar).
- *Incorrecto:* `.pricing-card--big` (no es descriptivo de su propósito).

## 5. Conclusión
La aplicación estricta de BEM resulta en un código CSS con muy baja especificidad, predecible y fácil de leer. Cualquier desarrollador nuevo en el proyecto puede entender la estructura de la interfaz solo con leer las clases HTML.
