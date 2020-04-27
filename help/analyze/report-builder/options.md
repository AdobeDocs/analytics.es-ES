---
description: En el panel Opciones se puede especificar la configuración de fecha, la configuración de latencia (Datos actuales), el registro de información y configurar actualizaciones.
title: Opciones de Report Builder
topic: Report builder
uuid: f2920dee-4245-4617-a02e-03726dde2bb5
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Opciones de Report Builder

En el panel Opciones se puede especificar la configuración de fecha, la configuración de latencia (Datos actuales), el registro de información y configurar actualizaciones.

1. In the Add-Ins toolbar, click **[!UICONTROL Options]** ![](assets/options_icon.png):

| Elemento | Descripción |
|--- |--- |
| [!UICONTROL As Of Date] |  |
| Establecer en fecha actual | Lets you specify or reset the  [!UICONTROL As Of Date] so that report builder uses the current date or asks you which date to use upon refresh. |
| Solicitar establecer al actualizar | Permite establecer el [!UICONTROL As Of Date] al actualizar una solicitud. |
| [!UICONTROL Data Recency] |  |
| [!UICONTROL Include Current Data] | Lets you view data latency (also known as  [!UICONTROL Data Recency]) down to the minute in reporting, occasionally even before this data has been processed by  Adobe Analytics.<br>Cuando no se utiliza esta opción, se utiliza el modo finalizado (procesado), que suele ser más [latente](https://marketing.adobe.com/resources/help/es_ES/reference/data_latency.html).<br>Esta configuración se aplica a todas las solicitudes del libro que sean datos actuales compatibles. Si la solicitud no es compatible, se aplica el modo finalizado.<br>Tenga en cuenta las siguientes situaciones para utilizar el [!UICONTROL Include Current Data] modo:Opciones<br>**de formato **: Puede especificar si desea mostrar esta información ([!UICONTROL Data Recency]) al[dar formato a los encabezados](/help/analyze/report-builder/layout/t-format-display-headers.md)de visualización.<br>**Desgloses**: no compatibles. If the  [!UICONTROL Data Recency] mode is set to the Current Data, and one of the requests contains a break-down element, this request reverts to non-current data mode. No obstante, el resto de solicitudes seguirán usando el modo Datos actuales.<br>**Administrador de solicitudes **: es posible ver una columna de Datos actuales en el Administrador de solicitudes para así comprobar si la configuración se aplica a una solicitud programada.<br>**Libros programados**: este modo se almacena durante el proceso de programación en el nivel de libro. If you open a scheduled workbook that is using finalized data, and apply [!UICONTROL Include Current Data], current mode is used thereafter.<br>**Permisos **: esta opción está oculta para los usuarios que no tengan acceso a los datos actuales.  Al habilitar esta opción, si una o varias solicitudes no se pueden aplicar, se genera una advertencia. |
| Desactivar advertencias de solicitud incompatible con Datos actuales | Displays warnings if the  [!UICONTROL Include Current Data] mode is selected but the data mode cannot be applied to the edited request.  For example, if you set [!UICONTROL Include Current Data], and then edit a request that has a segment selected, a warning is issued. |
| Registrar solicitudes de Report Builder en archivo local (para solución de problemas) | Permite registrar solicitudes en un archivo local. Use este archivo de registro para solucionar problemas. |
| Interpretar el valor escrito... | Interpreta el valor escrito en un control de filtro como una ubicación de celda antes de considerarlo una expresión de filtro.<br>Por ejemplo, si crea una solicitud de las 10 páginas más visitadas con un filtro de zapatos, la solicitud mostrará una celda que contenga algo similar a:   Filtro: Página principal 1-10, Página contiene Zapatos |
| Actualizar cuando haya una versión nueva disponible | Indica al sistema que notifique si hay una versión nueva disponibles para su instalación. |
