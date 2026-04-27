Manual de uso de OpenMetadata en el proyecto NutriTracker

Este documento recoge los pasos principales seguidos para utilizar OpenMetadata en el análisis de calidad de datos de la plataforma NutriTracker.
1. Acceso a la herramienta

OpenMetadata se ejecuta de forma local y se accede desde el navegador mediante la siguiente dirección:

    URL: http://localhost:8585

Las credenciales utilizadas para acceder al entorno local son:

    Usuario: admin

    Contraseña: admin

2. Objetivo del uso de OpenMetadata

En este trabajo, OpenMetadata se utiliza para documentar y analizar los principales activos de datos de NutriTracker. La herramienta permite centralizar información sobre tablas, columnas, responsables, etiquetas, glosario y reglas de calidad.

El propósito no es solo visualizar la estructura técnica de la base de datos, sino comprender el significado de cada dato, definir responsabilidades y establecer los controles mínimos de calidad necesarios para el negocio.
3. Activos de datos analizados

Las tablas principales integradas en este análisis son:

    user_account

    user_profile

    product

    intake

    daily_goal

    body_weight_log

    water_intake_log

Estas tablas representan los pilares fundamentales de NutriTracker: gestión de usuarios, perfiles nutricionales, catálogo de alimentos, registro de ingestas, objetivos diarios y seguimiento antropométrico.
4. Proceso de trabajo

El flujo de trabajo dentro de OpenMetadata se organiza en los siguientes pasos:

    Acceso: Iniciar sesión en la instancia local.

    Registro: Revisar o registrar la base de datos de NutriTracker como fuente de datos.

    Identificación: Localizar las tablas principales dentro del catálogo.

    Documentación: Definir descripciones para tablas y columnas, asegurando que los tipos de datos sean correctos.

    Clasificación: Añadir etiquetas (Tags) para identificar datos sensibles o PII (Información de Identificación Personal).

    Gobernanza: Revisar o asignar responsables del dato (Ownership).

    Glosario: Crear y asociar términos de negocio en el Glosario.

    Calidad: Definir reglas y pruebas de calidad (Data Profiler & Quality) para las tablas críticas.

    Evidencia: Generar capturas de pantalla para el informe final.

5. Capturas de evidencia

Las imágenes utilizadas como evidencia se almacenan en la siguiente ruta:

docs/capturas/

Se han previsto las siguientes capturas:

    Pantalla principal (Dashboard) de OpenMetadata.

    Listado completo de tablas de NutriTracker.

    Detalle de la tabla product.

    Detalle de la tabla intake.

    Detalle de la tabla user_profile.

    Glosario de términos de negocio.

    Configuración de reglas de calidad.

    Etiquetado de datos sensibles (Tags).

    Asignación de responsables (Ownership).

6. Observaciones

Este manual es un documento vivo y se irá actualizando conforme se avance en la configuración de la herramienta y se definan nuevos activos o reglas de calidad dentro de OpenMetadata.