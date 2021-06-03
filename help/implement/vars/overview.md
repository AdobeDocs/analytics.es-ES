---
title: Información general sobre variables, funciones, métodos y complementos
description: Descubra qué variables puede incluir en los datos que envía a Adobe para mejorar los informes.
keywords: appmeasurement,variables,vars,configuración,página,implementación
exl-id: 7ffcd943-f9ac-4daf-bbdf-248d75925b04
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 97%

---

# Información general sobre variables, funciones, métodos y complementos

Analytics proporciona varias variables para recopilar los datos que necesita. Las variables de esta sección se dividen en varias secciones:

* **Las variables de página** son valores que generalmente se utilizan de forma directa en los informes. Las variables de página comunes incluyen `props`, `eVars` y `events`.
* **Las variables de configuración** son valores de configuración que ayudan a garantizar que los datos correctos llegan a Adobe. Las variables de configuración comunes incluyen `trackingServerSecure`, `charSet` y `linkTrackVars`. Las variables de configuración generalmente no rellenan los elementos de dimensión.
* **Las funciones y los métodos** son fragmentos de código que realizan una tarea específica cuando se hace referencia a ellos. Las funciones comunes incluyen `t()`, `tl()` y `clearVars()`.

## Variables y métodos de implementación

Adobe ofrece varias formas de implementar Adobe Analytics. Cada página ofrece una sección sobre cómo implementar la variable mediante Launch y AppMeasurement para JavaScript.

## Orden de las operaciones

Las bibliotecas de AppMeasurement publicadas por Adobe Analytics siguen un orden específico al enviar datos a Adobe. Si ejecuta estas tareas de forma desordenada, los datos pueden estar incompletos.

1. Si su sitio utiliza una capa de datos, asegúrese de que todas las variables aplicables se rellenen primero. Consulte las [Capas de datos](../prepare/data-layer.md) para obtener más información.
2. Utilice la capa de datos para rellenar variables de Analytics. Si utiliza Launch, esta tarea se realiza fácilmente mediante el uso de elementos de datos y, a continuación, asignando el elemento de datos a una variable. Consulte [Elementos de datos](https://experienceleague.adobe.com/docs/launch/using/reference/manage-resources/data-elements.html) en la guía de usuario de Launch.
3. Llame a la función de seguimiento. La mayoría de las bibliotecas de AppMeasurement utilizan el método `t()`, aunque algunos SDK móviles utilizan `track()`. Cuando se llama a la función de seguimiento, todas las variables admitidas definidas en el objeto de Analytics se envían a Adobe en forma de solicitud de imagen.

## Caracteres no permitidos

Las variables de JavaScript nunca permiten los siguientes caracteres y cadenas.

* Tabulación (`0x09`)
* Retorno de carro (`0x0D`)
* Nueva línea (`0x0A`)
* Etiquetas HTML (por ejemplo, `<b></b>` o `&#153`)

Algunas variables tienen limitaciones o requisitos de sintaxis adicionales. Por ejemplo, la variable [`products`](page-vars/products.md) utiliza punto y coma y comas para delimitar productos y categorías independientes.
