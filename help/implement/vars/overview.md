---
title: Información general sobre variables, funciones, métodos y complementos
description: Descubra qué variables puede incluir en los datos que envía a Adobe para mejorar los informes.
keywords: appmeasurement,variables,vars,configuración,página,implementación
feature: Variables
exl-id: 7ffcd943-f9ac-4daf-bbdf-248d75925b04
source-git-commit: 1516a1353c1b0a3b7365c3e3f10ce74ae1255696
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 70%

---

# Información general sobre variables, funciones, métodos y complementos

Analytics proporciona varias variables para recopilar los datos que necesita. Las variables de esta sección se dividen en varias secciones:

* **Las variables de página** son valores que generalmente se utilizan de forma directa en los informes. Las variables de página comunes incluyen `props`, `eVars` y `events`.
* **Las variables de configuración** son valores de configuración que ayudan a garantizar que los datos correctos llegan a Adobe. Las variables de configuración comunes incluyen `trackingServerSecure`, `charSet` y `linkTrackVars`. Las variables de configuración generalmente no rellenan los elementos de dimensión.
* **Las funciones y los métodos** son fragmentos de código que realizan una tarea específica cuando se hace referencia a ellos. Las funciones comunes incluyen `t()`, `tl()` y `clearVars()`.

## Variables y métodos de implementación

Adobe ofrece varias formas de implementar Adobe Analytics. Cada página ofrece una sección sobre cómo implementar la variable mediante el SDK web, la extensión de Adobe Analytics y el AppMeasurement para JavaScript.

Aquí hay un vídeo sobre la configuración de variables en Adobe Analytics:

>[!VIDEO](https://video.tv.adobe.com/v/28755/?quality=12)

## Orden de las operaciones

Las bibliotecas de AppMeasurement publicadas por Adobe Analytics siguen un orden específico al enviar datos a Adobe. Si ejecuta estas tareas de forma desordenada, los datos pueden estar incompletos.

1. Si su sitio utiliza una capa de datos, asegúrese de que todas las variables aplicables se rellenen primero. Por ejemplo, puede rellenar `adobeDataLayer.page.title` con el título de la página. Consulte las [Capas de datos](../prepare/data-layer.md) para obtener más información.
2. Utilice la capa de datos para rellenar variables de Analytics. <br/>Si utiliza etiquetas en Adobe Experience Platform, esta tarea se realiza mediante el uso de elementos de datos intermedios. Los elementos de datos se rellenan con valores de la capa de datos. Por ejemplo, elemento de datos `Page Title` obtiene el valor de la variable de capa de datos `adobeDataLayer.page.title`. <br/>A continuación, puede utilizar el elemento de datos para rellenar variables de Analytics. Por ejemplo `eVar4` obtiene el valor del elemento de datos `Page Title`. <br/>Consulte para obtener más información [Elementos de datos](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/data-elements.html?lang=es), [Asignación de objetos de capa de datos a elementos de datos](../launch/layer-to-elements.md), y [Asignación de elementos de datos de etiquetas a variables de Analytics](../launch/elements-to-variable.md)
3. Finalmente, llame a la función de seguimiento. La mayoría de las bibliotecas de AppMeasurement utilizan el método `t()`, aunque algunos SDK móviles utilizan `track()`. Cuando se llama a la función de seguimiento, todas las variables admitidas definidas en el objeto de Analytics se envían a Adobe en forma de solicitud de imagen.

## Caracteres no permitidos

Las variables de JavaScript nunca permiten los siguientes caracteres y cadenas.

* Tabulación (`0x09`)
* Retorno de carro (`0x0D`)
* Nueva línea (`0x0A`)
* Etiquetas HTML (por ejemplo, `<b></b>` o `&#153`)

Algunas variables tienen limitaciones o requisitos de sintaxis adicionales. Por ejemplo, la variable [`products`](page-vars/products.md) utiliza punto y coma y comas para delimitar productos y categorías independientes.
