---
description: Las condiciones determinan cuándo se activa una regla basada en eventos.
keywords: Administración dinámica de etiquetas;regla;crear regla;nueva regla;regla basada en eventos;demora en la activación del vínculo;aplicación del controlador de eventos directamente al elemento;propagación;propagación de eventos
seo-description: Las condiciones determinan cuándo se activa una regla basada en eventos.
seo-title: Crear condiciones para reglas basadas en eventos
solution: Experience Cloud,Analytics,Target,Administración dinámica de etiquetas
title: Crear condiciones para reglas basadas en eventos
uuid: a847391c-5aec-4d64-8a35-388587731598
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Crear condiciones para reglas basadas en eventos

Las condiciones determinan cuándo se activa una regla basada en eventos.

1. Seleccione el tipo de interacción que desea rastrear, como clics con el ratón o envíos de formularios.

   ![](assets/condition-event-based.png)

   Para obtener más información, consulte [Tipos de evento](https://marketing.adobe.com/resources/help/en_US/dtm/event_types.html) en Documentación del producto de Tag Management.

1. Habilite las opciones siguientes según sea necesario:

   | Elemento | Descripción |
   |--- |--- |
   | Retraso de activación de vínculo | Habilita si el evento activa un vínculo y si desea que el vínculo se retrase hasta que el evento se active. |
   | Aplicar el controlador de eventos directamente al elemento | Aplica el controlador de eventos a un elemento específico objetivo. Esta configuración está unida al concepto de propagación y capas de un explorador. |

   For example, when you click an image inside an anchor tag like `<a href="abc.html"><img src="xyz.png"/></a>`, you might expect the click to be associated with the anchor tag, because the tag is in the bubble stream. However, when you inspect the click in the developer tools, the click may actually affect only the `<img>` tag. To ensure that the event is handled correctly, associate the click with the `<img>` tag and do not depend on the browser to bubble up the click to a parent element. Un evento como un clic puede propagarse potencialmente a `<body>`. Es importante comprender a dónde está vinculado realmente el evento, y establecerlo específicamente como objetivo para asegurarse de que la regla se activa correctamente.

   *Propagación* significa que el evento primero se captura, se administra por el elemento más interior y, a continuación, se propaga a los elementos externos.

1. Indique el nombre de la etiqueta que quiere rastrear, así como las propiedades adicionales de la etiqueta que desea hacer coincidir.

   ![](assets/condition-event-based2.png)

   Consulte [Uso del selector CSS](https://marketing.adobe.com/resources/help/en_US/dtm/css-selector.html) en Documentación del producto de Dynamic Tag Management para obtener información sobre cómo se busca la etiqueta de elemento correcta.

1. Seleccione y configure cualquier tipo de condición o criterio adicional que desee relacionar con la regla.

   ![](assets/condition-event-based3.png)

1. Indique su preferencia con respecto a la propagación del evento.

   La propagación de eventos es una manera de difusión de eventos en HTML DOM.

   | Si usted... | Marque esta opción |
   |--- |--- |
   | Desea interacciones relacionadas en elementos secundarios del selector de regla que identificó para activar la regla. | Permitir propagación de eventos en elementos secundarios. |
   | Desea evitar la propagación si el elemento secundario ya activa su propio evento. | No permitir si el elemento secundario ya activa un evento. |
   | No desea que los eventos del selector de regla que identificó vayan más allá del propio elemento en la jerarquía de eventos. | No permitir que los eventos se propaguen hacia los principales. |
