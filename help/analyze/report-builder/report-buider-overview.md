---
title: ¿Cuál es la nueva versión de Adobe Report Builder?
description: Describe la nueva funcionalidad del Report Builder
role: User
feature: Report Builder
type: Documentation
solution: Analytics
source-git-commit: 7e8a25381f2eadafc5dc22a0991060ea475b5d43
workflow-type: tm+mt
source-wordcount: '561'
ht-degree: 27%

---

# Acerca del nuevo Adobe Report Builder

El nuevo complemento Report Builder de JavaScript que inicialmente solo estaba disponible en Customer Journey Analytics ahora también se está introduciendo en Adobe Analytics. Esta nueva versión tiene varias ventajas:

- Encuentre perspectivas en Excel de forma más rápida y sencilla con flujos de trabajo mejorados para la creación y administración de bloques de datos, incluida una mayor flexibilidad de bloques de datos
- Cross-platform: no más inicio de sesión en su VM para utilizar Report Builder, ya que ahora se admiten PC, Mac y Excel Online
- Menos tiempo de espera para que se devuelvan los bloques de datos, gracias a la actualización a la API 2.0
- Se ha mejorado la velocidad.

>[!NOTE]
>
>La programación de libros para esta versión de Report Builder en Adobe Analytics aún no se ha publicado, pero estará disponible a principios de 2025. Ahora puede empezar a trabajar con libros que no requieran programación.

Los usuarios de la herramienta Report Builder heredado pueden [convertir libros heredados](/help/analyze/report-builder/convert-workbooks.md) al nuevo Report Builder.

Report Builder permite crear, editar y actualizar fácilmente informes personalizados con datos de Adobe Analytics. Con la sencilla y flexible IU de arrastrar y soltar de Report Builder, puede crear consultas de datos complejas e informes personalizados a partir de datos de Adobe Analytics, todo ello dentro de Excel.

Con Report Builder, puede:

- Hacer referencia a celdas de la hoja de trabajo existente para obtener el orden de fila, el intervalo de fecha o el filtro perfecto
- Crear fechas personalizadas con el calendario, referencias a celdas o aritmética de fechas
- Diseñar tablas y visualizaciones con herramientas habituales para dar formato de Excel

## Uso del Report Builder heredado y el nuevo Report Builder en paralelo

Puede seguir utilizando ambas versiones de Report Builder, con las siguientes advertencias:

- No utilice ambas versiones de Report Builder en el mismo archivo al mismo tiempo. Son mutuamente excluyentes.
- Puede seguir utilizando Report Builder heredado en libros heredados y el nuevo Report Builder en libros nuevos.
- Además, puede [convertir automáticamente libros heredados](/help/analyze/report-builder/convert-workbooks.md) al nuevo formato de Report Builder. Antes de hacerlo, duplique y cambie el nombre del archivo.

## Funciones de Report Builder heredadas no admitidas en el nuevo Report Builder

Al comparar la funcionalidad de un Report Builder heredado con la del nuevo complemento Report Builder, algunas funciones heredadas ya no están disponibles:

- Solicitudes en tiempo real

- Informes de ruta/abandonos

- Opción de FTP para informes programados

- Métricas de visitantes. Las siguientes métricas se convertirán en &quot;visitantes únicos&quot;, aunque el resultado del informe puede no ser una coincidencia exacta: `visitorshourly`, `visitorsdaily`, `visitorsweekly`, `visitorsmonthly`, `visitorsquarterly` y `visitorsyearly`. Esto también se aplica a `mobilevisitorshourly`, `mobilevisitorsdaily`, `mobilevisitorsweekly`, `mobilevisitorsmonthly`, `mobilevisitorsquarterly` y `mobilevisitorsyearly`.

## Casos de uso comunes

- **Extracción de datos**: Adobe Report Builder le permite extraer datos de Adobe Analytics a Excel. Puede crear informes y consultas personalizadas para recuperar puntos de datos específicos relevantes para el análisis.

- **Creación de informes personalizados**: puede diseñar y dar formato a informes personalizados en Excel para adaptarlos a sus necesidades específicas de creación de informes. Esto resulta especialmente útil para adaptar los informes a las distintas partes interesadas.

- **Ad Hoc Analysis**: los usuarios pueden generar rápidamente informes ad-hoc para responder preguntas específicas o explorar tendencias de datos sin tener que pasar por un largo proceso de creación de informes.

- **Tablero**: los datos extraídos de CJA se pueden utilizar para crear paneles y visualizaciones basados en Excel para obtener una visión general de alto nivel de los indicadores clave de rendimiento (KPI).

- **Compartir perspectivas**: puede compartir informes y perspectivas de Excel con integrantes del equipo o partes interesadas que pueden no tener acceso directo a CJA.

## Vídeo de información general

>[!IMPORTANT]
>
>Este vídeo de información general muestra la interfaz de usuario del Report Builder en Customer Journey Analytics. Algunos términos y la interfaz de usuario son diferentes. De lo contrario, la experiencia del usuario es idéntica.

>[!VIDEO](https://video.tv.adobe.com/v/337569/?quality=12&learn=on)

Puede descargar Report Builder desde [Microsoft Store](https://appsource.microsoft.com/en-us/product/office/WA200003101?tab=Overview).
