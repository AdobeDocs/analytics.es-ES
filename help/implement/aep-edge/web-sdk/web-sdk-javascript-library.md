---
title: Enviar datos a Adobe Analytics mediante la biblioteca JavaScript del SDK web
description: Comience con una implementación limpia del SDK web para enviar datos a Adobe Analytics mediante la biblioteca JavaScript.
hide: true
hidefromtoc: true
source-git-commit: d4c9bddf18311e13d025ed9d62c0636a33eb7b85
workflow-type: tm+mt
source-wordcount: '602'
ht-degree: 0%

---

# Enviar datos a Adobe Analytics mediante la biblioteca JavaScript del SDK web

Esta ruta de implementación implica una nueva instalación del SDK web mediante la biblioteca JavaScript del SDK web. Otras rutas de implementación se tratan en páginas independientes:

* [Extensión de etiqueta de SDK web](web-sdk-tag-extension.md): una instalación nueva del SDK web que utiliza la extensión de etiqueta del SDK web. Es similar al método de biblioteca JavaScript del SDK web (esta página), excepto que la implementación se administra mediante etiquetas en la recopilación de datos de Adobe Experience Platform. Requiere el grupo de campos Adobe Analytics ExperienceEvent, que incluye variables típicas de Analytics que se deben incluir en el esquema XDM.
* [Extensión de Analytics a SDK web](analytics-extension-to-web-sdk.md): Adopte un enfoque suave y metódico para pasar de la extensión de etiquetas de Adobe Analytics a la extensión de etiquetas del SDK web. Este método suprime la necesidad de utilizar XDM hasta que su organización esté lista para utilizar los servicios de Adobe Experience Platform, como Customer Journey Analytics. Utilice el `data` en lugar del objeto `xdm` objeto para enviar datos al Adobe.
* [AppMeasurement a la biblioteca JavaScript del SDK web](appmeasurement-to-web-sdk.md): un enfoque suave y metódico para migrar al SDK web, excepto que no utiliza etiquetas. En su lugar, puede quitar manualmente la biblioteca de recopilación de datos de Adobe Analytics (`AppMeasurement.js`) y reemplácelo por la biblioteca JavaScript del SDK web (`alloy.js`).

## Ventajas y desventajas de esta ruta de implementación

El uso de la biblioteca JavaScript del SDK web para enviar datos a Adobe Analytics tiene ventajas y desventajas. Valore cuidadosamente cada opción para decidir qué enfoque es el mejor para su organización.

| Ventajas | Desventajas |
| --- | --- |
| <ul><li>**Enfoque directo**: Esta ruta de implementación es más sencilla que los enfoques que mueven las implementaciones de Adobe Analytics existentes. Si no tiene una implementación de Adobe Analytics actual de la que preocuparse, rellene los campos XDM aplicables del SDK web.</li><li>**Esquema predefinido**: Si su organización no necesita su propio esquema, simplemente puede utilizar el esquema orientado a Adobe Analytics. Este concepto se aplica incluso cuando se mueve hacia Customer Journey Analytics; el concepto de props y eVars no se aplica a Customer Journey Analytics, pero puede seguir utilizando props y eVars como dimensiones personalizadas simples.</li></ul> | <ul><li>**Los cambios de implementación requieren la intervención del desarrollador**: Si desea realizar cambios en la implementación del SDK web, debe trabajar con el equipo de desarrollo para editar el código en el sitio. El enfoque que utiliza la variable [Extensión de etiqueta de SDK web](web-sdk-tag-extension.md) evita esta desventaja.</li><li>**Bloqueado en mediante un esquema específico**: Cuando su organización se traslada a Customer Journey Analytics, debe elegir continuar utilizando el esquema de Adobe Analytics o migrar al esquema de su propia organización (que sería un conjunto de datos independiente). Si su organización desea evitar el esquema de Adobe Analytics y la migración a un conjunto de datos independiente al pasar a Customer Journey Analytics, Adobe recomienda uno de los dos métodos siguientes:</li><ul><li>Utilice el `data` objeto: El `data` permite enviar datos a Adobe Analytics sin ajustarse a un esquema XDM. Una vez creado el esquema de su organización, puede utilizar la asignación de flujos de datos para asignar `data` campos de objeto a XDM. Tanto la [Extensión de Analytics a SDK web](analytics-extension-to-web-sdk.md) y [AppMeasurement a la biblioteca JavaScript del SDK web](appmeasurement-to-web-sdk.md) use esto `data` objeto.</li><li>Omitir Adobe Analytics por completo: si va a implementar el SDK web, puede enviar esos datos a un conjunto de datos en Adobe Experience Platform para su uso en Customer Journey Analytics. Puede utilizar cualquier esquema que desee; Adobe Analytics no participa en absoluto en este flujo de trabajo y, por lo tanto, no requiere el grupo de campos Adobe Analytics ExperienceEvent. Este método incurre en la menor cantidad de deuda técnica, pero también deja a Adobe Analytics fuera del panorama por completo.</li></ul></ul> |
