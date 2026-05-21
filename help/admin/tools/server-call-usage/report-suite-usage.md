---
description: La ficha Uso del grupo de informes proporciona datos sobre el uso del servidor para cada grupo de informes en todas las empresas de inicio de sesión asociadas a su empresa de facturación durante el periodo de uso actual.
title: Ver uso del grupo de informes
feature: Server Call Usage
exl-id: bedd4ed8-1c8b-45fd-a059-fed88e9fbe73
role: Admin
TQID: https://experienceleague.adobe.com/reCYMlZM7HH2H1ewI6tN6x6Bn4ghaKKyrkXGUzC64-g
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 9e2c89f4188c723b4623a6e7859b74ede15e155b
workflow-type: tm+mt
source-wordcount: 436
ht-degree: 44%

---

# Ver uso del grupo de informes

La ficha Uso del grupo de informes proporciona datos sobre el uso del servidor para cada grupo de informes en todas las empresas de inicio de sesión asociadas a su empresa de facturación durante el periodo de uso actual.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Uso de llamadas al servidor]** > **[!UICONTROL Uso del grupo de informes]**

>[!IMPORTANT]
>
>Si un grupo de informes no está vinculado a una organización de CX Enterprise, sus datos de uso no se reflejan en este panel. Además, se podría asociar un ID de facturación a varias organizaciones empresariales de CX; no siempre hay una relación 1:1 entre una organización y un ID de facturación.

El tablero Uso del grupo de informes

* Muestra el uso de llamadas al servidor del período de uso actual (todas las llamadas, primarias, secundarias, primarias móviles, secundarias móviles) para cada grupo de informes de su organización empresarial de CX.
* Muestra el porcentaje del uso general por categoría de llamada al servidor.
* Se actualiza a diario.
* Se puede descargar.
* Permite acceder a la interfaz de usuario de **[!UICONTROL Administrar alertas]**.

![](/help/admin/tools/server-call-usage/assets/report-suite-usage.png)

## Configuración del panel {#settings}

| Columna | Definición |
|--- |--- |
| Nombre del grupo de informes | Nombre descriptivo del grupo de informes |
| Todas las llamadas (% del total) | Todas las llamadas al servidor realizadas en el periodo de uso actual. |
| Llamadas primarias (%) | Todas las llamadas primarias al servidor (y su porcentaje del total) realizadas en el periodo de uso actual. |
| Llamadas secundarias (%) | Todas las llamadas secundarias al servidor (y su porcentaje del total) realizadas en el periodo de uso actual. |
| Móvil principal (%) | Todas las llamadas al servidor primarias móviles (y su porcentaje del total) realizadas en el periodo de uso actual. |
| Secundario móvil (%) | Todas las llamadas al servidor secundarias móviles (y su porcentaje del total) realizadas en el periodo de uso actual. |

{style="table-layout:auto"}

## Descargar informe de uso {#download}

Esta opción le permite descargar datos de uso actuales, así como datos de periodos de tiempo anteriores al periodo de uso actual (que se remontan a enero de 2015). El informe se descarga como archivo .csv.

1. Seleccione al menos un grupo de informes.
1. Haga clic en **[!UICONTROL Descargar informe]**.

   ![](/help/admin/tools/server-call-usage/assets/download_report.png)

| Elemento de informe | Descripción |
|--- |--- |
| Nombre del archivo | Nombre codificado: Informe de uso `day and time of report creation.csv` |
| Conjuntos de informes incluidos | Cualquier grupo de informes que haya seleccionado en la página Uso del servidor de informes se incluye en esta lista. |
| Tipos de llamada incluidos | Especifique cualquier combinación de estas: Todas las llamadas (predeterminado), Primarias, Secundarias, Primarias móviles, Secundarias móviles. |
| Intervalo de tiempo | Puede elegir el periodo de uso actual o especificar un intervalo personalizado.  Para un intervalo personalizado, especifique el comienzo del intervalo y el final del intervalo. <br>**Nota:** Recuerde que no puede descargar datos de uso anteriores a enero de 2015 </br>. |

{style="table-layout:auto"}

1. Haga clic en **[!UICONTROL Descargar]**.

A continuación se muestra una captura de pantalla del aspecto del archivo .csv descargado. Incluye una columna para la ID del grupo de informes. El ID del grupo de informes especifica un ID único que solo puede contener caracteres alfanuméricos. Esta ID no se puede cambiar después de crear un grupo de informes.

![](/help/admin/tools/server-call-usage/assets/download-usage.png)
