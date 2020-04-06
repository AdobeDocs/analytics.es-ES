---
description: La página Facturación permite acceder a la información de facturación, incluidos los detalles de tráfico de cada grupo de informes. Solo un administrador autorizado tiene acceso a esta página.
title: Facturación
topic: Admin tools
uuid: ad6ee1c4-d317-4320-a36e-ee966c8f145e
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Facturación

La página Facturación permite acceder a la información de facturación, incluidos los detalles de tráfico de cada grupo de informes. Solo un administrador autorizado tiene acceso a esta página.

>[!NOTE] Si una empresa tiene deshabilitado el acceso a la ficha de facturación, deberá ponerse en contacto con el Administrador de cuentas correspondiente.

Los datos de información general sobre el tráfico de la página de facturación le permiten correlacionar los datos de vista de página en los informes con las llamadas al servidor facturables de la factura. La [!UICONTROL Billing] página le permite hacer lo siguiente:

* Audite la factura.
* Desglose los costos por grupo de informes para las asignaciones contables internas.
* Vista de la distribución de llamadas primarias y secundarias al servidor.

La [!UICONTROL Billing] página organiza la información por mes.

To view monthly traffic overview data, locate the month where you want to view traffic data, then click **[!UICONTROL View]**.

El [!UICONTROL Monthly Invoice] informe resultante incluye la siguiente información:

| Columna | Descripción |
|--- |--- |
| Report Suite | El grupo de informes asociado a la actividad de recopilación de datos. |
| Ubicación | El centro de datos que almacena los datos del grupo de informes: San José (California), Dallas (Texas), Noroeste del Pacífico (EE.UU.), Londres (Reino Unido) o Singapur. En la mayoría de los casos, todos los grupos de informes de compañía están ubicados en el mismo centro de datos. |
| Llamadas primarias al servidor | Solicitudes recibidas directamente desde los exploradores de visitante del sitio web o la API de inserción de datos. Incluye visitas individuales primarias (Vistas de página), Eventos personalizados primarios, Eventos de descarga principales y Eventos de salida principales. |
| Llamadas secundarias al servidor | Copias de las llamadas al servidor primarias creadas mediante etiquetas de conjuntos múltiples, o copiadas o movidas a través de una regla de VISTA.  Si una regla de VISTA ha movido (no copiado) a otro grupo de informes una llamada secundaria al servidor, la página Facturación indica esta transferencia con un número negativo. En ese caso, la suma de las llamadas secundarias se resta de las llamadas primarias al servidor. |
| Total de llamadas al servidor | Total combinado de llamadas primarias y secundarias al servidor de este grupo de informes en la ubicación determinada. |
| Vistas de páginas | Los totales de las vistas de páginas correspondientes a cada grupo de informes. Puede confirmar los valores de las vistas de páginas en Métricas del sitio > Vistas de páginas. |
| Descargas | Descargas totales de cada grupo de informes. Puede confirmar los valores de descarga en Contenido del sitio > Vínculos > Descargas de archivos. |
| Vínculos personalizados | Vínculos personalizados totales por cada grupo de informes. Puede confirmar los valores de vínculos personalizados en Contenido del sitio > Vínculos > Vínculos personalizados. |
| Vínculos de salida | Vínculos de salida totales por cada grupo de informes. Puede confirmar los valores de vínculos de salida en Contenido del sitio > Vínculos > Vínculos de salida. |

>[!NOTE] Para obtener una copia de trabajo del [!UICONTROL Monthly Invoice] informe, cópielo en el portapapeles y péguelo en un programa de hoja de cálculo como Microsoft Excel*.

## Fecha de informes vs. Fecha de procesamiento {#section_51A48C2F223F4904BE1407C13333C457}

En la interfaz de usuario de sistema de informes, los datos presentados siempre se adjuntan a la fecha **de** Sistema de informes, que es la marca de tiempo adjunta al evento.

Uso/Facturación, por otro lado, siempre utiliza la fecha **de** procesamiento o cuando los datos se procesaron realmente en el sistema. Debido a la latencia básica, las importaciones de datos o las diferencias de huso horario de evento (todo se procesa en la hora del Pacífico), la fecha de Sistema de informes y la fecha de procesamiento no suelen coincidir completamente.
