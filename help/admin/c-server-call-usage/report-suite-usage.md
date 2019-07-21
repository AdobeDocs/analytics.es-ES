---
description: La ficha Uso del grupo de informes proporciona datos sobre el uso del servidor para cada grupo de informes en todas las empresas de inicio de sesión asociadas a su empresa de facturación durante el periodo de uso actual.
seo-description: La ficha Uso del grupo de informes proporciona datos sobre el uso del servidor para cada grupo de informes en todas las empresas de inicio de sesión asociadas a su empresa de facturación durante el periodo de uso actual.
seo-title: Ver el uso del grupo de informes
title: Ver el uso del grupo de informes
uuid: c 609 ed 99-9 acc -4023-905 a -81 a 40 dd 07 a 79
translation-type: tm+mt
source-git-commit: a6aac17d93877ed2a6525484ba5aa4e741ca116a

---


# Ver el uso del grupo de informes

La ficha Uso del grupo de informes proporciona datos sobre el uso del servidor para cada grupo de informes en todas las empresas de inicio de sesión asociadas a su empresa de facturación durante el periodo de uso actual.

**[!UICONTROL Analytics]** &gt; **[!UICONTROL Administración]** &gt; **[!UICONTROL Uso de llamadas al servidor]** &gt; **[!UICONTROL Uso del grupo de informes]**

>[!IMPORTANT]
>
>If a report suite is not [linked to an Experience Cloud Organization](https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html), its usage data will not be reflected in this dashboard. También se puede asociar un ID de facturación a varias organizaciones de Experience Cloud; no siempre hay una relación 1:1 entre una organización y un ID de facturación.

El tablero de Uso del grupo de informes:

* Muestra el uso de llamadas al servidor del periodo de uso actual (todas las llamadas, primarias, secundarias, primarias móviles, secundarias móviles) para cada grupo de informes de su organización de Experience Cloud.
* Muestra el porcentaje del uso global por categoría de llamadas al servidor.
* Se actualiza a diario.
* Se puede descargar.
* Permite acceder a la interfaz de usuario de **[!UICONTROL Administrar alertas].**

![](assets/report-suite-usage.png)

| Columna | Definición |
|--- |--- |
| Nombre del grupo de informes | Nombre descriptivo del grupo de informes. |
| Todas las llamadas (% del total) | Todas las llamadas al servidor en las que se ha incurrido en el periodo de uso actual. |
| Llamadas primarias (%) | Todas las llamadas al servidor primarias (y su porcentaje del total) en las que se ha incurrido en el periodo de uso actual. |
| Llamadas secundarias (%) | Todas las llamadas al servidor secundarias (y su porcentaje del total) en las que se ha incurrido en el periodo de uso actual. |
| Primarias móviles (%) | Todas las llamadas al servidor primarias móviles (y su porcentaje del total) en las que se ha incurrido en el periodo de uso actual. |
| Secundarias móviles (%) | Todas las llamadas al servidor secundarias móviles (y su porcentaje del total) en las que se ha incurrido en el periodo de uso actual. |


## Descargar informe de uso {#section_D7345660B5E043CD8850954216509A3D}

Esta opción permite descargar los datos de uso actual y datos de periodos anteriores al periodo de uso actual (hasta enero de 2015). El informe se descarga como archivo .csv.

1. Seleccione al menos un grupo de informes.
1. Haga clic en **[!UICONTROL Descargar informe]**.

   ![](assets/download_report.png)

| Elemento de informe | Descripción |
|--- |--- |
| Nombre del archivo | Hardcoded name: Usage Report `day and time of report creation.csv` |
| Grupos de informes incluidos | Cualquier grupo de informes que seleccione en la página Uso del servidor de informes se incluye en esta lista. |
| Tipos de llamada incluidos | Especifique cualquier combinación de estas: Todas las llamadas (predeterminado), Primarias, Secundarias, Primarias móviles, Secundarias móviles. |
| Intervalo de tiempo | Puede elegir el periodo de uso actual o especificar un intervalo personalizado.  Para un intervalo personalizado, especifique el comienzo del intervalo y el final del intervalo. <br>**Nota:** No puede descargar datos de uso anteriores a enero de 2015 </br>. |

1. Haga clic en **[!UICONTROL Descargar]**.

Esta es una captura de pantalla del archivo. csv descargado. Incluye una columna para la ID del grupo de informes. La ID del grupo de informes especifica un ID exclusivo que solo puede contener caracteres alfanuméricos. Este ID no se puede cambiar después de crear un grupo de informes.

![](assets/download-usage.png)