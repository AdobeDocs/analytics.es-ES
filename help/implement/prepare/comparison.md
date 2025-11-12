---
title: Comparación de métodos de implementación
description: Consulte las ventajas de cada método para enviar datos a Adobe Analytics.
exl-id: 19353255-6356-4426-a2ef-5a2672a00eca
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: ca84a5f807545d7196e2e0e90d3209c32d3fd789
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 38%

---

# Comparación de métodos de implementación

Consulte cómo se compara cada método de implementación de Adobe Analytics entre sí. Puede utilizar estas tablas para ayudar a su organización a determinar la forma más ideal de enviar datos a Adobe. Haga clic en cada columna para obtener información más específica.

## Web

| | [AppMeasurement](/help/implement/js/overview.md) | [Extensión de Adobe Analytics](/help/implement/launch/overview.md) | [SDK web &#x200B;](/help/implement/aep-edge/web-sdk/overview.md#web-sdk) | [Extensión de Web SDK](/help/implement/aep-edge/web-sdk/overview.md#web-sdk-extension) |
| --- | --- | --- | --- | --- |
| Requisitos de implementación | Hacer referencia a `AppMeasurement.js` en cada página, definir variables y enviar datos mediante `s.t()` a Adobe Analytics | Haga referencia al cargador de etiquetas en cada página y utilice la IU de recopilación de datos para definir variables y enviar datos a Adobe Analytics | Haga referencia a `Alloy.js` en cada página, utilice `alloy("sendEvent",{})` para componer objetos XDM y enviar los datos deseados mediante Edge Network a Adobe Analytics | Cargador de etiquetas de referencia en cada página, utilice la IU de recopilación de datos para componer objetos XDM y enviar los datos deseados mediante Edge Network a Adobe Analytics |
| Destino de los datos | Enviado directamente a Adobe Analytics | Enviado directamente a Adobe Analytics | Enviado a Adobe Experience Platform Edge, que reenvía datos a Adobe Analytics | Enviado a Adobe Experience Platform Edge, que reenvía datos a Adobe Analytics |
| Dificultad para realizar ajustes de implementación | Requiere acceso al código del sitio web para cada cambio de implementación | Cambie el código del sitio web una vez para instalar la etiqueta del cargador; todas las actualizaciones de implementación posteriores se pueden realizar en la IU de recopilación de datos | Requiere acceso al código del sitio web para cada cambio de implementación | Cambie el código del sitio web una vez para instalar la etiqueta del cargador; todas las actualizaciones de implementación posteriores se pueden realizar en la IU de recopilación de datos |
| Cómo se gestiona A4T | Las llamadas a A4T se incluyen en las visitas enviadas a Adobe | Las llamadas a A4T se incluyen en las visitas enviadas a Adobe | Las llamadas a A4T se envían como visitas separadas | Las llamadas a A4T se envían como visitas separadas |
| Datos de contexto | Utilice `s.contextData`. | Usar `s.contextData` en bloques de código personalizado | Todos los campos no asignados se envían automáticamente como `a.x.*` variables de datos de contexto. | Todos los campos no asignados se envían automáticamente como `a.x.*` variables de datos de contexto. |

{style="table-layout:auto"}

## Mobile y otros

>[!CAUTION]
>
>La compatibilidad con los SDK Mobile de la versión 4 finalizó el 31 de agosto de 2021. Consulte [Preguntas frecuentes sobre el fin de vida útil de Adobe Mobile Services](https://experienceleague.adobe.com/docs/discontinued/using/mobile-services.html?lang=es) para obtener más información.


| | [SDK móvil](/help/implement/aep-edge/mobile-sdk/overview.md) | [API de Edge Network](/help/implement/aep-edge/api/overview.md) |
| --- | --- | --- |
| Requisitos de implementación | Haga referencia al cargador de etiquetas en la aplicación y, a continuación, utilice llamadas API directas o reglas en la IU de recopilación de datos para componer objetos XDM y enviar los datos deseados mediante Edge Network a Adobe Analytics | Utilice la API de Edge Network para componer objetos XDM y enviar los datos deseados mediante Edge Network a Adobe Analytics |
| Destino de los datos | Enviado a Adobe Experience Platform Edge, que reenvía datos a Adobe Analytics | Enviado a Adobe Experience Platform Edge, que reenvía datos a Adobe Analytics |
| Dificultad para realizar ajustes de implementación | Cambie el código de la aplicación donde se realizan las llamadas directas de API o realice cambios en la IU de recopilación de datos | Requiere acceso al código de la aplicación para cada cambio de implementación |
| Cómo se gestiona A4T | Las llamadas a A4T se envían como visitas separadas | Las llamadas a A4T se envían como visitas separadas |
| Datos de contexto | Todos los campos no asignados se envían automáticamente como `a.x.*` variables de datos de contexto. | Todos los campos no asignados se envían automáticamente como `a.x.*` variables de datos de contexto |

{style="table-layout:auto"}
