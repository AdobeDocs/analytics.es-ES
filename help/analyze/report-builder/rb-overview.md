---
title: Información general de Report Builder
description: Describe la funcionalidad de Report Builder
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: b6f2b1f5-8790-4342-85c8-524fdf346073
source-git-commit: 9a2d4c582b6a3946b658924851e5b5ada2f5a7ee
workflow-type: ht
source-wordcount: '527'
ht-degree: 100%

---

# Información general de Report Builder

El nuevo complemento Report Builder de JavaScript, inicialmente solo disponible en Customer Journey Analytics, ahora también está en Adobe Analytics. Esta nueva versión presenta varias ventajas:

- Encuentre información útil Excel de forma más rápida y sencilla con flujos de trabajo mejorados para la creación y administración de bloques de datos, incluida una mayor flexibilidad de bloques de datos
- Plataformas múltiples: ya no es necesario iniciar sesión en la VM, puesto que puede utilizar Report Builder en Excel en línea en ordenadores de escritorio y Mac.
- Menos tiempo de espera para que se devuelvan los bloques de datos, gracias a la actualización a la API 2.0
- Mejoramiento de la velocidad

Los usuarios de la herramienta Report Builder heredada pueden [convertir los libros heredados](/help/analyze/report-builder/convert-workbooks.md) al nuevo Report Builder.

Report Builder le permite crear, editar y actualizar fácilmente informes personalizados utilizando datos de Adobe Analytics. Con la sencilla y flexible IU de tipo &quot;arrastrar y soltar&quot; de Report Builder, puede crear consultas de datos complejas e informes personalizados a partir de datos de Adobe Analytics, todo ello dentro de Excel.

Con Report Builder, puede:

- Hacer referencia a celdas de la hoja de trabajo existente para obtener el orden de fila, el intervalo de fecha o el filtro perfecto
- Crear fechas personalizadas con el calendario, referencias a celdas o aritmética de fechas
- Diseñar tablas y visualizaciones con herramientas habituales para dar formato de Excel

## Uso simultáneo del Report Builder heredado y del nuevo Report Builder

Puede seguir utilizando ambas versiones de Report Builder, con las siguientes salvedades:

- No utilice ambas versiones de Report Builder en el mismo archivo al mismo tiempo. Son mutuamente excluyentes.
- Puede seguir utilizando el Report Builder heredado en los libros heredados y el Report Builder nuevo en los libros nuevos.
- Además, puede [convertir automáticamente los libros heredados](/help/analyze/report-builder/convert-workbooks.md) al nuevo formato de Report Builder. Antes de hacerlo, duplique y cambie el nombre del archivo.

## Las funciones heredadas de Report Builder no son compatibles con el nuevo Report Builder

Al comparar la funcionalidad del Report Builder heredado con el nuevo complemento de Report Builder, algunas de las funcionalidades heredadas ya no están disponibles:

- Solicitudes en tiempo real

- Informes de rutas/visitas en el orden previsto

- Opción de FTP para informes programados

- Métricas de visitantes. Las siguientes métricas se convierten en “visitantes únicos”, aunque el resultado del sistema de informe puede no generar una coincidencia exacta: `visitorshourly`, `visitorsdaily`, `visitorsweekly`, `visitorsmonthly`, `visitorsquarterly` y `visitorsyearly`. Esto también se aplica a `mobilevisitorshourly`, `mobilevisitorsdaily`, `mobilevisitorsweekly`, `mobilevisitorsmonthly`, `mobilevisitorsquarterly` y `mobilevisitorsyearly`.

## Casos de uso comunes

- **Extracción de datos**: Adobe Report Builder permite extraer datos de Adobe Analytics a Excel. Puede crear informes y consultas personalizadas para recuperar puntos de datos específicos relevantes para el análisis.

- **Creación de informes personalizados**: puede diseñar y dar formato a informes personalizados en Excel para adaptarlos a sus necesidades específicas de creación de informes. Esto resulta especialmente útil para adaptar los informes a las distintas partes interesadas.

- **Ad Hoc Analysis**: los usuarios pueden generar rápidamente informes ad-hoc para responder preguntas específicas o explorar tendencias de datos sin tener que pasar por un largo proceso de creación de informes.

- **Tablero**: los datos extraídos de CJA se pueden utilizar para crear paneles y visualizaciones basados en Excel para obtener una visión general de alto nivel de los indicadores clave de rendimiento (KPI).

- **Compartir perspectivas**: puede compartir informes y perspectivas de Excel con integrantes del equipo o partes interesadas que pueden no tener acceso directo a CJA.

## Vídeo de información general

>[!IMPORTANT]
>
>En este vídeo de información general se muestra la interfaz de usuario de Report Builder en Customer Journey Analytics. Algunos de los términos y la interfaz de usuario son diferentes. De lo contrario, la experiencia del usuario es idéntica.


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut ](/help/assets/icons/VideoCheckedOut.svg) [Información general de Report Builder](https://video.tv.adobe.com/v/3452583?quality=12&learn=on&captions=spa){target="_blank"} para ver un vídeo de demostración.

>[!ENDSHADEBOX]

Puede descargar Report Builder desde [Microsoft Store](https://appsource.microsoft.com/es-es/product/office/WA200003101?tab=Overview).
