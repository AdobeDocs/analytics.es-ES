---
description: La ficha Uso del grupo de informes proporciona datos sobre el uso del servidor para cada grupo de informes en todas las empresas de inicio de sesión asociadas a su empresa de facturación durante el periodo de uso actual.
title: Ver uso del grupo de informes
feature: Server Call Usage
exl-id: bedd4ed8-1c8b-45fd-a059-fed88e9fbe73
role: Admin
source-git-commit: 938795c7378cb1f0537ff84eddeab3feddf8d073
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 99%

---

# Ver uso del grupo de informes

La ficha Uso del grupo de informes proporciona datos sobre el uso del servidor para cada grupo de informes en todas las empresas de inicio de sesión asociadas a su empresa de facturación durante el periodo de uso actual.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Uso de llamadas al servidor]** > **[!UICONTROL Uso del grupo de informes]**

>[!IMPORTANT]
>
>Si un grupo de informes no está vinculado a una organización de Experience Cloud, sus datos de uso no se reflejarán en este panel. También se puede asociar un ID de facturación a varias organizaciones de Experience Cloud; no siempre hay una relación 1:1 entre una organización y un ID de facturación.

El tablero de Uso del grupo de informes:

* Muestra el uso de llamadas al servidor del periodo de uso actual (todas las llamadas, primarias, secundarias, primarias móviles, secundarias móviles) para cada grupo de informes de su organización de Experience Cloud.
* Muestra el porcentaje del uso global por categoría de llamadas al servidor.
* Se actualiza a diario.
* Se puede descargar.
* Permite acceder a la interfaz de usuario de **[!UICONTROL Administrar alertas]**.

![](/help/admin/admin/c-server-call-usage/assets/report-suite-usage.png)

## Configuración del panel {#settings}

| Columna | Definición |
|--- |--- |
| Nombre del grupo de informes | Nombre descriptivo del grupo de informes. |
| Todas las llamadas (% del total) | Todas las llamadas al servidor en las que se ha incurrido en el periodo de uso actual. |
| Llamadas primarias (%) | Todas las llamadas al servidor primarias (y su porcentaje del total) en las que se ha incurrido en el periodo de uso actual. |
| Llamadas secundarias (%) | Todas las llamadas al servidor secundarias (y su porcentaje del total) en las que se ha incurrido en el periodo de uso actual. |
| Primarias móviles (%) | Todas las llamadas al servidor primarias móviles (y su porcentaje del total) en las que se ha incurrido en el periodo de uso actual. |
| Secundarias móviles (%) | Todas las llamadas al servidor secundarias móviles (y su porcentaje del total) en las que se ha incurrido en el periodo de uso actual. |

{style="table-layout:auto"}

## Descargar informe de uso {#download}

Esta opción permite descargar los datos de uso actual y datos de periodos anteriores al periodo de uso actual (hasta enero de 2015). El informe se descarga como archivo .csv.

1. Seleccione al menos un grupo de informes.
1. Haga clic en **[!UICONTROL Descargar informe]**.

   ![](/help/admin/admin/c-server-call-usage/assets/download_report.png)

| Elemento de informe | Descripción |
|--- |--- |
| Nombre del archivo | Nombre codificado: Informe de uso `day and time of report creation.csv` |
| Grupos de informes incluidos | Cualquier grupo de informes que seleccione en la página Uso del servidor de informes se incluye en esta lista. |
| Tipos de llamada incluidos | Especifique cualquier combinación de estas: Todas las llamadas (predeterminado), Primarias, Secundarias, Primarias móviles, Secundarias móviles. |
| Intervalo de tiempo | Puede elegir el periodo de uso actual o especificar un intervalo personalizado.  Para un intervalo personalizado, especifique el comienzo del intervalo y el final del intervalo. <br>**Nota:** Recuerde que no puede descargar datos de uso anteriores a enero de 2015 </br>. |

{style="table-layout:auto"}

1. Haga clic en **[!UICONTROL Descargar]**.

A continuación se muestra una captura de pantalla del aspecto del archivo .csv descargado. Incluye una columna para la ID del grupo de informes. El ID del grupo de informes especifica un ID único que solo puede contener caracteres alfanuméricos. Esta ID no se puede cambiar después de crear un grupo de informes.

![](/help/admin/admin/c-server-call-usage/assets/download-usage.png)
