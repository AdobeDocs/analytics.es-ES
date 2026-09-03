---
description: Obtenga información acerca de las opciones de Report Builder.
title: Acerca de las opciones Report Builder
uuid: f2920dee-4245-4617-a02e-03726dde2bb5
feature: Report Builder
role: User, Admin
exl-id: d3388990-7919-461d-a96e-4c996b8bdb8b
TQID: https://experienceleague.adobe.com/56Wyy-f9kDXxFSanTNILr4rNQ0OB3YtbIFPcRT082sc
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 474
ht-degree: 45%

---

# Opciones de Report Builder

{{legacy-arb}}

En el panel Opciones se puede especificar la configuración de fecha, la configuración de latencia (Datos actuales), el registro de información y configurar actualizaciones.

1. En la barra de herramientas Complementos, haga clic en **[!UICONTROL Opciones]** ![](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg):

| Elemento | Descripción |
|--- |--- |
| [!UICONTROL Con fecha] |  |
| Establecer en fecha actual | Permite especificar o restablecer [!UICONTROL Con fecha] para que Report Builder utilice la fecha actual o pregunte qué fecha usar tras la actualización. |
| Solicitar establecer al actualizar | Permite establecer el valor [!UICONTROL Con fecha] cuando se actualiza una solicitud. |
| [!UICONTROL Actualización de datos] |  |
| [!UICONTROL Incluir datos actuales] | Permite ver la latencia de los datos (también conocida como [!UICONTROL Actualización de los datos]) con una precisión de minutos en los informes, a veces incluso antes de que estos datos hayan sido procesados por Adobe Analytics.<br>Si no utiliza esta opción, se utilizará el modo finalizado (procesado), que suele ser más latente.<br>Esta configuración se aplica a todas las solicitudes del libro que sean datos actuales compatibles. Si la solicitud no es compatible, se aplica el modo finalizado.<br>Tenga en cuenta las siguientes situaciones para usar el modo [!UICONTROL Incluir datos actuales]:<br>**Opciones de formato**: Puede especificar si desea mostrar esta información ([!UICONTROL Actualización de los datos]) al [dar formato a los encabezados de visualización](/help/analyze/legacy-report-builder/layout/t-format-display-headers.md).<br>**Desgloses**: No se admite. Si el modo [!UICONTROL Actualización de datos] está definido en Datos actuales y una de las solicitudes contiene un elemento de desglose, esta solicitud se convierte a modo de datos no actuales. Sin embargo, otras solicitudes siguen utilizando el modo Datos actuales.<br>**Administrador de solicitudes**: es posible ver una columna de Datos actuales en el Administrador de solicitudes para así comprobar si la configuración se aplica a una solicitud programada.<br>**Libros programados**: este modo se almacena durante el proceso de programación en el nivel de libro. Si abre un libro programado que usa datos finalizados y aplica [!UICONTROL Incluir datos actuales], a partir de entonces se utilizará el modo actual.<br>**Permisos**: Para los usuarios que no tienen acceso a los datos actuales, esta opción está oculta.  Al habilitar esta opción, si no se pueden aplicar una o más solicitudes, se envía una advertencia. |
| Deshabilitar advertencias de solicitudes incompatibles con datos actuales | Muestra advertencias si el modo [!UICONTROL Incluir datos actuales] está seleccionado pero el modo de datos no se puede aplicar a la solicitud editada.  Por ejemplo, si se establece [!UICONTROL Incluir datos actuales] y después se edita una solicitud que tiene un segmento seleccionado, se genera una advertencia. |
| Registrar solicitudes de Report Builder en archivo local (para solución de problemas) | Permite registrar solicitudes en un archivo local. Utilice este archivo de registro para solucionar problemas. |
| Interpretar valor escrito... | Interpreta un valor escrito en un control de filtro como una ubicación de celda antes de considerarlo una expresión de filtro.<br>Por ejemplo, si crea una solicitud de las 10 páginas más visitadas con un filtro de zapatos, la solicitud mostrará una celda que contenga algo similar a:   Filtro: Página principal 1-10, Página contiene Zapatos |
| Actualizar cuando haya una nueva versión disponible | Indica al sistema que le notifique si hay una nueva versión disponible para la instalación. |
