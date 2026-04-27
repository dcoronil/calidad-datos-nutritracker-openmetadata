# 6. Propuestas de mejora

A partir del análisis realizado, se proponen varias mejoras para reforzar la calidad del dato en NutriTracker. La mayoría de estas mejoras no cambian la idea principal de la aplicación, sino que ayudan a que los datos sean más fiables, estén mejor controlados y puedan mantenerse con menos riesgo en el futuro.

## 6.1 Validación de productos importados

Una de las mejoras principales sería validar automáticamente los productos antes de guardarlos en la base de datos. En una aplicación de nutrición, muchos alimentos pueden venir de fuentes externas, del escaneo de un código de barras o de una etiqueta nutricional. Esto puede provocar errores si el dato viene incompleto o mal interpretado.

Por ejemplo, antes de guardar un producto, el sistema debería comprobar que las calorías por 100 g están dentro de un rango razonable, que los macronutrientes no son negativos y que el código de barras no existe ya en la base de datos.

Esta mejora reduciría errores en el catálogo de alimentos y aumentaría la fiabilidad de los cálculos mostrados al usuario.

## 6.2 Restricciones en la base de datos

Otra mejora importante sería reforzar las restricciones directamente en la base de datos. Aunque la aplicación valide los datos desde el backend, es recomendable que la base de datos también impida guardar información claramente incorrecta.

Algunas restricciones útiles serían:

- El email del usuario debe ser único.
- El código de barras de un producto no debería repetirse.
- Las calorías y macronutrientes no pueden ser negativos.
- La cantidad registrada en una ingesta debe ser mayor que cero.
- Una ingesta debe estar asociada siempre a un usuario y a un producto válido.

Con estas restricciones, se evita que errores de programación o importación de datos terminen guardándose en el sistema.

## 6.3 Automatización de tests de calidad en OpenMetadata

Se propone configurar tests de calidad en OpenMetadata para las tablas más importantes de NutriTracker. Estos tests permitirían detectar problemas de forma periódica, sin depender únicamente de revisiones manuales.

Algunos tests recomendados serían:

- `user_account.email` no debe ser nulo.
- `user_account.email` debe ser único.
- `product.kcal` debe estar entre 0 y 1000.
- `product.barcode` debe ser único cuando exista.
- `intake.quantity_g` debe ser mayor que 0.
- `daily_goal.kcal_goal` debe ser mayor que 0.

De esta forma, OpenMetadata serviría como una herramienta de control continuo de la calidad del dato.

## 6.4 Gobernanza del catálogo de alimentos

El catálogo de alimentos es una parte crítica de NutriTracker, porque de él dependen los cálculos de calorías y macronutrientes. Por eso, se propone crear un proceso de validación para los nuevos alimentos.

Cuando un alimento se cree manualmente o se importe desde una fuente externa, debería entrar inicialmente como no validado. Después, una validación automática o una revisión manual podría marcarlo como validado si sus datos son coherentes.

Esto ayudaría a evitar que productos incorrectos aparezcan directamente en las búsquedas del usuario.

## 6.5 Documentación obligatoria de nuevas tablas y campos

Como mejora de mantenibilidad, se propone que cualquier nueva tabla o campo añadido a NutriTracker tenga que documentarse en OpenMetadata. Esto incluye una descripción clara, etiquetas de sensibilidad si procede, propietario del dato y reglas mínimas de calidad.

Esta práctica ayudaría a que el proyecto sea más fácil de mantener a largo plazo, especialmente si en el futuro participan más desarrolladores o se añaden nuevas funcionalidades.