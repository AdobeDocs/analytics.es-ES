---
description: La opción Incluir datos actuales de Reports & Analytics le permite ver los datos de Analytics más recientes, con frecuencia antes incluso de que dichos datos se hayan completado y procesado totalmente. Datos actuales muestra la mayoría de las métricas en cuestión de minutos y proporciona datos procesables que facilitan una toma de decisiones rápida.
subtopic: Current Data
title: Datos actuales
topic: Reports
uuid: 601d3695-be13-4b7f-9df0-de01c8bd64ee
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Datos actuales

La opción Incluir datos actuales de Reports &amp; Analytics le permite ver los datos de Analytics más recientes, con frecuencia antes incluso de que dichos datos se hayan completado y procesado totalmente. Datos actuales muestra la mayoría de las métricas en cuestión de minutos y proporciona datos procesables que facilitan una toma de decisiones rápida.

Es visible como una opción como parte de la configuración de un informe:

![Captura de pantalla Datos actuales](assets/current_data.png)

Datos actuales está habilitado de forma predeterminada en todos los informes compatibles. Si prefiere ver todas las métricas una vez que los datos se hayan procesado completamente, existen varias opciones:

* Utilice Analysis Workspace, que utiliza datos completamente procesados.
* Haga clic en 'No' en la configuración del informe de datos actual para usar solamente los datos completamente procesados.
* Elimine el elemento de permiso 'Datos actuales' de un perfil de producto en Admin Console para evitar que los usuarios que no son administradores vean esta opción. Consulte los elementos [de permiso Herramientas de](/help/admin/admin-console/permissions/analytics-tools.md) Analytics en la guía del usuario de Administración para obtener más información.

Debido a la disponibilidad de los datos con prioridad, los datos actuales no se pueden utilizar actualmente con segmentos, clasificaciones, desgloses, rutas y algunas métricas. Si se utiliza una de estas características, los datos actuales se obligan a 'No' en el informe y se muestra un aviso amarillo que explica por qué no se encuentran disponibles los datos actuales.

![Aviso de datos actual](assets/current_data_notice.png)

## Latencia de datos actuales típica

Las métricas aparecen en uno de los tres lapsos de tiempo siguientes. Al hacer clic en el icono de reloj que aparece junto al botón de alternancia Incluir datos actuales, se muestra el valor de latencia real de las distintas métricas del informe.

| Lapso de tiempo | Métricas |
| --- | --- |
| Menos de 10 minutos | Instancias y vistas de página en variables de tráfico |
| Entre 10 y 35 minutos | Eventos de conversión, instancias y vistas de página en variables de conversión |
| Entre 45 y 120 minutos | Todos los demás datos, como visitas, visitantes únicos y participación |

Debido a que algunos de los datos que se muestran en la vista de datos actual no se han procesado completamente, puede ver una diferencia entre los valores informados en la vista de datos actual y la vista finalizada. En los informes de tendencias, la diferencia de los datos suele alcanzar un 1%.

## Métricas calculadas

Las métricas calculadas pueden crearse con métricas de latencia variada, por lo que es posible que algunos valores recientes se calculen en la vista de datos actuales con datos incompletos.

Por ejemplo, se crea la métrica calculada 'Vistas de página por visita mediante la fórmula `Page Views divided by Visits`. Las vistas de página suelen aparecer en 10 minutos y las visitas suelen aparecer en 2 horas. Las métricas calculadas dentro de esta ventana de latencia se calculan usando métricas incompletas. Si publica una página nueva que obtiene 4000 visitas de 4000 visitas diferentes en un intervalo de tiempo de 2 horas, la diferencia de latencia entre estas métricas puede causar cálculos incompletos.

Esta diferencia de datos es más visible cuando se generan informes sobre nuevos valores o se utilizan intervalos de tiempo cortos. Cuando un informe utiliza intervalos de fechas más largos, es poco probable que las diferencias de latencia que se producen en las últimas horas de generación de informes tengan un impacto significativo en las métricas calculadas.

Si ha calculado métricas que podrían verse afectadas por estas diferencias, desactive los datos actuales o utilice métricas con la misma ventana de latencia esperada.

## Informes descargados

Al descargar un informe con la vista de datos actuales habilitada, el informe se coloca en cola, se genera y a continuación se devuelve al explorador. Si los datos se recopilan mientras se genera el informe, esos datos se muestran en el informe. Esta ventana de tiempo puede hacer que el informe descargado tenga un poco más de datos.
