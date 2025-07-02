---
description: Obtenga información sobre los errores y la resolución de problemas de Analysis Workspace.
title: Errores En La Resolución De Problemas En Analysis Workspace
feature: Workspace Basics
role: User, Admin
exl-id: e5c6f710-a205-48db-aeee-ee5b83c42795
source-git-commit: 0146d0798571d8589a74fb6d3fbbd574af224631
workflow-type: tm+mt
source-wordcount: '583'
ht-degree: 97%

---

# Errores y solución de problemas

Puedes encontrar errores al interactuar con Analysis Workspace que también afectarán a su funcionalidad o rendimiento. A continuación se enumeran los tipos de error más comunes, por qué se producen y las optimizaciones que se pueden realizar.

## Mensajes de error

Algunos mensajes de error comunes que puedes ver al utilizar Analysis Workspace:

| Mensaje de error | ¿Por qué se produce el error? | Optimización |
| --- | --- | --- |
| [!UICONTROL La vista de datos está experimentando una creación de informes inusualmente alta. Inténtelo nuevamente más tarde.] | Su organización está intentando ejecutar demasiadas solicitudes simultáneas en una vista de informes específica. Los factores que contribuyen a este error son las solicitudes de API, los proyectos programados, los informes programados, las alertas programadas y los usuarios simultáneos que realizan solicitudes de informes. | Distribuya las solicitudes y programaciones de la vista de informes de forma más uniforme durante todo el día.<p>Los administradores pueden usar el [Administrador de actividades de creación de informes para identificar y cancelar las solicitudes](/help/admin/admin/reporting-activity-manager/reporting-activity-overview.md) que consumen capacidad de creación de informes.</p> |
| [!UICONTROL Este informe es demasiado complejo. Consulte las prácticas recomendadas para generar informes de Analysis Workspace.] | La solicitud de creación de informes es demasiado grande y no se puede ejecutar. Los factores que contribuyen a este error son los tiempos de espera debido a la complejidad de la solicitud. | Simplifica tu solicitud. Por ejemplo, acortar el intervalo de fechas, simplificar los criterios de segmento o quitar algunas columnas o filas de la tabla. O bien, considera la posibilidad de dividir la tabla en solicitudes independientes. |
| [!UICONTROL Actualmente, la vista de datos supera su capacidad de creación de informes. Simplifique la solicitud o inténtelo de nuevo más tarde.] | Su organización está intentando ejecutar demasiadas solicitudes simultáneas en una vista de informes específica. Los factores que contribuyen a este error son las solicitudes de API, los proyectos programados y los usuarios simultáneos que realizan solicitudes de informes. | Distribuya las solicitudes y programaciones de la vista de informes de forma más uniforme durante todo el día. |
| [!UICONTROL Se ha producido un error del sistema. Registre una solicitud del Servicio de atención al cliente en **[!UICONTROL Ayuda > Enviar ticket de asistencia técnica]** e incluya su código de error.] | Adobe está experimentando un problema que debe resolverse. | Envíe el código de error al Servicio de atención al cliente. |
| [!UICONTROL Error 500: No se pudo cargar la página] | Los problemas con la red local, como la [configuración del firewall](/help/technotes/ip-addresses.md) de la compañía, son un factor que contribuye a este error. Además, es posible que el Adobe esté experimentando un problema que debe resolverse. | Intente iniciar sesión nuevamente después de varios minutos. Si el problema persiste, envíe el código de ID de instancia de EIM al Servicio de atención al cliente. |
| [!UICONTROL Su solicitud falló como resultado de demasiadas columnas o filas preconfiguradas.] | La tabla tiene demasiadas celdas improvisadas (columnas de fila *). | Elimine columnas o filas de la tabla, o bien considere la posibilidad de dividir la tabla en solicitudes independientes. |


## Resolución de problemas

Al utilizar Analysis Workspace, puedes utilizar la información siguiente para solucionar algunos problemas comunes.

| Problema | Pasos para solucionar los problemas |
|---|---|
| Cuando arrastro una métrica, dice *“Datos no válidos”*. | Datos no válidos significa que Adobe no puede devolver datos mediante la combinación de dimensiones y métricas utilizadas en el informe. Por ejemplo: dos métricas apiladas una encima de la otra no se pueden devolver como datos, ya que no hay forma de mostrar dos métricas de esa manera. En su lugar, coloque las métricas una al lado de la otra. |
| Cuando arrastro una métrica, no veo ningún dato real, solo ceros. | Si ha creado correctamente un informe de Workspace pero no hay datos, puede comprobar algunas cosas:<ul><li>Si aplicó un segmento en el informe, es posible que los criterios del segmento no coincidan con ningún dato. Intente eliminar el segmento o ajustar la definición del mismo.</li><li>Comprueba el intervalo de fechas en la esquina superior derecha y comprueba que está establecido en un valor que esperabas.</li><li>Vaya al sitio web y utilice [Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=es) para validar que se están recopilando datos.</li></ul> |



<!--
# Common error messages

You may encounter errors when interacting with Analysis Workspace that will also influence performance. Listed below are the most common error types, why they occur, and optimizations that can be made.

| Error message | Why does this occur? | Optimization |
| --- | --- | --- |
| [!UICONTROL The report suite is experiencing unusually heavy reporting. Please try again later.] | Your organization is trying to run too many concurrent requests against a specific report suite. Contributors to this error are API requests, scheduled projects, and concurrent users making reporting requests. | Spread your requests and schedules for the report suite more evenly throughout the day. <p>Administrators can use the [Reporting Activity Manager to identify and cancel requests](/help/admin/admin/reporting-activity-manager/reporting-activity-overview.md) that are consuming reporting capacity. |
| [!UICONTROL The report suite is currently exceeding its reporting capacity. Please simplify the request or try again later.] |  Your organization is trying to run too many concurrent requests against a specific report suite. Contributors to this error are API requests, scheduled projects, scheduled reports, scheduled alerts, and concurrent users making reporting requests. | Spread your requests and schedules for the report suite more evenly throughout the day. |
| [!UICONTROL A system error has occurred. Please log a Customer Care request under Help > Submit Support Ticket and include your error code.] | Adobe is experiencing an issue that needs to be resolved. | Submit the error code to Customer Care. |
| [!UICONTROL An unexpected error has occurred; try refreshing your project again. If the problem persists, please submit this error ID to Adobe Customer Care for further diagnosis.] | Adobe is experiencing an issue that needs to be resolved. | Try refreshing your project and if the problem persists, submit the error code to Customer Care. |
| [!UICONTROL Error 500: Failed to load page] | Issues with your local network, such as company [firewall settings](https://experienceleague.adobe.com/docs/analytics/technotes/ip-addresses.html), are a contributing factor to this error. Additionally, Adobe may be experiencing an issue that needs to be resolved. | Try logging in again after several minutes. If the issue persists, submit the EIM instance ID code to Customer Care. |
| [!UICONTROL One of the segments or the search in this visualization contains a text search that returned too many results.] | Your segment criteria or report filter is too broad. | Narrow your search text criteria and try the request again. |
| [!UICONTROL This dimension does not currently support non-default attribution models.] | Non-default attribution is not supported for the dimension that you are using. | Replace the dimension in your table with one that is compatible with [Attribution](/help/analyze/analysis-workspace/attribution/overview.md). |
| [!UICONTROL Your request failed as a result of too many columns or pre-configured rows.] | Your table has too many freeform cells (row * columns). | Remove columns or rows in your table, or consider splitting the table into separate requests. |
-->