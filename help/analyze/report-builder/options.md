---
description: En el panel Opciones se puede especificar la configuración de fecha, la configuración de latencia (Datos actuales), el registro de información y configurar actualizaciones.
seo-description: En el panel Opciones se puede especificar la configuración de fecha, la configuración de latencia (Datos actuales), el registro de información y configurar actualizaciones.
seo-title: Opciones del Creador de informes
solution: Analytics
title: Opciones del Creador de informes
topic: Creador de informes
uuid: f 2920 dee -4245-4617-a 02 e -03726 dde 2 bb 5
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Opciones del Creador de informes

En el panel Opciones se puede especificar la configuración de fecha, la configuración de latencia (Datos actuales), el registro de información y configurar actualizaciones.

1. En la barra de herramientas de Complementos, haga clic en **[!UICONTROL Opciones]** ![](assets/options_icon.png):

| Elemento | Descripción |
|--- |--- |
| [!UICONTROL Con fecha] |  |
| Establecer en fecha actual | Permite especificar o restablecer el valor [!UICONTROL Con fecha] para que el Creador de informes utilice la fecha actual o pregunte qué fecha utilizar tras la actualización. |
| Solicitar establecer al actualizar | Permite establecer el valor [!UICONTROL Con fecha] cuando se actualiza una solicitud. |
| [!UICONTROL Actualización de datos] |  |
| [!UICONTROL Incluir datos actuales] | Permite ver la latencia de los datos (también conocida como [!UICONTROL Actualización de datos]) con una precisión de minutos en los informes, a veces incluso antes de que estos datos hayan sido procesados por Adobe Analytics.<br>Cuando no utiliza esta opción, se utiliza el modo finalizado (procesado), que suele ser más [latente](https://marketing.adobe.com/resources/help/en_US/reference/index.html?f=data_latency).<br>Esta configuración se aplica a todas las solicitudes del libro que sean datos actuales compatibles. Si la solicitud no es compatible, se aplica el modo finalizado.<br>Tenga en cuenta las situaciones siguientes para utilizar el modo [!UICONTROL Incluir datos] actuales:<br>**Opciones de formato**: Puede especificar si desea mostrar esta información ([!UICONTROL Creación de datos]) al [dar formato a los encabezados de visualización](../../analyze/report-builder/layout/t-format-display-headers.md).<br>**Desgloses**: no compatibles. Si el modo [!UICONTROL Actualización de datos] está definido en Datos actuales y una de las solicitudes contiene un elemento de desglose, esta solicitud se convierte a modo de datos no actuales. No obstante, el resto de solicitudes seguirán usando el modo Datos actuales.<br>**Administrador de solicitudes**: es posible ver una columna de Datos actuales en el Administrador de solicitudes para así comprobar si la configuración se aplica a una solicitud programada.<br>**Libros programados**: este modo se almacena durante el proceso de programación en el nivel de libro. If you open a scheduled workbook that is using finalized data, and apply [!UICONTROL Include Current Data], current mode is used thereafter.<br>**Permisos**: esta opción está oculta para los usuarios que no tengan acceso a los datos actuales.  Al habilitar esta opción, si una o varias solicitudes no se pueden aplicar, se genera una advertencia. |
| Desactivar advertencias de solicitud incompatible con Datos actuales | Muestra advertencias si el modo [!UICONTROL Incluir datos actuales] está seleccionado pero el modo de datos no se puede aplicar a la solicitud editada.  Por ejemplo, si se establece [!UICONTROL Incluir datos actuales] y después se edita una solicitud que tiene un segmento seleccionado, se genera una advertencia. |
| Registrar solicitudes del Creador de informes en archivo local (para solución de problemas) | Permite registrar solicitudes en un archivo local. Use este archivo de registro para solucionar problemas. |
| Interpretar el valor escrito... | Interpreta el valor escrito en un control de filtro como una ubicación de celda antes de considerarlo una expresión de filtro.<br>Por ejemplo, si crea una solicitud de más 10 páginas, utilizando zapatos de filtro, la solicitud mostrará una celda que contenga algo similar a: Filtro: Página 1-10 principal, Página contiene zapatos |
| Actualizar cuando haya una versión nueva disponible | Indica al sistema que notifique si hay una versión nueva disponibles para su instalación. |
