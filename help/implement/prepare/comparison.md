---
title: Comparación de métodos de implementación
description: Consulte las ventajas de cada método para enviar datos a Adobe Analytics.
exl-id: 19353255-6356-4426-a2ef-5a2672a00eca
feature: Implementation Basics
source-git-commit: d9948fbb63d44c851e08745c77af5618de84a89c
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Comparación de métodos de implementación

Consulte cómo se compara cada método de implementación de Adobe Analytics entre sí. Puede utilizar esta tabla para ayudar a su organización a determinar la forma más ideal de enviar datos a Adobe.

| | AppMeasurement | Extensión de Adobe Analytics | SDK web | Extensión del SDK web |
| --- | --- | --- | --- | --- |
| Requisitos de implementación | Haga referencia a `AppMeasurement.js` en cada página, defina las variables y envíe datos mediante `s.t()` | Haga referencia al cargador de etiquetas en cada página, utilice la interfaz de usuario de recopilación de datos para definir variables y enviar datos a Adobe | Haga referencia a `Alloy.js` en cada página, utilice `alloy("sendEvent",{})` para enviar un objeto JSON que contenga los datos deseados | Haga referencia al cargador de etiquetas en cada página, utilice la interfaz de usuario de recopilación de datos para establecer el objeto JSON para enviar datos |
| Destino de los datos | Enviado directamente a Adobe Analytics | Enviado directamente a Adobe Analytics | Enviado a Adobe Experience Platform Edge, que reenvía datos a Adobe Analytics | Enviado a Adobe Experience Platform Edge, que reenvía datos a Adobe Analytics |
| Dificultad para realizar ajustes de implementación | Requiere acceso al código del sitio web para cada cambio de implementación | Cambie el código del sitio web una vez para instalar la etiqueta del cargador; todas las actualizaciones de implementación posteriores se pueden realizar en la IU de recopilación de datos | Requiere acceso al código del sitio web para cada cambio de implementación | Cambie el código del sitio web una vez para instalar la etiqueta del cargador; todas las actualizaciones de implementación posteriores se pueden realizar en la IU de recopilación de datos |
| Cómo se gestiona A4T | Las llamadas a A4T se incluyen en las visitas enviadas a Adobe | Las llamadas a A4T se incluyen en las visitas enviadas a Adobe | Las llamadas a A4T se envían como visitas separadas | Las llamadas a A4T se envían como visitas separadas |
| Datos de contexto | Utilice `s.contextData`. | Uso `s.contextData` en bloques de código personalizado | Todos los campos no asignados se envían automáticamente como `a.x.*` variables de datos de contexto. | Todos los campos no asignados se envían automáticamente como `a.x.*` variables de datos de contexto. |

{style="table-layout:auto"}
