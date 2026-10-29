---
title: Recopilación de datos de Debug Analytics
description: Confirme que Adobe Analytics recibe los datos esperados de AppMeasurement, la extensión de Analytics, Web SDK, Mobile SDK y la API de inserción de datos.
keywords: depuración, validación, analizador de paquetes, packet monitor, /b/ss/, seguimiento de Edge, Assurance, hitdebugger, grupo de informes
feature: Implementation Basics
role: Admin, Developer
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
subfeature_v2:
  - id: e992d880-33bc-4949-a648-aa7d410276cd
    internal-label: Validation
  - id: c24fe15a-643a-47bd-8278-5e027df49785
    internal-label: Implementation basics
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 049b9b7447c7f91d67eb58fc781898b685bd9d91
workflow-type: tm+mt
source-wordcount: '1050'
ht-degree: 2%
---
# Recopilación de datos de Debug Analytics

En este artículo se explica qué comprobar al depurar los datos enviados a Adobe Analytics. Busque el método de implementación en la tabla siguiente y siga su sección. Si está investigando datos de informes inesperados, comience con [Comparar solicitudes con informes](#reports).

Para ver los pasos y las herramientas que se aplican a toda la recopilación de datos de Adobe, como capturar solicitudes de red, habilitar el registro de depuración e investigar solicitudes canceladas, consulte [Depuración y solución de problemas de la recopilación de datos](https://experienceleague.adobe.com/en/docs/experience-platform/collection/debugging/overview).

| Método de implementación | Dónde ver los datos que Analytics recibe | Guía |
| --- | --- | --- |
| AppMeasurement o la extensión de etiquetas de Analytics | Solicitudes del explorador directamente a los servidores de recopilación de datos de Analytics | [AppMeasurement](#appmeasurement) |
| SDK web | Seguimiento de Edge, después de que Edge Network convierta su evento en una visita de Analytics | [SDK web &#x200B;](#web-sdk) |
| SDK móvil | La vista Eventos de Analytics en Assurance. Si usa la extensión Edge Network o Edge Bridge, active la **[!UICONTROL Vista de Analytics Edge]**. | [Vista de eventos de Adobe Analytics en Assurance](https://experienceleague.adobe.com/es/docs/experience-platform/assurance/view/adobe-analytics) |
| API de inserción de datos | Las solicitudes salientes del servidor y sus respuestas | [Solucionar problemas de solicitudes de API de inserción de datos](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/troubleshooting) |

## AppMeasurement y la extensión de Analytics {#appmeasurement}

### Buscar la solicitud {#appmeasurement-find}

[Capturar solicitudes de red](https://experienceleague.adobe.com/en/docs/experience-platform/collection/debugging/inspect-requests#web) y filtrar para `/b/ss/`. Los depuradores de etiquetas como Adobe Experience Platform Debugger identifican y descodifican estas solicitudes por usted.

Si no aparece ninguna solicitud `/b/ss/`:

* Compruebe si hay errores de JavaScript en la consola del explorador.
* Si utiliza la extensión de etiqueta de Analytics, confirme que el código incrustado de etiqueta se encuentra dentro del elemento `<head>` de la página y que la biblioteca se ha publicado en el entorno que está probando. [Modo de depuración de etiquetas](https://experienceleague.adobe.com/en/docs/experience-platform/collection/debugging/logging) muestra si se activó la regla que envía la visita.
* Si aloja AppMeasurement, abra la dirección URL de la biblioteca directamente para confirmar que el archivo se carga y contiene código de.
* Deshabilite las extensiones de explorador, como los bloqueadores de anuncios, que pueden evitar que se envíen solicitudes.
* Debugger no reconoce solicitudes enviadas desde dentro de un iframe. En su lugar, utilice las herramientas para desarrolladores del explorador. Ver [Usar AppMeasurement con iFrames](../use-cases/iframe.md).

### Comprobación de lo que Analytics ha recibido {#appmeasurement-contents}

* **Grupos de informes**: El segmento de ruta después de `/b/ss/` enumera los ID de los grupos de informes que reciben la visita. Confirme que son los grupos de informes que espera, como un grupo de informes de desarrollo en páginas de desarrollo.
* **Variables**: las solicitudes sin procesar utilizan nombres de parámetros de consulta en lugar de nombres de variables; por ejemplo, eVar1 aparece como `v1` y prop1 aparece como `c1`. Ver la [referencia de variable](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference). Cuando una solicitud es demasiado larga, AppMeasurement la envía con HTTP `POST`, de modo que las variables aparecen en el cuerpo de la solicitud en lugar de en la dirección URL.
* **Tipo de visita**: las solicitudes enviadas por [`tl()`](../vars/functions/tl-method.md) incluyen el parámetro `pe` y no incrementan las vistas de página. Las solicitudes enviadas por [`t()`](../vars/functions/t-method.md) no incluyen `pe`.

Si los valores están presentes pero son incorrectos, consulte [Solucionar problemas de implementación de JavaScript](../js/troubleshooting.md) para causas comunes, como comillas, mayúsculas y minúsculas y espacios en blanco.

### Compruebe la respuesta {#appmeasurement-response}

Una respuesta de `2xx` confirma únicamente que el servidor de recopilación de datos recibió la solicitud, pero no que se registró la visita. Con el tipo de respuesta predeterminado, una solicitud puede devolver un resultado correcto incluso cuando se pierde la visita. Se espera una respuesta `302` en la primera solicitud de un nuevo visitante. Ver [códigos de respuesta HTTP](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/troubleshooting#http-response-codes).

AppMeasurement envía solicitudes de vínculo de salida, y todas las solicitudes cuando [`useBeacon`](../vars/config-vars/usebeacon.md) está habilitado, con `navigator.sendBeacon()`. Las herramientas para desarrolladores pueden etiquetar estas solicitudes como canceladas incluso cuando el explorador las envía. Ver [solicitudes anuladas](https://experienceleague.adobe.com/en/docs/experience-platform/collection/debugging/inspect-requests#aborted-requests).

## SDK web {#web-sdk}

### Buscar la solicitud {#web-sdk-find}

Con Web SDK, el explorador envía eventos a Edge Network en lugar de directamente a Analytics, por lo que no ve una solicitud `/b/ss/`. [Inspeccione la solicitud de Edge Network](https://experienceleague.adobe.com/en/docs/experience-platform/collection/debugging/inspect-requests#edge-network-requests) y confirme lo siguiente:

* El parámetro `configId` coincide con un conjunto de datos que tiene habilitado el servicio [Adobe Analytics](https://experienceleague.adobe.com/es/docs/experience-platform/datastreams/configure#analytics) con los grupos de informes que espera.
* La carga útil se califica como una vista de página o un evento de vínculo. Analytics ignora las cargas útiles que no contienen detalles de página ni un tipo de interacción web. Ver [tipos de eventos de Edge Network en Adobe Analytics](../aep-edge/hit-types.md).

### Comprobación de lo que Analytics ha recibido {#web-sdk-contents}

Inicie un [seguimiento de Edge](https://experienceleague.adobe.com/en/docs/experience-platform/debugger/edge-trace) y reproduzca la acción. Busque la fila que comienza con **[!UICONTROL Asignación automática de Analytics]** y, a continuación, expanda `mappedQueryParams` y el ID del grupo de informes debajo de ella.

* **Variables**: los valores asignados utilizan los mismos nombres de parámetros de consulta que las solicitudes de AppMeasurement, a veces en forma abreviada, como `gn` para el nombre de página y `pl` para los productos. Consulte [Asignación de campos de objetos XDM](../aep-edge/xdm-var-mapping.md) y [Asignación de campos de objetos de datos](../aep-edge/data-var-mapping.md).
* **Datos de contexto**: los campos XDM que no se asignan a una variable de Analytics aparecen como datos de contexto con el prefijo `c.a.x.`. Use [reglas de procesamiento](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md) para asignarlas a variables.
* **Grupos de informes**: si usa las invalidaciones de grupos de informes, la fila de configuración de la secuencia de datos en el seguimiento de Edge muestra los grupos de informes que Edge Network usó.

### Comprobar procesamiento {#web-sdk-processing}

En la sesión de Assurance que abre Edge Trace, busque eventos para `hitdebugger`. Estos eventos utilizan el proveedor `com.adobe.analytics.hitdebugger` y sus cargas muestran valores después del procesamiento de Analytics, como el Experience Cloud ID (`mcvisId`) y `pageName`.

Para ver un tutorial guiado, vea [Configurar Adobe Analytics con Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/es/docs/platform-learn/implement-web-sdk/applications-setup/setup-analytics).

## Comparación de solicitudes con informes {#reports}

Las visitas que llegan a Analytics no aparecen inmediatamente en los informes, y los valores de los informes pueden diferir de los valores de la solicitud:

* **Latencia**: los datos completos suelen aparecer en los informes unas dos horas después de su recopilación. Algunos datos, como las visitas con marca de hora, pueden tardar más. Ver [Disponibilidad y latencia de los datos](/help/technotes/latency.md).
* **Procesamiento**: las reglas de procesamiento, las reglas de VISTA, las reglas de bots y otros pasos de procesamiento pueden cambiar o excluir valores después de la recopilación. Consulte [Orden de procesamiento de los datos en Adobe Analytics](/help/technotes/processing-order.md). Los datos posprocesados de Assurance muestran el resultado del procesamiento de una visita individual.
* **Grupo de informes**: confirme que está viendo el mismo grupo de informes al que se dirigió la solicitud o la secuencia de datos.
* **Valores inesperados**: Si una dimensión muestra picos o valores inesperados, consulte [Conflictos de hash](hash-collisions.md).

Para ver cambios de tráfico más amplios, consulte [Solución de problemas de picos y caídas de datos](/help/technotes/event/spikes-drops.md).
