---
title: Implementación de Web SDK en el asistente de actualización de Web SDK
description: Revise las acciones de Web SDK que el asistente de actualización añade a las reglas de etiquetas existentes.
feature: Implementation Basics
role: Admin, Developer, Leader
badge: Beta
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
subfeature_v2:
  - id: e4f5f438-eabb-4c54-9133-b817e3d125f5
    internal-label: Use cases
  - id: c24fe15a-643a-47bd-8278-5e027df49785
    internal-label: Implementation basics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 629efca210346d32b8555c60f7db15d1d8285b20
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 0%
---
# Implementación de Web SDK

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_websdkimplementation"
>title="Implementación de Web SDK"
>abstract="Revise las acciones de Web SDK que el asistente de actualización añade a las reglas. Las acciones de Adobe Analytics se mantienen en su lugar. Seleccione un componente para comparar sus configuraciones actuales y de Web SDK en paralelo. A la migración solo se agregan los componentes en cola."

<!-- markdownlint-enable MD034 -->

Con los componentes que seleccionó y la asignación [XDM](xdm-mapping.md), el asistente de actualización agrega acciones de Web SDK a las reglas, directamente después de cada acción de Adobe Analytics. Las acciones de Analytics permanecen, por lo que estas reglas envían datos a Adobe Analytics y a Web SDK. La mayoría de los elementos de datos se transfieren sin cambios y las reglas siguen haciendo referencia a ellos por su nombre.

La columna **[!UICONTROL Tipo de cambio]** muestra lo que hace la migración a cada componente:

* **[!UICONTROL Se agregaron acciones de Web SDK]**: El asistente de actualización agrega acciones de Web SDK a la regla.
* **[!UICONTROL Sin cambios]**: el componente se transfiere sin cambios.
* **[!UICONTROL Bloqueado]**: el componente necesita su revisión para que el asistente de actualización pueda agregarle acciones de Web SDK. Seleccione el componente para ver qué lo bloquea.

Seleccione un componente para comparar su configuración actual con su configuración de Web SDK en paralelo. Si necesita más contexto, el asistente de actualización vincula al componente en la interfaz de usuario de etiquetas.

Los componentes en cola se agregan a la migración. Para poner un componente en cola, selecciónelo en la lista o seleccione **[!UICONTROL Cola]** en sus detalles. Para retirarlo, seleccione **[!UICONTROL Quitar de la cola]**. El asistente de actualización no cambia la propiedad de etiquetas hasta que [finalice la migración](final-review.md#finalize).

El asistente de actualización utiliza IA para generar las acciones de Web SDK, y es posible que los resultados no sean precisos o completos. La generación de las acciones no verifica cómo se comportan en el sitio, por lo que debe probarlas antes de publicar la biblioteca.
