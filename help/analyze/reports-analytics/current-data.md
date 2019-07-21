---
description: La opción Incluir datos actuales de Reports & Analytics le permite ver los datos de Analytics más recientes, con frecuencia antes incluso de que dichos datos se hayan completado y procesado totalmente. Datos actuales muestra la mayoría de las métricas en cuestión de minutos y proporciona datos procesables que facilitan una toma de decisiones rápida.
seo-title: Datos actuales
solution: Analytics
subtopic: Datos actuales
title: Datos actuales
topic: 'Informes '
uuid: 601 d 3695-be 13-4 b 7 f -9 df 0-de 01 c 8 bd 64 ee
translation-type: tm+mt
source-git-commit: 1fdd14497171dbf5850ec1b1d873a06931d58435

---


# Datos actuales

La opción Incluir datos actuales de Reports &amp; Analytics le permite ver los datos de Analytics más recientes, con frecuencia antes incluso de que dichos datos se hayan completado y procesado totalmente. Datos actuales muestra la mayoría de las métricas en cuestión de minutos y proporciona datos procesables que facilitan una toma de decisiones rápida.

Es visible como una opción como parte de la configuración de un informe:

![Captura de pantalla de datos actuales](assets/current_data.png)

Datos actuales está habilitado de forma predeterminada en todos los informes compatibles. Si prefiere ver todas las métricas una vez que se hayan procesado todos los datos, existen varias opciones:

* Utilice Analysis Workspace, que utiliza datos totalmente procesados.
* Haga clic en'No'en la configuración del informe de datos actual para utilizar solamente datos completamente procesados.
* Elimine el elemento de permiso'Datos actuales'de un perfil de producto en la Consola de administración para evitar que los usuarios no administradores vean esta opción. See [Analytics Tools permission items](../../admin/admin-console/permissions/analytics-tools.md) in the Admin user guide for more information.

Debido a la prioridad de la disponibilidad de los datos, actualmente no se pueden utilizar los datos actuales con segmentos, clasificaciones, desgloses, rutas y algunas métricas. Si se utiliza una de estas funciones, los datos actuales se forzarán a'No'en el informe y aparece un aviso amarillo que explica por qué los datos actuales no están disponibles.

![Aviso de datos actuales](assets/current_data_notice.png)

## Latencia de datos actuales típica

Las métricas aparecen en uno de los tres lapsos de tiempo siguientes. Al hacer clic en el icono de reloj que aparece junto al botón de alternancia Incluir datos actuales, se muestra el valor de latencia real de las distintas métricas del informe.

| Lapso de tiempo | Métricas |
| --- | --- |
| Menos de 10 minutos | Instancias y vistas de páginas en variables de tráfico |
| Entre 10 y 35 minutos | Eventos de conversión, instancias y vistas de página en variables de conversión |
| Entre 45 y 120 minutos | Todos los demás datos, como visitas, visitantes únicos y participación |

Dado que algunos de los datos que se muestran en la vista de datos actual no se han procesado completamente, puede ver una diferencia entre los valores informados en la vista de datos actual y la vista completada. En los informes de tendencias, la diferencia de los datos suele alcanzar un 1%.

## Métricas calculadas

Las métricas calculadas pueden crearse con métricas de latencia variada, por lo que es posible que algunos valores recientes se calculen en la vista de datos actuales con datos incompletos.

For example, you create the calculated metric 'Page Views per Visit using the formula `Page Views divided by Visits`. Las vistas de página suelen aparecer en menos de 10 minutos y las visitas suelen aparecer en 2 horas, las métricas calculadas dentro de esta ventana de latencia se calculan usando métricas incompletas. Si publica una página nueva que recibe 4000 visitas de 4000 visitas diferentes durante un intervalo de tiempo de 2 horas, la diferencia de latencia entre estas métricas puede provocar cálculos incompletos.

Esta diferencia de datos es la más visible al generar informes sobre nuevos valores o utilizar intervalos de tiempo cortos. Cuando un informe utiliza intervalos de fechas más largos, las diferencias de latencia que se producen en las últimas horas de los informes no tendrán ningún impacto significativo en las métricas calculadas.

Si tiene métricas calculadas que pueden verse afectadas por estas diferencias, desactive los datos actuales o utilice métricas con la misma ventana de latencia esperada.

## Informes descargados

Al descargar un informe con la vista de datos actuales habilitada, el informe se coloca en cola, se genera y a continuación se devuelve al explorador. Si se recopilan datos mientras se genera el informe, esos datos aparecen en el informe. Esta ventana de tiempo puede llevar al informe descargado con un poco más de datos.
