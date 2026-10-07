---
title: Selección de componentes en el asistente de actualización de Web SDK
description: Elija las reglas de etiquetas, los elementos de datos y las extensiones que se incluirán en una migración de Web SDK.
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
source-wordcount: '401'
ht-degree: 0%
---
# Selección de componentes

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_componentselection"
>title="Selección de componentes"
>abstract="Elija las reglas, los elementos de datos y las extensiones que desea incluir en esta migración. Los componentes que contribuyen activamente a la implementación de Adobe Analytics se seleccionan de forma predeterminada. Los pasos posteriores solo funcionan con los componentes que seleccione aquí."

La selección de componentes es el primer paso de una migración. Utilícelo para elegir qué reglas, elementos de datos y extensiones de la propiedad de etiquetas incluir en la migración.

El asistente de actualización organiza los componentes de la propiedad de etiquetas en las fichas **[!UICONTROL Reglas]**, **[!UICONTROL Elementos de datos]** y **[!UICONTROL Extensiones]**. Cada ficha enumera todos los componentes de la propiedad de ese tipo, según la instantánea de la biblioteca que tomó el asistente de actualización cuando [creó la migración](manager.md#create). De forma predeterminada, solo se seleccionan los componentes que contribuyen activamente a la implementación de Adobe Analytics. Puede seleccionar o borrar cualquier componente.

La columna **[!UICONTROL Publicado]** muestra si cada componente forma parte de la biblioteca que seleccionó. Los componentes que no forman parte de la biblioteca existen en la propiedad de etiquetas, pero no en esa biblioteca. Para filtrar la lista con este criterio, usa el filtro **[!UICONTROL Source]**.

Puede incluir componentes que no están relacionados con Adobe Analytics, como componentes para Adobe Target, Adobe Audience Manager o extensiones de terceros, pero el asistente de actualización no los convierte a Web SDK.

Los componentes que seleccione determinan qué pasos posteriores funcionan con. Por ejemplo, puede incluir elementos de datos a los que no se hace referencia para que [resultados de auditoría](audit-findings.md) puedan marcarlos para su limpieza.

## Ver detalles del componente {#details}

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_componentselection_tagsusage"
>title="Uso de etiquetas"
>abstract="Reglas, elementos de datos y extensiones que utilizan este componente. El uso de extensiones solo abarca los ajustes de configuración de extensión. El uso dentro de una regla aparece en Uso de reglas."

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_componentselection_analyticsusage"
>title="Uso de Analytics"
>abstract="Las variables Adobe Analytics a las que está asignado este componente, agrupadas por tipo de variable."

<!-- markdownlint-enable MD034 -->

Seleccione el nombre de un componente para abrir un panel que muestre su configuración y dónde se utiliza:

* **[!UICONTROL Uso de etiquetas]**: Las reglas, los elementos de datos y las extensiones que utilizan el componente. **[!UICONTROL Uso de extensiones]** cubre únicamente los ajustes de configuración de extensión. El uso dentro de una regla aparece en **[!UICONTROL Uso de reglas]**.
* **[!UICONTROL Uso de Analytics]**: Las variables de Adobe Analytics a las que está asignado el componente, agrupadas por tipo de variable.

Para ver el componente en la interfaz de usuario de etiquetas, seleccione su nombre en la parte superior del panel.

Cuando haya terminado, seleccione **[!UICONTROL Guardar y continuar]** para ir a [resultados de auditoría](audit-findings.md).