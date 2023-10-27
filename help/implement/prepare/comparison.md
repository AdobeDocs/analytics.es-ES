---
title: Comparación de métodos de implementación
description: Consulte las ventajas de cada método para enviar datos a Adobe Analytics.
exl-id: 19353255-6356-4426-a2ef-5a2672a00eca
feature: Implementation Basics
source-git-commit: d64f6687dd6e6f688d332926e6d90fa699cac968
workflow-type: tm+mt
source-wordcount: '501'
ht-degree: 43%

---

# Comparación de métodos de implementación

Consulte cómo se compara cada método de implementación de Adobe Analytics entre sí. Puede utilizar estas tablas para ayudar a su organización a determinar la forma más ideal de enviar datos al Adobe. Haga clic en cada columna para obtener información más específica.

## Web

| | [AppMeasurement](/help/implement/js/overview.md) | [Extensión de Adobe Analytics](/help/implement/launch/overview.md) | [SDK web](/help/implement/aep-edge/web-sdk/overview.md#web-sdk) | [Extensión del SDK web](/help/implement/aep-edge/web-sdk/overview.md#web-sdk-extension) |
| --- | --- | --- | --- | --- |
| Requisitos de implementación | Haga referencia a `AppMeasurement.js` en cada página, defina las variables y envíe datos mediante `s.t()` a ADOBE ANALYTICS | Haga referencia al cargador de etiquetas en cada página y utilice la IU de recopilación de datos para definir variables y enviar datos a Adobe Analytics | Referencia `Alloy.js` en cada página, utilice `alloy("sendEvent",{})` para componer objetos XDM y enviar los datos deseados mediante la red perimetral a Adobe Analytics | Cargador de etiquetas de referencia en cada página, utilice la IU de recopilación de datos para componer objetos XDM y enviar los datos deseados mediante la red perimetral a Adobe Analytics |
| Destino de los datos | Enviado directamente a Adobe Analytics | Enviado directamente a Adobe Analytics | Enviado a Adobe Experience Platform Edge, que reenvía datos a Adobe Analytics | Enviado a Adobe Experience Platform Edge, que reenvía datos a Adobe Analytics |
| Dificultad para realizar ajustes de implementación | Requiere acceso al código del sitio web para cada cambio de implementación | Cambie el código del sitio web una vez para instalar la etiqueta del cargador; todas las actualizaciones de implementación posteriores se pueden realizar en la IU de recopilación de datos | Requiere acceso al código del sitio web para cada cambio de implementación | Cambie el código del sitio web una vez para instalar la etiqueta del cargador; todas las actualizaciones de implementación posteriores se pueden realizar en la IU de recopilación de datos |
| Cómo se gestiona A4T | Las llamadas a A4T se incluyen en las visitas enviadas a Adobe | Las llamadas a A4T se incluyen en las visitas enviadas a Adobe | Las llamadas a A4T se envían como visitas separadas | Las llamadas a A4T se envían como visitas separadas |
| Datos de contexto | Utilice `s.contextData`. | Uso `s.contextData` en bloques de código personalizado | Todos los campos no asignados se envían automáticamente como `a.x.*` variables de datos de contexto. | Todos los campos no asignados se envían automáticamente como `a.x.*` variables de datos de contexto. |

{style="table-layout:auto"}

## Mobile y otros

>[!CAUTION]
>
>La compatibilidad con los SDK Mobile de la versión 4 finalizó el 31 de agosto de 2021. Consulte [Preguntas frecuentes sobre el fin de vida útil de Adobe Mobile Services](https://experienceleague.adobe.com/docs/discontinued/using/mobile-services.html) para obtener más información.


| | [SDK móvil](/help/implement/aep-edge/mobile-sdk/overview.md) | [API de servidor](/help/implement/aep-edge/server-api/overview.md) |
| --- | --- | --- |
| Requisitos de implementación | Haga referencia al cargador de etiquetas en la aplicación y, a continuación, utilice llamadas API directas o reglas en la IU de recopilación de datos para componer objetos XDM y enviar los datos deseados mediante Edge Network a Adobe Analytics | Utilice las API del servidor de red perimetral para componer objetos XDM y enviar los datos deseados mediante la red perimetral a Adobe Analytics |
| Destino de los datos | Enviado a Adobe Experience Platform Edge, que reenvía datos a Adobe Analytics | Enviado a Adobe Experience Platform Edge, que reenvía datos a Adobe Analytics |
| Dificultad para realizar ajustes de implementación | Cambie el código de la aplicación donde se realizan las llamadas directas de API o realice cambios en la IU de recopilación de datos | Requiere acceso al código de la aplicación para cada cambio de implementación |
| Cómo se gestiona A4T | Las llamadas a A4T se envían como visitas separadas | Las llamadas a A4T se envían como visitas separadas |
| Datos de contexto | Todos los campos no asignados se envían automáticamente como `a.x.*` variables de datos de contexto. | Todos los campos no asignados se envían automáticamente como `a.x.*` variables de datos de contexto |

{style="table-layout:auto"}
