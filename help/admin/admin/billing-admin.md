---
description: La página Facturación permite acceder a la información de facturación, que contiene los detalles de tráfico correspondientes a cada grupo de informes. Solo los administradores autorizados tienen acceso a esta página.
seo-description: La página Facturación permite acceder a la información de facturación, que contiene los detalles de tráfico correspondientes a cada grupo de informes. Solo los administradores autorizados tienen acceso a esta página.
seo-title: Facturación
solution: Analytics
title: Facturación
topic: Herramientas de administración
uuid: ad 6 ee 1 c 4-d 317-4320-a 36 e-ee 966 c 8 f 145 e
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Facturación

La página Facturación permite acceder a la información de facturación, que contiene los detalles de tráfico correspondientes a cada grupo de informes. Solo los administradores autorizados tienen acceso a esta página.

>[!NOTE]
>
>Si el acceso a la ficha Facturación está deshabilitado para su empresa, comuníquese con el administrador de cuentas.

Los datos de información general del tráfico de la página de facturación permiten establecer una correlación entre los datos de vistas de página de los informes y las llamadas al servidor facturables incluidas en la factura. La página [!UICONTROL Facturación] permite lo siguiente:

* Auditar su factura.
* Desglosar los costes por grupo de informes, para su asignación en la contabilidad interna.
* Ver la distribución de llamadas al servidor primarias y secundarias.

En la página [!UICONTROL Facturación], la información se organiza por meses.

Para ver los datos de información general sobre el tráfico de un mes específico, localice este mes y haga clic en **[!UICONTROL Ver]**.

El informe de [!UICONTROL facturación mensual] resultante incluirá la siguiente información:

| Columna | Descripción |
|--- |--- |
| Grupo de informes | El grupo de informes asociado a la actividad de recopilación de datos. |
| Ubicación | El centro de datos que almacena datos de grupos de informes: San José (California), Dallas (Texas), Noroeste del Pacífico (Estados Unidos), Londres (Reino Unido) o Singapur. En la mayoría de los casos, todos los grupos de informes de la empresa están ubicados en el mismo centro de datos. |
| Llamadas primarias al servidor | Solicitudes recibidas directamente desde los exploradores de los visitantes del sitio web o la API de inserción de datos. Incluye Visitas individuales primarias (Vistas de página), Eventos personalizados primarios, Eventos de descarga primarios y Eventos de salida primarios. |
| Llamadas secundarias al servidor | Copias de las llamadas al servidor primarias creadas mediante etiquetas de conjuntos múltiples, o copiadas o movidas a través de una regla de VISTA.  Si una regla de VISTA ha movido (no copiado) a otro grupo de informes una llamada secundaria al servidor, la página Facturación indica esta transferencia con un número negativo. En ese caso, la suma de las llamadas secundarias se resta de las llamadas primarias al servidor. |
| Total de llamadas al servidor | Total combinado de llamadas primarias y secundarias al servidor de este grupo de informes en la ubicación determinada. |
| Vistas de páginas | Los totales de las vistas de páginas correspondientes a cada grupo de informes. Puede confirmar los valores de las vistas de páginas en Métricas del sitio &gt; Vistas de páginas. |
| Descargas | Descargas totales de cada grupo de informes. Puede confirmar los valores de descarga en Contenido del sitio &gt; Vínculos &gt; Descargas de archivos. |
| Vínculos personalizados | Vínculos personalizados totales por cada grupo de informes. Puede confirmar los valores de vínculos personalizados en Contenido del sitio &gt; Vínculos &gt; Vínculos personalizados. |
| Vínculos de salida | Vínculos de salida totales por cada grupo de informes. Puede confirmar los valores de vínculos de salida en Contenido del sitio &gt; Vínculos &gt; Vínculos de salida. |

>[!NOTE]
>
>To obtain a working copy of the [!UICONTROL Monthly Invoice] report, copy it onto your clipboard, then paste it into a spreadsheet program such as Microsoft Excel*.

## Fecha de informes vs. Fecha de procesamiento {#section_51A48C2F223F4904BE1407C13333C457}

En la interfaz de usuario de informes, los datos presentados siempre están adjuntos a la **Fecha de informes**, que es la marca de tiempo adjunta al evento.

Por otro lado, Uso/Facturación siempre usa la **Fecha de procesamiento**, o bien cuando los datos realmente se procesaron en el sistema. Debido a una latencia básica, las importaciones de datos o las diferencias de zonas horarias de eventos (todo se procesa en la Hora del Pacífico), la Fecha de informes y Fecha de procesamiento generalmente no coinciden por completo.
